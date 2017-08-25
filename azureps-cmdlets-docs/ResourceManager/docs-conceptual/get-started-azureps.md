---
title: "Introdução aos cmdlets do Azure PowerShell | Microsoft Docs"
description: 
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 03/30/2017
ms.openlocfilehash: f1c13317f0b42b547166a8130dd8c29bed5759c9
ms.sourcegitcommit: db5c50de90764a9bdc7c1f1dbca3aed5bfeb05fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2017
---
# <a name="getting-started-with-azure-powershell"></a><span data-ttu-id="7191c-102">Introdução ao Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7191c-102">Getting started with Azure PowerShell</span></span>

<span data-ttu-id="7191c-103">O Azure PowerShell foi projetado para gerenciar e administrar os recursos do Azure da linha de comando e para a compilação de scripts de automação que funcionam no Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="7191c-103">Azure PowerShell is designed for managing and administering Azure resources from the command line, and for building automation scripts that work against the Azure Resource Manager.</span></span> <span data-ttu-id="7191c-104">Este artigo ajuda você a começar a usá-lo, além de ensinar os conceitos básicos por trás dele.</span><span class="sxs-lookup"><span data-stu-id="7191c-104">This article helps get you started using it, and teaches you the core concepts behind it.</span></span>

## <a name="install-azure-powershell"></a><span data-ttu-id="7191c-105">Instalar o Azure Powershell</span><span class="sxs-lookup"><span data-stu-id="7191c-105">Install Azure PowerShell</span></span>

<span data-ttu-id="7191c-106">A primeira etapa é certificar-se de que você tem a versão mais recente do Azure PowerShell instalada.</span><span class="sxs-lookup"><span data-stu-id="7191c-106">The first step is to make sure you have the latest version of the Azure PowerShell installed.</span></span> <span data-ttu-id="7191c-107">Para saber mais sobre a versão mais recente, veja as [notas de versão](./release-notes-azureps.md).</span><span class="sxs-lookup"><span data-stu-id="7191c-107">For information about the latest release, see the [release notes](./release-notes-azureps.md).</span></span>

1. <span data-ttu-id="7191c-108">[Instale o Azure PowerShell](install-azurerm-ps.md).</span><span class="sxs-lookup"><span data-stu-id="7191c-108">[Install Azure PowerShell](install-azurerm-ps.md).</span></span>
2. <span data-ttu-id="7191c-109">Para verificar se a instalação foi bem-sucedida, execute `Get-Module AzureRM` na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="7191c-109">To verify the installation was successful, run `Get-Module AzureRM` from your command line.</span></span>

## <a name="log-in-to-azure"></a><span data-ttu-id="7191c-110">Fazer logon no Azure</span><span class="sxs-lookup"><span data-stu-id="7191c-110">Log in to Azure</span></span>

<span data-ttu-id="7191c-111">Logon interativo:</span><span class="sxs-lookup"><span data-stu-id="7191c-111">Sign on interactively:</span></span>

1. <span data-ttu-id="7191c-112">Digite `Login-AzureRmAccount`.</span><span class="sxs-lookup"><span data-stu-id="7191c-112">Type `Login-AzureRmAccount`.</span></span> <span data-ttu-id="7191c-113">Será exibida a caixa de diálogo solicitando as credenciais do Azure.</span><span class="sxs-lookup"><span data-stu-id="7191c-113">You will get dialog box asking for your Azure credentials.</span></span> <span data-ttu-id="7191c-114">A opção '-EnvironmentName' pode permitir que você faça logon no Azure China ou Azure Alemanha.</span><span class="sxs-lookup"><span data-stu-id="7191c-114">Option '-EnvironmentName' can let you login in Azure China or Azure Germany.</span></span>

   <span data-ttu-id="7191c-115">Por exemplo, Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="7191c-115">e.g. Login-AzureRmAccount -EnvironmentName AzureChinaCloud</span></span>

2. <span data-ttu-id="7191c-116">Digite o endereço de e-mail e a senha associada à sua conta.</span><span class="sxs-lookup"><span data-stu-id="7191c-116">Type the email address and password associated with your account.</span></span> <span data-ttu-id="7191c-117">O Azure autentica e salva as informações de credenciais e, em seguida, fecha a janela.</span><span class="sxs-lookup"><span data-stu-id="7191c-117">Azure authenticates and saves the credential information, and then closes the window.</span></span>

<span data-ttu-id="7191c-118">Depois de entrar em uma conta do Azure, use os cmdlets do Azure PowerShell para acessar e gerenciar os recursos em sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="7191c-118">Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and manager the resources in your subscription.</span></span>

## <a name="create-a-resource-group"></a><span data-ttu-id="7191c-119">Criar um grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="7191c-119">Create a resource group</span></span>

<span data-ttu-id="7191c-120">Agora que tudo foi configurado, vamos usar o Azure PowerShell para criar recursos no Azure.</span><span class="sxs-lookup"><span data-stu-id="7191c-120">Now that we've got everything set up, let's use Azure PowerShell to create resources within Azure.</span></span>

<span data-ttu-id="7191c-121">Primeiro, crie um Grupo de Recursos.</span><span class="sxs-lookup"><span data-stu-id="7191c-121">First, create a Resource Group.</span></span> <span data-ttu-id="7191c-122">Os Grupos de recursos no Azure fornecem uma maneira de gerenciar vários recursos que você deseja agrupar logicamente.</span><span class="sxs-lookup"><span data-stu-id="7191c-122">Resource Groups in Azure provide a way to manage multiple resources that you want to logically group together.</span></span> <span data-ttu-id="7191c-123">Por exemplo, você pode criar um Grupo de recursos para um aplicativo ou projeto e adicionar uma máquina virtual, um banco de dados e um serviço CDN dentro dele.</span><span class="sxs-lookup"><span data-stu-id="7191c-123">For example, you might create a Resource Group for an application or project and add a virtual machine, a database and a CDN service within it.</span></span>

<span data-ttu-id="7191c-124">Vamos criar um grupo de recursos chamado "MyResourceGroup" na região Europa Ocidental do Azure.</span><span class="sxs-lookup"><span data-stu-id="7191c-124">Let's create a resource group named "MyResourceGroup" in the westeurope region of Azure.</span></span> <span data-ttu-id="7191c-125">Para fazer isso, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7191c-125">To do so type the following command:</span></span>

```powershell
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

## <a name="create-a-windows-virtual-machine"></a><span data-ttu-id="7191c-126">Criar uma máquina virtual do Windows</span><span class="sxs-lookup"><span data-stu-id="7191c-126">Create a Windows Virtual Machine</span></span>

<span data-ttu-id="7191c-127">Agora que temos nosso grupo de recursos, vamos criar uma VM do Windows dentro dele.</span><span class="sxs-lookup"><span data-stu-id="7191c-127">Now that we have our resource group, let's create a Windows VM within it.</span></span> <span data-ttu-id="7191c-128">Para criar uma nova VM, primeiro crie os outros recursos necessários e atribua-os a uma configuração.</span><span class="sxs-lookup"><span data-stu-id="7191c-128">To create a new VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="7191c-129">Em seguida, podemos usar essa configuração para criar a VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-129">Then we can use that configuration to create the VM.</span></span>

### <a name="create-the-required-network-resources"></a><span data-ttu-id="7191c-130">Criar os recursos de rede necessários</span><span class="sxs-lookup"><span data-stu-id="7191c-130">Create the required network resources</span></span>

<span data-ttu-id="7191c-131">Primeiro, precisamos criar uma configuração de sub-rede para usar com o processo de criação da rede virtual.</span><span class="sxs-lookup"><span data-stu-id="7191c-131">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="7191c-132">Também criamos um endereço IP público para que possamos nos conectar a essa VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-132">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="7191c-133">Criamos um grupo de segurança de rede para proteger o acesso ao endereço público.</span><span class="sxs-lookup"><span data-stu-id="7191c-133">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="7191c-134">Finalmente, criamos a NIC virtual usando todos os recursos anteriores.</span><span class="sxs-lookup"><span data-stu-id="7191c-134">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myWindowsVM"

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet1 -AddressPrefix 192.168.1.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET1 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 3389
$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 3389 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup1 -SecurityRules $nsgRuleRDP

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic1 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-virtual-machine"></a><span data-ttu-id="7191c-135">Criar a máquina virtual</span><span class="sxs-lookup"><span data-stu-id="7191c-135">Create the virtual machine</span></span>

<span data-ttu-id="7191c-136">Primeiro, precisamos de um conjunto de credenciais para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7191c-136">First we need a set of credentials for the OS.</span></span>

```powershell
# Create user object
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

<span data-ttu-id="7191c-137">Agora que temos os recursos necessários, podemos criar a VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-137">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="7191c-138">Para esta etapa, criamos um objeto de configuração da VM, depois, usamos a configuração para criar a VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-138">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Windows -ComputerName $vmName -Credential $cred |
  Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="7191c-139">O comando `New-AzureRmVM` gera resultados após a VM ter sido totalmente criada e estar pronta para ser usada.</span><span class="sxs-lookup"><span data-stu-id="7191c-139">The `New-AzureRmVM` command outputs results once the VM has been fully created and is ready to be used.</span></span>

```
RequestId IsSuccessStatusCode StatusCode ReasonPhrase
--------- ------------------- ---------- ------------
                         True         OK OK
```

<span data-ttu-id="7191c-140">Agora faça logon em sua VM do Windows Server criada recentemente usando a Área de Trabalho Remota e o endereço IP público da VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-140">Now log on to your newly created Windows Server VM using Remote Desktop and the public IP address of the VM.</span></span> <span data-ttu-id="7191c-141">O comando a seguir exibe o endereço IP público criado no script anterior.</span><span class="sxs-lookup"><span data-stu-id="7191c-141">The following command displays the public IP address created in the previous script.</span></span>

```powershell
$publicIp | Select-Object Name,IpAddress
```

```
Name                  IpAddress
----                  ---------
mypublicdns1400512543 xx.xx.xx.xx
```

<span data-ttu-id="7191c-142">Se você estiver em um sistema baseado em Windows, faça isso na linha de comando usando o comando mstsc:</span><span class="sxs-lookup"><span data-stu-id="7191c-142">If you are on a Windows-based system, you can do this from the command line using the mstsc command:</span></span>

```
mstsc /v:xx.xxx.xx.xxx
```

<span data-ttu-id="7191c-143">Forneça a mesma combinação de nome de usuário/senha usada ao criar a VM para efetuar o logon.</span><span class="sxs-lookup"><span data-stu-id="7191c-143">Supply the same username/password combination you used when creating the VM to log in.</span></span>


## <a name="create-a-linux-virtual-machine"></a><span data-ttu-id="7191c-144">Criar uma máquina virtual do Linux</span><span class="sxs-lookup"><span data-stu-id="7191c-144">Create a Linux Virtual Machine</span></span>

<span data-ttu-id="7191c-145">Para criar uma nova VM do Linux, primeiro crie os outros recursos necessários e atribua-os a uma configuração.</span><span class="sxs-lookup"><span data-stu-id="7191c-145">To create a new Linux VM we must first create the other required resources and assign them to a configuration.</span></span> <span data-ttu-id="7191c-146">Em seguida, podemos usar essa configuração para criar a VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-146">Then we can use that configuration to create the VM.</span></span> <span data-ttu-id="7191c-147">Isso pressupõe que você já criou o grupo de recursos conforme mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7191c-147">This assumes that you have already created the resource group as previously shown.</span></span> <span data-ttu-id="7191c-148">Além disso, você precisará ter uma chave pública SSH chamada `id_rsa.pub` no diretório .ssh do perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="7191c-148">Also, you will need to have an SSH public key named `id_rsa.pub` in the .ssh directory of your user profile.</span></span>

### <a name="create-the-required-network-resources"></a><span data-ttu-id="7191c-149">Criar os recursos de rede necessários</span><span class="sxs-lookup"><span data-stu-id="7191c-149">Create the required network resources</span></span>

<span data-ttu-id="7191c-150">Primeiro, precisamos criar uma configuração de sub-rede para usar com o processo de criação da rede virtual.</span><span class="sxs-lookup"><span data-stu-id="7191c-150">First we need to create a subnet configuration to be used with the virtual network creation process.</span></span> <span data-ttu-id="7191c-151">Também criamos um endereço IP público para que possamos nos conectar a essa VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-151">We also create a public IP address so that we can connect to this VM.</span></span> <span data-ttu-id="7191c-152">Criamos um grupo de segurança de rede para proteger o acesso ao endereço público.</span><span class="sxs-lookup"><span data-stu-id="7191c-152">We create a network security group to secure access to the public address.</span></span> <span data-ttu-id="7191c-153">Finalmente, criamos a NIC virtual usando todos os recursos anteriores.</span><span class="sxs-lookup"><span data-stu-id="7191c-153">Finally we create the virtual NIC using all of the previous resources.</span></span>

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString ' ' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential ("azureuser", $securePassword)

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 192.168.2.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET2 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 22
$nsgRuleSSH = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleSSH  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 22 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup2 -SecurityRules $nsgRuleSSH

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic2 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-virtual-machine"></a><span data-ttu-id="7191c-154">Criar a máquina virtual</span><span class="sxs-lookup"><span data-stu-id="7191c-154">Create the virtual machine</span></span>

<span data-ttu-id="7191c-155">Agora que temos os recursos necessários, podemos criar a VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-155">Now that we have the required resources we can create the VM.</span></span> <span data-ttu-id="7191c-156">Para esta etapa, criamos um objeto de configuração da VM, depois, usamos a configuração para criar a VM.</span><span class="sxs-lookup"><span data-stu-id="7191c-156">For this step, we create a VM configuration object, then we use the configuration to create the VM.</span></span>

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

<span data-ttu-id="7191c-157">Agora que a VM foi criada, faça logon em sua nova VM do Linux usando SSH com o endereço IP público da VM criada:</span><span class="sxs-lookup"><span data-stu-id="7191c-157">Now that the VM has been created, you can log on to your new Linux VM using SSH with the public IP address of the VM you created:</span></span>

```bash
ssh xx.xxx.xxx.xxx
```

```
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.19.0-65-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Feb 19 00:32:28 UTC 2017

  System load: 0.31              Memory usage: 3%   Processes:       89
  Usage of /:  39.6% of 1.94GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

my-login@MyLinuxVM:~$
```

## <a name="creating-other-resources-in-azure"></a><span data-ttu-id="7191c-158">Criar outros recursos no Azure</span><span class="sxs-lookup"><span data-stu-id="7191c-158">Creating other resources in Azure</span></span>

<span data-ttu-id="7191c-159">Agora percorremos a criação de um Grupo de recursos, uma VM do Linux e uma VM do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7191c-159">We've now walked through how to create a Resource Group, a Linux VM, and a Windows Server VM.</span></span> <span data-ttu-id="7191c-160">Você também pode criar vários outros tipos de recursos do Azure.</span><span class="sxs-lookup"><span data-stu-id="7191c-160">You can create many other types of Azure resources as well.</span></span>

<span data-ttu-id="7191c-161">Por exemplo, para criar um Balanceador de carga de rede do Azure que poderíamos associar às nossas VMs recém-criadas, podemos usar o seguinte comando create:</span><span class="sxs-lookup"><span data-stu-id="7191c-161">For example, to create an Azure Network Load Balancer that we could then associate with our newly created VMs, we can use the following create command:</span></span>

```powershell
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

<span data-ttu-id="7191c-162">Também poderíamos criar uma nova Rede Virtual privada (conhecida como "VNet" no Azure) para nossa infraestrutura usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7191c-162">We could also create a new private Virtual Network (commonly referred to as a "VNet" within Azure) for our infrastructure using the following command:</span></span>

```powershell
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

<span data-ttu-id="7191c-163">O que torna o Azure e o Azure PowerShell tão poderosos é que podemos usar isso não apenas para obter a infraestrutura baseada em nuvem, mas também para criar serviços de plataforma gerenciados.</span><span class="sxs-lookup"><span data-stu-id="7191c-163">What makes Azure and the Azure PowerShell powerful is that we can use it not just to get cloud-based infrastructure but also to create managed platform services.</span></span> <span data-ttu-id="7191c-164">Os serviços de plataforma gerenciados também podem ser combinados com a infraestrutura para compilar soluções ainda mais eficientes.</span><span class="sxs-lookup"><span data-stu-id="7191c-164">The managed platform services can also be combined with infrastructure to build even more powerful solutions.</span></span>

<span data-ttu-id="7191c-165">Por exemplo, é possível usar o Azure PowerShell para criar um Serviço de Aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="7191c-165">For example, you can use the Azure PowerShell to create an Azure AppService.</span></span> <span data-ttu-id="7191c-166">Serviço de Aplicativo do Azure é um serviço de plataforma gerenciado que fornece uma ótima maneira para hospedar aplicativos Web sem precisar se preocupar com a infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="7191c-166">Azure AppService is a managed platform service that provides a great way to host web apps without having to worry about infrastructure.</span></span> <span data-ttu-id="7191c-167">Depois de criar o Serviço de Aplicativo do Azure, você pode criar dois novos Aplicativos Web do Azure dentro do Serviço de Aplicativo usando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7191c-167">After creating the Azure AppService, you can create two new Azure Web Apps within the AppService using the following commands:</span></span>

```powershell
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <a name="listing-deployed-resources"></a><span data-ttu-id="7191c-168">Listar os recursos implantados</span><span class="sxs-lookup"><span data-stu-id="7191c-168">Listing deployed resources</span></span>

<span data-ttu-id="7191c-169">Usar o cmdlet `Get-AzureRmResource` para listar os recursos em execução no Azure.</span><span class="sxs-lookup"><span data-stu-id="7191c-169">You can use the `Get-AzureRmResource` cmdlet to list the resources running in Azure.</span></span> <span data-ttu-id="7191c-170">O exemplo a seguir mostra os recursos que acabamos de criar no novo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="7191c-170">The following example shows the resources we just created in the new resource group.</span></span>

```powershell
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```
Name                                                  Location   ResourceType
----                                                  --------   ------------
myLinuxVM_OsDisk_1_36ca038791f642ba91270879088c249a   westeurope Microsoft.Compute/disks
myWindowsVM_OsDisk_1_f627e6e2bb454c72897d72e9632adf9a westeurope Microsoft.Compute/disks
myLinuxVM                                             westeurope Microsoft.Compute/virtualMachines
myWindowsVM                                           westeurope Microsoft.Compute/virtualMachines
myWindowsVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic1                                                westeurope Microsoft.Network/networkInterfaces
myNic2                                                westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup1                               westeurope Microsoft.Network/networkSecurityGroups
myNetworkSecurityGroup2                               westeurope Microsoft.Network/networkSecurityGroups
mypublicdns245369171                                  westeurope Microsoft.Network/publicIPAddresses
mypublicdns779537141                                  westeurope Microsoft.Network/publicIPAddresses
MYvNET1                                               westeurope Microsoft.Network/virtualNetworks
MYvNET2                                               westeurope Microsoft.Network/virtualNetworks
micromyresomywi032907510                              westeurope Microsoft.Storage/storageAccounts
```

## <a name="deleting-resources"></a><span data-ttu-id="7191c-171">Excluir os recursos</span><span class="sxs-lookup"><span data-stu-id="7191c-171">Deleting resources</span></span>

<span data-ttu-id="7191c-172">Para limpar sua conta do Azure, convém remover os recursos que criamos neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="7191c-172">To clean up your Azure account, you want to remove the resources we created in this example.</span></span> <span data-ttu-id="7191c-173">Usar os cmdlets `Remove-AzureRm*` para excluir os recursos desnecessários.</span><span class="sxs-lookup"><span data-stu-id="7191c-173">You can use the `Remove-AzureRm*` cmdlets to delete the resources you no longer need.</span></span> <span data-ttu-id="7191c-174">Para remover a VM do Windows que criamos, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7191c-174">To remove the Windows VM we created, using the following command:</span></span>

```powershell
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

<span data-ttu-id="7191c-175">Você receberá uma solicitação para confirmar se deseja remover os recursos.</span><span class="sxs-lookup"><span data-stu-id="7191c-175">You will be prompted to confirm that you want to remove the resource.</span></span>

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="7191c-176">Também é possível usar a exclusão de vários recursos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="7191c-176">You can also use the delete many resources at one time.</span></span> <span data-ttu-id="7191c-177">Por exemplo, o comando a seguir exclui todo o grupo de recursos "MyResourceGroup" que usamos para todos os exemplos neste tutorial de Introdução.</span><span class="sxs-lookup"><span data-stu-id="7191c-177">For example, the following command deletes all the resource group "MyResourceGroup" that we've used for all the samples in this Get Started tutorial.</span></span> <span data-ttu-id="7191c-178">Isso remove o grupo de recursos e todos os recursos contidos nele.</span><span class="sxs-lookup"><span data-stu-id="7191c-178">This removes the resource group and all of the resources in it.</span></span>

```powershell
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

<span data-ttu-id="7191c-179">Isso pode demorar vários minutos.</span><span class="sxs-lookup"><span data-stu-id="7191c-179">This can take several minutes to complete.</span></span>

## <a name="get-samples"></a><span data-ttu-id="7191c-180">Obter exemplos</span><span class="sxs-lookup"><span data-stu-id="7191c-180">Get samples</span></span>

<span data-ttu-id="7191c-181">Para saber mais sobre como usar o Azure PowerShell, confira nossos scripts mais comuns para [VMs do Linux](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [VMs do Windows](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Aplicativos Web](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json) e [Bancos de Dados SQL](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="7191c-181">To learn more about ways to use the Azure PowerShell, check out our most common scripts for [Linux VMs](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Windows VMs](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Web Apps](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), and [SQL Databases](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7191c-182">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7191c-182">Next steps</span></span>

* [<span data-ttu-id="7191c-183">Logon com o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7191c-183">Login with Azure PowerShell</span></span>](authenticate-azureps.md)
* [<span data-ttu-id="7191c-184">Gerenciar as assinaturas do Azure com o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7191c-184">Manage Azure subscriptions with Azure PowerShell</span></span>](manage-subscriptions-azureps.md)
* [<span data-ttu-id="7191c-185">Criar entidades de serviço no Azure usando o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7191c-185">Create service principals in Azure using Azure PowerShell</span></span>](create-azure-service-principal-azureps.md)
* <span data-ttu-id="7191c-186">Leia as notas de versão sobre a migração de uma versão mais antiga: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span><span class="sxs-lookup"><span data-stu-id="7191c-186">Read the Release notes about migrating from an older release: [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).</span></span>
* <span data-ttu-id="7191c-187">Obtenha ajuda da comunidade:</span><span class="sxs-lookup"><span data-stu-id="7191c-187">Get help from the community:</span></span>
  + [<span data-ttu-id="7191c-188">Fórum do Azure no MSDN</span><span class="sxs-lookup"><span data-stu-id="7191c-188">Azure forum on MSDN</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  + [<span data-ttu-id="7191c-189">Stackoverflow</span><span class="sxs-lookup"><span data-stu-id="7191c-189">stackoverflow</span></span>](http://go.microsoft.com/fwlink/?LinkId=320213)
