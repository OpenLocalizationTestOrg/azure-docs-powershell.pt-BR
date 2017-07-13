---
title: "Log de Alterações do Azure PowerShell | Microsoft Docs"
description: "É um histórico das alterações feitas na versão mais recente do Azure PowerShell."
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-resource-manager
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload: 
ms.date: 05/18/2017
ms.openlocfilehash: 5c8fa2a5a8f94cd24b66f42c237749a7b89af3b3
ms.sourcegitcommit: 226527be7cb647acfe2ea9ab151185053ab3c6db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2017
---
# <span data-ttu-id="c353b-103">Notas de versão</span><span class="sxs-lookup"><span data-stu-id="c353b-103">Release notes</span></span>
<a id="release-notes" class="xliff"></a>

<span data-ttu-id="c353b-104">É uma lista das alterações feitas nesta versão do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c353b-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <span data-ttu-id="c353b-105">Versão 4.0.0</span><span class="sxs-lookup"><span data-stu-id="c353b-105">Version 4.0.0</span></span>
<a id="version-400" class="xliff"></a>

* <span data-ttu-id="c353b-106">Esta versão contém alterações de última hora.</span><span class="sxs-lookup"><span data-stu-id="c353b-106">This release contains breaking changes.</span></span> <span data-ttu-id="c353b-107">Consulte o [guia de migração](https://aka.ms/azps-migration-guide) para obter os detalhes de alteração e saber o impacto sobre os scripts existentes.</span><span class="sxs-lookup"><span data-stu-id="c353b-107">Please see [the migration guide](https://aka.ms/azps-migration-guide) for change details and the impact on existing scripts.</span></span>
* <span data-ttu-id="c353b-108">ApiManagement</span><span class="sxs-lookup"><span data-stu-id="c353b-108">ApiManagement</span></span>
  - <span data-ttu-id="c353b-109">Suporte adicionado para configurar grupos externos no New-AzureRmApiManagementGroup.</span><span class="sxs-lookup"><span data-stu-id="c353b-109">Added support for configuring external groups in New-AzureRmApiManagementGroup.</span></span>
* <span data-ttu-id="c353b-110">Cobrança</span><span class="sxs-lookup"><span data-stu-id="c353b-110">Billing</span></span>
  - <span data-ttu-id="c353b-111">Novo cmdlet Get-AzureRmBillingPeriod</span><span class="sxs-lookup"><span data-stu-id="c353b-111">New Cmdlet Get-AzureRmBillingPeriod</span></span>
    + <span data-ttu-id="c353b-112">Cmdlet para recuperar períodos de cobrança de assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="c353b-112">cmdlet to retrieve azure billing periods of the subscription.</span></span>
  - <span data-ttu-id="c353b-113">Atualizar o cmdlet Get-AzureRmBillingInvoice</span><span class="sxs-lookup"><span data-stu-id="c353b-113">Update Cmdlet Get-AzureRmBillingInvoice</span></span>
  - <span data-ttu-id="c353b-114">nova propriedade BillingPeriodNames</span><span class="sxs-lookup"><span data-stu-id="c353b-114">new property BillingPeriodNames</span></span>
  - <span data-ttu-id="c353b-115">saída em modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="c353b-115">output in list view</span></span>
* <span data-ttu-id="c353b-116">Computação</span><span class="sxs-lookup"><span data-stu-id="c353b-116">Compute</span></span>
  - <span data-ttu-id="c353b-117">Os cmdlets atualizados AzureRmVMAEMExtension e Test-AzureRmVMAEMExtension oferecem suporte ao Managed Disks Premium</span><span class="sxs-lookup"><span data-stu-id="c353b-117">Updated Set-AzureRmVMAEMExtension and Test-AzureRmVMAEMExtension cmdlets to support Premium managed disks</span></span>
  - <span data-ttu-id="c353b-118">Configurações de criptografia de backup para VMs de IaaS e restauração em caso de falha</span><span class="sxs-lookup"><span data-stu-id="c353b-118">Backup encryption settings for IaaS VMs and restore on failure</span></span>
  - <span data-ttu-id="c353b-119">A opção ChefServiceInterval foi renomeada como ChefDaemonInterval.</span><span class="sxs-lookup"><span data-stu-id="c353b-119">ChefServiceInterval option is renamed to ChefDaemonInterval now.</span></span> <span data-ttu-id="c353b-120">No entanto, a antiga opção continuará funcionando.</span><span class="sxs-lookup"><span data-stu-id="c353b-120">Old one will continue to work however.</span></span>
  - <span data-ttu-id="c353b-121">Remover as propriedades duplicadas DataDiskNames e NetworkInterfaceIDs do objeto PS da VM.</span><span class="sxs-lookup"><span data-stu-id="c353b-121">Remove duplicated DataDiskNames and NetworkInterfaceIDs properties from PS VM object.</span></span>
  - <span data-ttu-id="c353b-122">Tornar os parâmetros DataDiskNames e NetworkInterfaceIDs opcionais em Remove-AzureRmVMDataDisk e Remove-AzureRmVMNetworkInterface, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c353b-122">Make DataDiskNames and NetworkInterfaceIDs parameters optional in Remove-AzureRmVMDataDisk and Remove-AzureRmVMNetworkInterface, respectively.</span></span>
  - <span data-ttu-id="c353b-123">Corrigir o problema de direcionamento dos cmdlets Get quando eles retornarem um objeto de lista.</span><span class="sxs-lookup"><span data-stu-id="c353b-123">Fix the piping issue of Get cmdlets when the Get cmdlets return a list object.</span></span>
  - <span data-ttu-id="c353b-124">Os cmdlets que entraram em conflito com os cmdlets RDFE foram renomeados.</span><span class="sxs-lookup"><span data-stu-id="c353b-124">Cmdlets that conflicted with RDFE cmdlets have been renamed.</span></span> <span data-ttu-id="c353b-125">Consulte o problema em https://github.com/Azure/azure-powershell/issues/2917 para obter mais detalhes</span><span class="sxs-lookup"><span data-stu-id="c353b-125">See issue https://github.com/Azure/azure-powershell/issues/2917 for more details</span></span>
    + <span data-ttu-id="c353b-126">`New-AzureVMSqlServerAutoBackupConfig` foi renomeado para `New-AzureRmVMSqlServerAutoBackupConfig`</span><span class="sxs-lookup"><span data-stu-id="c353b-126">`New-AzureVMSqlServerAutoBackupConfig` has been renamed to `New-AzureRmVMSqlServerAutoBackupConfig`</span></span>
    + <span data-ttu-id="c353b-127">`New-AzureVMSqlServerAutoPatchingConfig` foi renomeado para `New-AzureRmVMSqlServerAutoPatchingConfig`</span><span class="sxs-lookup"><span data-stu-id="c353b-127">`New-AzureVMSqlServerAutoPatchingConfig` has been renamed to `New-AzureRmVMSqlServerAutoPatchingConfig`</span></span>
    + <span data-ttu-id="c353b-128">`New-AzureVMSqlServerKeyVaultCredentialConfig` foi renomeado para `New-AzureRmVMSqlServerKeyVaultCredentialConfig`</span><span class="sxs-lookup"><span data-stu-id="c353b-128">`New-AzureVMSqlServerKeyVaultCredentialConfig` has been renamed to `New-AzureRmVMSqlServerKeyVaultCredentialConfig`</span></span>
* <span data-ttu-id="c353b-129">Consumo</span><span class="sxs-lookup"><span data-stu-id="c353b-129">Consumption</span></span>
  - <span data-ttu-id="c353b-130">Novo cmdlet Get-AzureRmConsumptionUsageDetail</span><span class="sxs-lookup"><span data-stu-id="c353b-130">New Cmdlet Get-AzureRmConsumptionUsageDetail</span></span>
    + <span data-ttu-id="c353b-131">Cmdlet para recuperar detalhes de uso da assinatura.</span><span class="sxs-lookup"><span data-stu-id="c353b-131">cmdlet to retrieve usage details of the subscription.</span></span>
* <span data-ttu-id="c353b-132">ContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="c353b-132">ContainerRegistry</span></span>
  - <span data-ttu-id="c353b-133">Adicionar cmdlets do PowerShell ao Registro de Contêiner do Azure</span><span class="sxs-lookup"><span data-stu-id="c353b-133">Add PowerShell cmdlets for Azure Container Registry</span></span>
    + <span data-ttu-id="c353b-134">New-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="c353b-134">New-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="c353b-135">Get-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="c353b-135">Get-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="c353b-136">Update-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="c353b-136">Update-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="c353b-137">Remove-AzureRmContainerRegistry</span><span class="sxs-lookup"><span data-stu-id="c353b-137">Remove-AzureRmContainerRegistry</span></span>
    + <span data-ttu-id="c353b-138">Get-AzureRmContainerRegistryCredential</span><span class="sxs-lookup"><span data-stu-id="c353b-138">Get-AzureRmContainerRegistryCredential</span></span>
    + <span data-ttu-id="c353b-139">Update-AzureRmContainerRegistryCredential</span><span class="sxs-lookup"><span data-stu-id="c353b-139">Update-AzureRmContainerRegistryCredential</span></span>
    + <span data-ttu-id="c353b-140">Test-AzureRmContainerRegistryNameAvailability</span><span class="sxs-lookup"><span data-stu-id="c353b-140">Test-AzureRmContainerRegistryNameAvailability</span></span>
* <span data-ttu-id="c353b-141">DataLakeAnalytics</span><span class="sxs-lookup"><span data-stu-id="c353b-141">DataLakeAnalytics</span></span>
  - <span data-ttu-id="c353b-142">Adicionar suporte aos pacotes de catálogo get e list</span><span class="sxs-lookup"><span data-stu-id="c353b-142">Add support for catalog package get and list</span></span>
  - <span data-ttu-id="c353b-143">Adicionar suporte à listagem dos seguintes itens de catálogo de ancestrais mais antigos:</span><span class="sxs-lookup"><span data-stu-id="c353b-143">Add support for listing the following catalog items from deeper ancestors:</span></span>
    + <span data-ttu-id="c353b-144">Tabela</span><span class="sxs-lookup"><span data-stu-id="c353b-144">Table</span></span>
    + <span data-ttu-id="c353b-145">TVF</span><span class="sxs-lookup"><span data-stu-id="c353b-145">TVF</span></span>
    + <span data-ttu-id="c353b-146">Visualizar</span><span class="sxs-lookup"><span data-stu-id="c353b-146">View</span></span>
    + <span data-ttu-id="c353b-147">Estatísticas</span><span class="sxs-lookup"><span data-stu-id="c353b-147">Statistics</span></span>
* <span data-ttu-id="c353b-148">DataLakeStore</span><span class="sxs-lookup"><span data-stu-id="c353b-148">DataLakeStore</span></span>
  - <span data-ttu-id="c353b-149">O registro de rastreamento de `Import-AzureRMDataLakeStoreItem` e `Export-AzureRMDataLakeStoreItem` foi desabilitado por padrão para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="c353b-149">For `Import-AzureRMDataLakeStoreItem` and `Export-AzureRMDataLakeStoreItem` trace logging has been disabled by default to improve performance.</span></span> <span data-ttu-id="c353b-150">Caso registro de rastreamento seja desejável, utilize os parâmetros `-DiagnosticLogLevel` e `-DiagnosticLogPath`</span><span class="sxs-lookup"><span data-stu-id="c353b-150">If trace logging is desired please use the `-DiagnosticLogLevel` and `-DiagnosticLogPath` parameters</span></span>
  - <span data-ttu-id="c353b-151">O bug que ocasionalmente fazia com que o PowerShell falhasse ao fazer o upload de vários arquivos pequenos para o ADLS foi corrigido.</span><span class="sxs-lookup"><span data-stu-id="c353b-151">Fixed a bug that would sometimes cause PowerShell to crash when uploading lots of small file to ADLS.</span></span>
* <span data-ttu-id="c353b-152">EventHub</span><span class="sxs-lookup"><span data-stu-id="c353b-152">EventHub</span></span>
  - <span data-ttu-id="c353b-153">Correção de bug:</span><span class="sxs-lookup"><span data-stu-id="c353b-153">Bug fix :</span></span>
    + <span data-ttu-id="c353b-154">Correção do erro do cmdlet Set-AzureRmEventHubNamespace – 'Tier' não pode ser null, quando deve ser 'SkuName'</span><span class="sxs-lookup"><span data-stu-id="c353b-154">Fix for Set-AzureRmEventHubNamespace cmdlet error  - 'Tier' cannot be null, where it should be 'SkuName'</span></span>
    + <span data-ttu-id="c353b-155">Set-AzureRmEventHub – Correção do erro “A referência do objeto não está definida como uma instância de um objeto” ao atualizar o EventHub</span><span class="sxs-lookup"><span data-stu-id="c353b-155">Set-AzureRmEventHub - Fix 'Object reference not set to an instance of an object' error while updating EventHub</span></span>
* <span data-ttu-id="c353b-156">Insights</span><span class="sxs-lookup"><span data-stu-id="c353b-156">Insights</span></span>
  - <span data-ttu-id="c353b-157">Add-AzureRm*AlertRule</span><span class="sxs-lookup"><span data-stu-id="c353b-157">Add-AzureRm*AlertRule</span></span>
    + <span data-ttu-id="c353b-158">Retorna um único objeto: newResource, statusCode, requestId</span><span class="sxs-lookup"><span data-stu-id="c353b-158">Returns a single object: newResource, statusCode, requestId</span></span>
  - <span data-ttu-id="c353b-159">Get-AzureRmAlertRule</span><span class="sxs-lookup"><span data-stu-id="c353b-159">Get-AzureRmAlertRule</span></span>
    + <span data-ttu-id="c353b-160">Agora, a saída é numerada, em vez de considerada um único objeto.</span><span class="sxs-lookup"><span data-stu-id="c353b-160">The output is now enumerated instead of considered a single object.</span></span> <span data-ttu-id="c353b-161">O tipo não foi alterado, ainda é uma lista.</span><span class="sxs-lookup"><span data-stu-id="c353b-161">Its type did not change, it is still a list.</span></span>
  - <span data-ttu-id="c353b-162">Remove-AzureRmAlertRule</span><span class="sxs-lookup"><span data-stu-id="c353b-162">Remove-AzureRmAlertRule</span></span>
    + <span data-ttu-id="c353b-163">O statusCode segue o código de status retornado pela solicitação, antes era sempre Ok.</span><span class="sxs-lookup"><span data-stu-id="c353b-163">The statusCode follows the status code returned by the request, before it was Ok always.</span></span>
  - <span data-ttu-id="c353b-164">Add-AzureRmAutoscaleSetting</span><span class="sxs-lookup"><span data-stu-id="c353b-164">Add-AzureRmAutoscaleSetting</span></span>
    + <span data-ttu-id="c353b-165">Agora, retorna um objeto único (e não uma lista, como antes) que contém statusCode, requestId e o recurso criado/atualizado recentemente.</span><span class="sxs-lookup"><span data-stu-id="c353b-165">Returns now a single object (not a list as before) containing statusCode, requestId, and the newly created/updated resource.</span></span>
    + <span data-ttu-id="c353b-166">O código de status segue o status retornado pela solicitação, antes era sempre Ok.</span><span class="sxs-lookup"><span data-stu-id="c353b-166">The status code follows the status returned by the request, before it was always Ok.</span></span>
  - <span data-ttu-id="c353b-167">New-AzureRmAutoscaleRule</span><span class="sxs-lookup"><span data-stu-id="c353b-167">New-AzureRmAutoscaleRule</span></span>
    + <span data-ttu-id="c353b-168">O parâmetro ScaleActionType foi estendido e agora recebe os seguintes valores: ChangeCount, PercentChangeCount e ExactCount.</span><span class="sxs-lookup"><span data-stu-id="c353b-168">The parameter ScaleActionType has been extended, it receives the following values now: ChangeCount, PercentChangeCount, ExactCount.</span></span>
  - <span data-ttu-id="c353b-169">Remove-AzureRmAutoscaleSetting</span><span class="sxs-lookup"><span data-stu-id="c353b-169">Remove-AzureRmAutoscaleSetting</span></span>
    + <span data-ttu-id="c353b-170">O statusCode na saída segue o statusCode retornado pela solicitação.</span><span class="sxs-lookup"><span data-stu-id="c353b-170">The statusCode in the output follows the statusCode returned by the request.</span></span> <span data-ttu-id="c353b-171">Antes, era sempre Ok.</span><span class="sxs-lookup"><span data-stu-id="c353b-171">Before it was always Ok.</span></span>
  - <span data-ttu-id="c353b-172">Get-AzureRMLogProfile</span><span class="sxs-lookup"><span data-stu-id="c353b-172">Get-AzureRMLogProfile</span></span>
    + <span data-ttu-id="c353b-173">Agora, a saída é enumerada.</span><span class="sxs-lookup"><span data-stu-id="c353b-173">The output is now enumerated.</span></span> <span data-ttu-id="c353b-174">Antes, ela era considerada um objeto único.</span><span class="sxs-lookup"><span data-stu-id="c353b-174">Before it was considered a single object.</span></span> <span data-ttu-id="c353b-175">O tipo da saída ainda é uma lista, como antes.</span><span class="sxs-lookup"><span data-stu-id="c353b-175">The type of the output remains a list as before.</span></span>
  - <span data-ttu-id="c353b-176">Remove-AzureRmLogProfile</span><span class="sxs-lookup"><span data-stu-id="c353b-176">Remove-AzureRmLogProfile</span></span>
    + <span data-ttu-id="c353b-177">O parâmetro PassThru foi implementado.</span><span class="sxs-lookup"><span data-stu-id="c353b-177">The PassThru parameter has been implemented.</span></span>
  - <span data-ttu-id="c353b-178">API de Métrica</span><span class="sxs-lookup"><span data-stu-id="c353b-178">Metrics API</span></span>
    + <span data-ttu-id="c353b-179">Agora, o SDK recupera métrica do MDM.</span><span class="sxs-lookup"><span data-stu-id="c353b-179">The SDK now retrieves metrics from MDM.</span></span>
  - <span data-ttu-id="c353b-180">Get-AzureRmMetricDefinition</span><span class="sxs-lookup"><span data-stu-id="c353b-180">Get-AzureRmMetricDefinition</span></span>
    + <span data-ttu-id="c353b-181">A saída ainda é uma lista, mas a estrutura dessa lista foi alterada.</span><span class="sxs-lookup"><span data-stu-id="c353b-181">The output is still a list, but the structure of the list changed.</span></span>
  - <span data-ttu-id="c353b-182">Get-AzureRmMetric</span><span class="sxs-lookup"><span data-stu-id="c353b-182">Get-AzureRmMetric</span></span>
    + <span data-ttu-id="c353b-183">A chamada foi alterada.</span><span class="sxs-lookup"><span data-stu-id="c353b-183">The call has changed.</span></span> <span data-ttu-id="c353b-184">Esta é a nova sintaxe: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]</span><span class="sxs-lookup"><span data-stu-id="c353b-184">This is the new syntax: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]</span></span>
    + <span data-ttu-id="c353b-185">A saída é uma lista e a estrutura de seus elementos foi alterada.</span><span class="sxs-lookup"><span data-stu-id="c353b-185">The output is a list, and the structure of its elements has changed.</span></span>
* <span data-ttu-id="c353b-186">KeyVault</span><span class="sxs-lookup"><span data-stu-id="c353b-186">KeyVault</span></span>
  - <span data-ttu-id="c353b-187">Adicionar suporte de backup/restauração aos segredos do KeyVault</span><span class="sxs-lookup"><span data-stu-id="c353b-187">Adding backup/restore support for KeyVault secrets</span></span>
    + <span data-ttu-id="c353b-188">É possível fazer backup e restaurar os segredos, de acordo com a funcionalidade que dá suporte para as Chaves atualmente</span><span class="sxs-lookup"><span data-stu-id="c353b-188">Secrets can be backed up and restored, matching the functionality currently supported for Keys</span></span>

  - <span data-ttu-id="c353b-189">Os cmdlets de backup para Chaves e Segredos agora aceitam um objeto correspondente como um parâmetro de entrada</span><span class="sxs-lookup"><span data-stu-id="c353b-189">Backup cmdlets for Keys and Secrets now accept a corresponding object as an input parameter</span></span>
    + <span data-ttu-id="c353b-190">O chamador pode encadear operações de backup e recuperação: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey</span><span class="sxs-lookup"><span data-stu-id="c353b-190">The caller may chain retrieval and backup operations: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey</span></span>

  - <span data-ttu-id="c353b-191">Agora, os cmdlets de backup oferecem suporte a um comutador -Force para substituir um arquivo existente</span><span class="sxs-lookup"><span data-stu-id="c353b-191">Backup cmdlets now support a -Force switch to overwrite an existing file</span></span>
    + <span data-ttu-id="c353b-192">Observe que a tentativa de substituir um arquivo existente não lançará mais e, em vez disso, solicitará que o usuário escolha como proceder.</span><span class="sxs-lookup"><span data-stu-id="c353b-192">Note that attempting to overwrite an existing file will no longer throw, and will instead prompt the user for a choice on how to proceed.</span></span>
* <span data-ttu-id="c353b-193">LogicApp</span><span class="sxs-lookup"><span data-stu-id="c353b-193">LogicApp</span></span>
  - <span data-ttu-id="c353b-194">Novos parâmetros para os cmdlets de recuperação de desastre de Número de Controle de Intercâmbio:</span><span class="sxs-lookup"><span data-stu-id="c353b-194">New parameters for Interchange Control Number disaster recovery cmdlets:</span></span>
    + <span data-ttu-id="c353b-195">Parâmetro opcional -AgreementType (“X12” ou “Edifact”) para especificar os números de controle relevantes</span><span class="sxs-lookup"><span data-stu-id="c353b-195">Optional -AgreementType parameter ("X12", or "Edifact") to specify the relevant control numbers</span></span>
* <span data-ttu-id="c353b-196">MachineLearning</span><span class="sxs-lookup"><span data-stu-id="c353b-196">MachineLearning</span></span>
  - <span data-ttu-id="c353b-197">Use a nova versão do SDK .Net do Azure Machine Learning e adicione um novo cmdlet</span><span class="sxs-lookup"><span data-stu-id="c353b-197">Consume new version of Azure Machine Learning .Net SDK and add a new cmdlet</span></span>
    + <span data-ttu-id="c353b-198">Add-AzureRmMlWebServiceRegionalProperty</span><span class="sxs-lookup"><span data-stu-id="c353b-198">Add-AzureRmMlWebServiceRegionalProperty</span></span>
  - <span data-ttu-id="c353b-199">Pequenas correções de palavras no texto de ajuda.</span><span class="sxs-lookup"><span data-stu-id="c353b-199">Minor wording fixes in help text.</span></span>
* <span data-ttu-id="c353b-200">Rede</span><span class="sxs-lookup"><span data-stu-id="c353b-200">Network</span></span>
  - <span data-ttu-id="c353b-201">Cmdlet Test-AzureRmNetworkWatcherConnectivity</span><span class="sxs-lookup"><span data-stu-id="c353b-201">Added Test-AzureRmNetworkWatcherConnectivity cmdlet</span></span>
    + <span data-ttu-id="c353b-202">Retorna informações de conectividade para uma VM de origem especificada e um destino</span><span class="sxs-lookup"><span data-stu-id="c353b-202">Returns connectivity information for a specified source VM and a destination</span></span>
    + <span data-ttu-id="c353b-203">Se a conectividade entre a origem e o destino não puder ser estabelecida, o cmdlet retornará detalhes sobre o problema</span><span class="sxs-lookup"><span data-stu-id="c353b-203">If connectivity between the source and destination cannot be established, the cmdlet returns details about the issue</span></span>
* <span data-ttu-id="c353b-204">Perfil</span><span class="sxs-lookup"><span data-stu-id="c353b-204">Profile</span></span>
  - <span data-ttu-id="c353b-205">O cmdlet Send-Feedback adicionado: permite que o usuário inicie um conjunto de prompts que enviam comentários à equipe do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c353b-205">Added \`Send-Feedback' cmdlet: allows a user to initiate a set of prompts which sends feedback to the Azure PowerShell team.</span></span>
  - <span data-ttu-id="c353b-206">Os aliases a seguir foram removidos, pois entravam em conflito com os nomes de cmdlet existentes no módulo do Azure:</span><span class="sxs-lookup"><span data-stu-id="c353b-206">The following aliases have been removed as they conflicted with existing cmdlet names in the Azure module:</span></span>
    + <span data-ttu-id="c353b-207">`Enable-AzureDataCollection` (com suporte de `Enable-AzureRmDataCollection`)</span><span class="sxs-lookup"><span data-stu-id="c353b-207">`Enable-AzureDataCollection` (supported by `Enable-AzureRmDataCollection`)</span></span>
    + <span data-ttu-id="c353b-208">`Disable-AzureDataCollection` (com suporte de `Disable-AzureRmDataCollection`)</span><span class="sxs-lookup"><span data-stu-id="c353b-208">`Disable-AzureDataCollection` (supported by `Disable-AzureRmDataCollection`)</span></span>
* <span data-ttu-id="c353b-209">Retransmissão</span><span class="sxs-lookup"><span data-stu-id="c353b-209">Relay</span></span>
  - <span data-ttu-id="c353b-210">Adiciona cmdlets à Retransmissão do Azure, o que permite que os usuários criem e gerenciem todos os recursos da Retransmissão do Azure.</span><span class="sxs-lookup"><span data-stu-id="c353b-210">Adds cmdlets for the Azure Relay which allows users to create and manage all Azure Relay resources.</span></span>
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* <span data-ttu-id="c353b-211">Recursos</span><span class="sxs-lookup"><span data-stu-id="c353b-211">Resources</span></span>
  - <span data-ttu-id="c353b-212">Suporte para implantações de grupo de recursos cruzados do New-AzureRmResourceGroupDeployment</span><span class="sxs-lookup"><span data-stu-id="c353b-212">Support cross-resource-group deployments for New-AzureRmResourceGroupDeployment</span></span>
    + <span data-ttu-id="c353b-213">Agora, os usuários podem usar implantações aninhadas para implantar grupos de recursos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c353b-213">Users can now use nested deployments to deploy to different resource groups.</span></span>
* <span data-ttu-id="c353b-214">ServiceBus</span><span class="sxs-lookup"><span data-stu-id="c353b-214">ServiceBus</span></span>

  - <span data-ttu-id="c353b-215">Correção de bug: Os valores de propriedade do objeto de fila ServiceBus foram definidos como null, o objeto é utilizado como parâmetro de entrada no cmdlet Set-AzureRmServiceBusQueue para atualizar a fila.</span><span class="sxs-lookup"><span data-stu-id="c353b-215">Bug Fix: ServiceBus Queue object property values were set to null, the object is used as input parameter in Set-AzureRmServiceBusQueue cmdlet to update Queue.</span></span>
   - <span data-ttu-id="c353b-216">As propriedades afetadas são LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount e MessageCount</span><span class="sxs-lookup"><span data-stu-id="c353b-216">Properties affected are LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount and MessageCount</span></span>
* <span data-ttu-id="c353b-217">ServiceFabric</span><span class="sxs-lookup"><span data-stu-id="c353b-217">ServiceFabric</span></span>

  - <span data-ttu-id="c353b-218">Cmdlets adicionadas ao Service Fabric</span><span class="sxs-lookup"><span data-stu-id="c353b-218">Added cmdlets for service fabric</span></span>
    + <span data-ttu-id="c353b-219">Add-AzureRmServiceFabricApplicationCertificate Adiciona um certificado que será utilizado como certificado de aplicativo</span><span class="sxs-lookup"><span data-stu-id="c353b-219">Add-AzureRmServiceFabricApplicationCertificate       Add a certificate which will be used as application certificate</span></span>
    + <span data-ttu-id="c353b-220">Add-AzureRmServiceFabricClientCertificate Adiciona um nome comum ou impressão digital às configurações do cluster para a autenticação de cliente</span><span class="sxs-lookup"><span data-stu-id="c353b-220">Add-AzureRmServiceFabricClientCertificate       Add a common name or thumbprint to the cluster settings for client authentication</span></span>
    + <span data-ttu-id="c353b-221">Add-AzureRmServiceFabricClusterCertificate Adiciona um certificado de cluster secundário ao cluster a fim de sobrepor o certificado existente</span><span class="sxs-lookup"><span data-stu-id="c353b-221">Add-AzureRmServiceFabricClusterCertificate       Add a secondary cluster certificate to the cluster for rolling over the existing certificate</span></span>
    + <span data-ttu-id="c353b-222">Add-AzureRmServiceFabricNodes Adiciona nós/VMs de um tipo específico de nó a um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-222">Add-AzureRmServiceFabricNodes       Add nodes/VMs of a specific node type to a cluster</span></span>
    + <span data-ttu-id="c353b-223">Add-AzureRmServiceFabricNodeType Adiciona um tipo de nó/VMs a um cluster existente</span><span class="sxs-lookup"><span data-stu-id="c353b-223">Add-AzureRmServiceFabricNodeType       Add a node type/VMs to an existing cluster</span></span>
    + <span data-ttu-id="c353b-224">Get-AzureRmServiceFabricCluster       Obtém os detalhes do recurso do cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-224">Get-AzureRmServiceFabricCluster       Get the details of the cluster resource</span></span>
    + <span data-ttu-id="c353b-225">New-AzureRmServiceFabricCluster Cria um novo cluster ServiceFabric.</span><span class="sxs-lookup"><span data-stu-id="c353b-225">New-AzureRmServiceFabricCluster Create a new ServiceFabric cluster.</span></span> <span data-ttu-id="c353b-226">Esse comando tem muitas sobrecargas para cobrir vários cenários</span><span class="sxs-lookup"><span data-stu-id="c353b-226">This command has many overloads to cover various scenarios</span></span>
    + <span data-ttu-id="c353b-227">Remove-AzureRmServiceFabricClientCertificate       Impede que um certificado de cliente seja usado para acessar um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-227">Remove-AzureRmServiceFabricClientCertificate       Remove a client certificate from being used to access a cluster</span></span>
    + <span data-ttu-id="c353b-228">Remove-AzureRmServiceFabricClusterCertificate       Impede que um certificado de cluster seja usado para a segurança de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-228">Remove-AzureRmServiceFabricClusterCertificate       Remove a cluster certificate from being used for cluster security</span></span>
    + <span data-ttu-id="c353b-229">Remove-AzureRmServiceFabricNodes Remove nós de um tipo de nó específico de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-229">Remove-AzureRmServiceFabricNodes       Remove nodes from a specific node type from a cluster</span></span>
    + <span data-ttu-id="c353b-230">Remove-AzureRmServiceFabricNodeType       Remove um tipo de nó de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-230">Remove-AzureRmServiceFabricNodeType       Remove a node type from a cluster</span></span>
    + <span data-ttu-id="c353b-231">Remove-AzureRmServiceFabricSettings       Remove uma ou mais configurações do ServiceFabric de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-231">Remove-AzureRmServiceFabricSettings       Remove one or more ServiceFabric settings from a cluster</span></span>
    + <span data-ttu-id="c353b-232">Set-AzureRmServiceFabricSettings       Adiciona ou atualiza uma ou mais configurações do ServiceFabric de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-232">Set-AzureRmServiceFabricSettings       Add or update one or more ServiceFabric settings of a cluster</span></span>
    + <span data-ttu-id="c353b-233">Set-AzureRmServiceFabricUpgradeType Altera o tipo de atualização do ServiceFabric de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-233">Set-AzureRmServiceFabricUpgradeType       Change the ServiceFabric upgrade type of a cluster</span></span>
    + <span data-ttu-id="c353b-234">Update-AzureRmServiceFabricDurability Altera a camada de durabilidade de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-234">Update-AzureRmServiceFabricDurability       Change the durability tier of a cluster</span></span>
    + <span data-ttu-id="c353b-235">Update-AzureRmServiceFabricReliability Altera a camada de confiabilidade de um cluster</span><span class="sxs-lookup"><span data-stu-id="c353b-235">Update-AzureRmServiceFabricReliability       Change the reliability tier of a cluster</span></span>
* <span data-ttu-id="c353b-236">Sql</span><span class="sxs-lookup"><span data-stu-id="c353b-236">Sql</span></span>
  - <span data-ttu-id="c353b-237">Parâmetro -SampleName adicionado ao New-AzureRmSqlDatabase</span><span class="sxs-lookup"><span data-stu-id="c353b-237">Added -SampleName parameter to New-AzureRmSqlDatabase</span></span>
  - <span data-ttu-id="c353b-238">Atualizações para os cmdlets de Grupo de Failover</span><span class="sxs-lookup"><span data-stu-id="c353b-238">Updates to Failover Group cmdlets</span></span>
  - <span data-ttu-id="c353b-239">Remover os parâmetros 'Tag'</span><span class="sxs-lookup"><span data-stu-id="c353b-239">Remove 'Tag' parameters</span></span>
  - <span data-ttu-id="c353b-240">Remover os parâmetros 'PartnerResourceGroupName' e 'PartnerServerName' do cmdlet Remove-AzureRmSqlDatabaseFailoverGroup</span><span class="sxs-lookup"><span data-stu-id="c353b-240">Remove 'PartnerResourceGroupName' and 'PartnerServerName' parameters from Remove-AzureRmSqlDatabaseFailoverGroup cmdlet</span></span>
  - <span data-ttu-id="c353b-241">Adicionar o parâmetro 'GracePeriodWithDataLossHours' aos cmdlets New- e Set-, que no devido tempo substituirão 'GracePeriodWithDataLossHour'</span><span class="sxs-lookup"><span data-stu-id="c353b-241">Add 'GracePeriodWithDataLossHours' parameter to New- and Set- cmdlets, which shall eventually replace 'GracePeriodWithDataLossHour'</span></span>
  - <span data-ttu-id="c353b-242">A documentação foi elaborada e atualizada</span><span class="sxs-lookup"><span data-stu-id="c353b-242">Documentation has been fleshed out and updated</span></span>
  - <span data-ttu-id="c353b-243">Alterar a formatação de objetos retornados e corrigir alguns bugs em que os campos nem sempre foram preenchidos</span><span class="sxs-lookup"><span data-stu-id="c353b-243">Change formatting of returned objects and fix some bugs where fields were not always populated</span></span>
  - <span data-ttu-id="c353b-244">Adicionar as propriedades 'DatabaseNames' e 'PartnerLocation' ao objeto Grupo de Failover</span><span class="sxs-lookup"><span data-stu-id="c353b-244">Add 'DatabaseNames' and 'PartnerLocation' properties to Failover Group object</span></span>
  - <span data-ttu-id="c353b-245">Corrigir o bug, fazendo com que o cmdlet Switch- retorne imediatamente, em vez de aguardar a conclusão da operação</span><span class="sxs-lookup"><span data-stu-id="c353b-245">Fix bug causing Switch- cmdlet to return immediately rather than waiting for operation to complete</span></span>
  - <span data-ttu-id="c353b-246">Corrigir o bug de estouro do inteiro quando os valores do período de carência forem utilizados</span><span class="sxs-lookup"><span data-stu-id="c353b-246">Fix integer overflow bug when high grace period values are used</span></span>
  - <span data-ttu-id="c353b-247">Ajustar o período de carência para um mínimo de 1 hora se um valor menor for fornecido</span><span class="sxs-lookup"><span data-stu-id="c353b-247">Adjust grace period to a minimum of 1 hour if a lower one is provided</span></span>
  - <span data-ttu-id="c353b-248">Remover "Usage_Anomaly" dos valores aceitos do parâmetro "ExcludedDetectionType" dos cmdlets Set-AzureRmSqlDatabaseThreatDetectionPolicy e Set-AzureRmSqlServerThreatDetectionPolicy.</span><span class="sxs-lookup"><span data-stu-id="c353b-248">Remove "Usage_Anomaly" from the accepted values for "ExcludedDetectionType" parameter of Set-AzureRmSqlDatabaseThreatDetectionPolicy cmdlet and Set-AzureRmSqlServerThreatDetectionPolicy cmdlet.</span></span>
* <span data-ttu-id="c353b-249">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="c353b-249">Storage</span></span>
  - <span data-ttu-id="c353b-250">Atualizar o SDK da política SRP para 6.3.0</span><span class="sxs-lookup"><span data-stu-id="c353b-250">Upgrade SRP SDK to 6.3.0</span></span>
  - <span data-ttu-id="c353b-251">New/Set-AzureRmStorageAccount: Adicionar um novo parâmetro com suporte para EnableHttpsTrafficOnly</span><span class="sxs-lookup"><span data-stu-id="c353b-251">New/Set-AzureRmStorageAccount:Add a new parameter to support EnableHttpsTrafficOnly</span></span>
  - <span data-ttu-id="c353b-252">New/Set/Get-AzureRmStorageAccount: A conta de armazenamento retornada contém um novo atributo EnableHttpsTrafficOnly</span><span class="sxs-lookup"><span data-stu-id="c353b-252">New/Set/Get-AzureRmStorageAccount: Returned Storage Account contains a new attribute EnableHttpsTrafficOnly</span></span>
* <span data-ttu-id="c353b-253">Azure.Storage</span><span class="sxs-lookup"><span data-stu-id="c353b-253">Azure.Storage</span></span>
  - <span data-ttu-id="c353b-254">Atualizar para a Biblioteca do Cliente do Armazenamento do Azure 8.1.1 e Biblioteca de Movimentação de Dados do Armazenamento do Azure 0.5.1</span><span class="sxs-lookup"><span data-stu-id="c353b-254">Upgrade to Azure Storage Client Library 8.1.1 and Azure Storage DataMovement Library 0.5.1</span></span>
  - <span data-ttu-id="c353b-255">Adicionar um novo cmdlet para oferecer suporte ao recurso de Cópia Incremental do blob</span><span class="sxs-lookup"><span data-stu-id="c353b-255">Add a new cmdlet to support blob Incremental Copy feature</span></span>