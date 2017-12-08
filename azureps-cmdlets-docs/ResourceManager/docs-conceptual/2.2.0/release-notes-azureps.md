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
ms.openlocfilehash: 143d92384fd270711378f6741ba59e88c12833d1
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2017
---
# <a name="release-notes"></a><span data-ttu-id="7de50-103">Notas de versão</span><span class="sxs-lookup"><span data-stu-id="7de50-103">Release notes</span></span>

<span data-ttu-id="7de50-104">É uma lista das alterações feitas nesta versão do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7de50-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-220"></a><span data-ttu-id="7de50-105">Versão 2.2.0</span><span class="sxs-lookup"><span data-stu-id="7de50-105">Version 2.2.0</span></span>
* <span data-ttu-id="7de50-106">Computação</span><span class="sxs-lookup"><span data-stu-id="7de50-106">Compute</span></span>
  - <span data-ttu-id="7de50-107">Adicionar suporte para consultar o status da criptografia a partir da extensão AzureDiskEncryptionForLinux</span><span class="sxs-lookup"><span data-stu-id="7de50-107">Add support for querying encryption status from the AzureDiskEncryptionForLinux extension</span></span>
* <span data-ttu-id="7de50-108">DataFactory</span><span class="sxs-lookup"><span data-stu-id="7de50-108">DataFactory</span></span>
  - <span data-ttu-id="7de50-109">Novo cmdlet adicionado para listar as janelas de atividade</span><span class="sxs-lookup"><span data-stu-id="7de50-109">Added new cmdlet for listing activity windows</span></span>
    + <span data-ttu-id="7de50-110">Get-AzureRmDataFactoryActivityWindow</span><span class="sxs-lookup"><span data-stu-id="7de50-110">Get-AzureRmDataFactoryActivityWindow</span></span>
* <span data-ttu-id="7de50-111">DataLake</span><span class="sxs-lookup"><span data-stu-id="7de50-111">DataLake</span></span>
  - <span data-ttu-id="7de50-112">Parâmetro alterado `Host` para `DatabaseHost` e alias adicionado a `Host`</span><span class="sxs-lookup"><span data-stu-id="7de50-112">Changed parameter `Host` to `DatabaseHost` and added alias to `Host`</span></span>
    + <span data-ttu-id="7de50-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="7de50-113">New-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
    + <span data-ttu-id="7de50-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span><span class="sxs-lookup"><span data-stu-id="7de50-114">Set-AzureRmDataLakeAnalyticsCatalogSecret</span></span>
  - <span data-ttu-id="7de50-115">Adicionar suporte para a ACL e a remoção da ACL padrão</span><span class="sxs-lookup"><span data-stu-id="7de50-115">Add support for ACL and Default ACL removal</span></span>
  - <span data-ttu-id="7de50-116">Adicionar suporte para obter e definir permissões sem nome em arquivos e pastas</span><span class="sxs-lookup"><span data-stu-id="7de50-116">Add support for getting and setting unnamed permissions on files and folders</span></span>
* <span data-ttu-id="7de50-117">KeyVault</span><span class="sxs-lookup"><span data-stu-id="7de50-117">KeyVault</span></span>
  - <span data-ttu-id="7de50-118">Adicionar suporte para certificados</span><span class="sxs-lookup"><span data-stu-id="7de50-118">Add support for certificates</span></span>
    + <span data-ttu-id="7de50-119">Add-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="7de50-119">Add-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="7de50-120">Add-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="7de50-120">Add-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="7de50-121">Get-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="7de50-121">Get-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="7de50-122">Get-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="7de50-122">Get-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="7de50-123">Get-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="7de50-123">Get-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="7de50-124">Get-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="7de50-124">Get-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="7de50-125">Get-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-125">Get-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="7de50-126">Import-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="7de50-126">Import-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="7de50-127">New-AzureKeyVaultCertificateAdministratorDetails</span><span class="sxs-lookup"><span data-stu-id="7de50-127">New-AzureKeyVaultCertificateAdministratorDetails</span></span>
    + <span data-ttu-id="7de50-128">New-AzureKeyVaultCertificateOrganizationDetails</span><span class="sxs-lookup"><span data-stu-id="7de50-128">New-AzureKeyVaultCertificateOrganizationDetails</span></span>
    + <span data-ttu-id="7de50-129">New-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-129">New-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="7de50-130">Remove-AzureKeyVaultCertificate</span><span class="sxs-lookup"><span data-stu-id="7de50-130">Remove-AzureKeyVaultCertificate</span></span>
    + <span data-ttu-id="7de50-131">Remove-AzureKeyVaultCertificateContact</span><span class="sxs-lookup"><span data-stu-id="7de50-131">Remove-AzureKeyVaultCertificateContact</span></span>
    + <span data-ttu-id="7de50-132">Remove-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="7de50-132">Remove-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="7de50-133">Remove-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="7de50-133">Remove-AzureKeyVaultCertificateOperation</span></span>
    + <span data-ttu-id="7de50-134">Set-AzureKeyVaultCertificateAttribute</span><span class="sxs-lookup"><span data-stu-id="7de50-134">Set-AzureKeyVaultCertificateAttribute</span></span>
    + <span data-ttu-id="7de50-135">Set-AzureKeyVaultCertificateIssuer</span><span class="sxs-lookup"><span data-stu-id="7de50-135">Set-AzureKeyVaultCertificateIssuer</span></span>
    + <span data-ttu-id="7de50-136">Set-AzureKeyVaultCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-136">Set-AzureKeyVaultCertificatePolicy</span></span>
    + <span data-ttu-id="7de50-137">Stop-AzureKeyVaultCertificateOperation</span><span class="sxs-lookup"><span data-stu-id="7de50-137">Stop-AzureKeyVaultCertificateOperation</span></span>
* <span data-ttu-id="7de50-138">Rede</span><span class="sxs-lookup"><span data-stu-id="7de50-138">Network</span></span>

  - <span data-ttu-id="7de50-139">Novo parâmetro de opção adicionado ao adaptador de rede para habilitar/desabilitar o +New-AzureRmNetworkInterface -EnableAcceleratedNetworking de redes aceleradas</span><span class="sxs-lookup"><span data-stu-id="7de50-139">New switch parameter added for network interface to enable/disable accelerated networking +New-AzureRmNetworkInterface -EnableAcceleratedNetworking</span></span>
  - <span data-ttu-id="7de50-140">Habilitar cmdlets do PowerShell de recurso do gateway de Ativo-Ativo</span><span class="sxs-lookup"><span data-stu-id="7de50-140">Enable Active-Active gateway feature PowerShell cmdlets</span></span>
    + <span data-ttu-id="7de50-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="7de50-141">Add-AzureRmVirtualNetworkGatewayIpConfig</span></span>
    + <span data-ttu-id="7de50-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span><span class="sxs-lookup"><span data-stu-id="7de50-142">Remove-AzureRmVirtualNetworkGatewayIpConfig</span></span>
  - <span data-ttu-id="7de50-143">Novo cmdlet adicionado</span><span class="sxs-lookup"><span data-stu-id="7de50-143">Added new cmdlet</span></span>
    + <span data-ttu-id="7de50-144">Test-AzureRmPrivateIpAddressAvailability</span><span class="sxs-lookup"><span data-stu-id="7de50-144">Test-AzureRmPrivateIpAddressAvailability</span></span>
* <span data-ttu-id="7de50-145">Recursos</span><span class="sxs-lookup"><span data-stu-id="7de50-145">Resources</span></span>
  - <span data-ttu-id="7de50-146">Suporte a zonas nos cmdlets do provedor e de recursos</span><span class="sxs-lookup"><span data-stu-id="7de50-146">Support zones in provider and resource cmdlets</span></span>
    + <span data-ttu-id="7de50-147">Get-AzureRmProvider</span><span class="sxs-lookup"><span data-stu-id="7de50-147">Get-AzureRmProvider</span></span>
    + <span data-ttu-id="7de50-148">New-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="7de50-148">New-AzureRmResource</span></span>
    + <span data-ttu-id="7de50-149">Set-AzureRmResource</span><span class="sxs-lookup"><span data-stu-id="7de50-149">Set-AzureRmResource</span></span>
* <span data-ttu-id="7de50-150">Sql</span><span class="sxs-lookup"><span data-stu-id="7de50-150">Sql</span></span>
  - <span data-ttu-id="7de50-151">Novos cmdlets adicionados para o gerenciamento das políticas de detecção de ameaças do SQL Azure no nível do servidor</span><span class="sxs-lookup"><span data-stu-id="7de50-151">Added new cmdlets for Azure SQL threat detection policy management at server level</span></span>
    + <span data-ttu-id="7de50-152">Get-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-152">Get-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="7de50-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-153">Remove-AzureRmSqlServerThreatDetectionPolicy</span></span>
    + <span data-ttu-id="7de50-154">Set-AzureRmSqlServerThreatDetectionPolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-154">Set-AzureRmSqlServerThreatDetectionPolicy</span></span>
  - <span data-ttu-id="7de50-155">Novos cmdlets adicionados para oferecer suporte para habilitar/desabilitar a GeoBackupPolicy do Sql Azure DataWarehouses</span><span class="sxs-lookup"><span data-stu-id="7de50-155">Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses</span></span>
    + <span data-ttu-id="7de50-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-156">Get-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
    + <span data-ttu-id="7de50-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span><span class="sxs-lookup"><span data-stu-id="7de50-157">Set-AzureRmSqlDatabaseGeoBackupPolicy</span></span>
  - <span data-ttu-id="7de50-158">Novos cmdlets adicionados para os Assistentes do Sql Azure e APIs de Ações Recomendadas</span><span class="sxs-lookup"><span data-stu-id="7de50-158">Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs</span></span>
    + <span data-ttu-id="7de50-159">Get-AzureRmSqlDatabaseAdvisor</span><span class="sxs-lookup"><span data-stu-id="7de50-159">Get-AzureRmSqlDatabaseAdvisor</span></span>
    + <span data-ttu-id="7de50-160">Get-AzureRmSqlElasticPoolAdvisor</span><span class="sxs-lookup"><span data-stu-id="7de50-160">Get-AzureRmSqlElasticPoolAdvisor</span></span>
    + <span data-ttu-id="7de50-161">Get-AzureRmSqlServerAdvisor</span><span class="sxs-lookup"><span data-stu-id="7de50-161">Get-AzureRmSqlServerAdvisor</span></span>
    + <span data-ttu-id="7de50-162">Get-AzureRmSqlDatabaseRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="7de50-162">Get-AzureRmSqlDatabaseRecommendedActions</span></span>
    + <span data-ttu-id="7de50-163">Get-AzureRmSqlElasticPoolRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="7de50-163">Get-AzureRmSqlElasticPoolRecommendedActions</span></span>
    + <span data-ttu-id="7de50-164">Get-AzureRmSqlServerRecommendedActions</span><span class="sxs-lookup"><span data-stu-id="7de50-164">Get-AzureRmSqlServerRecommendedActions</span></span>
    + <span data-ttu-id="7de50-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="7de50-165">Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="7de50-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="7de50-166">Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="7de50-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span><span class="sxs-lookup"><span data-stu-id="7de50-167">Set-AzureRmSqlServerAdvisorAutoExecuteStatus</span></span>
    + <span data-ttu-id="7de50-168">Set-AzureRmSqlDatabaseRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="7de50-168">Set-AzureRmSqlDatabaseRecommendedActionState</span></span>
    + <span data-ttu-id="7de50-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="7de50-169">Set-AzureRmSqlElasticPoolRecommendedActionState</span></span>
    + <span data-ttu-id="7de50-170">Set-AzureRmSqlServerRecommendedActionState</span><span class="sxs-lookup"><span data-stu-id="7de50-170">Set-AzureRmSqlServerRecommendedActionState</span></span>
