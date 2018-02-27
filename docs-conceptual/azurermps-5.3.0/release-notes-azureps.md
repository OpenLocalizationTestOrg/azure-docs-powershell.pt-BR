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
ms.date: 2/20/2018
ms.openlocfilehash: 40d5a9199e000d0e2d605527c27409ac65d48dd1
ms.sourcegitcommit: 48461455bc8b70576a75eaa62318bcf66d9ddbb9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2018
---
# <a name="release-notes"></a>Notas de versão

É uma lista das alterações feitas nesta versão do Azure PowerShell.

---

## <a name="530---february-2018"></a>5.3.0 - Fevereiro de 2018
### <a name="azurermprofile"></a>AzureRM.profile
* Aviso de reprovação adicionado para PowerShell 3 e 4
* `Add-AzureRmAccount` foi renomeado como `Connect-AzureRmAccount`; foi adicionado um alias para o nome antigo do cmdlet e outros aliases (`Login-AzAccount` e `Login-AzureRmAccount`) foram redirecionados para o novo nome do cmdlet.
* `Remove-AzureRmAccount` foi renomeado como `Disconnect-AzureRmAccount`; foi adicionado um alias para o nome antigo do cmdlet e outros aliases (`Logout-AzAccount` e `Logout-AzureRmAccount`) foram redirecionados para o novo nome do cmdlet.
* Cadeias de caracteres de recurso corrigidas para usar `Connect-AzureRmAccount` em vez de `Login-AzureRmAccount`
* `Add-AzureRmEnvironment` e `Set-AzureRmEnvironment`
  - `-AzureOperationalInsightsEndpoint` e `-AzureOperationalInsightsEndpointResourceId` adicionados como parâmetros para uso com RP de plano de dados OperationalInsights.

### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Uso de `Login-AzureRmAccount` corrigido para usar `Connect-AzureRmAccount`

### <a name="azurermcompute"></a>AzureRM.Compute
* Parâmetro `-AvailabilitySetName` adicionado ao parameterset simplificado de `New-AzureRmVM`.
* Uso de `Login-AzureRmAccount` corrigido para usar `Connect-AzureRmAccount`
* Suporte de identidade atribuída ao usuário para VM e conjunto de dimensionamento de VM
    - Os parâmetros `-IdentityType` e `-IdentityId` são adicionados a `New-AzureRmVMConfig`, `New-AzureRmVmssConfig`, `Update-AzureRmVM` e `Update-AzureRmVmss`
* Parâmetro `-EnableIPForwarding` adicionado a `Add-AzureRmVmssNetworkInterfaceConfig`
* Parâmetro `-Priority` adicionado a `New-AzureRmVmssConfig`

### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Uso de `Login-AzureRmAccount` corrigido para usar `Connect-AzureRmAccount`

### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Uso de `Login-AzureRmAccount` corrigido para usar `Connect-AzureRmAccount`
* Mensagem de erro corrigida de `Test-AzureRmDataLakeStoreAccount` ao executar este cmdlet sem ter se conectado a `Login-AzureRmAccount`

### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Atualizado para usar a versão da API “2018-01-01”.

### <a name="azurermeventhub"></a>AzureRM.EventHub
* Adicionado abaixo novos comandos para as operações de recuperação de desastre de replicação geográfica.
    - Criar um novo Alias (configuração de recuperação de desastre): - `New-AzureRmEventHubGeoDRConfiguration` - Recuperar Alias (configuração de recuperação de desastre): - `Get-AzureRmEventHubGeoDRConfiguration` - Desabilitar a recuperação de desastre e deixar de replicar altera os namespaces do principal para secundário - `Set-AzureRmEventHubGeoDRConfigurationBreakPair`- Invocar failover de recuperação de desastre e reconfigurar o alias para apontar para o namespace secundário - `Set-AzureRmEventHubGeoDRConfigurationFailOver` - Excluir um alias (configuração de recuperação de desastre) - `Remove-AzureRmEventHubGeoDRConfiguration`
* Novos comandos adicionados abaixo para verificar o nome do namespace e o nome da configuração GeoDr - disponibilidade de alias.
    - Verifique a disponibilidade do nome do namespace ou do alias (configuração de recuperação de desastre):- `Test-AzureRmEventHubName`

### <a name="azurerminsights"></a>AzureRM.Insights
* Uso de `Login-AzureRmAccount` corrigido para usar `Connect-AzureRmAccount`

### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Uso de `Login-AzureRmAccount` corrigido para usar `Connect-AzureRmAccount`

### <a name="azurermnetwork"></a>AzureRM.Network
* Corrija a mensagem de substituição 'Tem certeza de que deseja substituir o recurso'

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Suporte adicionado para a consulta da API V2 por meio de `Invoke-AzureRmOperationalInsightsQuery`. Confira [https://dev.loganalytics.io/](https://dev.loganalytics.io/) para obter mais informações sobre a nova API.

### <a name="azurermresources"></a>AzureRM.Resources
* `Get-AzureRmADServicePrincipal`: `-ServicePrincipalName` removido do conjunto de parâmetros padrão Vazio porque era redundante com o conjunto de parâmetros SPN

### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Correção de funcionalidade adicionada para `Remove-AzureRmServiceBusRule` e `Get-AzureRmServiceBusKey`
* Adicionado abaixo novos commandlets para as operações de recuperação de desastre de replicação geográfica.
    - Criar um novo Alias (configuração de recuperação de desastre): - `New-AzureRmServiceBusDRConfigurations` - Recuperar Alias (configuração de recuperação de desastre): - `Get-AzureRmServiceBusDRConfigurations` - Desabilitar a recuperação de desastre e deixar de replicar altera os namespaces do principal para secundário - `Set-AzureRmServiceBusDRConfigurationsBreakPairing`- Invocar failover de recuperação de desastre e reconfigurar o alias para apontar para o namespace secundário - `Set-AzureRmServiceBusDRConfigurationsFailOver` - Excluir um alias (configuração de recuperação de desastre) - `Remove-AzureRmServiceBusDRConfigurations`
* Os commandlets `Test-AzureRmServiceBusName` foram atualizados para dar suporte à recuperação de desastre de replicação geográfica - Operações de disponibilidade de verificação do nome do alias.
    - Verifique a disponibilidade do nome do namespace ou do alias (configuração de recuperação de desastre):- `Test-AzureRmServiceBusName`

### <a name="azurermusageaggregates"></a>AzureRM.UsageAggregates
* Uso de `Login-AzureRmAccount` corrigido para usar `Connect-AzureRmAccount`

## <a name="520---january-2018"></a>5.2.0 – Janeiro de 2018
#### <a name="azurermprofile"></a>AzureRM.profile
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Add-AzureRmAccount
  * Adicionado o Logon -MSI para autenticação usando as credenciais da Identidade do serviço gerenciado da VM/serviço atual
  * Autenticação de KeyVault corrigida ao fazer logon com tokens de acesso fornecidos pelo usuário

#### <a name="azurestorage"></a>Azure.Storage
* Adicionar os cmdlets para obter e definir propriedades do serviço de armazenamento
    - Get-AzureStorageServiceProperty
    - Update-AzureStorageServiceProperty

#### <a name="azurermanalysisservices"></a>AzureRM.AnalysisServices
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermapimanagement"></a>AzureRM.ApiManagement
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmApiManagementProperty, Set-AzureRmApiManagementProperty e New-AzureRmApiManagement

#### <a name="azurermapplicationinsights"></a>AzureRM.ApplicationInsights
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermautomation"></a>AzureRM.Automation
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para Set-AzureRmAutomationRunbook

#### <a name="azurermbackup"></a>AzureRM.Backup
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermbatch"></a>AzureRM.Batch
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermcdn"></a>AzureRM.Cdn
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmCdnEndpoint e New-AzureRmCdnProfile

#### <a name="azurermcognitiveservices"></a>AzureRM.CognitiveServices
* Integrar ao SDK de Gerenciamento dos Serviços Cognitivos versão 3.0.0.

#### <a name="azurermcompute"></a>AzureRM.Compute
* Um conjunto de parâmetros simplificado foi adicionado a New-AzureRmVmss, que cria um Conjunto de dimensionamento de máquinas virtuais e todos os recursos necessários usando padrões inteligentes
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmVm e Update-AzureRmVm
* Corrigido o cmdlet Get-AzureRmComputeResourceSku fixo quando a Zona está incluída na restrição.
* Atualizado o esquema de configuração do agente de diagnóstico para suporte do coletor do Azure Monitor.

#### <a name="azurermcontainerinstance"></a>AzureRM.ContainerInstance
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermcontainerregistry"></a>AzureRM.ContainerRegistry
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermdatafactories"></a>AzureRM.DataFactories
* Habilitado o suporte do Azure Key Vault para todos os serviços vinculados de armazenamento de dados
* Adicionada propriedade de tipo de licença para tempo de execução de integração do Azure SSIS
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmDataFactory

#### <a name="azurermdatafactoryv2"></a>AzureRM.DataFactoryV2
* Habilitado o suporte do Azure Key Vault para todos os serviços vinculados de armazenamento de dados
* Adicionada propriedade de tipo de licença para tempo de execução de integração do Azure SSIS
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Adicionar parâmetro "LicenseType" para cmd "Set-AzureRmDataFactoryV2IntegrationRuntime" para habilitar a funcionalidade AHUB

#### <a name="azurermdatalakeanalytics"></a>AzureRM.DataLakeAnalytics
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmDataLakeAnalyticsAccount e Set-AzureRmDataLakeAnalyticsAccount

#### <a name="azurermdatalakestore"></a>AzureRM.DataLakeStore
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmDataLakeStoreAccount e Set-AzureRmDataLakeStoreAccount

#### <a name="azurermdevtestlabs"></a>AzureRM.DevTestLabs
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermdns"></a>AzureRM.Dns
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermeventgrid"></a>AzureRM.EventGrid
* Adicionado o novo cmdlet a seguir:
    - Update-AzureRmEventGridSubscription
        - Atualize as propriedades de uma assinatura de evento de Grade de Eventos.
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermeventhub"></a>AzureRM.EventHub
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermhdinsight"></a>AzureRM.HDInsight
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurerminsights"></a>AzureRM.Insights
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermiothub"></a>AzureRM.IotHub
* Adicionar suporte a Certificado para cmdlets IoTHub
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermkeyvault"></a>AzureRM.KeyVault
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Adicionado suporte a -AsJob para cmdlets de longa execução de KeyVault. Permite que os cmdlets selecionados sejam executados em segundo plano e devolvam um trabalho para rastreamento e controle de progresso.
    * O cmdlet afetado é: Remove-AzureRmKeyVault
* Correção do bug em Set-AzureRmKeyVaultAccessPolicy em que o filtro AAD estava definindo o SPN para o UPN fornecido, em vez de definir o UPN
   - Consulte o problema a seguir para obter mais informações: https://github.com/Azure/azure-powershell/issues/5201

#### <a name="azurermlogicapp"></a>AzureRM.LogicApp
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermmachinelearning"></a>AzureRM.MachineLearning
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para Update-AzureRmMlCommitmentPlan

#### <a name="azurermmachinelearningcompute"></a>AzureRM.MachineLearningCompute
* Adicionar parâmetro IncludeAllResources ao cmdlet Remove-AzureRmMlOpCluster
    - O uso desse parâmetro de opção removerá todos os recursos que foram criados originalmente com o cluster
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermmedia"></a>AzureRM.Media
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para Set-AzureRmMediaService e New-AzureRmMediaService

#### <a name="azurermnetwork"></a>AzureRM.Network
* Adicionado suporte para -AsJob para cmdlets de Rede de longa execução. Permite que os cmdlets selecionados sejam executados em segundo plano e devolvam um trabalho para rastreamento e controle de progresso.
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermnotificationhubs"></a>AzureRM.NotificationHubs
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmNotificationHubsNamespace e Set-AzureRmNotificationHubsNamespace

#### <a name="azurermoperationalinsights"></a>AzureRM.OperationalInsights
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmOperationalInsightsSavedSearch, Set-AzureRmOperationalInsightsSavedSearch, New-AzureRmOperationalInsightsWorkspacee Set-AzureRmOperationalInsightsWorkspace

#### <a name="azurermpowerbiembedded"></a>AzureRM.PowerBIEmbedded
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermrecoveryservices"></a>AzureRM.RecoveryServices
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermrecoveryservicesbackup"></a>AzureRM.RecoveryServices.Backup
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Adicionada a opção -UseOriginalStorageAccount para o cmdlet Restore-AzureRmRecoveryServicesBackupItem.
    - Habilitando esses resultados de sinalizador em discos de restauração para suas contas de armazenamento originais, o que permite aos usuários manter a configuração da VM restaurada o mais próximo possível das VMs originais.
    - Também ajuda a melhorar o desempenho da operação de restauração.

#### <a name="azurermrediscache"></a>AzureRM.RedisCache
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Adicionados 3 novos cmdlets para regras de firewall
* Adicionados 3 novos cmdlets para replicação geográfica
* Adicionado suporte para zonas e marcas
* Deixe o ResourceGroup como opcional sempre que possível.

#### <a name="azurermrelay"></a>AzureRM.Relay
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermresources"></a>AzureRM.Resources
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Adicionado suporte para -AsJob para cmdlets de Recursos de longa execução. Permite que os cmdlets selecionados sejam executados em segundo plano e devolvam um trabalho para rastreamento e controle de progresso.
* Adicionado alias de Get-AzureRmProviderOperation para Get-AzureRmResourceProviderAction para manter a conformidade com as convenções de nomenclatura

#### <a name="azurermscheduler"></a>AzureRM.Scheduler
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermservermanagement"></a>AzureRM.ServerManagement
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Obsoleto -Tags a favor de -Tag para New-AzureRmServerManagementNode e New-AzureRmServerManagementGateway

#### <a name="azurermservicebus"></a>AzureRM.ServiceBus
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermservicefabric"></a>AzureRM.ServiceFabric
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermsiterecovery"></a>AzureRM.SiteRecovery
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermsql"></a>AzureRM.Sql
* Atualizar a descrição de parâmetros de comandos de Auditoria
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Adicionado o parâmetro -AsJob para cmdlets de longa execução
* Obsoleto parâmetro -DatabaseName de Get-AzureRmSqlServiceObjective

#### <a name="azurermstorage"></a>AzureRM.Storage
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Corrigir um problema de referência nula de execução de cmdlet New-AzureRMStorageAccount com o parâmetro -EnableEncryptionService None
* Adicionado suporte para -AsJob para cmdlets de Armazenamento de longa execução. Permite que os cmdlets selecionados sejam executados em segundo plano e devolvam um trabalho para rastreamento e controle de progresso.
    - Os cmdlets afetados são New-, Remove-, Add- e Update- para a Conta de Armazenamento e a Regra de Conta de Armazenamento em Rede.

#### <a name="azurermstreamanalytics"></a>AzureRM.StreamAnalytics
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermtrafficmanager"></a>AzureRM.TrafficManager
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual

#### <a name="azurermwebsites"></a>AzureRM.Websites
* Adicionado o Completador de local parâmetros de -Location, permitindo o preenchimento da guia por meio de locais válidos
* Adicionado o ResourceGroup Completer aos parâmetros -ResourceGroup, permitindo o preenchimento da guia por meio de grupos de recursos na assinatura atual
* Adicionado suporte para -AsJob para cmdlets de Sites de longa execução. Permite que os cmdlets selecionados sejam executados em segundo plano e devolvam um trabalho para rastreamento e controle de progresso.
     - Os cmdlets afetados são New-, Remove-, Add- e Set- para WebApps, AppServicePlan e Slots

## <a name="2017128-version-511"></a>8/12/2017 Versão 5.1.1
* AnalysisServices
    - Alterar o conjunto validado de locais da pesquisa dinâmica para que todas as nuvens tenham suporte.
* Automação
    - Atualizar para Import-AzureRMAutomationRunbook
        - O suporte agora está sendo fornecido para runbooks Python2
* Batch
    - Correção de bug em que as operações de conta sem um grupo de recursos não conseguiam detectar o grupo de recursos automaticamente
* Computação
    - Get-AzureRmComputeResourceSku mostra informações de zona.
    - Atualizar Disable-AzureRmVmssDiskEncryption para corrigir o problema https://github.com/Azure/azure-powershell/issues/5038
    - Adicionado: suporte AsJob para cmdlets de computação de longa execução. Permite que os cmdlets selecionados sejam executados em segundo plano e devolvam um trabalho para rastreamento e controle de progresso.
        - Os cmdlets afetados incluem: New-, Update-, Set-, Remove-, Start-, Restart-, Stop- para Máquinas Virtuais e Conjuntos de Dimensionamento de Máquinas Virtuais
    - Um conjunto de parâmetros simplificado foi adicionado a New-AzureRmVM, que cria uma Máquina Virtual e todos os recursos necessários usando padrões inteligentes
* ContainerInstance
    - Aplicar o SDK de Instância de Contêiner do Azure 2017-10-01
        - Suporte à execução do contêiner até a conclusão
        - Suporte à montagem de volume do Arquivo do Azure
        - Suporte à abertura de várias portas para IP público
* ContainerRegistry
    - Novos cmdlets para replicação geográfica e webhooks
        - Get/New/Remove-AzureRmContainerRegistryReplication
        - Get/New/Remove/Test/Update-AzureRmContainerRegistryWebhook
* DataFactories
    - A funcionalidade de criptografia de credenciais agora funciona com "Acesso Remoto" habilitado (pela rede) e "Acesso Remoto" desabilitado (computador local).
* DataFactoryV2
    - Dois novos cmdlets foram adicionados: Update-AzureRmDataFactoryV2 e Stop-AzureRmDataFactoryV2PipelineRun
* DataLakeAnalytics
    - Um parâmetro chamado ScriptParameter foi adicionado a Submit-AzureRmDataLakeAnalyticsJob
        - As informações detalhadas sobre ScriptParameter podem ser encontradas usando Get-Help em Submit-AzureRmDataLakeAnalyticsJob
    - Em relação a New-AzureRmDataLakeAnalyticsAccount, o parâmetro MaxDegreeOfParallelism foi alterado para MaxAnalyticsUnits
        - Um alias foi adicionado ao parâmetro MaxAnalyticsUnits: MaxDegreeOfParallelism
    - Em relação a New-AzureRmDataLakeAnalyticsComputePolicy, o parâmetro MaxDegreeOfParallelismPerJob foi alterado para MaxAnalyticsUnitsPerJob
        - Um alias foi adicionado ao parâmetro MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
    - Em relação a Set-AzureRmDataLakeAnalyticsAccount, o parâmetro MaxDegreeOfParallelism foi alterado para MaxAnalyticsUnits
        - Um alias foi adicionado ao parâmetro MaxAnalyticsUnits: MaxDegreeOfParallelism
    - Em relação a Submit-AzureRmDataLakeAnalyticsJob, o parâmetro DegreeOfParallelism foi alterado para AnalyticsUnits
        - Um alias foi adicionado ao parâmetro AnalyticsUnits: DegreeOfParallelism
    - Em relação a Update-AzureRmDataLakeAnalyticsComputePolicy, o parâmetro MaxDegreeOfParallelismPerJob foi alterado para MaxAnalyticsUnitsPerJob
        - Um alias foi adicionado ao parâmetro MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
* MachineLearningCompute
    - Adicionar Set-AzureRmMlOpCluster
        - Atualizar a contagem de um agente ou a configuração de SSL de um cluster
    - As propriedades do Orchestrator são opcionais
        - O serviço irá criar uma entidade de serviço se este não for fornecido e, portanto, as propriedades do orquestrador agora são opcionais
* PowerBIEmbedded
    - Adicionar suporte aos cmdlets da Capacidade do Power BI Embedded
    - Novo Cmdlet Get-AzureRmPowerBIEmbeddedCapacity - Obtém os detalhes de uma Capacidade do Power BI Embedded.
    - Novo Cmdlet New-AzureRmPowerBIEmbeddedCapacity - Cria uma nova Capacidade do Power BI Embedded
    - Novo Cmdlet Remove-AzureRmPowerBIEmbeddedCapacity - Exclui uma instância da Capacidade do Power BI Embedded
    - Novo Cmdlet Resume-AzureRmPowerBIEmbeddedCapacity - Retoma uma instância da Capacidade do Power BI Embedded
    - Novo Cmdlet Suspend-AzureRmPowerBIEmbeddedCapacity - Suspende uma instância da Capacidade do Power BI Embedded
    - Novo Cmdlet Test-AzureRmPowerBIEmbeddedCapacity - Testa a existência de uma instância da Capacidade do Power BI Embedded
    - Novo Cmdlet Update-AzureRmPowerBIEmbeddedCapacity - Modifica uma instância da Capacidade do Power BI Embedded
* Perfil
    - O USGovernmentActiveDirectoryEndpoint foi atualizado para https://login.microsoftonline.us/
        - Para saber mais sobre os mapeamentos de ponto de extremidade do Azure Governamental, confira o seguinte: https://docs.microsoft.com/en-us/azure/azure-government/documentation-government-developer-guide#endpoint-mapping
    - O suporte -AsJob foi adicionado para cmdlets, permitindo que cmdlets selecionados sejam executados em segundo plano e devolvam um trabalho para rastreamento e controle de progresso
    - O parâmetro -AsJob foi adicionado ao cmdlet Get-AzureRmSubscription
* RecoveryServices.Backup
    - Correção do bug – Get-AzureRmRecoveryServicesBackupItem deve fazer uma comparação no filtro de nome de contêiner que não diferencia maiúsculas de minúsculas.
    - Correção do bug – AzureVmItem agora tem uma propriedade que mostra a última vez que uma operação de backup aconteceu: LastBackupTime.
* Recursos
    - Foi corrigido um problema em que o Get-AzureRMRoleAssignment resultava em atribuições sem nome de roledefiniton para funções personalizadas
        - Os usuários agora podem usar Get-AzureRMRoleAssignment com atribuições com nomes de roledefinition independentemente do tipo de função
    - Correção do problema em que o Set-AzureRMRoleRoleDefinition costumava lançar erro de DF não encontrada quando havia um novo escopo em assignablescopes
        - Os usuários agora podem usar Set-AzureRMRoleRoleDefinition com escopos atribuíveis, incluindo novos escopos independentemente da posição do escopo
    - Permitir que os escopos terminem com "/"
        - Os usuários agora podem usar commandlets de RoleDefinition e RoleAssignment com escopos terminados em "/", consistentes com API e CLI
    - Permitir que usuários criem RoleAssignment usando o sinalizador de delegação
        - Os usuários agora podem usar New-AzureRMRoleAssignment com uma opção de adicionar o sinalizador de delegação
    - Corrigir o get do RoleAssignment para respeitar o parâmetro de escopo
    - Adicionar um alias a ServicePrincipalName no Commandlet New-AzureRmRoleAssignment
        - Os usuários agora podem usar ApplicationId em vez de ServicePrincipalName ao usar o commandlet New-AzureRmRoleAssignment
* SiteRecovery
    - Adicionar avisos de obsolescência para todos os cmdlets neste módulo em preparação para a próxima versão de alteração.
        - Confira o guia de alterações futuras para saber mais sobre como migrar seus cmdlets do AzureRM.
* Sql
    - Adicionada a capacidade de renomeação de banco de dados usando Set-AzureRmSqlDatabase
    - Correção do problema https://github.com/Azure/azure-powershell/issues/4974
        - O fornecimento de um valor AUDIT_CHANGED_GROUP inválido para cmdlets de auditoria não gera mais um erro e será removido em uma versão futura.
    - Correção do problema https://github.com/Azure/azure-powershell/issues/5046
        - O parâmetro AuditAction em cmdlets de auditoria não é mais ignorado
    - Corrigido um problema em cmdlets de auditoria quando um StorageKeyType 'Secundário' é fornecido
        - Ao configurar a auditoria de blobs, a chave da conta de armazenamento primária era usada em vez da chave secundária ao fornecer o valor 'Secundário' para o parâmetro StorageKeyType.
    - Alterando o texto da mensagem de confirmação de Set-AzureRmSqlServerTransparentDataEncryptionProtector
* Azure (RDFE)
    - Removidos todos os cmdlets RemoteApp
* Azure.Storage
    - Atualizar para a Biblioteca de Clientes do Armazenamento do Azure 8.6.0 e a Biblioteca de Movimentação de Dados do Armazenamento do Azure 0.6.5

## <a name="20171110-version-501"></a>10/11/2017 Versão 5.0.1
* Problema de carregamento do assembly corrigido, que causou a falha de alguns cmdlets ao executar nos seguintes módulos:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices.Backup
    - AzureRM.RecoveryServices.SiteRecovery
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## <a name="2017118---version-500"></a>08/11/2017 - Versão 5.0.0
* Observação: esta é uma versão de alteração significativa. Confira o guia de migração (https://aka.ms/azps-migration-guide) para obter uma lista completa das alterações significativas introduzidas.
* Agora, todos os cmdlets no AzureRM oferecem suporte à ajuda online
    - Execute Get-Help com o parâmetro -Online para abrir a ajuda online em seu navegador de Internet padrão
* AnalysisServices
    * Comando Synchronize-AzureAsInstance corrigido para trabalhar com a nova API REST do AsAzure para a sincronização
* ApiManagement
    * Confira o guia de migração para ver as alterações significativas feitas no ApiManagement desta versão
    * Cmdlet Get-AzureRmApiManagementUser atualizado para corrigir o problema https://github.com/Azure/azure-powershell/issues/4510
    * Cmdlet New-AzureRmApiManagementApi atualizado para criar a Api com o Caminho Vazio https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Adicionar comandos para obter/criar/remover recurso do Application Insights
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Adicionar comandos para obter/atualizar os preços/capacidade diária do recurso do Application Insights
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Adicionar comandos para obter/criar/atualizar/remover exportação contínua do recurso do Application Insights
        - Get-AzureRmApplicationInsightsContinuousExport
        - Set-AzureRmApplicationInsightsContinuousExport
        - New-AzureRmApplicationInsightsContinuousExport
        - Remove-AzureRmApplicationInsightsContinuousExport
    * Adicionar comandos para obter/criar/remover chaves de API do recurso do application insights
        - Get-AzureRmApplicationInsightsApiKey
        - New-AzureRmApplicationInsightsApiKey
        - Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Novos parâmetros adicionados a `New-AzureRmBatchAccount`.
        - `PoolAllocationMode`: o modo de alocação a ser usado para criar pools na conta do Lote. Para criar uma conta do Lote que aloca nós do pool na assinatura do usuário, defina isso para `UserSubscription`.
        - `KeyVaultId`: a ID de recurso do cofre de chaves do Azure associada à conta do Lote.
        - `KeyVaultUrl`: a URL do cofre de chaves do Azure associada à conta do Lote.
    * Parâmetros atualizados para `New-AzureBatchTask`.
        - Opção `RunElevated` removida. O parâmetro `UserIdentity` foi adicionado para substituir `RunElevated` e o comportamento equivalente pode ser obtido construindo `PSUserIdentity` conforme mostrado abaixo:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - Parâmetro `AuthenticationTokenSettings` adicionado. Esse parâmetro permite solicitar que o serviço de Lote forneça um token de autenticação para a tarefa na execução, evitando a necessidade de passar as chaves de conta do Lote para a tarefa para fazer solicitações ao serviço de Lote.
        - Parâmetro `ContainerSettings` adicionado.
            - Esse parâmetro permite solicitar que o serviço de Lote execute a tarefa dentro de um contêiner.
        - Parâmetro `OutputFiles` adicionado.
            - Esse parâmetro permite que você configure a tarefa para carregar arquivos no Armazenamento do Azure após sua conclusão.
    * Parâmetros atualizados para `New-AzureBatchPool`.
        - Parâmetro `UserAccounts` adicionado.
            - Esse parâmetro define as contas de usuário criadas em cada nó no pool.
        - `TargetLowPriorityComputeNodes` adicionado e `TargetDedicated` renomeado como `TargetDedicatedComputeNodes`.
            - Um alias `TargetDedicated` foi criado para o parâmetro `TargetDedicatedComputeNodes`.
        - Parâmetro `NetworkConfiguration` adicionado.
            - Esse parâmetro permite que você defina as configurações de rede de pools.
    * Parâmetros atualizados para `New-AzureBatchCertificate`.
        - Agora, o parâmetro `Password` é `SecureString`.
    * Parâmetros atualizados para `New-AzureBatchComputeNodeUser`.
        - Agora, o parâmetro `Password` é `SecureString`.
    * Parâmetros atualizados para `Set-AzureBatchComputeNodeUser`.
        - Agora, o parâmetro `Password` é `SecureString`.
    * Parâmetro `Name` renomeado como `Path` em `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent` e `Remove-AzureBatchNodeFile`.
        - Um alias `Name` foi criado para o parâmetro `Path`.
    * Alterações nos objetos
        - Confira o log de alterações do Lote para obter a lista completa
    * Suporte adicionado para a autenticação baseada no Azure Active Directory.
        - Para usar a autenticação do Azure Active Directory, recupere um objeto `BatchAccountContext` usando o cmdlet `Get-AzureRmBatchAccount` e forneça `BatchAccountContext` ao parâmetro `-BatchContext` de um cmdlet do serviço de Lote. A autenticação do Azure Active Directory é obrigatória para as contas com `PoolAllocationMode = UserSubscription`.
        - Para as contas existentes ou novas contas criadas com `PoolAllocationMode = BatchService`, você pode continuar usando a autenticação da chave compartilhada recuperando um objeto `BatchAccountContext` com o cmdlet `Get-AzureRmBatchAccoutKeys`.
* Computação
    * Comandos de Extensão da Criptografia de Disco do Azure
        - O novo parâmetro para 'Set-AzureRmVmDiskEncryptionExtension': '-EncryptFormatAll' criptografa e formata os discos de dados
        - Os novos parâmetros para 'Set-AzureRmVmDiskEncryptionExtension': '-ExtensionPublisherName' e '-ExtensionType' permitem trocar para outras versões da extensão
        - Os novos parâmetros para 'Disable-AzureRmVmDiskEncryption': '-ExtensionPublisherName' e '-ExtensionType' permitem trocar para outras versões da extensão
        - Os novos parâmetros para 'Get-AzureRmVmDiskEncryptionStatus': '-ExtensionPublisherName' e '-ExtensionType' permitem trocar para outras versões da extensão
* DataLakeAnalytics
    * Confira o guia de migração para ver as alterações significativas feitas no DataLakeAnalytics desta versão
    * Um dos dois OutputTypes de Get-AzureRmDataLakeAnalyticsAccount foi alterado
        - Liste\<DataLakeAnalyticsAccount> para listar\<PSDataLakeAnalyticsAccountBasic>
        - As propriedades de PSDataLakeAnalyticsAccountBasic são um subconjunto exato das propriedades de DataLakeAnalyticsAccount
        - As propriedades adicionais que estão em DataLakeAnalyticsAccount não são retornadas pelo serviço.  Portanto, essa alteração é para refletir isso com precisão. Essas propriedades adicionais ainda estão em PSDataLakeAnalyticsAccountBasic, mas são marcadas como Obsoleto.
    * Um dos dois OutputTypes de Get-AzureRmDataLakeAnalyticsJob foi alterado
        - Liste \<JobInformation> para listar \<PSJobInformationBasic>
        - As propriedades de PSJobInformationBasic são um subconjunto exato das propriedades de JobInformation
        - As propriedades adicionais que estão em JobInformation não são retornadas pelo serviço.  Portanto, essa alteração é para refletir isso com precisão. Essas propriedades adicionais ainda estão em PSJobInformationBasic, mas são marcadas como Obsoleto.
* DataLakeStore
    * Confira o guia de migração para ver as alterações significativas feitas no DataLakeStore desta versão
    * Um dos dois OutputTypes de Get-AzureRmDataLakeStoreAccount foi alterado
        - Liste\<PSDataLakeStoreAccount> para listar\<PSDataLakeStoreAccountBasic>
        - As propriedades de PSDataLakeStoreAccountBasic são um subconjunto exato das propriedades de PSDataLakeStoreAccount
        - As propriedades adicionais que estão em PSDataLakeStoreAccount não são retornadas pelo serviço.  Portanto, essa alteração é para refletir isso com precisão. Essas propriedades adicionais ainda estão em PSDataLakeStoreAccountBasic, mas são marcadas como Obsoleto.
* DNS
    * Suporte para os tipos de registro CAA no DNS do Azure
       - Oferece suporte a todas as operações do tipo de registro CAA
* EventHub
    * Confira o guia de migração para ver as alterações significativas feitas no EventHub desta versão
* Insights
    * Confira o guia de migração para ver as alterações significativas feitas no Insights desta versão
* Rede
    * Confira o guia de migração para ver as alterações significativas feitas no Network desta versão
    * Cmdlet adicionado à lista de provedores de serviço da Internet disponíveis para uma região específica do Azure
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Cmdlet adicionado para obter a pontuação de latência relativa dos provedores de serviço da Internet a partir de um local especificado para as regiões do Azure
        - Get-AzureRmNetworkWatcherReachabilityReport
* Perfil
    - Set-AzureRmDefault
        - Use esse cmdlet para definir um grupo de recursos padrão.  Isso tornará o parâmetro -ResourceGroup opcional para alguns cmdlets e usará o padrão quando um grupo de recursos não for especificado
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - Se o grupo de recursos especificado existir na assinatura, esse grupo será definido para o padrão.  Do contrário, o grupo será criado e definido para o padrão.
    - Get-AzureRmDefault
        - Use esse cmdlet para obter o grupo de recursos padrão atual (e outros padrões no futuro).
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - Use esse cmdlet para remover o grupo de recursos padrão atual
        - ```Clear-AzureRmDefault -ResourceGroup```
    - Add-AzureRmEnvironment e Set-AzureRmEnvironment
        - Adicione o parâmetro BatchAudience, que permite especificar o público de Lote do Azure Active Directory a usar ao adquirir tokens de autenticação para o serviço de Lote.
* RecoveryServices.Backup
    * Cmdlets adicionados para executar a recuperação de arquivos instantânea.
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * Versão do SDK RecoveryServices.Backup atualizada para a mais recente
    * Testes atualizados para a carga de trabalho da VM do Azure para que todas as configurações necessárias para as execuções de teste sejam feitas pelos próprios testes.
    * Correções https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Alterações do VMware ASR para o Azure Site Recovery (os cmdlets atualmente oferecem suporte a operações entre Empresas, Empresa para Azure, HyperV para Azure)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Suporte adicionado ao cofre baseado no AAD
    * Cmdlets adicionados para gerenciar os recursos do VCenter
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Outros cmdlets adicionados
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - Confira o guia de migração para ver as alterações significativas feitas no ServiceBus desta versão
* Sql
    * Adicionar suporte para a lista e cancelar a operação assíncrona updateslo no banco de dados
        - Atualize o cmdlet Get-AzureRmSqlDatabaseActivity existente para retornar ao status da operação updateslo do BD.
        - Adicione um novo cmdlet Stop-AzureRmSqlDatabaseActivity para cancelar a operação assíncrona updateslo no banco de dados.
    * Adicionando suporte para a Redundância de Zona para os bancos de dados e pools elásticos
        - Adicionando o parâmetro da opção ZoneRedundant a New-AzureRmSqlDatabase
        - Adicionando o parâmetro da opção ZoneRedundant a Set-AzureRmSqlDatabase
        - Adicionando o parâmetro da opção ZoneRedundant a New-AzureRmSqlElasticPool
        - Adicionando o parâmetro da opção ZoneRedundant a Set-AzureRmSqlElasticPool
    * Adicionando suporte para os Aliases de DNS do Servidor
        - Adicionando o cmdlet Get-AzureRmSqlServerDnsAlias que obtém os aliases de DNS do servidor por servidor e o nome de alias, ou uma lista de aliases de DNS do servidor para um Azure SQL Server.
        - Adicionando o cmdlet New-AzureRmSqlServerDnsAlias que cria o novo alias de DNS do servidor para um determinado Azure SQL Server
        - Adicionando o cmdlet Set-AzurermSqlServerDnsAlias que permite atualizar um Azure SQL Server para o qual o alias de DNS do servidor está apontando
        - Adicionando o cmdlet Remove-AzureRmSqlServerDnsAlias que remove um alias de DNS do servidor para um Azure SQL Server
* Azure.Storage
    * Atualizar para a Biblioteca de Clientes do Armazenamento do Azure 8.5.0 e a Biblioteca de Movimentação de Dados do Armazenamento do Azure 0.6.3
    * Adicionar Recurso de Suporte do Instantâneo de Compartilhamento de Arquivos
        - Adicionar parâmetro 'SnapshotTime' a Get-AzureStorageShare
        - Adicionar parâmetro 'IncludeAllSnapshot' a Remove-AzureStorageShare
