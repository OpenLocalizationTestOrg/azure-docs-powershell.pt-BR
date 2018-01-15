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
ms.openlocfilehash: 2357bb5d71c221a782a297c41e7a6d08cd3f2952
ms.sourcegitcommit: 4ebdeea3c472d94c1aedb10b9d85bf2e76826e83
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2018
---
# <a name="install-and-configure-azure-powershell-on-macos-and-linux"></a><span data-ttu-id="5a80e-103">Instalar e configurar o Azure PowerShell em macOS e Linux</span><span class="sxs-lookup"><span data-stu-id="5a80e-103">Install and configure Azure PowerShell on macOS and Linux</span></span>

<span data-ttu-id="5a80e-104">Agora é possível instalar o PowerShell 6 (beta) e o Azure PowerShell em plataformas não Windows.</span><span class="sxs-lookup"><span data-stu-id="5a80e-104">It is now possible to install PowerShell 6 (beta) and Azure PowerShell on non-Windows platforms.</span></span>
<span data-ttu-id="5a80e-105">O processo de instalação do Azure PowerShell em macOS e Linux não é diferente do Windows, no entanto, você deve primeiro instalar PowerShell 6 (beta).</span><span class="sxs-lookup"><span data-stu-id="5a80e-105">The process of installing Azure PowerShell on macOS and Linux is not that different from Windows, however, you must first install PowerShell 6 (beta).</span></span>

> [!NOTE]

> <span data-ttu-id="5a80e-106">Atualmente, o PowerShell 6 (beta) e o Azure PowerShell para .NET Core ainda estão na versão beta.</span><span class="sxs-lookup"><span data-stu-id="5a80e-106">At this time, both PowerShell 6 (beta) and Azure PowerShell for .NET Core are still in beta.</span></span>
> <span data-ttu-id="5a80e-107">O suporte para esses produtos é limitado.</span><span class="sxs-lookup"><span data-stu-id="5a80e-107">Support for these products is limited.</span></span> <span data-ttu-id="5a80e-108">Se você tiver problemas ou detectar erros, envie os problemas no GitHub.</span><span class="sxs-lookup"><span data-stu-id="5a80e-108">If you have problems or discover bugs, please file Issues in GitHub.</span></span>
>
> * [<span data-ttu-id="5a80e-109">Problemas do PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="5a80e-109">Issues for PowerShell 6 (beta)</span></span>](https://github.com/PowerShell/PowerShell/issues)
> * [<span data-ttu-id="5a80e-110">Problemas do Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a80e-110">Issues for Azure PowerShell</span></span>](https://github.com/azure/azure-docs-powershell/issues)

## <a name="step-1-install-powershell-6-beta"></a><span data-ttu-id="5a80e-111">Etapa 1: instalar o PowerShell 6 (beta)</span><span class="sxs-lookup"><span data-stu-id="5a80e-111">Step 1: Install PowerShell 6 (beta)</span></span>

<span data-ttu-id="5a80e-112">O processo de instalação do PowerShell 6 (beta) varia dependendo do sistema operacional de destino.</span><span class="sxs-lookup"><span data-stu-id="5a80e-112">The process of installing PowerShell 6 (beta) on varies depending on the target operating system.</span></span>
<span data-ttu-id="5a80e-113">Embora seja possível instalar o PowerShell 6 (beta) no Windows, este artigo concentra-se em macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="5a80e-113">While it is possible to install PowerShell 6 (beta) on Windows, this article focuses on macOS and Linux.</span></span> <span data-ttu-id="5a80e-114">Se você quiser usar o Azure PowerShell no Windows, consulte o artigo de [instalação](./install-azurerm-ps.md) para Windows.</span><span class="sxs-lookup"><span data-stu-id="5a80e-114">If you want to use Azure PowerShell on Windows, see the [install](./install-azurerm-ps.md) article for Windows.</span></span>

<span data-ttu-id="5a80e-115">Para instalar o **PowerShell 6** (beta) no Linux ou macOS, você precisa:</span><span class="sxs-lookup"><span data-stu-id="5a80e-115">To install **PowerShell 6** (beta) on Linux or macOS, you need to:</span></span>

1. <span data-ttu-id="5a80e-116">Obter o PowerShell para o sistema operacional e a versão específicos por meio do [GitHub](https://github.com/powershell/powershell#get-powershell)</span><span class="sxs-lookup"><span data-stu-id="5a80e-116">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
2. <span data-ttu-id="5a80e-117">Seguir as instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="5a80e-117">Follow the installation instructions</span></span>
   - [<span data-ttu-id="5a80e-118">Linux</span><span class="sxs-lookup"><span data-stu-id="5a80e-118">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
   - [<span data-ttu-id="5a80e-119">macOS</span><span class="sxs-lookup"><span data-stu-id="5a80e-119">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)

## <a name="step-2-install-azure-powershell-for-net-core"></a><span data-ttu-id="5a80e-120">Etapa 2: instalar o Azure PowerShell para .NET Core</span><span class="sxs-lookup"><span data-stu-id="5a80e-120">Step 2: Install Azure PowerShell for .NET Core</span></span>

<span data-ttu-id="5a80e-121">O PowerShell 6 (beta) é fornecido com o módulo PowerShellGet já instalado.</span><span class="sxs-lookup"><span data-stu-id="5a80e-121">PowerShell 6 (beta) comes with the PowerShellGet module already installed.</span></span> <span data-ttu-id="5a80e-122">Isso torna fácil instalar qualquer módulo que está publicado na Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a80e-122">This makes it easy to install any module that is published to the PowerShell Gallery.</span></span> <span data-ttu-id="5a80e-123">Para instalar o Azure PowerShell, abra uma nova sessão do PowerShell e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5a80e-123">To install Azure PowerShell, open a new PowerShell session and run the following command:</span></span>

```powershell
Install-Module AzureRM.NetCore
```

## <a name="step-3-load-the-azurermnetcore-module"></a><span data-ttu-id="5a80e-124">Etapa 3: carregar o módulo AzureRM.Netcore</span><span class="sxs-lookup"><span data-stu-id="5a80e-124">Step 3: Load the AzureRM.Netcore module</span></span>

<span data-ttu-id="5a80e-125">Depois de instalar o módulo, você precisa carregá-lo em sua sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a80e-125">Once the module is installed, you need to load the module into your PowerShell session.</span></span> <span data-ttu-id="5a80e-126">Os módulos são carregados usando o cmdlet `Import-Module` da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5a80e-126">Modules are loaded using the `Import-Module` cmdlet, as follows:</span></span>

```powershell
Import-Module AzureRM.Netcore
Import-Module AzureRM.Profile.Netcore
```

<span data-ttu-id="5a80e-127">Depois que a importação for concluída, você poderá testar seu módulo recém-instalado tentando entrar no Azure usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5a80e-127">After the import completes, you can test your newly installed and module by attempting to sign into Azure using the following command:</span></span>

```powershell
Login-AzureRMAccount
```

<span data-ttu-id="5a80e-128">O comando acima solicitará que você acesse `https://aka.ms/devicelogin` e insira o código fornecido.</span><span class="sxs-lookup"><span data-stu-id="5a80e-128">The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the provided code.</span></span>

## <a name="available-cmdlets"></a><span data-ttu-id="5a80e-129">Cmdlets disponíveis</span><span class="sxs-lookup"><span data-stu-id="5a80e-129">Available cmdlets</span></span>

<span data-ttu-id="5a80e-130">Os módulos do Azure PowerShell para .NET padrão ainda estão em desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="5a80e-130">The Azure PowerShell modules for .NET Standard are still in development.</span></span> <span data-ttu-id="5a80e-131">Esses módulos não fornecem o conjunto completo de cmdlets que estão disponíveis para a versão do Windows dos módulos.</span><span class="sxs-lookup"><span data-stu-id="5a80e-131">These modules do not provide the full set of cmdlets that are available for the Windows version of the modules.</span></span> <span data-ttu-id="5a80e-132">As funções a seguir são implementadas em módulos AzureRM.Netcore:</span><span class="sxs-lookup"><span data-stu-id="5a80e-132">The following functions are implemented in AzureRM.Netcore modules:</span></span>

* <span data-ttu-id="5a80e-133">Gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="5a80e-133">Account management</span></span>
  - <span data-ttu-id="5a80e-134">Fazer logon com a conta da Microsoft, conta organizacional ou entidade de serviço por meio do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5a80e-134">Login with Microsoft account, Organizational account, or Service Principal through Microsoft Azure Active Directory</span></span>
  - <span data-ttu-id="5a80e-135">Salvar credenciais para o disco com Save-AzureRmContext e carregar as credenciais salvas usando Import-AzureRmContext</span><span class="sxs-lookup"><span data-stu-id="5a80e-135">Save Credentials to disk with Save-AzureRmContext and load saved credentials using Import-AzureRmContext</span></span>
* <span data-ttu-id="5a80e-136">Ambiente</span><span class="sxs-lookup"><span data-stu-id="5a80e-136">Environment</span></span>
  - <span data-ttu-id="5a80e-137">Obter os diferentes ambientes do Microsoft Azure prontos para uso</span><span class="sxs-lookup"><span data-stu-id="5a80e-137">Get the different out-of-box Microsoft Azure environments</span></span>
  - <span data-ttu-id="5a80e-138">Adicionar/definir/remover ambientes personalizados (como seus ambientes do Azure Stack ou do Pacote do Microsoft Azure)</span><span class="sxs-lookup"><span data-stu-id="5a80e-138">Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)</span></span>
* <span data-ttu-id="5a80e-139">Cmdlets de plano de gerenciamento para os Serviços do Azure usando as interfaces do Resource Manager e do Gerenciamento de Serviços.</span><span class="sxs-lookup"><span data-stu-id="5a80e-139">Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.</span></span>
  - <span data-ttu-id="5a80e-140">Máquina Virtual</span><span class="sxs-lookup"><span data-stu-id="5a80e-140">Virtual Machine</span></span>
  - <span data-ttu-id="5a80e-141">Serviço de Aplicativo (Sites)</span><span class="sxs-lookup"><span data-stu-id="5a80e-141">App Service (Websites)</span></span>
  - <span data-ttu-id="5a80e-142">Banco de dados SQL</span><span class="sxs-lookup"><span data-stu-id="5a80e-142">SQL Database</span></span>
  - <span data-ttu-id="5a80e-143">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="5a80e-143">Storage</span></span>
  - <span data-ttu-id="5a80e-144">Rede</span><span class="sxs-lookup"><span data-stu-id="5a80e-144">Network</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a80e-145">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5a80e-145">Next Steps</span></span>

<span data-ttu-id="5a80e-146">Para saber mais sobre como usar o Azure PowerShell, confira o artigo [Introdução ao Azure PowerShell](get-started-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="5a80e-146">For more information about using Azure PowerShell, see the [Get started with Azure PowerShell](get-started-azureps.md) article.</span></span>
