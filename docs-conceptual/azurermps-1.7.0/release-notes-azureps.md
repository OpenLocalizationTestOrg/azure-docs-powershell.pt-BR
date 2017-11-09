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
ms.openlocfilehash: 0a3f152751fee569d3ac5fba6bcff8c1737f7b8c
ms.sourcegitcommit: b256bf48e15ee98865de0fae50e7b81878b03a54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2017
---
# <a name="release-notes"></a><span data-ttu-id="48b84-103">Notas de versão</span><span class="sxs-lookup"><span data-stu-id="48b84-103">Release notes</span></span>

<span data-ttu-id="48b84-104">É uma lista das alterações feitas nesta versão do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b84-104">This is a list of changes made to Azure PowerShell in this release.</span></span>

## <a name="version-170"></a><span data-ttu-id="48b84-105">Versão 1.7.0</span><span class="sxs-lookup"><span data-stu-id="48b84-105">Version 1.7.0</span></span>

* <span data-ttu-id="48b84-106">**Alteração de comportamento para os parâmetros -Force, -Confirm e $ConfirmPreference de todos os cmdlets. Estamos alterando essa implementação para estar alinhada com as diretrizes do PowerShell. Para a maioria dos cmdlets, isso significa remover o parâmetro Force e ignorar o prompt ShouldProcess. Os usuários precisarão incluir o parâmetro ‘-Confirm:$false’ em seus scripts do PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="48b84-106">**Behavioral change for -Force, –Confirm and $ConfirmPreference parameters for all cmdlets. We are changing this implementation to be in line with PowerShell guidelines. For most cmdlets, this means removing the Force parameter and to skip the ShouldProcess prompt, users will need to include the parameter: ‘-Confirm:$false’ in their PowerShell scripts.**</span></span> <span data-ttu-id="48b84-107">Essas alterações estão abordando os seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="48b84-107">This changes are addressing following issues:</span></span>
  - <span data-ttu-id="48b84-108">implementação correta da funcionalidade –WhatIf, que permite ao usuário determinar os efeitos de um cmdlet ou script sem fazer nenhuma alteração real</span><span class="sxs-lookup"><span data-stu-id="48b84-108">Correct implementation of –WhatIf functionality, allowing a user to determine the effects of a cmdlet or script without making any actual changes</span></span>
  - <span data-ttu-id="48b84-109">controle sobre a solicitação usando um $ConfirmPreference de toda a sessão, para que o usuário seja solicitado com base no impacto de uma alteração em potencial (conforme relatado na configuração ConfirmImpact no cmdlet)</span><span class="sxs-lookup"><span data-stu-id="48b84-109">Control over prompting using a session-wide $ConfirmPreference, so that the user is prompted based on the impact of a prospective change (as reported in the ConfirmImpact setting in the cmdlet)</span></span>
  - <span data-ttu-id="48b84-110">controle específico do cmdlet sobre as solicitações de confirmação usando o parâmetro –Confirm</span><span class="sxs-lookup"><span data-stu-id="48b84-110">Cmdlet-specific control over confirmation prompts using the –Confirm parameter</span></span>
  - <span data-ttu-id="48b84-111">uso consistente de ShouldContinue e do parâmetro –Force nos cmdlets, apenas para as ações que exigem solicitar ao usuário devido à natureza especial das alterações (por exemplo, exclusão de arquivos ocultos)</span><span class="sxs-lookup"><span data-stu-id="48b84-111">Consistent use of ShouldContinue and the –Force parameter across cmdlets, for only those actions that would require prompting from the user due to the special nature of the changes (for example, deleting hidden files)</span></span>
  - <span data-ttu-id="48b84-112">consistência com outros cmdlets do PowerShell, para que esse conhecimento de script do PowerShell em relação a outros cmdlets seja imediatamente aplicável aos cmdlets do Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48b84-112">Consistency with other PowerShell cmdlets, so that PowerShell scripting knowledge from other cmdlets is immediately applicable to the Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="48b84-113">**Observe que agora para ignorar *automaticamente todas as Solicitações em todas as Circunstâncias*, os cmdlets do Azure PowerShell exigem que o usuário forneça dois parâmetros:**</span><span class="sxs-lookup"><span data-stu-id="48b84-113">**Notice that now to *automatically skip all Prompts in all Circumstances* Azure PowerShell cmdlets require the user to supply two parameters:**</span></span>
```powershell
My-CmdletWithConfirmation –Confirm:$false -Force
```
* <span data-ttu-id="48b84-114">Computação do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-114">Azure Compute</span></span>
  - <span data-ttu-id="48b84-115">Set-AzureRmVMADDomainExtension</span><span class="sxs-lookup"><span data-stu-id="48b84-115">Set-AzureRmVMADDomainExtension</span></span>
  - <span data-ttu-id="48b84-116">Get-AzureRmVMADDomainExtension</span><span class="sxs-lookup"><span data-stu-id="48b84-116">Get-AzureRmVMADDomainExtension</span></span>
  - <span data-ttu-id="48b84-117">Parâmetro -Redeploy de Restart-AzureVM</span><span class="sxs-lookup"><span data-stu-id="48b84-117">-Redeploy parameter for Restart-AzureVM</span></span>
  - <span data-ttu-id="48b84-118">Parâmetro -Validate para Move-AzureService, Move-AzureStorageAccount, e Move-AzureVirtualNetwork</span><span class="sxs-lookup"><span data-stu-id="48b84-118">-Validate parameter for Move-AzureService, Move-AzureStorageAccount, and Move-AzureVirtualNetwork</span></span>
  - <span data-ttu-id="48b84-119">Os parâmetros name e version dos cmdlets de extensão são opcionais como antes.</span><span class="sxs-lookup"><span data-stu-id="48b84-119">Name and version parameters for extension cmdlets are optional as before.</span></span>
  - <span data-ttu-id="48b84-120">New-AzureVM pode obter um tipo de licença no objeto de VM.</span><span class="sxs-lookup"><span data-stu-id="48b84-120">New-AzureVM can get a license type from VM object.</span></span>
* <span data-ttu-id="48b84-121">Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-121">Azure Storage</span></span>
  - <span data-ttu-id="48b84-122">Alterar o Parâmetro Tags para Tag e adicionar as Marcas de alias do parâmetro</span><span class="sxs-lookup"><span data-stu-id="48b84-122">Change Tags Parameter to Tag, and add parameter alias Tags</span></span>
    + <span data-ttu-id="48b84-123">New-AzureRmStorageAccount</span><span class="sxs-lookup"><span data-stu-id="48b84-123">New-AzureRmStorageAccount</span></span>
    + <span data-ttu-id="48b84-124">Set-AzureRmStorageAccount</span><span class="sxs-lookup"><span data-stu-id="48b84-124">Set-AzureRmStorageAccount</span></span>
* <span data-ttu-id="48b84-125">Rede do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-125">Azure Network</span></span>
  - <span data-ttu-id="48b84-126">Novo cmdlet adicionado para emparelhamento da Rede Virtual</span><span class="sxs-lookup"><span data-stu-id="48b84-126">New cmdlet added for Virtual Network Peering</span></span>
* <span data-ttu-id="48b84-127">Cache Redis do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-127">Azure Redis Cache</span></span>
  - <span data-ttu-id="48b84-128">Novo cmdlet adicionado para Reset-AzureRmRedisCache</span><span class="sxs-lookup"><span data-stu-id="48b84-128">New cmdlet added for Reset-AzureRmRedisCache</span></span>
  - <span data-ttu-id="48b84-129">Novo cmdlet adicionado para Export-AzureRmRedisCache</span><span class="sxs-lookup"><span data-stu-id="48b84-129">New cmdlet added for Export-AzureRmRedisCache</span></span>
  - <span data-ttu-id="48b84-130">Novo cmdlet adicionado para Import-AzureRmRedisCache</span><span class="sxs-lookup"><span data-stu-id="48b84-130">New cmdlet added for Import-AzureRmRedisCache</span></span>
  - <span data-ttu-id="48b84-131">Cmdlet New-AzureRmRedisCache modificado para incluir a alteração do parâmetro para vNet</span><span class="sxs-lookup"><span data-stu-id="48b84-131">Modified cmdlet New-AzureRmRedisCache to include parameter change for vNet</span></span>
* <span data-ttu-id="48b84-132">Backup/Restauração do Banco de Dados SQL Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-132">Azure SQL DB Backup/Restore</span></span>
  - <span data-ttu-id="48b84-133">Cmdlets para o recurso de backup LTR (Retenção de Longo Prazo)</span><span class="sxs-lookup"><span data-stu-id="48b84-133">Cmdlets for LTR (Long Term Retention) backup feature</span></span>
  - <span data-ttu-id="48b84-134">Get-AzureRmSqlServerBackupLongTermRetentionVault</span><span class="sxs-lookup"><span data-stu-id="48b84-134">Get-AzureRmSqlServerBackupLongTermRetentionVault</span></span>
  - <span data-ttu-id="48b84-135">Get-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span><span class="sxs-lookup"><span data-stu-id="48b84-135">Get-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span></span>
  - <span data-ttu-id="48b84-136">Set-AzureRmSqlServerBackupLongTermRetentionVault</span><span class="sxs-lookup"><span data-stu-id="48b84-136">Set-AzureRmSqlServerBackupLongTermRetentionVault</span></span>
  - <span data-ttu-id="48b84-137">Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span><span class="sxs-lookup"><span data-stu-id="48b84-137">Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy</span></span>
  - <span data-ttu-id="48b84-138">Restore-AzureRmSqlDatabase agora oferece suporte à restauração pontual de um banco de dados excluído</span><span class="sxs-lookup"><span data-stu-id="48b84-138">Restore-AzureRmSqlDatabase now supports point-in-time restore of a deleted database</span></span>
  - <span data-ttu-id="48b84-139">Restore-AzureRmSqlDatabase agora oferece suporte à restauração de um backup de Retenção de Longo Prazo</span><span class="sxs-lookup"><span data-stu-id="48b84-139">Restore-AzureRmSqlDatabase now supports restoring from a Long Term Retention backup</span></span>
* <span data-ttu-id="48b84-140">LogicApp do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-140">Azure LogicApp</span></span>
  - <span data-ttu-id="48b84-141">Cmdlets adicionados das contas de Integração do LogicApp.</span><span class="sxs-lookup"><span data-stu-id="48b84-141">Added LogicApp Integration accounts cmdlets.</span></span>
  - <span data-ttu-id="48b84-142">Get-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="48b84-142">Get-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="48b84-143">Get-AzureRmIntegrationAccountCallbackUrl</span><span class="sxs-lookup"><span data-stu-id="48b84-143">Get-AzureRmIntegrationAccountCallbackUrl</span></span>
  - <span data-ttu-id="48b84-144">Get-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="48b84-144">Get-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="48b84-145">Get-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="48b84-145">Get-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="48b84-146">Get-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="48b84-146">Get-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="48b84-147">Get-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="48b84-147">Get-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="48b84-148">Get-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="48b84-148">Get-AzureRmIntegrationAccountSchema</span></span>
  - <span data-ttu-id="48b84-149">New-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="48b84-149">New-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="48b84-150">New-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="48b84-150">New-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="48b84-151">New-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="48b84-151">New-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="48b84-152">New-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="48b84-152">New-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="48b84-153">New-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="48b84-153">New-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="48b84-154">New-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="48b84-154">New-AzureRmIntegrationAccountSchema</span></span>
  - <span data-ttu-id="48b84-155">Remove-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="48b84-155">Remove-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="48b84-156">Remove-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="48b84-156">Remove-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="48b84-157">Remove-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="48b84-157">Remove-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="48b84-158">Remove-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="48b84-158">Remove-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="48b84-159">Remove-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="48b84-159">Remove-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="48b84-160">Remove-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="48b84-160">Remove-AzureRmIntegrationAccountSchema</span></span>
  - <span data-ttu-id="48b84-161">Set-AzureRmIntegrationAccountAgreement</span><span class="sxs-lookup"><span data-stu-id="48b84-161">Set-AzureRmIntegrationAccountAgreement</span></span>
  - <span data-ttu-id="48b84-162">Set-AzureRmIntegrationAccountCertificate</span><span class="sxs-lookup"><span data-stu-id="48b84-162">Set-AzureRmIntegrationAccountCertificate</span></span>
  - <span data-ttu-id="48b84-163">Set-AzureRmIntegrationAccount</span><span class="sxs-lookup"><span data-stu-id="48b84-163">Set-AzureRmIntegrationAccount</span></span>
  - <span data-ttu-id="48b84-164">Set-AzureRmIntegrationAccountMap</span><span class="sxs-lookup"><span data-stu-id="48b84-164">Set-AzureRmIntegrationAccountMap</span></span>
  - <span data-ttu-id="48b84-165">Set-AzureRmIntegrationAccountPartner</span><span class="sxs-lookup"><span data-stu-id="48b84-165">Set-AzureRmIntegrationAccountPartner</span></span>
  - <span data-ttu-id="48b84-166">Set-AzureRmIntegrationAccountSchema</span><span class="sxs-lookup"><span data-stu-id="48b84-166">Set-AzureRmIntegrationAccountSchema</span></span>
* <span data-ttu-id="48b84-167">Repositório Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="48b84-167">Azure Data Lake Store</span></span>
  - <span data-ttu-id="48b84-168">Melhore drasticamente o desempenho do arquivo, o carregamento e o download da pasta.</span><span class="sxs-lookup"><span data-stu-id="48b84-168">Drastically improve performance of file and folder upload and download.</span></span>
  - <span data-ttu-id="48b84-169">Isso inclui uma pequena mudança nos nomes do parâmetro para download e a inclusão de dois parâmetros novos para carregar:</span><span class="sxs-lookup"><span data-stu-id="48b84-169">This includes a slight change to the parameter names for download and inclusion of two new parameters for upload:</span></span>
    + <span data-ttu-id="48b84-170">NumThreads -> PerFileThreadCount, usados para indicar o número de threads a usar em um único arquivo</span><span class="sxs-lookup"><span data-stu-id="48b84-170">NumThreads -> PerFileThreadCount, used to indicate the number of threads to use in a single file</span></span>
    + <span data-ttu-id="48b84-171">ConcurrentFileCount, usado para indicar o número de arquivos para carregar/baixar em paralelo para o upload/download de uma pasta.</span><span class="sxs-lookup"><span data-stu-id="48b84-171">ConcurrentFileCount, used to indicate the number of files to upload/download in parallel for folder upload/download.</span></span>
  - <span data-ttu-id="48b84-172">Os valores de threading padrão agora são projetados para oferecer uma melhor taxa de transferência para a maioria dos tamanhos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="48b84-172">Default threading values are now designed to give a better all around throughput for most file sizes.</span></span> <span data-ttu-id="48b84-173">Se o desempenho não for o desejado, os valores acima poderão ser modificados para atender aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="48b84-173">If performance is not as desired, the values above can be modified to meet requirements.</span></span>
* <span data-ttu-id="48b84-174">Análise Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="48b84-174">Azure Data Lake Analytics</span></span>
  - <span data-ttu-id="48b84-175">Get-AzureRMDataLakeAnalyticsDataSource agora retorna todas as fontes de dados quando chamado sem argumentos.</span><span class="sxs-lookup"><span data-stu-id="48b84-175">Get-AzureRMDataLakeAnalyticsDataSource now returns all data sources when called with no arguments.</span></span>
  - <span data-ttu-id="48b84-176">Essa alteração também remove do cmdlet o parâmetro do tipo da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="48b84-176">This change also removes the data source type parameter from the cmdlet.</span></span>
  - <span data-ttu-id="48b84-177">Essa alteração resulta em um novo objeto sendo retornado para a operação de lista com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="48b84-177">This change results in a new object being returned for the list operation with the following properties:</span></span>
    + <span data-ttu-id="48b84-178">Type, o tipo da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="48b84-178">Type, the type of data source</span></span>
    + <span data-ttu-id="48b84-179">Name, o nome da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="48b84-179">Name, the name of the data source</span></span>
    + <span data-ttu-id="48b84-180">IsDefault, definido para true se esta for a fonte de dados padrão da conta</span><span class="sxs-lookup"><span data-stu-id="48b84-180">IsDefault, set to true if this is the default data source for the account</span></span>
  - <span data-ttu-id="48b84-181">Get-AzureRMDataLakeAnalyticsJob corrigido para a lista de certos valores de deslocamento de data e hora ao filtrar em submittedBefore e submittedAfter.</span><span class="sxs-lookup"><span data-stu-id="48b84-181">Get-AzureRMDataLakeAnalyticsJob fixed for list for certain date time offset values when filtering on submittedBefore and submittedAfter.</span></span>
* <span data-ttu-id="48b84-182">Aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="48b84-182">Web Apps</span></span>
  - <span data-ttu-id="48b84-183">Adicionar o cmdlet Swap-AzureRmWebAppSlot de troca regular e trocar pela visualização</span><span class="sxs-lookup"><span data-stu-id="48b84-183">Add Swap-AzureRmWebAppSlot cmdlet for regular swap and swap with preview</span></span>
  - <span data-ttu-id="48b84-184">Estender o cmdlet Set-AzureRmWebAppSlot para oferecer suporte à troca automática</span><span class="sxs-lookup"><span data-stu-id="48b84-184">Extend Set-AzureRmWebAppSlot cmdlet to support auto swap</span></span>
* <span data-ttu-id="48b84-185">Gerenciamento de API do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-185">Azure API Management</span></span>
  - <span data-ttu-id="48b84-186">Cmdlets de Implantação do Gerenciamento de Api do Azure corrigidos para o AzureChinaCloud.</span><span class="sxs-lookup"><span data-stu-id="48b84-186">Fixed Azure Api Management Deployment cmdlets for AzureChinaCloud.</span></span>
  - <span data-ttu-id="48b84-187">O cmdlet Set-AzureRmApiManagementTenantGitAccess removido como Acesso ao Git é habilitado por Padrão.</span><span class="sxs-lookup"><span data-stu-id="48b84-187">Removed cmdlet Set-AzureRmApiManagementTenantGitAccess as Git Access is enabled by Default.</span></span>
* <span data-ttu-id="48b84-188">Backup dos Serviços de Recuperação do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-188">Azure Recovery Services Backup</span></span>
  - <span data-ttu-id="48b84-189">Suporte adicionado para a carga de trabalho do SQL Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-189">Added support for the Azure SQL workload</span></span>
  - <span data-ttu-id="48b84-190">Suporte adicionado para o backup e a restauração das VMs criptografadas do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-190">Added support for backing up and restoring encrypted Azure VMs</span></span>
  - <span data-ttu-id="48b84-191">Backup-AzureRmRecoveryServicesBackupItem - recurso do tempo de retenção opcional adicionado para os pontos de recuperação</span><span class="sxs-lookup"><span data-stu-id="48b84-191">Backup-AzureRmRecoveryServicesBackupItem - Added optional retention time feature for recovery points</span></span>
  - <span data-ttu-id="48b84-192">Correções menores do bug relacionado ao filtro nos cmdlets Get-AzureRmRecoveryServicesBackupContainer e Get-AzureRmRecoveryServicesBackupItem</span><span class="sxs-lookup"><span data-stu-id="48b84-192">Minor filter-related bug fixes in Get-AzureRmRecoveryServicesBackupContainer and Get-AzureRmRecoveryServicesBackupItem cmdlets</span></span>
* <span data-ttu-id="48b84-193">Automação do Azure</span><span class="sxs-lookup"><span data-stu-id="48b84-193">Azure Automation</span></span>
  - <span data-ttu-id="48b84-194">Get-AzureRmAutomationHybridWorkerGroup adicionado</span><span class="sxs-lookup"><span data-stu-id="48b84-194">Added Get-AzureRmAutomationHybridWorkerGroup</span></span>
