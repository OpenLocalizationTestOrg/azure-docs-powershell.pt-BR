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
ms.date: 11/14/2017
ms.openlocfilehash: cf58789ba69fd2fc157e37d0b052827b361246e5
ms.sourcegitcommit: c42c7176276ec4e1cc3360a93e6b15d32083bf9f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2017
---
# <a name="release-notes"></a>Notas de versão

É uma lista das alterações feitas nesta versão do Azure PowerShell.

## <a name="20171208-version-511"></a>8/12/2017 Versão 5.1.1
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

Alterações ocorridas desde a última versão: as alterações ocorridas desde a última versão: https://github.com/azure/azure-powershell/compare/v5.0.1-November2017...v5.1.1-December2017

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
