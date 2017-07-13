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
# <a name="release-notes"></a>Notas de versão

É uma lista das alterações feitas nesta versão do Azure PowerShell.

## <a name="version-400"></a>Versão 4.0.0

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
