---
title: Instalar e configurar o Azure PowerShell em macOS e Linux | Microsoft Docs
description: Como instalar e configurar o Azure PowerShell para o primeiro uso em macOS e Linux.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.openlocfilehash: 94b39c18acaca7a4b17b5207feed025442665acc
ms.sourcegitcommit: 358d260a867c6ee2e8700b91f776ba4f1b0e24a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2017
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a>Instalar e configurar o Azure PowerShell em macOS e Linux

Agora é possível instalar o PowerShell 6 (beta) e o Azure PowerShell em plataformas não Windows.
O processo de instalação do Azure PowerShell em macOS e Linux não é diferente do Windows, no entanto, você deve primeiro instalar PowerShell 6 (beta).

> [!NOTE]

> Atualmente, o PowerShell 6 (beta) e o Azure PowerShell para .NET Core ainda estão na versão beta.
> O suporte para esses produtos é limitado. Se você tiver problemas ou detectar erros, envie os problemas no GitHub.
>
> * [Problemas do PowerShell 6 (beta)](https://github.com/PowerShell/PowerShell/issues)
> * [Problemas do Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a>Etapa 1: instalar o PowerShell 6 (beta)

O processo de instalação do PowerShell 6 (beta) varia dependendo do sistema operacional de destino.
Embora seja possível instalar o PowerShell 6 (beta) no Windows, este artigo concentra-se em macOS e Linux. Se você quiser usar o Azure PowerShell no Windows, consulte o artigo de [instalação](./install-azurerm-ps.md) para Windows.

Para instalar o **PowerShell 6** (beta) no Linux ou macOS, você precisa:

1. Obter o PowerShell para o sistema operacional e a versão específicos por meio do [GitHub](https://github.com/powershell/powershell#get-powershell)
2. Seguir as instruções de instalação
   - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a>Etapa 2: instalar o Azure PowerShell para .NET Core

O PowerShell 6 (beta) é fornecido com o módulo PowerShellGet já instalado. Isso torna fácil instalar qualquer módulo que está publicado na Galeria do PowerShell. Para instalar o Azure PowerShell, abra uma nova sessão do PowerShell e execute o seguinte comando:

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a>Etapa 3: carregar o módulo AzureRM.Netcore

Depois de instalar o módulo, você precisa carregá-lo em sua sessão do PowerShell. Os módulos são carregados usando o cmdlet `Import-Module` da seguinte maneira:

```powershell
Import-Module AzureRM.Netcore
```

Depois que a importação for concluída, você poderá testar seu módulo recém-instalado tentando entrar no Azure usando o seguinte comando:

```powershell
Login-AzureRMAccount
```

O comando acima solicitará que você acesse `https://aka.ms/devicelogin` e insira o código fornecido.

## <a name="available-cmdlets"></a>Cmdlets disponíveis

Os módulos do Azure PowerShell para .NET padrão ainda estão em desenvolvimento. Esses módulos não fornecem o conjunto completo de cmdlets que estão disponíveis para a versão do Windows dos módulos. As funções a seguir são implementadas em módulos AzureRM.Netcore:

* Gerenciamento de Contas
  - Fazer logon com a conta da Microsoft, conta organizacional ou entidade de serviço por meio do Microsoft Azure Active Directory
  - Salvar credenciais para o disco com Save-AzureRmContext e carregar as credenciais salvas usando Import-AzureRmContext
* Ambiente
  - Obter os diferentes ambientes do Microsoft Azure prontos para uso
  - Adicionar/definir/remover ambientes personalizados (como seus ambientes do Azure Stack ou do Pacote do Microsoft Azure)
* Cmdlets de plano de gerenciamento para os Serviços do Azure usando as interfaces do Resource Manager e do Gerenciamento de Serviços.
  - Máquina Virtual
  - Serviço de Aplicativo (Sites)
  - Banco de dados SQL
  - Armazenamento
  - Rede

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre como usar o Azure PowerShell, confira o artigo [Introdução ao Azure PowerShell](get-started-azureps.md).
