---
title: "Visão geral do Azure PowerShell | Microsoft Docs"
description: "Visão geral do Azure PowerShell com links para instalação e configuração."
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.manager: carmonm
ms.date: 08/31/2017
ms.openlocfilehash: ed681a6e920f698caab978ad57fcee9a76420afd
ms.sourcegitcommit: e6b7e20bbd04eda51416c56b13f867102b602d1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2017
---
# <a name="overview-of-azure-powershell"></a><span data-ttu-id="cc102-103">Visão geral do Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc102-103">Overview of Azure PowerShell</span></span>

<span data-ttu-id="cc102-104">O Azure PowerShell fornece um conjunto de cmdlets que usa o modelo do [Azure Resource Manager](/azure/azure-resource-manager/resource-group-overview) para gerenciar os recursos do Azure.</span><span class="sxs-lookup"><span data-stu-id="cc102-104">Azure PowerShell provides a set of cmdlets that use the [Azure Resource Manager](/azure/azure-resource-manager/resource-group-overview) model for managing your Azure resources.</span></span> <span data-ttu-id="cc102-105">Você pode usá-lo em seu navegador com o [Azure Cloud Shell](/azure/cloud-shell/overview), ou você pode instalá-lo em seu computador local e usá-lo em qualquer sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc102-105">You can use it in your browser with [Azure Cloud Shell](/azure/cloud-shell/overview), or you can install it on your local machine and use it in any PowerShell session.</span></span>

<span data-ttu-id="cc102-106">Use o [Cloud Shell](/azure/cloud-shell/overview) para executar o Azure PowerShell no seu navegador, ou [instale-o](install-azurerm-ps.md) no seu próprio computador.</span><span class="sxs-lookup"><span data-stu-id="cc102-106">Use the [Cloud Shell](/azure/cloud-shell/overview) to run the Azure PowerShell in your browser, or [install](install-azurerm-ps.md) it on own computer.</span></span> <span data-ttu-id="cc102-107">Em seguida, leia o artigo de [Introdução](get-started-azureps.md) para começar a usá-lo.</span><span class="sxs-lookup"><span data-stu-id="cc102-107">Then read the [Get Started](get-started-azureps.md) article to begin using it.</span></span> <span data-ttu-id="cc102-108">Para saber mais sobre a versão mais recente, veja as [notas de versão](release-notes-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="cc102-108">For information about the latest release, see the [release notes](release-notes-azureps.md).</span></span>

<span data-ttu-id="cc102-109">Os exemplos a seguir podem ajudar você a saber mais sobre como executar cenários comuns com o Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cc102-109">The following samples can help you learn how to perform common scenarios with Azure PowerShell:</span></span>

* [<span data-ttu-id="cc102-110">Máquinas Virtuais do Linux</span><span class="sxs-lookup"><span data-stu-id="cc102-110">Linux Virtual Machines</span></span>](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=/powershell/azure/toc.json)
* [<span data-ttu-id="cc102-111">Máquinas Virtuais do Windows</span><span class="sxs-lookup"><span data-stu-id="cc102-111">Windows Virtual Machines</span></span>](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=/powershell/azure/toc.json)
* [<span data-ttu-id="cc102-112">Aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="cc102-112">Web Apps</span></span>](/azure/app-service-web/app-service-powershell-samples?toc=/powershell/azure/toc.json)
* [<span data-ttu-id="cc102-113">Bancos de dados SQL</span><span class="sxs-lookup"><span data-stu-id="cc102-113">SQL Databases</span></span>](/azure/sql-database/sql-database-powershell-samples?toc=/powershell/azure/toc.json)

> [!NOTE]<span data-ttu-id="cc102-114"> > Se você tiver implantações que usam o modelo de implantação clássico que não pode ser convertido, será possível instalar a versão de Gerenciamento de Serviços do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc102-114"> > If you have deployments that use the classic deployment model that cannot be converted, you can install the Service Management version of Azure PowerShell.</span></span> <span data-ttu-id="cc102-115">Para obter mais informações, veja [Instalar o módulo Gerenciamento de Serviços do Azure PowerShell](/powershell/azure/servicemanagement/install-azure-ps).</span><span class="sxs-lookup"><span data-stu-id="cc102-115">For more information, see [Install the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/install-azure-ps).</span></span>


### <a name="need-help-with-powershell"></a><span data-ttu-id="cc102-116">Precisa de ajuda com o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cc102-116">Need help with PowerShell?</span></span>

<span data-ttu-id="cc102-117">Se você não estiver familiarizado com o PowerShell, uma introdução ao PowerShell poderá ser útil.</span><span class="sxs-lookup"><span data-stu-id="cc102-117">If you are unfamiliar with PowerShell, you may find an introduction to PowerShell helpful.</span></span>

* [<span data-ttu-id="cc102-118">Instalando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc102-118">Installing PowerShell</span></span>](/powershell/scripting/installing-windows-powershell)
* <span data-ttu-id="cc102-119">[Scripting with PowerShell](/powershell/scripting/scripting-with-windows-powershell) (Script com o PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cc102-119">[Scripting with PowerShell](/powershell/scripting/scripting-with-windows-powershell)</span></span>

<span data-ttu-id="cc102-120">Você também pode assistir a este vídeo: [Noções básicas do PowerShell: (Parte 1) Introdução ao PowerShell](https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1).</span><span class="sxs-lookup"><span data-stu-id="cc102-120">You can also watch this video: [PowerShell Basics: (Part 1) Getting Started with PowerShell](https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1).</span></span>

## <a name="other-azure-powershell-modules"></a><span data-ttu-id="cc102-121">Outros módulos do Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc102-121">Other Azure PowerShell modules</span></span>

* [<span data-ttu-id="cc102-122">Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="cc102-122">Azure Active Directory</span></span>](/powershell/azure/active-directory/)
* [<span data-ttu-id="cc102-123">Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="cc102-123">Azure Information Protection</span></span>](/powershell/azure/aip/)
* [<span data-ttu-id="cc102-124">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="cc102-124">Azure Service Fabric</span></span>](/powershell/azure/service-fabric/)
* [<span data-ttu-id="cc102-125">ElasticDB do Azure</span><span class="sxs-lookup"><span data-stu-id="cc102-125">Azure ElasticDB</span></span>](/powershell/azure/elasticdbjobs/)
