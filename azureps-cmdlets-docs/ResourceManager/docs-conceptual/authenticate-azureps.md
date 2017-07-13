---
title: <span data-ttu-id="04ae0-101">Fazer logon com o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="04ae0-101">Log in with Azure PowerShell</span></span>
description: <span data-ttu-id="04ae0-102">Fazer logon com o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="04ae0-102">Log in with Azure PowerShell</span></span>
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: f6d249ca5bb09c4fe8445ba5b339ffa6012815ed
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="04ae0-103">Fazer logon com o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="04ae0-103">Log in with Azure PowerShell</span></span>
<a id="log-in-with-azure-powershell" class="xliff"></a>

<span data-ttu-id="04ae0-104">O Azure PowerShell oferece suporte a vários métodos de logon.</span><span class="sxs-lookup"><span data-stu-id="04ae0-104">Azure PowerShell supports multiple login methods.</span></span> <span data-ttu-id="04ae0-105">É a maneira mais simples para começar a fazer logon interativamente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="04ae0-105">The simplest way to get started is to log in interactively at the command line.</span></span>

## <span data-ttu-id="04ae0-106">Logon Interativo</span><span class="sxs-lookup"><span data-stu-id="04ae0-106">Interactive log in</span></span>
<a id="interactive-log-in" class="xliff"></a>

1. <span data-ttu-id="04ae0-107">Digite `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="04ae0-107">Type `Login-AzureRmAccount`.</span></span> <span data-ttu-id="04ae0-108">Será exibida a caixa de diálogo solicitando as credenciais do Azure.</span><span class="sxs-lookup"><span data-stu-id="04ae0-108">You will get dialog box asking for your Azure credentials.</span></span>

2. <span data-ttu-id="04ae0-109">Digite o endereço de e-mail e a senha associada à sua conta.</span><span class="sxs-lookup"><span data-stu-id="04ae0-109">Type the email address and password associated with your account.</span></span> <span data-ttu-id="04ae0-110">O Azure autentica e salva as informações de credenciais e, em seguida, fecha a janela.</span><span class="sxs-lookup"><span data-stu-id="04ae0-110">Azure authenticates and saves the credential information, and then closes the window.</span></span>

## <span data-ttu-id="04ae0-111">Fazer logon com uma entidade de serviço</span><span class="sxs-lookup"><span data-stu-id="04ae0-111">Log in with a service principal</span></span>
<a id="log-in-with-a-service-principal" class="xliff"></a>

<span data-ttu-id="04ae0-112">As entidades de serviço oferecem uma maneira de criar contas não interativas para manipular recursos.</span><span class="sxs-lookup"><span data-stu-id="04ae0-112">Service principals provide a way for you to create non-interactive accounts that you can use to manipulate resources.</span></span> <span data-ttu-id="04ae0-113">As entidades de serviço são como as contas de usuário às quais você pode aplicar regras usando o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="04ae0-113">Service principals are like user accounts to which you can apply rules using Azure Active Directory.</span></span> <span data-ttu-id="04ae0-114">Ao conceder as permissões mínimas necessárias para uma entidade de serviço, você pode garantir que seus scripts de automação fiquem ainda mais seguros.</span><span class="sxs-lookup"><span data-stu-id="04ae0-114">By granting the minimum permissions needed to a service principal, you can ensure your automation scripts are even more secure.</span></span>

1. <span data-ttu-id="04ae0-115">Se você ainda não tiver uma entidade de serviço, [crie uma](create-azure-service-principal-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="04ae0-115">If you don't already have a service principal, [create one](create-azure-service-principal-azureps.md).</span></span>

2. <span data-ttu-id="04ae0-116">Faça logon com uma entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="04ae0-116">Log in with the service principal.</span></span>

    ```powershell
    Login-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
    ```

    <span data-ttu-id="04ae0-117">Para obter a TenantId, faça logon interativamente e obtenha a TenantId da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="04ae0-117">To get your TenantId, log in interactively and then get the TenantId from your subscription.</span></span>

    ```powershell
    Get-AzureRmSubscription
    ```

    ```
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :
    ```

## <span data-ttu-id="04ae0-118">Faça logon em outra Nuvem</span><span class="sxs-lookup"><span data-stu-id="04ae0-118">Log in to another Cloud</span></span>
<a id="log-in-to-another-cloud" class="xliff"></a>

<span data-ttu-id="04ae0-119">Os Serviços de Nuvem do Azure oferecem ambientes diferentes que estão de acordo com as regulamentações de manipulação de dados de diversos governos.</span><span class="sxs-lookup"><span data-stu-id="04ae0-119">Azure cloud services provide different environments that adhere to the data-handling regulations of various governments.</span></span> <span data-ttu-id="04ae0-120">Caso sua conta do Azure esteja em uma das nuvens de governo, será necessário especificar o ambiente ao se conectar.</span><span class="sxs-lookup"><span data-stu-id="04ae0-120">If your Azure account is in one the government clouds, you need to specify the environment when you sign in.</span></span> <span data-ttu-id="04ae0-121">Por exemplo, se sua conta está na nuvem da China, faça logon usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="04ae0-121">For example, if you account is in the China cloud you sign on using the following command:</span></span>

```powershell
Login-AzureRmAccount -EnvironmentName AzureChinaCloud
```

<span data-ttu-id="04ae0-122">Use o seguinte comando para obter uma lista de ambientes disponíveis:</span><span class="sxs-lookup"><span data-stu-id="04ae0-122">Use the following command to get a list of available environments:</span></span>

```powershell
Get-AzureRmEnvironment | Select-Object Name
```

```
Name
----
AzureCloud
AzureChinaCloud
AzureUSGovernment
AzureGermanCloud
```

## <span data-ttu-id="04ae0-123">Saiba mais sobre como gerenciar o acesso baseado em função do Azure</span><span class="sxs-lookup"><span data-stu-id="04ae0-123">Learn more about managing Azure role-based access</span></span>
<a id="learn-more-about-managing-azure-role-based-access" class="xliff"></a>

<span data-ttu-id="04ae0-124">Para obter mais informações sobre o gerenciamento de autenticação e assinatura no Azure, consulte [Gerenciar contas, assinaturas e funções administrativas](/azure/active-directory/role-based-access-control-configure) (a página pode estar em inglês).</span><span class="sxs-lookup"><span data-stu-id="04ae0-124">For more information about authentication and subscription management in Azure, see [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).</span></span>

<span data-ttu-id="04ae0-125">Cmdlets do Azure PowerShell para gerenciamento de função</span><span class="sxs-lookup"><span data-stu-id="04ae0-125">Azure PowerShell cmdlets for role management</span></span>

* [<span data-ttu-id="04ae0-126">Get-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="04ae0-126">Get-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [<span data-ttu-id="04ae0-127">Get-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="04ae0-127">Get-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [<span data-ttu-id="04ae0-128">New-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="04ae0-128">New-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [<span data-ttu-id="04ae0-129">New-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="04ae0-129">New-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [<span data-ttu-id="04ae0-130">Remove-AzureRmRoleAssignment</span><span class="sxs-lookup"><span data-stu-id="04ae0-130">Remove-AzureRmRoleAssignment</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [<span data-ttu-id="04ae0-131">Remove-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="04ae0-131">Remove-AzureRmRoleDefinition</span></span>](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [<span data-ttu-id="04ae0-132">Set-AzureRmRoleDefinition</span><span class="sxs-lookup"><span data-stu-id="04ae0-132">Set-AzureRmRoleDefinition</span></span>](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)