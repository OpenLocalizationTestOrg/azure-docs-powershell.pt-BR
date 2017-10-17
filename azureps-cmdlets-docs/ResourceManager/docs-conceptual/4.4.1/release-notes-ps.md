Instalador do Azure PowerShell 4.3.1: [link](https://github.com/Azure/azure-powershell/releases/download/v4.3.1-August2017/azure-powershell.4.3.1.msi)

Módulo de galeria para cmdlets do ARM: [link](https://www.powershellgallery.com/packages/AzureRM/4.3.1)

Módulo de galeria para cmdlets herdados para gerenciamento de serviço (RDFE): [link](https://www.powershellgallery.com/packages/Azure/4.3.1)

## <a name="changes-in-431"></a>Alterações no 4.3.1

- Foi corrigido o problema com determinados assemblies que não eram assinados, resultando em um erro `could not load file or assembly` quando os módulos eram importados

## <a name="changes-in-430"></a>Alterações no 4.3.0

* AnalysisServices
    * Bug corrigido em Set-AzureRmAnalysisServciesServer
        - Quando o administrador não for fornecido, o administrador será removido.
    * BackupBlobContainerUri foi incluído em New-AzureRmAnalysisServicesServer e em Set-AzureRmAnalysisServicesServer
        - Habilitar para definir/desabilitar o contêiner de blobs de backup para backup/restauração do Azure Analysis Services Server
    * A pesquisa de SKU foi atualizada em New-AzureRmAnalysisServicesServer e em Set-AzureRmAnalysisServicesServer
        - A SKU embutida em código foi alterada para consulta dinâmica.
    * Add-AzureAnalysisServicesAccount para dar suporte a logon com entidade de serviço
* Automação
    * Foram feitas alterações nos cmdlets AutomationDSC* para efetuar pull de mais de 100 registros
    * Foi resolvido o problema em que os fluxos detalhados param de funcionar depois de chamar alguns cmdlets de Automação (por exemplo, Get-AzureRmAutomationVariable, Get-AzureRmAutomationJob).
    * Foi incluído suporte para controle de versão de build de NodeConfiguration em StartAzureAutomationDscCompilationJob e em ImportAzureAutomationDscNodeConfiguration.
    * Correções de bug de problemas existentes – corrige o problema de alias n° 3775 e o alias runOn e o suporte para HybridWorkers.
* Computação
    * Set-AzureRmVMAEMExtension: adicionar suporte para novos tamanhos de disco Premium
    * Set-AzureRmVMAEMExtension: adicionar suporte para a série M
    * Adicionar o parâmetro ForceUpdateTag em AzureRmVmssExtension
    * Adicionar o parâmetro primário em New-AzureRmVmssIpConfig
    * Adicionar o parâmetro EnableAcceleratedNetworking em Add-AzureRmVmssNetworkInterfaceConfig
    * Adicionar InstanceId em Set-AzureRmVmss
    * Expor MaintenanceRedeployStatus para a saída de Get-AzureRmVM -Status
    * Expor a restrição e a capacidade para o formato de tabela de Get-AzureRmComputeResourceSku
* DataLakeStore
    * Correção do problema: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
    * A propriedade ResourceGroup foi adicionada em NamespaceAttributes
        - 'ResourceGroup' obtém o nome do grupo de recursos em que o Namespace está
    * os commandlets foram atualizados com novo parâmetro e alias de parâmetro
        - os cmdlets abaixo foram atualizados com Parametersets para Namespace e EventHub para a operação de AuthorizationRule
        - New-AzureRmEventHubAuthorizationRule
            + Adiciona uma nova AuthorizationRule ao NameSpace ou ao EventHub existente.
        - Get-AzureRmEventHubAuthorizationRule
            + Obtém a AuthorizationRule/Lista de AuthorizationRules para o NameSpace ou o EventHub existente.
        - Set-AzureRmEventHubAuthorizationRule
            + Atualiza as propriedades da AuthorizationRule existente do NameSpace do EventHub.
        - Remove-AzureRmEventHubAuthorizationRule
            + Exclui a AuthorizationRule existente do NameSpace ou do EventHub existente.
        - New-AzureRmEventHubKey
            + Gera uma nova chave primária/secundária para a AuthorizationRule do NameSpace ou do EventHub existente.
        - Get-AzureRmEventHubKey
            + Obtém a chave primária/secundária para a AuthorizationRule do NameSpace ou do EventHub existente.
* Rede
    * New-AzureRmExpressRouteCircuitPeeringConfig: foi adicionado o suporte para IPv6. Novo parâmetro opcional adicional
        - PeerAddressType
    * Set-AzureRmExpressRouteCircuitPeeringConfig: foi adicionado o suporte para IPv6. Novo parâmetro opcional adicional
        - PeerAddressType
    * Remove-AzureRmExpressRouteCircuitPeeringConfig: foi adicionado o suporte para IPv6. Novo parâmetro opcional adicional
        - PeerAddressType
    * O parâmetro -ProbeEnabled foi marcado como obsoleto
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Perfil
    * A coleta de dados foi habilitada por padrão. Os dados de uso são coletados pela Microsoft para aprimorar a experiência do usuário. Os dados são anônimos e não incluem os valores de argumento da linha de comando.
        - Use o cmdlet Disable-AzureRmDataCollection para desativar o recurso
        - Use o cmdlet Enable-AzureRmDataCollection para ativar esse recurso
* Recursos
    * Adicionar suporte para validação de escopos para os seguintes commandlets, roledefinition e roleassignment antes de enviar a solicitação para ARM
        - Get-AzureRMRoleAssignment
        - New-AzureRMRoleAssignment
        - Remove-AzureRMRoleAssignment
        - Get-AzureRMRoleDefinition
        - New-AzureRMRoleDefinition
        - Remove-AzureRMRoleDefinition
        - Set-AzureRMRoleDefinition
* ServiceBus
    * Foram adicionados os novos commandlets abaixo para AuthorizationRules de NameSpace, Fila e Tópico. de acordo com o conjunto de parâmetros, as operações de regra de autorização são executadas.
     - New-AzureRmServiceBusAuthorizationRule
       - Adiciona uma nova AuthorizationRule para o NameSpace/a Fila/o Tópico do ServiceBus existente.
     - Get-AzureRmServiceBusAuthorizationRule
       - Obtém a AuthorizationRule/Lista de AuthorizationRules para o NameSpace/a Fila/o Tópico do ServiceBus existente.
     - Set-AzureRmServiceBusAuthorizationRule
       - Atualiza as propriedades da AuthorizationRule existente do NameSpace/da Fila/do Tópico do Servicebus.
     - New-AzureRmServiceBusKey
       - Gera uma nova chave primária/secundária para AuthorizationRule do NameSpace/da Fila/do Tópico do ServiceBus existente.
     - Get-AzureRmServiceBusKey
       - Obtém uma chave primária/secundária para AuthorizationRule do NameSpace/da Fila/do Tópico do ServiceBus existente.
     - Remove-AzureRmServiceBusNamespaceAuthorizationRule
       - Exclui a AuthorizationRule existente do NameSpace/da Fila/do Tópico do ServiceBus.
    * Foi adicionada a propriedade do grupo de recursos em NamespceAttributes
* Sql
    * Set-AzureRmSqlServerTransparentDataEncryptionProtector está sendo atualizado para exibir um aviso e solicitar a confirmação se o tipo de protetor de criptografia estiver sendo definido como AzureKeyVault
    * Novo cmdlets atualizados foram adicionados nas configurações de auditoria
        - Adicionando o cmdlet Get-AzureRmSqlDatabaseAuditing que obtém as configurações de auditoria de um banco de dados SQL Azure.
        - Adicionando o cmdlet Get-AzureRmSqlServerAuditing que obtém as configurações de auditoria de um SQL Server do Azure.
        - Adicionando o cmdlet Set-AzureRmSqlDatabaseAuditing que altera as configurações de auditoria para um banco de dados SQL Azure.
        - Adicionando o cmdlet Set-AzureRmSqlServerAuditing que altera as configurações de auditoria de um SQL Server do Azure.
    * Os cmdlets de política de auditoria existentes foram preteridos
        - Get-AzureRmSqlDatabaseAuditingPolicy foi preterido
        - Get-AzureRmSqlServerAuditingPolicy foi preterido
        - Set-AzureRmSqlDatabaseAuditingPolicy foi preterido
        - Set-AzureRmSqlServerAuditingPolicy foi preterido
        - Use-AzureRmSqlServerAuditingPolicy foi preterido
        - Remove-AzureRmSqlDatabaseAuditing foi preterido
        - Remove-AzureRmSqlServerAuditing foi preterido
    * A análise do arquivo de esquema de Update-AzureRmSqlSyncGroup não diferencia mais maiúsculas de minúsculas.
* Armazenamento
    * Adicionar suporte a NeworkRule para cmdlets de conta de armazenamento de modo de recurso
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount
        - Get-AzureRmStorageAccountNetworkRuleSet
        - Update-AzureRmStorageAccountNetworkRuleSet
        - Add-AzureRmStorageAccountNetworkRule
        - Remove-AzureRmStorageAccountNetworkRule

Exibir [as alterações desde a última versão](https://github.com/Azure/azure-powershell/compare/v4.2.1-July2017...v4.3.1-August2017)
