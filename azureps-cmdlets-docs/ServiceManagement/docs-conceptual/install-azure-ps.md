---
title: "Instalar e configurar o módulo Gerenciamento de Serviços do Azure PowerShell | Microsoft Docs"
description: Como instalar e configurar o Azure PowerShell para o primeiro uso.
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/06/2017
ms.openlocfilehash: c51c727c1cb022eca59f819c7f24d8e058c677da
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2017
---
# <a name="installing-the-azure-powershell-service-management-module"></a>Instalação do módulo de Gerenciamento de Serviços do Azure PowerShell

Instalar o Azure PowerShell a partir da [Galeria do PowerShell](https://www.powershellgallery.com/) é o método preferido de instalação.

## <a name="step-1-install-powershellget"></a>Etapa 1: Instalar o PowerShellGet

Instalar os itens da Galeria do PowerShell requer o módulo PowerShellGet. Verifique se que você tem a versão apropriada do PowerShellGet e outros requisitos do sistema. Execute o seguinte comando para ver se você tem o PowerShellGet instalado em seu sistema.

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

Você deverá ver algo semelhante à seguinte saída:

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Se você não tiver o PowerShellGet instalado, consulte [Como obter o PowerShellGet](install-azurerm-ps.md#how-to-get-powershellget).

## <a name="step-2-install-azure-powershell"></a>Etapa 2: instalar o Azure PowerShell

Execute o seguinte comando no console do Windows PowerShell como Administrador:

```powershell
Install-Module Azure
```

O Azure é um módulo do pacote cumulativo de atualizações para os cmdlets do Azure Resource Manager. Ao instalar o módulo AzureRM, qualquer outro módulo do Azure que não tiver sido instalado anteriormente será baixado e instalado usando a Galeria do PowerShell.

O módulo Gerenciamento de Serviços do Azure compartilha dependências com os módulos Azure PowerShell Resource Manager. Se você instalou os módulos do Azure PowerShell Resource Manager, será necessário adicionar o parâmetro `-AllowClobber` ao comando de instalação. Isso permite a atualização dessas dependências compartilhadas existentes. Sem esse parâmetro, a instalação do módulo falha.

```powershell
Install-Module Azure -AllowClobber
```

Depois de instalar esse módulo, você pode importar o módulo executando o seguinte comando:

```powershell
Import-Module Azure
```

## <a name="to-use-the-cmdlets"></a>Para usar os cmdlets

Para começar a trabalhar com os cmdlets de Gerenciamento de Serviços do Azure, primeiro faça logon em sua conta do Azure. Para fazer logon em sua conta, execute o comando a seguir:

```powershell
Add-AzureAccount
```

Após fazer logon no Azure, o Azure PowerShell cria um contexto para a sessão específica. Esse contexto contém o ambiente, a conta, o locatário e a assinatura do Azure PowerShell que será usada para todos os cmdlets dentro dessa sessão. Agora você está pronto para usar os módulos abaixo.

## <a name="azure-service-management-cmdlets"></a>Cmdlets do Azure Service Management

Módulos do Azure PowerShell são atualizados com frequência. Se você perceber que a ajuda online do cmdlet inclui cmdlets ou parâmetros que não estão em seu módulo, baixe e instale a versão mais recente do módulo. Para localizar a versão de seu módulo, digite: `(Get-Module Azure).Version`.

Para obter exemplos de scripts que podem ajudar você a automatizar algumas tarefas comuns no Azure, consulte o [Centro de Script do Windows Azure](http://www.windowsazure.com/documentation/scripts/).

Para obter informações gerais sobre como instalar, aprender, usar e personalizar o Windows PowerShell, consulte [Criar scripts com o Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).
