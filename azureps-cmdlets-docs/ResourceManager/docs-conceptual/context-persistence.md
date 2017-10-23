---
title: "Persistência de logons de usuário nas sessões do PowerShell"
description: "Este artigo explica os novos recursos no Azure PowerShell que permitem a reutilização de credenciais e outras informações do usuário em várias sessões do PowerShell."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/31/2017
ms.openlocfilehash: 8ef20796b64b16c78a653e293a57d5e752d89710
ms.sourcegitcommit: e6b7e20bbd04eda51416c56b13f867102b602d1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2017
---
# <a name="persisting-user-logins-across-powershell-sessions"></a>Persistência de logons de usuário nas sessões do PowerShell

Na versão de setembro de 2017 do Azure PowerShell, os cmdlets do Azure Resource Manager apresentam um novo recurso, **Salvamento Automático de Contexto do Azure**. Esse recurso permite vários novos cenários de usuário, incluindo:

- Retenção de informações de logon para reutilização em novas sessões do PowerShell.
- Facilitar o uso de tarefas em segundo plano para executar os cmdlets de execução longa.
- Alternar entre contas, assinaturas e ambientes sem um logon separado.
- Execução de tarefas usando credenciais e assinaturas diferentes, simultaneamente, a partir da mesma sessão do PowerShell.

## <a name="azure-contexts-defined"></a>Contextos do Azure definidos

Um *contexto do Azure* é um conjunto de informações que define o destino de cmdlets do Azure PowerShell. O contexto consiste em cinco partes:

- Uma *Conta* - a entidade de serviço ou o nome de usuário usado para autenticar a comunicação com o Azure
- Uma *Assinatura* - a assinatura do Azure que contém os recursos que estão sendo tratados.
- Um *Locatário* - o locatário do Azure Active Directory que contém sua assinatura. Os Locatários são mais importantes para a autenticação ServicePrincipal.
- Um *Ambiente* - a nuvem de destino específica do Azure, normalmente a nuvem global do Azure.
  No entanto, a configuração do ambiente também permite usar nuvens nacionais, governamentais e locais (Azure Stack) como destino.
- *Credenciais* - as informações usadas pelo Azure para verificar sua identidade e certificar-se de sua autorização para acessar recursos no Azure

Em versões anteriores, o Contexto do Azure precisava ser criado sempre que você abria uma nova sessão do PowerShell. A partir do Azure PowerShell v4.4.0, passou a ser possível habilitar o salvamento automático e a reutilização de Contextos do Azure sempre que você abrir uma nova sessão do PowerShell.

## <a name="automatically-saving-the-context-for-the-next-login"></a>Salvar automaticamente o contexto para o próximo logon

Por padrão, o Azure PowerShell descarta suas informações de contexto sempre que você fechar a sessão do PowerShell.

Para permitir que o Azure PowerShell se lembre do seu contexto depois que a sessão do PowerShell for fechada, use `Enable-AzureRmContextAutosave`. As informações de contexto e as credenciais são salvas automaticamente em uma pasta oculta especial no diretório de usuário (`%AppData%\Roaming\Windows Azure PowerShell`).
Posteriormente, cada nova sessão do PowerShell terá como alvo o contexto usado na última sessão.

Para configurar o PowerShell para esquecer o contexto e as credenciais, use `Disable-AzureRmContextAutoSave`. Você precisará fazer logon no Azure sempre que abrir uma sessão do PowerShell.

Os cmdlets que permitem gerenciar contextos do Azure também permitem um controle refinado. Se quiser que as alterações sejam aplicadas somente à sessão atual do PowerShell (escopo `Process`) ou em cada sessão do PowerShell (escopo `CurrentUser`). Essas opções são discutidas em detalhes em [Usar Escopos de Contexto](#Using-Context-Scopes).

## <a name="running-azure-powershell-cmdlets-as-background-jobs"></a>Executar os cmdlets do Azure PowerShell como trabalhos em segundo plano

O recurso de **Salvamento Automático de Contexto do Azure** também permite compartilhar seu contexto com trabalhos em segundo plano do PowerShell. O PowerShell permite iniciar e monitorar tarefas de execução longa como trabalhos em segundo plano sem a necessidade de aguardar a conclusão das tarefas. Você pode compartilhar as credenciais com trabalhos em segundo plano de duas maneiras diferentes:

- Transmitir o contexto como um argumento

  A maioria dos cmdlets do AzureRM permite passar o contexto como um parâmetro para o cmdlet. Você pode passar um contexto para um trabalho em segundo plano, conforme mostrado no exemplo a seguir:

  ```powershell
  PS C:\> $job = Start-Job { param ($ctx) New-AzureRmVm -AzureRmContext $ctx [... Additional parameters ...]} -ArgumentList (Get-AzureRmContext)
  ```

- Usando o contexto padrão com Salvamento Automático habilitado

  Se você tiver habilitado o **Salvamento Automático de Contexto**, os trabalhos em segundo plano automaticamente usarão o contexto padrão salvo.

  ```powershell
  PS C:\> $job = Start-Job { New-AzureRmVm [... Additional parameters ...]}
  ```

Quando precisar saber o resultado da tarefa em segundo plano, use `Get-Job` para verificar o status do trabalho e `Wait-Job` para aguardar a conclusão do trabalho. Use `Receive-Job` para capturar ou exibir a saída do trabalho em segundo plano. Para obter mais informações, consulte [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="creating-selecting-renaming-and-removing-contexts"></a>Criando, selecionando, renomeando e removendo contextos

Para criar um contexto, você deve estar conectado ao Azure. O cmdlet `Add-AzureRmAccount` (ou seu alias, `Login-AzureRmAccount`) define o contexto padrão usado pelos cmdlets do Azure PowerShell posteriores e permite que você acesse qualquer assinatura ou locatário permitido por suas credenciais de logon.

Para adicionar um novo contexto após o logon, use `Set-AzureRmContext` (ou seu alias, `Select-AzureRmSubscription`).

```powershell
PS C:\> Set-AzureRMContext -Subscription "Contoso Subscription 1" -Name "Contoso1"
```

O exemplo anterior adiciona um novo contexto com 'Assinatura Contoso 1' como destino usando suas credenciais atuais. O novo contexto é denominado 'Contoso1'. Se você não fornecer um nome para o contexto, um nome padrão, usando a ID da conta e a ID da assinatura será usado.

Para renomear um contexto já existente, use o cmdlet `Rename-AzureRmContext`. Por exemplo:

```powershell
PS C:\> Rename-AzureRmContext '[user1@contoso.org; 123456-7890-1234-564321]` 'Contoso2'
```

Este exemplo renomeia o contexto com o nome automático `[user1@contoso.org; 123456-7890-1234-564321]` por um nome simples nome 'Contoso2'. Os cmdlets que gerenciam contextos também usam o preenchimento de guia e isso permite escolher rapidamente o contexto.

E, por último, para remover um contexto, use o cmdlet `Remove-AzureRmContext`.  Por exemplo:

```powershell
PS C:\> Remove-AzureRmContext Contoso2
```

Você se esquece do contexto que foi nomeado 'Contoso2'. É possível recriar este contexto posteriormente usando `Set-AzureRmContext`

## <a name="removing-credentials"></a>Removendo credenciais

Você pode remover todas as credenciais e contextos associados de um usuário ou entidade de serviço usando `Remove-AzureRmAccount` (também conhecido como `Logout-AzureRmAccount`). Quando executado sem parâmetros, o cmdlet `Remove-AzureRmAccount` remove todas as credenciais e contextos associados ao usuário ou entidade de serviço no contexto atual. Você pode passar um Nome de Usuário, o Nome da Entidade de Serviço ou o Contexto para uma determinada entidade de destino.

```powershell
Remove-AzureRmAccount user1@contoso.org
```

## <a name="using-context-scopes"></a>Usando escopos de contexto

Ocasionalmente, convém selecionar, alterar ou remover um contexto em uma sessão do PowerShell sem afetar outras sessões. Para alterar o comportamento padrão dos cmdlets de contexto, use o parâmetro `Scope`. O escopo `Process` substitui o comportamento padrão aplicando-o apenas à sessão atual. Por outro lado, o escopo `CurrentUser` altera o contexto em todas as sessões, em vez de apenas a sessão atual.

Por exemplo, para alterar o contexto padrão na sessão atual do PowerShell sem afetar outras janelas ou o contexto usado na próxima vez em que uma sessão for aberta, use:

```powershell
PS C:\> Select-AzureRmContext Contoso1 -Scope Process
```

## <a name="how-the-context-autosave-setting-is-remembered"></a>Como a configuração de salvamento automático de contexto é lembrada

A configuração de Salvamento Automático de contexto é salva no diretório do usuário do Azure PowerShell (`%AppData%\Roaming\Windows Azure PowerShell`). Alguns tipos de contas de computador podem não ter acesso a esse diretório. Para esses cenários, você pode usar a variável de ambiente

```powershell
$env:AzureRmContextAutoSave="true" | "false"
```

Se definido como 'true', o contexto é salvo automaticamente. Se definido como 'false', o contexto não é salvo.

## <a name="changes-to-the-azurermprofile-module"></a>Alterações no módulo AzureRM.Profile

Novos cmdlets para gerenciar contextos

- [Enable-AzureRmContextAutosave][enable] - Permite salvar o contexto entre sessões do Powershell.
  Qualquer alteração feita afetará o contexto global.
- [Disable-AzureRmContextAutosave][disable] - Desativa o salvamento automático do contexto. É necessário fazer logon novamente em cada nova sessão do PowerShell.
- [Select-AzureRmContext][select] - Seleciona um contexto como o padrão. Todos os cmdlets posteriores usam as credenciais neste contexto para autenticação.
- [Remove-AzureRmAccount][remove-cred] - Remove todas as credenciais e contextos associados a uma conta.
- [Remove-AzureRmContext][remove-context] - Remove um contexto nomeado.
- [Rename-AzureRmContext][rename] - Renomeia um contexto existente.

Alterações em cmdlets de perfil existentes

- [Add-AzureRmAccount][login] - Permite realizar o escopo de logon do processo ou do usuário atual.
  Permite nomear o contexto padrão após o logon.
- [Import-AzureRmContext][import] - Permite realizar o escopo de logon do processo ou do usuário atual.
- [Set-AzureRmContext][set-context] - Permite a seleção de contextos nomeados existentes e alterações no escopo do processo ou do usuário atual.

<!-- Hyperlinks -->
[enable]: /powershell/module/azurerm.profile/Enable-AzureRmContextAutosave
[disable]: /powershell/module/azurerm.profile/Disable-AzureRmContextAutosave
[select]: /powershell/module/azurerm.profile/Select-AzureRmContext
[remove-cred]: /powershell/module/azurerm.profile/Remove-AzureRmAccount
[remove-context]: /powershell/module/azurerm.profile/Remove-AzureRmContext
[rename]: /powershell/module/azurerm.profile/Rename-AzureRmContext

<!-- Updated cmdlets -->
[login]: /powershell/module/azurerm.profile/Add-AzureRmAccount
[import]: /powershell/module/azurerm.profile/Import-AzureRmAccount
[set-context]: /powershell/module/azurerm.profile/Import-AzureRmContext