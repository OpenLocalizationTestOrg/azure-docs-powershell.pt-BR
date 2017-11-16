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
ms.openlocfilehash: 49980b361c580a1a00f07c2002241e71f2c0b654
ms.sourcegitcommit: df44d5d9874b55455ec745f1846e06a4b3266d13
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2017
---
# <a name="azure-stack-powershell"></a><span data-ttu-id="b4d79-103">Azure Stack PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4d79-103">Azure Stack PowerShell</span></span>

<span data-ttu-id="b4d79-104">O Azure Stack requer os dois módulos do PowerShell a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4d79-104">Azure Stack requires the following two PowerShell modules:</span></span>  

1. <span data-ttu-id="b4d79-105">Módulo do **AzureRM** compatível com o Azure Stack que está disponível com a instalação do Perfil da Versão da API **2017-03-09-profile**.</span><span class="sxs-lookup"><span data-stu-id="b4d79-105">The Azure Stack compatible **AzureRM** module which is available by installing the **2017-03-09-profile** API Version Profile.</span></span> <span data-ttu-id="b4d79-106">Os cmdlets instalados usando esse perfil podem ser usados pelos operadores e usuários do Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="b4d79-106">The cmdlets installed by using this profile can be used by Azure Stack operators and users.</span></span>

2. <span data-ttu-id="b4d79-107">A versão mais atual é a instalação **1.2.11** do módulo do **AzureStack**.</span><span class="sxs-lookup"><span data-stu-id="b4d79-107">The most current version is the **1.2.11** install of the **AzureStack** module.</span></span> <span data-ttu-id="b4d79-108">Os cmdlets instalados usando esse módulo podem ser usados apenas pelos operadores do Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="b4d79-108">The cmdlets installed by using this module can be used by Azure Stack operators only.</span></span> <span data-ttu-id="b4d79-109">Os operadores podem executar operações como gerenciar ofertas, planos, serviços, cotas etc., usando os cmdlets do PowerShell fornecidos por esse módulo.</span><span class="sxs-lookup"><span data-stu-id="b4d79-109">Operators can perform operations such as manage offers, plans, services, quotas, etc. by using the PowerShell cmdlets provided by this module.</span></span> <span data-ttu-id="b4d79-110">Para saber mais sobre os cmdlets do PowerShell disponíveis neste módulo, consulte o conteúdo de referência do [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) e [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage).</span><span class="sxs-lookup"><span data-stu-id="b4d79-110">To learn about the PowerShell cmdlets available in this module, see the [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.11#azurerm.azurestackadmin) and [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.11#azurerm.azurestackstorage) Reference content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b4d79-111">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b4d79-111">Next Steps</span></span>

* [<span data-ttu-id="b4d79-112">Instalar o PowerShell para o Azure Stack</span><span class="sxs-lookup"><span data-stu-id="b4d79-112">Install PowerShell for Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [<span data-ttu-id="b4d79-113">Configurar o PowerShell para usar com o Azure Stack</span><span class="sxs-lookup"><span data-stu-id="b4d79-113">Configure PowerShell for use with Azure Stack</span></span>](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)