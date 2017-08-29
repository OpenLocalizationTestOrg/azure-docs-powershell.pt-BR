---
title: Outras maneiras de instalar o Azure PowerShell | Microsoft Docs
description: Como instalar o Azure PowerShell usando o pacote MSI ou o Web Platform Installer.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.openlocfilehash: 9cee582f74b7f3260c6ae167a8ac358d360ad8ab
ms.sourcegitcommit: 45587b5091293288e16cfae8ac412e0d42f8f450
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2017
---
# <a name="other-installation-methods"></a><span data-ttu-id="46aff-103">Outros métodos de instalação</span><span class="sxs-lookup"><span data-stu-id="46aff-103">Other installation methods</span></span>

<span data-ttu-id="46aff-104">O Azure PowerShell tem vários métodos de instalação.</span><span class="sxs-lookup"><span data-stu-id="46aff-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="46aff-105">O uso do PowerShellGet com a Galeria do PowerShell é o método preferencial.</span><span class="sxs-lookup"><span data-stu-id="46aff-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="46aff-106">O Azure PowerShell pode ser instalado usando o Web Platform Installer (WebPI) ou usando o MSI de arquivo disponível no [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="46aff-106">Azure PowerShell can be installed using the Web Platform Installer (WebPI) or by using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span>

## <a name="docker"></a><span data-ttu-id="46aff-107">Docker</span><span class="sxs-lookup"><span data-stu-id="46aff-107">Docker</span></span>

<span data-ttu-id="46aff-108">Vamos manter uma imagem do Docker pré-configurada no Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46aff-108">We maintain a Docker image preconfigured with Azure PowerShell.</span></span>

<span data-ttu-id="46aff-109">Execute o contêiner com `docker run`.</span><span class="sxs-lookup"><span data-stu-id="46aff-109">Run the container with `docker run`.</span></span>

```powershell
docker run azuresdk/azure-powershell
```

<span data-ttu-id="46aff-110">Além disso, vamos manter um subconjunto de cmdlets como um contêiner do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="46aff-110">In addition, we maintain a subset of cmdlets as a PowerShell Core container.</span></span>

<span data-ttu-id="46aff-111">Para Mac/Linux, use a imagem `latest`.</span><span class="sxs-lookup"><span data-stu-id="46aff-111">For Mac/Linux, use the `latest` image.</span></span>

```bash
docker run azuresdk/azure-powershell-core:latest
```

<span data-ttu-id="46aff-112">Para Windows, use a imagem `nanoserver`.</span><span class="sxs-lookup"><span data-stu-id="46aff-112">For Windows, use the `nanoserver` image.</span></span>

```powershell
docker run azuresdk/azure-powershell-core:nanoserver
```

<span data-ttu-id="46aff-113">O Azure PowerShell é instalado na imagem por meio de `Install-Module` da [Galeria do PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="46aff-113">Azure PowerShell is installed on the image via `Install-Module` from the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

## <a name="install-using-the-web-platform-installer"></a><span data-ttu-id="46aff-114">Instalar usando o Web Platform Installer</span><span class="sxs-lookup"><span data-stu-id="46aff-114">Install using the Web Platform Installer</span></span>

<span data-ttu-id="46aff-115">A instalação do Azure PowerShell mais recente do WebPI é feita da mesma maneira como era nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="46aff-115">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="46aff-116">Baixe o [pacote WebPI do Azure PowerShell](http://aka.ms/webpi-azps) e inicie a instalação.</span><span class="sxs-lookup"><span data-stu-id="46aff-116">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="46aff-117">Se você já tiver instalado módulos do Azure da Galeria do PowerShell, o instalador os removerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="46aff-117">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="46aff-118">Isso simplifica a seu ambiente, garantindo que apenas uma versão do Azure PowerShell está instalada.</span><span class="sxs-lookup"><span data-stu-id="46aff-118">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="46aff-119">No entanto, há cenários em que será necessário ter diversas versões instaladas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="46aff-119">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="46aff-120">Os módulos da Galeria do PowerShell instalam módulos no `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="46aff-120">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="46aff-121">Por outro lado, o instalador do WebPI instalam os módulos do Azure no `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="46aff-121">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="46aff-122">Se ocorrer um erro durante a instalação, você poderá remover manualmente as pastas do Azure* de sua pasta `$env:ProgramFiles\WindowsPowerShell\Modules` e tentar instalar novamente.</span><span class="sxs-lookup"><span data-stu-id="46aff-122">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="46aff-123">Quando a instalação for concluída, a configuração do `$env:PSModulePath` deverá incluir os diretórios que contêm os cmdlets do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46aff-123">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="46aff-124">O comando a seguir pode ser usado para verificar se o Azure PowerShell foi instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="46aff-124">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="46aff-125">Há um problema conhecido que pode ocorrer durante a instalação do WebPI.</span><span class="sxs-lookup"><span data-stu-id="46aff-125">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="46aff-126">Se o computador precisar de uma reinicialização devido a atualizações do sistema ou outras instalações, isso poderá fazer com que as atualizações do `$env:PSModulePath` falhem ao incluir o caminho em que o Azure PowerShell está instalado.</span><span class="sxs-lookup"><span data-stu-id="46aff-126">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="46aff-127">Ao tentar carregar ou executar cmdlets após a instalação, você poderá receber a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="46aff-127">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="46aff-128">Esse erro pode ser corrigido ao reiniciar o computador ou importar o módulo usando o caminho totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="46aff-128">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="46aff-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="46aff-129">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-using-the-msi-package"></a><span data-ttu-id="46aff-130">Instalar usando o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="46aff-130">Install using the MSI Package</span></span>

<span data-ttu-id="46aff-131">O Azure PowerShell pode ser instalado usando o arquivo MSI disponível no [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="46aff-131">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="46aff-132">Se você tiver versões anteriores dos módulos do Azure instaladas, o instalador as removerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="46aff-132">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="46aff-133">O pacote MSI instala módulos no `$env:ProgramFiles\WindowsPowerShell\Modules`, mas não cria pastas específicas de versão.</span><span class="sxs-lookup"><span data-stu-id="46aff-133">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>
