---
title: "Visão geral do Azure Stack PowerShell | Microsoft Docs"
description: "Visão geral da instalação e configuração do Azure Stack PowerShell."
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
ms.openlocfilehash: 2a03697e0f3e80d63c48f2dc5615f6c99b9ef716
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2017
---
# <a name="azure-stack-powershell"></a>Azure Stack PowerShell 

O Azure Stack requer os dois módulos do PowerShell a seguir:  

1. Módulo do **AzureRM** compatível com o Azure Stack que está disponível com a instalação do Perfil da Versão da API **2017-03-09-profile**. Os cmdlets instalados usando esse perfil podem ser usados pelos administradores de nuvem do Azure Stack e locatários. Para saber mais sobre os cmdlets do PowerShell disponíveis neste perfil, consulte o conteúdo de referência do PowerShell para a [versão 1.2.9 do módulo do AzureRM](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9).  

2. A versão **1.2.9** do módulo do **AzureStack**. Os cmdlets instalados usando esse módulo podem ser usados pelos administradores de nuvem do Azure Stack apenas. O administrador pode executar operações. tais como. gerenciar as ofertas, planos, serviços, cotas etc. usando os cmdlets do PowerShell fornecidos por esse módulo. Para saber mais sobre os cmdlets do PowerShell disponíveis neste módulo, consulte o conteúdo de referência do [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) e [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage).

## <a name="next-steps"></a>Próximas etapas

* [Instalar o PowerShell para o Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [Configurar o PowerShell para usar com o Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)


