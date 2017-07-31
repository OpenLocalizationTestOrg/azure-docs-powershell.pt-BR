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
ms.date: 07/26/2017
ms.openlocfilehash: cc2fe75f498f9043e5a4b632c144877af0143173
ms.sourcegitcommit: 20bcef86db4e4869125bb63085fcffd009c19280
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2017
---
# <a name="release-notes"></a>Notas de versão

É uma lista das alterações feitas nesta versão do Azure PowerShell.

## <a name="20170717---version-421"></a>17/07/2017 – Versão 4.2.1
* Computação
    - Corrigir problema com Disco de VM e com cmdlets de atualização e de criação de instantâneo do Disco de VM. Link: [https://github.com/azure/azure-powershell/issues/4309]
      - New-AzureRmDisk
      - New-AzureRmSnapshot
      - Update-AzureRmDisk
      - Update-AzureRmSnapshot
* Perfil
    - Corrigir problema com autenticação de usuário não interativo no RDFE. Link: [https://github.com/Azure/azure-powershell/issues/4299]
* ServiceManagement
    - Corrigir problema com autenticação de usuário não interativo. Link: [https://github.com/Azure/azure-powershell/issues/4299]

## <a name="2017711---version-420"></a>11/07/2017 – Versão 4.2.0
* AnalysisServices
    * Adicionar nova API de plano de dados
        - Introduzida API para buscar log do servidor AS: Export-AzureAnalysisServicesInstanceLog
* Automação
    * Configuração adequada do valor TimeZone nas agendas Semanal e Mensal de New-AzureRmAutomationSchedule
        - Mais informações podem ser encontradas neste problema: https://github.com/Azure/azure-powershell/issues/3043
* AzureBatch
    - Adicionado novo cmdlet Get-AzureBatchJobPreparationAndReleaseTaskStatus.
    - Adicionado início e término do intervalo de bytes aos parâmetros Get-AzureBatchNodeFileContent.
* CognitiveServices
    * Integrar ao SDK de Gerenciamento dos Serviços Cognitivos versão 1.0.0.
    * Corrigir um bug de verificação do comprimento do nome da conta.
* Computação
    * Suporte do tipo de conta de armazenamento para disco de imagem:
        - O parâmetro 'StorageAccountType' foi adicionado a Set-AzureRmImageOsDisk e a Add-AzureRmImageDataDisk
    * Recurso PrivateIP e PublicIP na Configuração de IP de Vmss:
        - Os nomes 'PrivateIPAddressVersion', 'PublicIPAddressConfigurationName', 'PublicIPAddressConfigurationIdleTimeoutInMinutes' e 'DnsSetting' foram adicionados a New-AzureRmVmssIpConfig
        - O parâmetro 'PrivateIPAddressVersion' para especificar IPv4 ou IPv6 foi adicionado a New-AzureRmVmssIpConfig
    * Recurso Manutenção de Desempenho:
        - O parâmetro da opção 'PerformMaintenance' foi adicionado a Restart-AzureRmVM.
        - Get-AzureRmVM -Status mostra as informações de manutenção de desempenho da VM em questão
    * Recurso Identidade da Máquina Virtual:
        - O parâmetro 'IdentityType' foi adicionado a New-AzureRmVMConfig e a UpdateAzureRmVM
        - Get-AzureRmVM mostra as informações da identidade da VM em questão
    * Recurso Identidade de Vmss:
        - O parâmetro 'IdentityType' foi adicionado a New-AzureRmVmssConfig
        - Get-AzureRmVmss mostra as informações da identidade do Vmss em questão
    * Recurso Diagnóstico de Inicialização de Vmss:
        - Novo cmdlet para configurar o diagnóstico de inicialização do objeto Vmss: Set-AzureRmVmssBootDiagnostics
        - O parâmetro 'BootDiagnostic' foi adicionado a New-AzureRmVmssConfig
    * Recurso LicenseType de Vmss:
        - O parâmetro 'LicenseType' foi adicionado a New-AzureRmVmssConfig
    * Suporte a RecoveryPolicyMode:
        - O parâmetro 'RecoveryPolicyMode' foi adicionado a New-AzureRmVmssConfig
    * Recurso SKU de Recurso de Computação:
        - Novo cmdlet 'Get-AzureRmComputeResourceSku' lista todas as SKUs dos recursos de computação
* DataFactories
    * Preterir New-AzureRmDataFactoryGatewayKey
    * Introduzir recurso de chave de autorização de gateway adicionando New-AzureRmDataFactoryGatewayAuthKey e Get-AzureRmDataFactoryGatewayAuthKey
* DataLakeAnalytics
    * Adicionar suporte ao CRUD da Política de Computação por meio dos comandos a seguir:
        - New-AzureRMDataLakeAnalyticsComputePolicy
        - Get-AzureRMDataLakeAnalyticsComputePolicy
        - Remove-AzureRMDataLakeAnalyticsComputePolicy
        - Update-AzureRMDataLakeAnalyticsComputePolicy
    * Adicionar suporte aos metadados de relação de trabalho para obter ajuda com trabalhos recorrentes e pipelines de trabalhos. Os comandos a seguir foram atualizados ou adicionados:
        - Submit-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJobRecurrence
        - Get-AzureRMDataLakeAnalyticsJobPipeline
    * Atualizado o público do token para que as APIs de trabalho e de catálogo usem o público específico correto do Data Lake, em vez do público do Recurso do Azure.
* DataLakeStore
    * Suporte adicionado para rotações de chave do KeyVault gerenciado pelo usuário no cmdlet Set-AzureRMDataLakeStoreAccount
    * Adicionada uma atualização de qualidade de vida para disparar automaticamente uma chamada a `enableKeyVault` quando um KeyVault gerenciado pelo usuário for adicionado ou uma chave for girada.
    * Atualizado o público do token para que as APIs de trabalho e de catálogo usem o público específico correto do Data Lake, em vez do público do Recurso do Azure.
    * Corrigido o bug que limitava o tamanho dos arquivos criados/anexados usando os seguintes cmdlets:
        - New-AzureRmDataLakeStoreItem
        - Add-AzureRmDataLakeStoreItemContent
* DNS
    * Corrigir bug no cenário de direcionamento para Get-AzureRmDnsZone
        - Mais informações podem ser encontradas aqui: https://github.com/Azure/azure-powershell/issues/4203
* HDInsight
    * Suporte adicionado para habilitar/desabilitar o OMS (Operations Management Suite)
    * Novos cmdlets
        - Enable-AzureRmHDInsightOperationsManagementSuite
        - Disable-AzureRmHDInsightOperationsManagementSuite
        - Get-AzureRmHDInsightOperationsManagementSuite
    * Adicionar novos parâmetros para definir configurações personalizadas do Spark a Add-AzureRmHDInsightConfigValues
        - Parâmetros SparkDefaults e SparkThriftConf para Spark 1.6
        - Parâmetros Spark2Defaults e Spark2ThriftConf para Spark 2.0
* Insights
    * O problema nº 4215 (solicitação de alteração) removeu o limite de 15 dias na janela de tempo do cmdlet Get-AzureRmLog. Além de pequenas alterações nos nomes dos testes de unidades.
    * Problema nº 3957 corrigido para Get-AzureRmLog
        - Problema nº 1: o back-end retorna os registros nas páginas de 200 registros cada, vinculados pelo token de continuação à próxima página. Os clientes viram o cmdlet retornando somente 200 registros quando sabiam que havia mais. Isso estava ocorrendo independentemente do valor definido para MaxEvents, a menos que o valor fosse menor que 200.
        - Problema nº 2: a documentação continha dados incorretos sobre esse cmdlet, por exemplo: a janela de tempo padrão era de uma hora.
        - Correção nº 1: O cmdlet agora segue o token de continuação retornado pelo back-end até atingir MaxEvents ou até o fim do conjunto.<br>O valor padrão de MaxEvents é 1000 e o máximo é 100000. Qualquer valor de MaxEvents menor que 1 é ignorado e o padrão é usado em vez disso. Esses valores e o comportamento não foram alterados. Agora eles são documentados corretamente.<br>Um alias para MaxEvents foi adicionado, MaxRecords, uma vez que o nome do cmdlet não fala mais sobre os eventos, mas somente sobre os Logs.
        - Correção nº 2: A documentação contém informações corretas e mais detalhadas: novo alias, janela de tempo correta, padrão correto e valores mínimo e máximo.
* KeyVault
    * Remover endereço de email da consulta de diretório quando -UserPrincipalName for especificado para os cmdlets Set-AzureRMKeyVaultAccessPolicy e Remove-AzureRMKeyVaultAccessPolicy.
      - Ambos os cmdlets agora tem um parâmetro -EmailAddress que pode ser usado em vez do parâmetro -UserPrincipalName quando consultar pelo endereço de email for apropriado.  Se houver mais de um endereço de email correspondente no diretório, o cmdlet falhará.
* Rede
    * New-AzureRmIpsecPolicy: SALifeTimeSeconds e SADataSizeKilobytes não são mais parâmetros obrigatórios
        - O padrão de SALifeTimeSeconds é 27000 segundos
        - O padrão de SADataSizeKilobytes é 102400000 KB
    * Suporte adicionado para configuração do conjunto de criptografia personalizada usando a política de SSL e listando todas as APIs de opções de SSL no Gateway de Aplicativo
        - Parâmetro opcional adicionado: -PolicyType, -PolicyName, -MinProtocolVersion e -Ciphersuite
            - Add-AzureRmApplicationGatewaySslPolicy
            - New-AzureRmApplicationGatewaySslPolicy
            - Set-AzureRmApplicationGatewaySslPolicy
        - Adicionado Get-AzureRmApplicationGatewayAvailableSslOptions (Alias: List-AzureRmApplicationGatewayAvailableSslOptions)
        - Adicionado Get-AzureRmApplicationGatewaySslPredefinedPolicy (Alias: List-AzureRmApplicationGatewaySslPredefinedPolicy)
    * Suporte a redirecionamento adicionado ao Gateway de Aplicativo
        - Adicionado Add-AzureRmApplicationGatewayRedirectConfiguration
        - Adicionado Get-AzureRmApplicationGatewayRedirectConfiguration
        - Adicionado New-AzureRmApplicationGatewayRedirectConfiguration
        - Adicionado Remove-AzureRmApplicationGatewayRedirectConfiguration
        - Adicionado Set-AzureRmApplicationGatewayRedirectConfiguration
        - Parâmetro opcional adicionado: -RedirectConfiguration
            - Add-AzureRmApplicationGatewayRequestRoutingRule
            - New-AzureRmApplicationGatewayRequestRoutingRule
            - Set-AzureRmApplicationGatewayRequestRoutingRule
        - Parâmetro opcional adicionado: -DefaultRedirectConfiguration
            - Add-AzureRmApplicationGatewayUrlPathMapConfig
            - New-AzureRmApplicationGatewayUrlPathMapConfig
            - Set-AzureRmApplicationGatewayUrlPathMapConfig
        - Parâmetro opcional adicionado: -RedirectConfiguration
            - Add-AzureRmApplicationGatewayPathRuleConfig
            - New-AzureRmApplicationGatewayPathRuleConfig
            - Set-AzureRmApplicationGatewayPathRuleConfig
        - Parâmetro opcional adicionado: -RedirectConfigurations
            - New-AzureRmApplicationGateway
            - Set-AzureRmApplicationGateway
    * Suporte adicionado aos Sites do Azure no Gateway de Aplicativo
        - Adicionado New-AzureRmApplicationGatewayProbeHealthResponseMatch
        - Parâmetros opcionais adicionados: -PickHostNameFromBackendHttpSettings, -MinServers e -Match
            - Add-AzureRmApplicationGatewayProbeConfig
            - New-AzureRmApplicationGatewayProbeConfig
            - Set-AzureRmApplicationGatewayProbeConfig
        - Parâmetros opcionais adicionados: -PickHostNameFromBackendAddress, -AffinityCookieName, -ProbeEnabled e -Path
            - Add-AzureRmApplicationGatewayBackendHttpSettings
            - New-AzureRmApplicationGatewayBackendHttpSettings
            - Set-AzureRmApplicationGatewayBackendHttpSettings
    * Atualizar Get-AzureRmPublicIPaddress para recuperar recursos de endereço público criados por meio do Conjunto de Dimensionamento de VMs
    * Adicionado cmdlet para obter uso atual da rede virtual
        - Get-AzureRmVirtualNetworkUsageList
* Perfil
    * Erro ao usar Import-AzureRmContext ou Save-AzureRmContext corrigido
        - Mais informações podem ser encontradas neste problema: https://github.com/Azure/azure-powershell/issues/3954
* RecoveryServices.SiteRecovery
    * Introdução de novo módulo para operações do Azure Site Recovery.
        - Todos os cmdlets começam com AzureRmRecoveryServicesAsr*
* Sql
    * Adicionar Cmdlets do PowerShell de Sincronização de Dados ao AzureRM.Sql
    * Cmdlets do AzureRmSqlServer atualizados para usar nova versão da API REST que evita esgotamento de tempo limite ao criar servidor.
    * Cmdlets de atualização de servidor preteridos porque a versão antiga do servidor (2.0) não existe mais.
    * Adicionar novo parâmetro de opção opcional "AssignIdentity" aos cmdlets New-AzureRmSqlServer e Set-AzureRmSqlServer para dar suporte ao provisionamento de uma identidade de recurso para o recurso do SQL Server
    * O parâmetro ResourceGroupName agora é opcional para Get-AzureRmSqlServer
        - Mais informações podem ser encontradas no seguinte problema: https://github.com/Azure/azure-powershell/issues/635
* ServiceManagement para ExpressRoute:
    * Cmdlet New-AzureBgpPeering atualizado para adicionar as seguintes novas opções:
        - PeerAddressType: os valores de "IPv4" ou de "IPv6" podem ser especificados para criar um emparelhamento via protocolo BGP do tipo de família do endereço correspondente
    * Cmdlet Set-AzureBgpPeering atualizado para adicionar as seguintes novas opções:
        - PeerAddressType: os valores de "IPv4" ou de "IPv6" podem ser especificados para atualizar o emparelhamento via protocolo BGP do tipo de família do endereço correspondente
    * Cmdlet Remove-AzureBgpPeering atualizado para adicionar as seguintes novas opções:
        - PeerAddressType: os valores de "IPv4", de "IPv6" ou de Todos podem ser especificados para remover o emparelhamento via protocolo BGP do tipo de família do endereço correspondente ou de todos eles

## <a name="20170607---version-410"></a>07/06/2017 – Versão 4.1.0
* AnalysisServices
    * Novas SKUs adicionadas: B1, B2 e S0
    * Suporte adicionado para aumentar/reduzir
* CognitiveServices
    * Atualizar exibição detalhada dos contratos de licença ao criar recursos dos Serviços Cognitivos
* Computação
    * Corrigir Test-AzureRmVMAEMExtension para máquinas virtuais com vários discos gerenciados
    * Set-AzureRmVMAEMExtension atualizado: adicionar informações de cache para discos gerenciados Premium
    * Add-AzureRmVhd: o limite de tamanho no VHD aumentou para 4 TB.
    * Stop-AzureRmVM: esclarecer documentação para o parâmetro STayProvisioned
    * New-AzureRmDiskUpdateConfig
      * Parâmetros preteridos: CreateOption, StorageAccountId, ImageReference, SourceUri e SourceResourceId
    * Set-AzureRmDiskUpdateImageReference: cmdlet preterido
    * New-AzureRmSnapshotUpdateConfig
      * Parâmetros preteridos: CreateOption, StorageAccountId, ImageReference, SourceUri e SourceResourceId
    * Set-AzureRmSnapshotUpdateImageReference: cmdlet preterido
* DataLakeStore
    * Enable-AzureRmDataLakeStoreKeyVault (Enable-AdlStoreKeyVault)
      * Habilitar criptografia gerenciada do KeyVault para um DataLake Store
* DevTestLabs
    * Atualizar cmdlets para funcionar com a versão atual e atualizada da API do DevTest Labs.
* IotHub
    * Adicionar suporte a roteamento aos cmdlets IoTHub
* KeyVault
  * Novos cmdlets para dar suporte a chaves de conta de armazenamento gerenciado do KeyVault
    * Get-AzureKeyVaultManagedStorageAccount
    * Add-AzureKeyVaultManagedStorageAccount
    * Remove-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccountKey
    * Get-AzureKeyVaultManagedStorageSasDefinition
    * Set-AzureKeyVaultManagedStorageSasDefinition
    * Remove-AzureKeyVaultManagedStorageSasDefinition
* Rede
    * Get-AzureRmNetworkUsage: novo cmdlet para mostrar detalhes de capacidade e de uso de rede
    * Adicionadas novas opções de GatewaySku para VirtualNetworkGateways
        * VpnGw1, VpnGw2 e VpnGw3 são as novas SKUs adicionadas aos gateways de VPN
    * Set-AzureRmNetworkWatcherConfigFlowLog
      * Exemplos de ajuda corrigidos
* NotificationHubs
    * Atualização transparente para os cmdlets NotificationHubs da nova API
* Perfil
    * Resolve-AzureRmError
      * Novo cmdlet para mostrar os detalhes das exceções e dos erros gerados pelos cmdlets, incluindo dados de solicitação/resposta do servidor
    * Send-Feedback
      * Habilitado o envio de comentários sem fazer logon
    * Get-AzureRmSubscription
      * Corrigir bug ao recuperar assinaturas de CSP
* Recursos
    * Problema corrigido no qual o Get-AzureRMRoleAssignment resultaria em uma Solicitação Inválida se o número de atribuições de função fosse maior que 1000
        * Os usuários agora poderão usar Get-AzureRMRoleAssignment mesmo se o número de atribuições de função retornado for maior que 1000
* Sql
    * Restore-AzureRmSqlDatabase: atualizar exemplo de documentação
* Armazenamento
    * Adicionar suporte à configuração AssignIdentity aos cmdlets de conta de armazenamento no modo de recurso
        * New-AzureRmStorageAccount
        * Set-AzureRmStorageAccount
    * Adicionar Suporte à Chave do Cliente aos cmdlets de conta de armazenamento no modo de recurso
        * Set-AzureRmStorageAccount
        * New-AzureRmStorageAccountEncryptionKeySource
* TrafficManager

    * Novas configurações de Monitor: 'MonitorIntervalInSeconds', 'MonitorTimeoutInSeconds' e 'MonitorToleratedNumberOfFailures'
    * Novo protocolo 'TCP' do Monitor
* ServiceManagement
    * Add-AzureVhd: o limite de tamanho no VHD aumentou para 4 TB.
    * New-AzureBGPPeering: suporte a LegacyMode
* Azure.Storage
    * Atualizar ajuda para os parâmetros que aceitam caracteres curinga e atualizar o tipo StorageContext

## <a name="20170523---version-402"></a>23/05/2017 – Versão 4.0.2
* Perfil
    * Add-AzureRmAccount
      * Adicionado alias do parâmetro `-EnvironmentName` para compatibilidade com versões anteriores 2.x do AzureRM.profile

## <a name="20170512---version-401"></a>12/05/2017 – Versão 4.0.1
 * Corrigir problema com o New-AzureStorageContext em cenários offline: https://github.com/Azure/azure-powershell/issues/3939

## <a name="20170510---version-400"></a>10/05/2017 – Versão 4.0.0


* Esta versão contém alterações de última hora. Consulte o [guia de migração](https://aka.ms/azps-migration-guide) para obter os detalhes de alteração e saber o impacto sobre os scripts existentes.
* ApiManagement
  - Suporte adicionado para configurar grupos externos no New-AzureRmApiManagementGroup.
* Cobrança
  - Novo cmdlet Get-AzureRmBillingPeriod
    + Cmdlet para recuperar períodos de cobrança de assinatura do Azure.
  - Atualizar o cmdlet Get-AzureRmBillingInvoice
  - nova propriedade BillingPeriodNames
  - saída em modo de exibição de lista
* Computação
  - Os cmdlets atualizados AzureRmVMAEMExtension e Test-AzureRmVMAEMExtension oferecem suporte ao Managed Disks Premium
  - Configurações de criptografia de backup para VMs de IaaS e restauração em caso de falha
  - A opção ChefServiceInterval foi renomeada como ChefDaemonInterval. No entanto, a antiga opção continuará funcionando.
  - Remover as propriedades duplicadas DataDiskNames e NetworkInterfaceIDs do objeto PS da VM.
  - Tornar os parâmetros DataDiskNames e NetworkInterfaceIDs opcionais em Remove-AzureRmVMDataDisk e Remove-AzureRmVMNetworkInterface, respectivamente.
  - Corrigir o problema de direcionamento dos cmdlets Get quando eles retornarem um objeto de lista.
  - Os cmdlets que entraram em conflito com os cmdlets RDFE foram renomeados. Consulte o problema em https://github.com/Azure/azure-powershell/issues/2917 para obter mais detalhes
    + `New-AzureVMSqlServerAutoBackupConfig` foi renomeado para `New-AzureRmVMSqlServerAutoBackupConfig`
    + `New-AzureVMSqlServerAutoPatchingConfig` foi renomeado para `New-AzureRmVMSqlServerAutoPatchingConfig`
    + `New-AzureVMSqlServerKeyVaultCredentialConfig` foi renomeado para `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Consumo
  - Novo cmdlet Get-AzureRmConsumptionUsageDetail
    + Cmdlet para recuperar detalhes de uso da assinatura.
* ContainerRegistry
  - Adicionar cmdlets do PowerShell ao Registro de Contêiner do Azure
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - Adicionar suporte aos pacotes de catálogo get e list
  - Adicionar suporte à listagem dos seguintes itens de catálogo de ancestrais mais antigos:
    + Tabela
    + TVF
    + Visualizar
    + Estatísticas
* DataLakeStore
  - O registro de rastreamento de `Import-AzureRMDataLakeStoreItem` e `Export-AzureRMDataLakeStoreItem` foi desabilitado por padrão para melhorar o desempenho. Caso registro de rastreamento seja desejável, utilize os parâmetros `-DiagnosticLogLevel` e `-DiagnosticLogPath`
  - O bug que ocasionalmente fazia com que o PowerShell falhasse ao fazer o upload de vários arquivos pequenos para o ADLS foi corrigido.
* EventHub
  - Correção de bug:
    + Correção do erro do cmdlet Set-AzureRmEventHubNamespace – 'Tier' não pode ser null, quando deve ser 'SkuName'
    + Set-AzureRmEventHub – Correção do erro “A referência do objeto não está definida como uma instância de um objeto” ao atualizar o EventHub
* Insights
  - Add-AzureRm*AlertRule
    + Retorna um único objeto: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + Agora, a saída é numerada, em vez de considerada um único objeto. O tipo não foi alterado, ainda é uma lista.
  - Remove-AzureRmAlertRule
    + O statusCode segue o código de status retornado pela solicitação, antes era sempre Ok.
  - Add-AzureRmAutoscaleSetting
    + Agora, retorna um objeto único (e não uma lista, como antes) que contém statusCode, requestId e o recurso criado/atualizado recentemente.
    + O código de status segue o status retornado pela solicitação, antes era sempre Ok.
  - New-AzureRmAutoscaleRule
    + O parâmetro ScaleActionType foi estendido e agora recebe os seguintes valores: ChangeCount, PercentChangeCount e ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + O statusCode na saída segue o statusCode retornado pela solicitação. Antes, era sempre Ok.
  - Get-AzureRMLogProfile
    + Agora, a saída é enumerada. Antes, ela era considerada um objeto único. O tipo da saída ainda é uma lista, como antes.
  - Remove-AzureRmLogProfile
    + O parâmetro PassThru foi implementado.
  - API de Métrica
    + Agora, o SDK recupera métrica do MDM.
  - Get-AzureRmMetricDefinition
    + A saída ainda é uma lista, mas a estrutura dessa lista foi alterada.
  - Get-AzureRmMetric
    + A chamada foi alterada. Esta é a nova sintaxe: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]
    + A saída é uma lista e a estrutura de seus elementos foi alterada.
* KeyVault
  - Adicionar suporte de backup/restauração aos segredos do KeyVault
    + É possível fazer backup e restaurar os segredos, de acordo com a funcionalidade que dá suporte para as Chaves atualmente

  - Os cmdlets de backup para Chaves e Segredos agora aceitam um objeto correspondente como um parâmetro de entrada
    + O chamador pode encadear operações de backup e recuperação: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - Agora, os cmdlets de backup oferecem suporte a um comutador -Force para substituir um arquivo existente
    + Observe que a tentativa de substituir um arquivo existente não lançará mais e, em vez disso, solicitará que o usuário escolha como proceder.
* LogicApp
  - Novos parâmetros para os cmdlets de recuperação de desastre de Número de Controle de Intercâmbio:
    + Parâmetro opcional -AgreementType (“X12” ou “Edifact”) para especificar os números de controle relevantes
* MachineLearning
  - Use a nova versão do SDK .Net do Azure Machine Learning e adicione um novo cmdlet
    + Add-AzureRmMlWebServiceRegionalProperty
  - Pequenas correções de palavras no texto de ajuda.
* Rede
  - Cmdlet Test-AzureRmNetworkWatcherConnectivity
    + Retorna informações de conectividade para uma VM de origem especificada e um destino
    + Se a conectividade entre a origem e o destino não puder ser estabelecida, o cmdlet retornará detalhes sobre o problema
* Perfil
  - O cmdlet Send-Feedback adicionado: permite que o usuário inicie um conjunto de prompts que enviam comentários à equipe do Azure PowerShell.
  - Os aliases a seguir foram removidos, pois entravam em conflito com os nomes de cmdlet existentes no módulo do Azure:
    + `Enable-AzureDataCollection` (com suporte de `Enable-AzureRmDataCollection`)
    + `Disable-AzureDataCollection` (com suporte de `Disable-AzureRmDataCollection`)
* Retransmissão
  - Adiciona cmdlets à Retransmissão do Azure, o que permite que os usuários criem e gerenciem todos os recursos da Retransmissão do Azure.
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
* Recursos
  - Suporte para implantações de grupo de recursos cruzados do New-AzureRmResourceGroupDeployment
    + Agora, os usuários podem usar implantações aninhadas para implantar grupos de recursos diferentes.
* ServiceBus

  - Correção de bug: Os valores de propriedade do objeto de fila ServiceBus foram definidos como null, o objeto é utilizado como parâmetro de entrada no cmdlet Set-AzureRmServiceBusQueue para atualizar a fila.
   - As propriedades afetadas são LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount e MessageCount
* ServiceFabric

  - Cmdlets adicionadas ao Service Fabric
    + Add-AzureRmServiceFabricApplicationCertificate Adiciona um certificado que será utilizado como certificado de aplicativo
    + Add-AzureRmServiceFabricClientCertificate Adiciona um nome comum ou impressão digital às configurações do cluster para a autenticação de cliente
    + Add-AzureRmServiceFabricClusterCertificate Adiciona um certificado de cluster secundário ao cluster a fim de sobrepor o certificado existente
    + Add-AzureRmServiceFabricNodes Adiciona nós/VMs de um tipo específico de nó a um cluster
    + Add-AzureRmServiceFabricNodeType Adiciona um tipo de nó/VMs a um cluster existente
    + Get-AzureRmServiceFabricCluster       Obtém os detalhes do recurso do cluster
    + New-AzureRmServiceFabricCluster Cria um novo cluster ServiceFabric. Esse comando tem muitas sobrecargas para cobrir vários cenários
    + Remove-AzureRmServiceFabricClientCertificate       Impede que um certificado de cliente seja usado para acessar um cluster
    + Remove-AzureRmServiceFabricClusterCertificate       Impede que um certificado de cluster seja usado para a segurança de um cluster
    + Remove-AzureRmServiceFabricNodes Remove nós de um tipo de nó específico de um cluster
    + Remove-AzureRmServiceFabricNodeType       Remove um tipo de nó de um cluster
    + Remove-AzureRmServiceFabricSettings       Remove uma ou mais configurações do ServiceFabric de um cluster
    + Set-AzureRmServiceFabricSettings       Adiciona ou atualiza uma ou mais configurações do ServiceFabric de um cluster
    + Set-AzureRmServiceFabricUpgradeType Altera o tipo de atualização do ServiceFabric de um cluster
    + Update-AzureRmServiceFabricDurability Altera a camada de durabilidade de um cluster
    + Update-AzureRmServiceFabricReliability Altera a camada de confiabilidade de um cluster
* Sql
  - Parâmetro -SampleName adicionado ao New-AzureRmSqlDatabase
  - Atualizações para os cmdlets de Grupo de Failover
  - Remover os parâmetros 'Tag'
  - Remover os parâmetros 'PartnerResourceGroupName' e 'PartnerServerName' do cmdlet Remove-AzureRmSqlDatabaseFailoverGroup
  - Adicionar o parâmetro 'GracePeriodWithDataLossHours' aos cmdlets New- e Set-, que no devido tempo substituirão 'GracePeriodWithDataLossHour'
  - A documentação foi elaborada e atualizada
  - Alterar a formatação de objetos retornados e corrigir alguns bugs em que os campos nem sempre foram preenchidos
  - Adicionar as propriedades 'DatabaseNames' e 'PartnerLocation' ao objeto Grupo de Failover
  - Corrigir o bug, fazendo com que o cmdlet Switch- retorne imediatamente, em vez de aguardar a conclusão da operação
  - Corrigir o bug de estouro do inteiro quando os valores do período de carência forem utilizados
  - Ajustar o período de carência para um mínimo de 1 hora se um valor menor for fornecido
  - Remover "Usage_Anomaly" dos valores aceitos do parâmetro "ExcludedDetectionType" dos cmdlets Set-AzureRmSqlDatabaseThreatDetectionPolicy e Set-AzureRmSqlServerThreatDetectionPolicy.
* Armazenamento
  - Atualizar o SDK da política SRP para 6.3.0
  - New/Set-AzureRmStorageAccount: Adicionar um novo parâmetro com suporte para EnableHttpsTrafficOnly
  - New/Set/Get-AzureRmStorageAccount: A conta de armazenamento retornada contém um novo atributo EnableHttpsTrafficOnly
* Azure.Storage
  - Atualizar para a Biblioteca do Cliente do Armazenamento do Azure 8.1.1 e Biblioteca de Movimentação de Dados do Armazenamento do Azure 0.5.1
  - Adicionar um novo cmdlet para oferecer suporte ao recurso de Cópia Incremental do blob
