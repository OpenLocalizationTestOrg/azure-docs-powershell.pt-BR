---
title: "Log de Alterações do Azure PowerShell | Microsoft Docs"
description: "É um histórico das alterações feitas na versão mais recente do Azure PowerShell."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 5fe7591855577e083aad5923aed37b18d0b2a40c
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="89e66-103">Notas de versão</span><span class="sxs-lookup"><span data-stu-id="89e66-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="89e66-104">É uma lista das alterações feitas nesta versão do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89e66-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="89e66-105">Versão 1.2.9</span><span class="sxs-lookup"><span data-stu-id="89e66-105">Version 1.2.9</span></span>
<a id="version-129" class="xliff"></a>

<span data-ttu-id="89e66-106">Alterações nesta Versão</span><span class="sxs-lookup"><span data-stu-id="89e66-106">Changes This Release</span></span>

* <span data-ttu-id="89e66-107">Módulo AzureRm.AzureStackAdmin</span><span class="sxs-lookup"><span data-stu-id="89e66-107">AzureRm.AzureStackAdmin Module</span></span>
    + <span data-ttu-id="89e66-108">Alterações no cmdlet Add-AzureRmResourceProviderRegistration para o suporte do Azure Resource Manager de Administração e divisão do Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="89e66-108">Changes in the Add-AzureRmResourceProviderRegistration cmdlet for the support of Admin Azure resource manager and tenant azure resource manager split.</span></span> <span data-ttu-id="89e66-109">Um novo parâmetro -ResourceManagerType foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="89e66-109">A new parameter -ResourceManagerType has been added.</span></span>
    + <span data-ttu-id="89e66-110">Remoção dos parâmetros -AdminUri, -ApiVersion, -SubscriptionId e -Token de cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="89e66-110">Removal of the parameters -AdminUri, -ApiVersion, -SubscriptionId and -Token from each cmdlets.</span></span> <span data-ttu-id="89e66-111">Estivemos imprimindo avisos de que esses parâmetros seriam substituídos e agora eles foram removidos.</span><span class="sxs-lookup"><span data-stu-id="89e66-111">We have been printing warnings that these parameters will be deprecated and now they got removed.</span></span>
* <span data-ttu-id="89e66-112">Módulo AzureStackStorage</span><span class="sxs-lookup"><span data-stu-id="89e66-112">AzureStackStorage module</span></span>
    + <span data-ttu-id="89e66-113">Novos cmdlets adicionados para oferecer suporte aos cenários de migração do contêiner.</span><span class="sxs-lookup"><span data-stu-id="89e66-113">Added new cmdlets to support container migration scenarios.</span></span>
    + <span data-ttu-id="89e66-114">Cmdlets removidos referindo-se aos componentes internos e aos recursos subjacentes.</span><span class="sxs-lookup"><span data-stu-id="89e66-114">Removed cmdlets referring to internal components and underlying features.</span></span>
* <span data-ttu-id="89e66-115">AzureRM.BootStrapper</span><span class="sxs-lookup"><span data-stu-id="89e66-115">AzureRM.BootStrapper</span></span>
    + <span data-ttu-id="89e66-116">Novo módulo criado para gerenciar as versões dos cmdlets do Azure PowerShell com o uso dos perfis da versão</span><span class="sxs-lookup"><span data-stu-id="89e66-116">Created new module to manage versions of Azure PowerShell cmdlets through the use of version profiles</span></span>