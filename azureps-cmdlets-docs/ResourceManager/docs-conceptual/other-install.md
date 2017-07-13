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
ms.openlocfilehash: 368404bcb5218814b4965bb1bcda1e2876441d2a
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="47a79-103">Outros métodos de instalação</span><span class="sxs-lookup"><span data-stu-id="47a79-103">Other installation methods</span></span>
<a id="other-installation-methods" class="xliff"></a>

<span data-ttu-id="47a79-104">O Azure PowerShell tem vários métodos de instalação.</span><span class="sxs-lookup"><span data-stu-id="47a79-104">Azure PowerShell has multiple installation methods.</span></span> <span data-ttu-id="47a79-105">O uso do PowerShellGet com a Galeria do PowerShell é o método preferencial.</span><span class="sxs-lookup"><span data-stu-id="47a79-105">Using PowerShellGet with the PowerShell Gallery is the preferred method.</span></span> <span data-ttu-id="47a79-106">O Azure PowerShell pode ser instalado usando o Web Platform Installer (WebPI) ou usando o MSI de arquivo disponível no [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="47a79-106">Azure PowerShell can be installed using the Web Platform Installer (WebPI) or by using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span>

## <span data-ttu-id="47a79-107">Instalar usando o Web Platform Installer</span><span class="sxs-lookup"><span data-stu-id="47a79-107">Install using the Web Platform Installer</span></span>
<a id="install-using-the-web-platform-installer" class="xliff"></a>

<span data-ttu-id="47a79-108">A instalação do Azure PowerShell mais recente do WebPI é feita da mesma maneira como era nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="47a79-108">Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.</span></span>
<span data-ttu-id="47a79-109">Baixe o [pacote WebPI do Azure PowerShell](http://aka.ms/webpi-azps) e inicie a instalação.</span><span class="sxs-lookup"><span data-stu-id="47a79-109">Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.</span></span>

> [!NOTE]
> <span data-ttu-id="47a79-110">Se você já tiver instalado módulos do Azure da Galeria do PowerShell, o instalador os removerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="47a79-110">If you have previously installed Azure modules from the PowerShell Gallery, the installer automatically removes them.</span></span> <span data-ttu-id="47a79-111">Isso simplifica a seu ambiente, garantindo que apenas uma versão do Azure PowerShell está instalada.</span><span class="sxs-lookup"><span data-stu-id="47a79-111">This simplifies your environment by ensuring that only one version of Azure PowerShell is installed.</span></span> <span data-ttu-id="47a79-112">No entanto, há cenários em que será necessário ter diversas versões instaladas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="47a79-112">However, there are scenarios where you may need multiple versions installed at the same time.</span></span>
>
> <span data-ttu-id="47a79-113">Os módulos da Galeria do PowerShell instalam módulos no `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="47a79-113">PowerShell Gallery modules install modules in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="47a79-114">Por outro lado, o instalador do WebPI instalam os módulos do Azure no `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span><span class="sxs-lookup"><span data-stu-id="47a79-114">In contrast, the WebPI installer installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.</span></span>
>
> <span data-ttu-id="47a79-115">Se ocorrer um erro durante a instalação, você poderá remover manualmente as pastas do Azure* de sua pasta `$env:ProgramFiles\WindowsPowerShell\Modules` e tentar instalar novamente.</span><span class="sxs-lookup"><span data-stu-id="47a79-115">If an error occurs during install, you can manually remove the Azure* folders in your `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.</span></span>

<span data-ttu-id="47a79-116">Quando a instalação for concluída, a configuração do `$env:PSModulePath` deverá incluir os diretórios que contêm os cmdlets do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47a79-116">Once the installation completes, your `$env:PSModulePath` setting should include the directories containing the Azure PowerShell cmdlets.</span></span> <span data-ttu-id="47a79-117">O comando a seguir pode ser usado para verificar se o Azure PowerShell foi instalado corretamente.</span><span class="sxs-lookup"><span data-stu-id="47a79-117">The following command can be used to verify that the Azure PowerShell is installed properly.</span></span>

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> <span data-ttu-id="47a79-118">Há um problema conhecido que pode ocorrer durante a instalação do WebPI.</span><span class="sxs-lookup"><span data-stu-id="47a79-118">There is a known issue that can occur when installing from WebPI.</span></span> <span data-ttu-id="47a79-119">Se o computador precisar de uma reinicialização devido a atualizações do sistema ou outras instalações, isso poderá fazer com que as atualizações do `$env:PSModulePath` falhem ao incluir o caminho em que o Azure PowerShell está instalado.</span><span class="sxs-lookup"><span data-stu-id="47a79-119">If your computer requires a restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to fail to include the path where Azure PowerShell is installed.</span></span>

<span data-ttu-id="47a79-120">Ao tentar carregar ou executar cmdlets após a instalação, você poderá receber a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="47a79-120">When attempting to load or execute cmdlets after installation, you can receive the following error message:</span></span>

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

<span data-ttu-id="47a79-121">Esse erro pode ser corrigido ao reiniciar o computador ou importar o módulo usando o caminho totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="47a79-121">This error can be corrected by restarting the machine or importing the module using the fully qualified path.</span></span> <span data-ttu-id="47a79-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="47a79-122">For example:</span></span>

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <span data-ttu-id="47a79-123">Instalar usando o pacote MSI</span><span class="sxs-lookup"><span data-stu-id="47a79-123">Install using the MSI Package</span></span>
<a id="install-using-the-msi-package" class="xliff"></a>

<span data-ttu-id="47a79-124">O Azure PowerShell pode ser instalado usando o arquivo MSI disponível no [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="47a79-124">Azure PowerShell can be installed using the MSI file available from [GitHub](https://github.com/Azure/azure-powershell/releases/latest).</span></span> <span data-ttu-id="47a79-125">Se você tiver versões anteriores dos módulos do Azure instaladas, o instalador as removerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="47a79-125">If you have installed previous versions of Azure modules, the installer automatically removes them.</span></span> <span data-ttu-id="47a79-126">O pacote MSI instala módulos no `$env:ProgramFiles\WindowsPowerShell\Modules`, mas não cria pastas específicas de versão.</span><span class="sxs-lookup"><span data-stu-id="47a79-126">The MSI package installs modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific folders.</span></span>