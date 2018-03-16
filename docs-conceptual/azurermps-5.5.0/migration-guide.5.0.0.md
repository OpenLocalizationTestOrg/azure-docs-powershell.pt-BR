# <a name="breaking-changes-for-microsoft-azure-powershell-500"></a><span data-ttu-id="fbc4f-101">Alterações interruptivas no Microsoft Azure PowerShell 5.0.0</span><span class="sxs-lookup"><span data-stu-id="fbc4f-101">Breaking changes for Microsoft Azure PowerShell 5.0.0</span></span>

<span data-ttu-id="fbc4f-102">Este documento serve como uma notificação de alterações interruptivas e como um guia de migração para consumidores dos cmdlets do Microsoft Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-102">This document serves as both a breaking change notification and migration guide for consumers of the Microsoft Azure PowerShell cmdlets.</span></span> <span data-ttu-id="fbc4f-103">Cada seção descreve o motivo da alteração significativa e o caminho de migração de menor resistência.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-103">Each section describes both the impetus for the breaking change and the migration path of least resistance.</span></span> <span data-ttu-id="fbc4f-104">Para obter um contexto detalhado, consulte a solicitação de pull associada a cada alteração.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-104">For in-depth context, please refer to the pull request associated with each change.</span></span>

## <a name="table-of-contents"></a><span data-ttu-id="fbc4f-105">Sumário</span><span class="sxs-lookup"><span data-stu-id="fbc4f-105">Table of Contents</span></span>

- [<span data-ttu-id="fbc4f-106">Alterações interruptivas em cmdlets de ApiManagement</span><span class="sxs-lookup"><span data-stu-id="fbc4f-106">Breaking changes to ApiManagement cmdlets</span></span>](#breaking-changes-to-apimanagement-cmdlets)
- [<span data-ttu-id="fbc4f-107">Alterações interruptivas em cmdlets do Lote</span><span class="sxs-lookup"><span data-stu-id="fbc4f-107">Breaking changes to Batch cmdlets</span></span>](#breaking-changes-to-batch-cmdlets)
- [<span data-ttu-id="fbc4f-108">Alterações interruptivas em cmdlets de Computação</span><span class="sxs-lookup"><span data-stu-id="fbc4f-108">Breaking changes to Compute cmdlets</span></span>](#breaking-changes-to-compute-cmdlets)
- [<span data-ttu-id="fbc4f-109">Alterações interruptivas em cmdlets do Hub de Eventos</span><span class="sxs-lookup"><span data-stu-id="fbc4f-109">Breaking changes to EventHub cmdlets</span></span>](#breaking-changes-to-eventhub-cmdlets)
- [<span data-ttu-id="fbc4f-110">Alterações interruptivas em cmdlets do Insights</span><span class="sxs-lookup"><span data-stu-id="fbc4f-110">Breaking changes to Insights cmdlets</span></span>](#breaking-changes-to-insights-cmdlets)
- [<span data-ttu-id="fbc4f-111">Alterações interruptivas em cmdlets de Rede</span><span class="sxs-lookup"><span data-stu-id="fbc4f-111">Breaking changes to Network cmdlets</span></span>](#breaking-changes-to-network-cmdlets)
- [<span data-ttu-id="fbc4f-112">Alterações interruptivas em cmdlets de Recursos</span><span class="sxs-lookup"><span data-stu-id="fbc4f-112">Breaking changes to Resources cmdlets</span></span>](#breaking-changes-to-resources-cmdlets)
- [<span data-ttu-id="fbc4f-113">Alterações interruptivas em mdlets do ServiceBus</span><span class="sxs-lookup"><span data-stu-id="fbc4f-113">Breaking Changes to ServiceBus Cmdlets</span></span>](#breaking-changes-to-servicebus-cmdlets)

## <a name="breaking-changes-to-apimanagement-cmdlets"></a><span data-ttu-id="fbc4f-114">Alterações interruptivas em cmdlets de ApiManagement</span><span class="sxs-lookup"><span data-stu-id="fbc4f-114">Breaking changes to ApiManagement cmdlets</span></span>

### <a name="new-azurermapimanagementbackendproxy"></a><span data-ttu-id="fbc4f-115">**New-AzureRmApiManagementBackendProxy**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-115">**New-AzureRmApiManagementBackendProxy**</span></span>
- <span data-ttu-id="fbc4f-116">Os parâmetros "UserName" e "Password" foram substituídos por uma PSCredential</span><span class="sxs-lookup"><span data-stu-id="fbc4f-116">Parameters "UserName" and "Password" are being replaced in favor of a PSCredential</span></span>

```powershell
# Old
New-AzureRmApiManagementBackendProxy [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
New-AzureRmApiManagementBackendProxy [other required parameters] -Credential $PSCredentialVariable
```

### <a name="new-azurermapimanagementuser"></a><span data-ttu-id="fbc4f-117">**New-AzureRmApiManagementUser**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-117">**New-AzureRmApiManagementUser**</span></span>
- <span data-ttu-id="fbc4f-118">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-118">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapimanagementuser"></a><span data-ttu-id="fbc4f-119">**Set-AzureRmApiManagementUser**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-119">**Set-AzureRmApiManagementUser**</span></span>
- <span data-ttu-id="fbc4f-120">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-120">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Set-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-batch-cmdlets"></a><span data-ttu-id="fbc4f-121">Alterações interruptivas nos cmdlets do Lote</span><span class="sxs-lookup"><span data-stu-id="fbc4f-121">Breaking changes to Batch cmdlets</span></span>

### <a name="new-azurebatchcertificate"></a><span data-ttu-id="fbc4f-122">**New-AzureBatchCertificate**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-122">**New-AzureBatchCertificate**</span></span>
- <span data-ttu-id="fbc4f-123">O parâmetro `Password` foi substituído por uma cadeia de caracteres Secure</span><span class="sxs-lookup"><span data-stu-id="fbc4f-123">Parameter `Password` being replaced in favor of a Secure string</span></span>

```powershell
# Old
New-AzureBatchCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureBatchCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchcomputenodeuser"></a><span data-ttu-id="fbc4f-124">**New-AzureBatchComputeNodeUser**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-124">**New-AzureBatchComputeNodeUser**</span></span>
- <span data-ttu-id="fbc4f-125">O parâmetro `Password` foi substituído por uma cadeia de caracteres Secure</span><span class="sxs-lookup"><span data-stu-id="fbc4f-125">Parameter `Password` being replaced in favor of a Secure string</span></span>

```powershell
# Old
New-AzureBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
New-AzureBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermbatchcomputenodeuser"></a><span data-ttu-id="fbc4f-126">**Set-AzureRmBatchComputeNodeUser**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-126">**Set-AzureRmBatchComputeNodeUser**</span></span>
- <span data-ttu-id="fbc4f-127">O parâmetro `Password` foi substituído por uma cadeia de caracteres Secure</span><span class="sxs-lookup"><span data-stu-id="fbc4f-127">Parameter `Password` being replaced in favor of a Secure string</span></span>

```powershell
# Old
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchtask"></a><span data-ttu-id="fbc4f-128">**New-AzureBatchTask**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-128">**New-AzureBatchTask**</span></span>
 - <span data-ttu-id="fbc4f-129">A opção `RunElevated` foi removida e substituída por `UserIdentity`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-129">Removed the `RunElevated` switch and replaced it with `UserIdentity`.</span></span>

```powershell
# Old
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -RunElevated $TRUE

# New
$autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
$userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -UserIdentity $userIdentity
```

<span data-ttu-id="fbc4f-130">Isso também afeta a propriedade `RunElevated` em `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask` e `PSJobReleaseTask`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-130">This additionally impacts the `RunElevated` property on `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask`, and `PSJobReleaseTask`.</span></span>

### <a name="psmultiinstancesettings"></a><span data-ttu-id="fbc4f-131">**PSMultiInstanceSettings**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-131">**PSMultiInstanceSettings**</span></span>

- <span data-ttu-id="fbc4f-132">O construtor `PSMultiInstanceSettings` não precisa mais de um parâmetro `numberOfInstances` obrigatório, mas obtém um parâmetro `coordinationCommandLine` obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-132">`PSMultiInstanceSettings` constructor no longer takes a required `numberOfInstances` parameter, instead it takes a required `coordinationCommandLine` parameter.</span></span>

```powershell
# Old
$settings = New-Object Microsoft.Azure.Commands.Batch.Models.PSMultiInstanceSettings -ArgumentList @(2)
$settings.CoordinationCommandLine = "cmd /c echo hello"
New-AzureBatchTask [other parameters] -MultiInstanceSettings $settings

# New
$settings = New-Object Microsoft.Azure.Commands.Batch.Models.PSMultiInstanceSettings -ArgumentList @("cmd /c echo hello", 2)
New-AzureBatchTask [other parameters] -MultiInstanceSettings $settings
```

### <a name="get-azurebatchtask"></a><span data-ttu-id="fbc4f-133">**Get-AzureBatchTask**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-133">**Get-AzureBatchTask**</span></span>
 - <span data-ttu-id="fbc4f-134">A propriedade `RunElevated` foi removida em `PSCloudTask`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-134">Removed the `RunElevated` property on `PSCloudTask`.</span></span> <span data-ttu-id="fbc4f-135">A propriedade `UserIdentity` foi adicionada para substituir `RunElevated`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-135">The `UserIdentity` property has been added to replace `RunElevated`.</span></span>

```powershell
# Old
$task = Get-AzureBatchTask [parameters]
$task.RunElevated

# New
$task = Get-AzureBatchTask [parameters]
$task.UserIdentity.AutoUser.ElevationLevel
```

<span data-ttu-id="fbc4f-136">Isso também afeta a propriedade `RunElevated` em `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask` e `PSJobReleaseTask`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-136">This additionally impacts the `RunElevated` property on `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask`, and `PSJobReleaseTask`.</span></span>

### <a name="multiple-types"></a><span data-ttu-id="fbc4f-137">**Vários tipos**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-137">**Multiple types**</span></span>

- <span data-ttu-id="fbc4f-138">A propriedade `SchedulingError` foi renomeada em `PSExitConditions` para `PreProcessingError`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-138">Renamed the `SchedulingError` property on `PSExitConditions` to `PreProcessingError`.</span></span>

```powershell
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.PreProcessingError
```

### <a name="multiple-types"></a><span data-ttu-id="fbc4f-139">**Vários tipos**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-139">**Multiple types**</span></span>

- <span data-ttu-id="fbc4f-140">A propriedade `SchedulingError` foi renomeada em `PSJobPreparationTaskExecutionInformation`, `PSJobReleaseTaskExecutionInformation`, `PSStartTaskInformation`, `PSSubtaskInformation` e `PSTaskExecutionInformation` para `FailureInformation`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-140">Renamed the `SchedulingError` property on `PSJobPreparationTaskExecutionInformation`, `PSJobReleaseTaskExecutionInformation`, `PSStartTaskInformation`, `PSSubtaskInformation`, and `PSTaskExecutionInformation` to `FailureInformation`.</span></span>
  - <span data-ttu-id="fbc4f-141">`FailureInformation` é retornado sempre que há uma falha de tarefa.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-141">`FailureInformation` is returned any time there is a task failure.</span></span> <span data-ttu-id="fbc4f-142">Isso inclui todos os casos de erro de agendamento anteriores, bem como códigos de saída de tarefa diferentes de zero e falhas de carregamento de arquivo do novo recurso de arquivos de saída.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-142">This includes all previous scheduling error cases, as well as nonzero task exit codes, and file upload failures from the new output files feature.</span></span>
  - <span data-ttu-id="fbc4f-143">Isso é estruturado da mesma forma como antes e, portanto, nenhuma alteração de código será necessária ao usar esse tipo.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-143">This is structured the same as before, so no code change is needed when using this type.</span></span>

```powershell
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.FailureInformation
```

<span data-ttu-id="fbc4f-144">Isso adicionalmente afeta: Get-AzureBatchPool, Get-AzureBatchSubtask e Get-AzureBatchJobPreparationAndReleaseTaskStatus</span><span class="sxs-lookup"><span data-stu-id="fbc4f-144">This additionally impacts: Get-AzureBatchPool, Get-AzureBatchSubtask, and Get-AzureBatchJobPreparationAndReleaseTaskStatus</span></span>

### <a name="new-azurebatchpool"></a><span data-ttu-id="fbc4f-145">**New-AzureBatchPool**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-145">**New-AzureBatchPool**</span></span>
 - <span data-ttu-id="fbc4f-146">`TargetDedicated` foi removido e substituído por `TargetDedicatedComputeNodes` e `TargetLowPriorityComputeNodes`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-146">Removed `TargetDedicated` and replaced it with `TargetDedicatedComputeNodes` and `TargetLowPriorityComputeNodes`.</span></span>
 - <span data-ttu-id="fbc4f-147">`TargetDedicatedComputeNodes` tem um alias `TargetDedicated`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-147">`TargetDedicatedComputeNodes` has an alias `TargetDedicated`.</span></span>

```powershell
# Old
New-AzureBatchPool [other parameters] [-TargetDedicated <Int32>]

# New
New-AzureBatchPool [other parameters] [-TargetDedicatedComputeNodes <Int32>] [-TargetLowPriorityComputeNodes <Int32>]
```

<span data-ttu-id="fbc4f-148">Isso também afeta: Start-AzureBatchPoolResize</span><span class="sxs-lookup"><span data-stu-id="fbc4f-148">This also impacts: Start-AzureBatchPoolResize</span></span>

### <a name="get-azurebatchpool"></a><span data-ttu-id="fbc4f-149">**Get-AzureBatchPool**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-149">**Get-AzureBatchPool**</span></span>
 - <span data-ttu-id="fbc4f-150">As propriedades `TargetDedicated` e `CurrentDedicated` foram renomeadas em `PSCloudPool` para `TargetDedicatedComputeNodes` e `CurrentDedicatedComputeNodes`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-150">Renamed the `TargetDedicated` and `CurrentDedicated` properties on `PSCloudPool` to `TargetDedicatedComputeNodes` and `CurrentDedicatedComputeNodes`.</span></span>

```powershell
# Old
$pool = Get-AzureBatchPool [parameters]
$pool.TargetDedicated
$pool.CurrentDedicated

# New
$pool = Get-AzureBatchPool [parameters]
$pool.TargetDedicatedComputeNodes
$pool.CurrentDedicatedComputeNodes
```

### <a name="type-pscloudpool"></a><span data-ttu-id="fbc4f-151">**Tipo PSCloudPool**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-151">**Type PSCloudPool**</span></span>

- <span data-ttu-id="fbc4f-152">`ResizeError` foi renomeado para `ResizeErrors` em `PSCloudPool` e agora é uma coleção.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-152">Renamed `ResizeError` to `ResizeErrors` on `PSCloudPool`, and it is now a collection.</span></span>

```powershell
# Old
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeError

# New
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeErrors[0]
```

### <a name="new-azurebatchjob"></a><span data-ttu-id="fbc4f-153">**New-AzureBatchJob**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-153">**New-AzureBatchJob**</span></span>
- <span data-ttu-id="fbc4f-154">A propriedade `TargetDedicated` foi renomeada em `PSPoolSpecification` para `TargetDedicatedComputeNodes`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-154">Renamed the `TargetDedicated` property on `PSPoolSpecification` to `TargetDedicatedComputeNodes`.</span></span>

```powershell
# Old
$poolInfo = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
$poolInfo.AutoPoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification.TargetDedicated = 5
New-AzureBatchJob [other parameters] -PoolInformation $poolInfo

# New
$poolInfo = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
$poolInfo.AutoPoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification.TargetDedicatedComputeNodes = 5
New-AzureBatchJob [other parameters] -PoolInformation $poolInfo
```

### <a name="get-azurebatchnodefile"></a><span data-ttu-id="fbc4f-155">**Get-AzureBatchNodeFile**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-155">**Get-AzureBatchNodeFile**</span></span>
 - <span data-ttu-id="fbc4f-156">`Name` foi removido e substituído por `Path`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-156">Removed `Name` and replaced it with `Path`.</span></span>
 - <span data-ttu-id="fbc4f-157">`Path` tem um alias `Name`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-157">`Path` has an alias `Name`.</span></span>

```powershell
# Old
Get-AzureBatchNodeFile [other parameters] [[-Name] <String>]

# New
Get-AzureBatchNodeFile [other parameters] [[-Path] <String>]
```

<span data-ttu-id="fbc4f-158">Isso também afeta: Get-AzureBatchNodeFileContent, Remove-AzureBatchNodeFile</span><span class="sxs-lookup"><span data-stu-id="fbc4f-158">This also impacts: Get-AzureBatchNodeFileContent, Remove-AzureBatchNodeFile</span></span>

### <a name="type-psnodefile"></a><span data-ttu-id="fbc4f-159">Tipo **PSNodeFile**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-159">Type **PSNodeFile**</span></span>

 - <span data-ttu-id="fbc4f-160">A propriedade `Name` foi renomeada em `PSNodeFile` para `Path`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-160">Renamed the `Name` property on `PSNodeFile` to `Path`.</span></span>

```powershell
# Old
$file = Get-AzureBatchNodeFile [parameters]
$file.Name

# New
$file = Get-AzureBatchNodeFile [parameters]
$file.Path
```

### <a name="get-azurebatchsubtask"></a><span data-ttu-id="fbc4f-161">**Get-AzureBatchSubtask**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-161">**Get-AzureBatchSubtask**</span></span>
- <span data-ttu-id="fbc4f-162">As propriedades `PreviousState` e `State` de `PSSubtaskInformation` não são mais do tipo `TaskState`, mas do tipo `SubtaskState`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-162">The `PreviousState` and `State` properties of `PSSubtaskInformation` are no longer of type `TaskState`, instead they are of type `SubtaskState`.</span></span>
  - <span data-ttu-id="fbc4f-163">Ao contrário de `TaskState`, `SubtaskState` não tem nenhum valor `Active`, pois subtarefas não podem ficar em um estado `Active`.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-163">Unlike `TaskState`, `SubtaskState` has no `Active` value, since it is not possible for subtasks to be in an `Active` state.</span></span>

```powershell
# Old
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.TaskState.Running) { }

# New
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.SubtaskState.Running) { }
```

## <a name="breaking-changes-to-compute-cmdlets"></a><span data-ttu-id="fbc4f-164">Alterações interruptivas em cmdlets de Computação</span><span class="sxs-lookup"><span data-stu-id="fbc4f-164">Breaking changes to Compute cmdlets</span></span>

### <a name="set-azurermvmaccessextension"></a><span data-ttu-id="fbc4f-165">**Set-AzureRmVMAccessExtension**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-165">**Set-AzureRmVMAccessExtension**</span></span>
- <span data-ttu-id="fbc4f-166">Os parâmetros "UserName" e "Password" foram substituídos por uma PSCredential</span><span class="sxs-lookup"><span data-stu-id="fbc4f-166">Parameters "UserName" and "Password" are being replaced in favor of a PSCredential</span></span>

```powershell
# Old
Set-AzureRmVMAccessExtension [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
Set-AzureRmVMAccessExtension [other required parameters] -Credential $PSCredential
```

## <a name="breaking-changes-to-eventhub-cmdlets"></a><span data-ttu-id="fbc4f-167">Alterações interruptivas em cmdlets do Hub de Eventos</span><span class="sxs-lookup"><span data-stu-id="fbc4f-167">Breaking changes to EventHub cmdlets</span></span>

### <a name="new-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-168">**New-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-168">**New-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-169">O cmdlet 'New-AzureRmEventHubNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-169">The 'New-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-170">Use o cmdlet 'New-AzureRmEventHubAuthorizationRule'</span><span class="sxs-lookup"><span data-stu-id="fbc4f-170">Please use the 'New-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="get-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-171">**Get-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-171">**Get-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-172">O cmdlet 'Get-AzureRmEventHubNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-172">The 'Get-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-173">Use o cmdlet 'Get-AzureRmEventHubAuthorizationRule'</span><span class="sxs-lookup"><span data-stu-id="fbc4f-173">Please use the 'Get-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="set-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-174">**Set-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-174">**Set-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-175">O cmdlet 'Set-AzureRmEventHubNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-175">The 'Set-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-176">Use o cmdlet 'Set-AzureRmEventHubAuthorizationRule'</span><span class="sxs-lookup"><span data-stu-id="fbc4f-176">Please use the 'Set-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="remove-azurermeventhubnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-177">**Remove-AzureRmEventHubNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-177">**Remove-AzureRmEventHubNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-178">O cmdlet 'Remove-AzureRmEventHubNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-178">The 'Remove-AzureRmEventHubNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-179">Use o cmdlet 'Remove-AzureRmEventHubAuthorizationRule'</span><span class="sxs-lookup"><span data-stu-id="fbc4f-179">Please use the 'Remove-AzureRmEventHubAuthorizationRule' cmdlet</span></span>
    
### <a name="new-azurermeventhubnamespacekey"></a><span data-ttu-id="fbc4f-180">**New-AzureRmEventHubNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-180">**New-AzureRmEventHubNamespaceKey**</span></span>
- <span data-ttu-id="fbc4f-181">O cmdlet 'New-AzureRmEventHubNamespaceKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-181">The 'New-AzureRmEventHubNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-182">Use o cmdlet 'New-AzureRmEventHubKey'</span><span class="sxs-lookup"><span data-stu-id="fbc4f-182">Please use the 'New-AzureRmEventHubKey' cmdlet</span></span>
    
### <a name="get-azurermeventhubnamespacekey"></a><span data-ttu-id="fbc4f-183">**Get-AzureRmEventHubNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-183">**Get-AzureRmEventHubNamespaceKey**</span></span>
- <span data-ttu-id="fbc4f-184">O cmdlet 'Get-AzureRmEventHubNamespaceKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-184">The 'Get-AzureRmEventHubNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-185">Use o cmdlet 'Get-AzureRmEventHubKey'</span><span class="sxs-lookup"><span data-stu-id="fbc4f-185">Please use the 'Get-AzureRmEventHubKey' cmdlet</span></span>
    
### <a name="new-azurermeventhubnamespace"></a><span data-ttu-id="fbc4f-186">**New-AzureRmEventHubNamespace**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-186">**New-AzureRmEventHubNamespace**</span></span>
- <span data-ttu-id="fbc4f-187">As propriedades 'Status' e 'Enabled' de NamespceAttributes serão removidas.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-187">The property 'Status' and 'Enabled' from the NamespceAttributes will be removed.</span></span> 

```powershell
# Old
# The $namespace has Status and Enabled property  
$namespace = New-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property    
$namespace = Get-AzureRmEventHubNamespace <parameters>
```
    
### <a name="get-azurermeventhubnamespace"></a><span data-ttu-id="fbc4f-188">**Get-AzureRmEventHubNamespace**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-188">**Get-AzureRmEventHubNamespace**</span></span>
- <span data-ttu-id="fbc4f-189">As propriedades 'Status' e 'Enabled' de NamespceAttributes serão removidas.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-189">The property 'Status' and 'Enabled' from the NamespceAttributes will be removed.</span></span> 

```powershell
# Old
# The $namespace has Status and Enabled property 
$namespace = Get-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property    
$namespace = Get-AzureRmEventHubNamespace <parameters>
```
    
### <a name="set-azurermeventhubnamespace"></a><span data-ttu-id="fbc4f-190">**Set-AzureRmEventHubNamespace**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-190">**Set-AzureRmEventHubNamespace**</span></span>
- <span data-ttu-id="fbc4f-191">As propriedades 'Status' e 'Enabled' de NamespceAttributes serão removidas.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-191">The property 'Status' and 'Enabled' from the NamespceAttributes will be removed.</span></span> 

```powershell
# Old
# The $namespace has Status and Enabled property 
$namespace = Set-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property    
$namespace = Set-AzureRmEventHubNamespace <parameters>
``` 
  
### <a name="new-azurermeventhubconsumergroup"></a><span data-ttu-id="fbc4f-192">**New-AzureRmEventHubConsumerGroup**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-192">**New-AzureRmEventHubConsumerGroup**</span></span>
- <span data-ttu-id="fbc4f-193">A propriedade 'EventHubPath' de ConsumerGroupAttributes será removida.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-193">The property 'EventHubPath' from the ConsumerGroupAttributes will be removed.</span></span>

```powershell
# Old
# The $consumergroup has EventHubPath property 
$consumergroup = New-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property    
$consumergroup = New-AzureRmEventHubConsumerGroup <parameters>
```
    
### <a name="set-azurermeventhubconsumergroup"></a><span data-ttu-id="fbc4f-194">**Set-AzureRmEventHubConsumerGroup**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-194">**Set-AzureRmEventHubConsumerGroup**</span></span>
- <span data-ttu-id="fbc4f-195">A propriedade 'EventHubPath' de ConsumerGroupAttributes será removida.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-195">The property 'EventHubPath' from the ConsumerGroupAttributes will be removed.</span></span>

```powershell
# Old
# The $consumergroup has EventHubPath property 
$consumergroup = Set-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property    
$consumergroup = Set-AzureRmEventHubConsumerGroup <parameters>
```
    
### <a name="get-azurermeventhubconsumergroup"></a><span data-ttu-id="fbc4f-196">**Get-AzureRmEventHubConsumerGroup**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-196">**Get-AzureRmEventHubConsumerGroup**</span></span>
- <span data-ttu-id="fbc4f-197">A propriedade 'EventHubPath' de ConsumerGroupAttributes será removida.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-197">The property 'EventHubPath' from the ConsumerGroupAttributes will be removed.</span></span>

```powershell
# Old
# The $consumergroup has EventHubPath property 
$consumergroup = Get-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property    
$consumergroup = Get-AzureRmEventHubConsumerGroup <parameters>
```

## <a name="breaking-changes-to-insights-cmdlets"></a><span data-ttu-id="fbc4f-198">Alterações interruptivas em cmdlets do Insights</span><span class="sxs-lookup"><span data-stu-id="fbc4f-198">Breaking changes to Insights cmdlets</span></span>

### <a name="add-azurermlogalertrule"></a><span data-ttu-id="fbc4f-199">**Add-AzureRMLogAlertRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-199">**Add-AzureRMLogAlertRule**</span></span>
- <span data-ttu-id="fbc4f-200">O cmdlet **Add-AzureRMLogAlertRule** foi preterido</span><span class="sxs-lookup"><span data-stu-id="fbc4f-200">The **Add-AzureRMLogAlertRule** cmdlet has been deprecated</span></span>
- <span data-ttu-id="fbc4f-201">Depois de 1º de outubro, o uso desse cmdlet não terá qualquer efeito, já que essa funcionalidade está sendo transferida para os Alertas de Log de Atividade.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-201">After October 1st using this cmdlet will no longer have any effect as this functionality is being transitioned to Activity Log Alerts.</span></span> <span data-ttu-id="fbc4f-202">Consulte https://aka.ms/migratemealerts para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-202">Please see https://aka.ms/migratemealerts for more information.</span></span>

### <a name="get-azurermusage"></a><span data-ttu-id="fbc4f-203">**Get-AzureRMUsage**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-203">**Get-AzureRMUsage**</span></span>
- <span data-ttu-id="fbc4f-204">O cmdlet **Get-AzureRMUsage** foi preterido</span><span class="sxs-lookup"><span data-stu-id="fbc4f-204">The **Get-AzureRMUsage** cmdlet has been deprecated</span></span>

### <a name="get-azurermalerthistory--get-azurermautoscalehistory--get-azurermlogs"></a><span data-ttu-id="fbc4f-205">**Get-AzureRmAlertHistory** / **Get-AzureRmAutoscaleHistory** / **Get-AzureRmLogs**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-205">**Get-AzureRmAlertHistory** / **Get-AzureRmAutoscaleHistory** / **Get-AzureRmLogs**</span></span>
- <span data-ttu-id="fbc4f-206">Alteração de saída: o campo EventChannels do objeto EventData (retornado por esses cmdlets) foi preterido porque agora retorna um valor constante (Admin, Operation).</span><span class="sxs-lookup"><span data-stu-id="fbc4f-206">Output change: The field EventChannels from the EventData object (returned by these cmdlets) is being deprecated since it now returns a constant value (Admin,Operation.)</span></span>

### <a name="get-azurermalertrule"></a><span data-ttu-id="fbc4f-207">**Get-AzureRmAlertRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-207">**Get-AzureRmAlertRule**</span></span>
- <span data-ttu-id="fbc4f-208">Alteração de saída: a saída desse cmdlet será bidirecional, ou seja, a eliminação do campo de propriedades para melhorar a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-208">Output change: The output of this cmdlet will be flattened, i.e. elimination of the properties field, to improve the user experience.</span></span>

```powershell
# Old
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -Foreground Red "Error updating alert rule"
    Write-Host $rules[0].Id
    Write-Host $rules[0].Properties.IsEnabled
    Write-Host $rules[0].Properties.Condition
}

# New
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -Foreground red "Error updating alert rule"
    Write-Host $rules[0].Id

    # Properties will remain for a while
    Write-Host $rules[0].Properties.IsEnabled
      
    # But the properties will be at the top level too. Later Properties will be removed
    Write-Host $rules[0].IsEnabled
    Write-Host $rules[0].Condition
}
```

### <a name="get-azurermautoscalesetting"></a><span data-ttu-id="fbc4f-209">**Get-AzureRmAutoscaleSetting**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-209">**Get-AzureRmAutoscaleSetting**</span></span>
- <span data-ttu-id="fbc4f-210">Alteração de saída: o campo AutoscaleSettingResourceName será preterido porque é sempre igual ao campo Name.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-210">Output change: The AutoscaleSettingResourceName field will be deprecated since it always equals the Name field.</span></span>

```powershell
# Old
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
if ($s1.AutoscaleSettingResourceName -ne $s1.Name)
{
    Write-Host "There is something wrong with the name"
}

# New
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
    
# there won't be a AutoscaleSettingResourceName
Write-Host $s1.Name    
```

### <a name="remove-azurermalertrule--remove-azurermlogprofile"></a><span data-ttu-id="fbc4f-211">**Remove-AzureRmAlertRule** / **Remove-AzureRmLogProfile**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-211">**Remove-AzureRmAlertRule** / **Remove-AzureRmLogProfile**</span></span>
- <span data-ttu-id="fbc4f-212">Alteração de saída: o tipo da saída será alterado para retornar um único objeto que contém a ID da solicitação e o código de status.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-212">Output change: The type of the output will change to return a single object containing the request Id and the status code.</span></span>

```powershell
# Old
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name $ruleName
if ($s1 -ne $null)
{
    $r = $s1[0].RequestId
    $s = $s1[0].StatusCode
}

# New
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name $ruleName
$r = $s1.RequestId
$s = $s1.StatusCode
```

## <a name="breaking-changes-to-network-cmdlets"></a><span data-ttu-id="fbc4f-213">Alterações interruptivas em cmdlets de Rede</span><span class="sxs-lookup"><span data-stu-id="fbc4f-213">Breaking changes to Network cmdlets</span></span>

### <a name="add-azurermapplicationgatewaysslcertificate"></a><span data-ttu-id="fbc4f-214">**Add-AzureRmApplicationGatewaySslCertificate**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-214">**Add-AzureRmApplicationGatewaySslCertificate**</span></span>
- <span data-ttu-id="fbc4f-215">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-215">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermapplicationgatewaysslcertificate"></a><span data-ttu-id="fbc4f-216">**New-AzureRmApplicationGatewaySslCertificate**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-216">**New-AzureRmApplicationGatewaySslCertificate**</span></span>
- <span data-ttu-id="fbc4f-217">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-217">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapplicationgatewaysslcertificate"></a><span data-ttu-id="fbc4f-218">**Set-AzureRmApplicationGatewaySslCertificate**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-218">**Set-AzureRmApplicationGatewaySslCertificate**</span></span>
- <span data-ttu-id="fbc4f-219">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-219">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-resources-cmdlets"></a><span data-ttu-id="fbc4f-220">Alterações interruptivas em cmdlets de Recursos</span><span class="sxs-lookup"><span data-stu-id="fbc4f-220">Breaking changes to Resources cmdlets</span></span>

### <a name="new-azurermadappcredential"></a><span data-ttu-id="fbc4f-221">**New-AzureRmADAppCredential**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-221">**New-AzureRmADAppCredential**</span></span>
- <span data-ttu-id="fbc4f-222">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-222">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADAppCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADAppCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadapplication"></a><span data-ttu-id="fbc4f-223">**New-AzureRmADApplication**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-223">**New-AzureRmADApplication**</span></span>
- <span data-ttu-id="fbc4f-224">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-224">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADApplication [other required parameters] -Password "plain-text string"

# New
New-AzureRmADApplication [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadserviceprincipal"></a><span data-ttu-id="fbc4f-225">**New-AzureRmADServicePrincipal**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-225">**New-AzureRmADServicePrincipal**</span></span>
- <span data-ttu-id="fbc4f-226">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-226">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADServicePrincipal [other required parameters] -Password "plain-text string"

# New
New-AzureRmADServicePrincipal [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadspcredential"></a><span data-ttu-id="fbc4f-227">**New-AzureRmADSpCredential**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-227">**New-AzureRmADSpCredential**</span></span>
- <span data-ttu-id="fbc4f-228">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-228">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADSpCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADSpCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermaduser"></a><span data-ttu-id="fbc4f-229">**New-AzureRmADUser**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-229">**New-AzureRmADUser**</span></span>
- <span data-ttu-id="fbc4f-230">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-230">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
New-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermaduser"></a><span data-ttu-id="fbc4f-231">**Set-AzureRmADUser**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-231">**Set-AzureRmADUser**</span></span>
- <span data-ttu-id="fbc4f-232">O parâmetro "Password" foi substituído por uma SecureString</span><span class="sxs-lookup"><span data-stu-id="fbc4f-232">Parameter "Password" being replaced in favor of a SecureString</span></span>

```powershell
# Old
Set-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-servicebus-cmdlets"></a><span data-ttu-id="fbc4f-233">Alterações interruptivas em cmdlets do ServiceBus</span><span class="sxs-lookup"><span data-stu-id="fbc4f-233">Breaking changes to ServiceBus cmdlets</span></span>

### <a name="get-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="fbc4f-234">**Get-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-234">**Get-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-235">O cmdlet 'Get-AzureRmServiceBusTopicAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-235">The 'Get-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-236">Use o cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-236">Please use the 'Get-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>    

### <a name="get-azurermservicebustopickey"></a><span data-ttu-id="fbc4f-237">**Get-AzureRmServiceBusTopicKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-237">**Get-AzureRmServiceBusTopicKey**</span></span>
- <span data-ttu-id="fbc4f-238">O cmdlet 'Get-AzureRmServiceBusTopicKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-238">The 'Get-AzureRmServiceBusTopicKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-239">Use o cmdlet 'Get-AzureRmServiceBusKey'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-239">Please use the 'Get-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="new-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="fbc4f-240">**New-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-240">**New-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-241">O cmdlet 'New-AzureRmServiceBusTopicAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-241">The 'New-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-242">Use o cmdlet 'New-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-242">Please use the 'New-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="new-azurermservicebustopickey"></a><span data-ttu-id="fbc4f-243">**New-AzureRmServiceBusTopicKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-243">**New-AzureRmServiceBusTopicKey**</span></span>
- <span data-ttu-id="fbc4f-244">O cmdlet 'New-AzureRmServiceBusTopicKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-244">The 'New-AzureRmServiceBusTopicKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-245">Use o cmdlet 'New-AzureRmServiceBusKey'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-245">Please use the 'New-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="remove-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="fbc4f-246">**Remove-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-246">**Remove-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-247">O cmdlet 'Remove-AzureRmServiceBusTopicAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-247">The 'Remove-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-248">Use o cmdlet 'Remove-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-248">Please use the 'Remove-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="set-azurermservicebustopicauthorizationrule"></a><span data-ttu-id="fbc4f-249">**Set-AzureRmServiceBusTopicAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-249">**Set-AzureRmServiceBusTopicAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-250">O cmdlet 'Set-AzureRmServiceBusTopicAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-250">The 'Set-AzureRmServiceBusTopicAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-251">Use o cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-251">Please use the 'Set-AzureRmServiceBusAuthorizationRule'cmdlet.</span></span>

### <a name="new-azurermservicebusnamespacekey"></a><span data-ttu-id="fbc4f-252">**New-AzureRmServiceBusNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-252">**New-AzureRmServiceBusNamespaceKey**</span></span>
- <span data-ttu-id="fbc4f-253">O cmdlet 'New-AzureRmServiceBusNamespaceKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-253">The 'New-AzureRmServiceBusNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-254">Use o cmdlet 'New-AzureRmServiceBusKey'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-254">Please use the 'New-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="get-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="fbc4f-255">**Get-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-255">**Get-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-256">O cmdlet 'Get-AzureRmServiceBusQueueAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-256">The 'Get-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-257">Use o cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-257">Please use the 'Get-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="get-azurermservicebusqueuekey"></a><span data-ttu-id="fbc4f-258">**Get-AzureRmServiceBusQueueKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-258">**Get-AzureRmServiceBusQueueKey**</span></span>
- <span data-ttu-id="fbc4f-259">O cmdlet 'Get-AzureRmServiceBusQueueKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-259">The 'Get-AzureRmServiceBusQueueKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-260">Use o cmdlet 'Get-AzureRmServiceBusKey'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-260">Please use the 'Get-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="new-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="fbc4f-261">**New-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-261">**New-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-262">O cmdlet 'New-AzureRmServiceBusQueueAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-262">The 'New-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-263">Use o cmdlet 'New-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-263">Please use the 'New-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="new-azurermservicebusqueuekey"></a><span data-ttu-id="fbc4f-264">**New-AzureRmServiceBusQueueKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-264">**New-AzureRmServiceBusQueueKey**</span></span>
- <span data-ttu-id="fbc4f-265">O cmdlet 'New-AzureRmServiceBusQueueKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-265">The 'New-AzureRmServiceBusQueueKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-266">Use o cmdlet 'New-AzureRmServiceBusKey'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-266">Please use the 'New-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="remove-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="fbc4f-267">**Remove-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-267">**Remove-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-268">O cmdlet 'Remove-AzureRmServiceBusQueueAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-268">The 'Remove-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-269">Use o cmdlet 'GRemove AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-269">Please use the 'GRemove-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="set-azurermservicebusqueueauthorizationrule"></a><span data-ttu-id="fbc4f-270">**Set-AzureRmServiceBusQueueAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-270">**Set-AzureRmServiceBusQueueAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-271">O cmdlet 'Set-AzureRmServiceBusQueueAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-271">The 'Set-AzureRmServiceBusQueueAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-272">Use o cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-272">Please use the 'Set-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="get-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-273">**Get-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-273">**Get-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-274">O cmdlet 'Get-AzureRmServiceBusNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-274">The 'Get-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-275">Use o cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-275">Please use the 'Get-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="get-azurermservicebusnamespacekey"></a><span data-ttu-id="fbc4f-276">**Get-AzureRmServiceBusNamespaceKey**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-276">**Get-AzureRmServiceBusNamespaceKey**</span></span>
- <span data-ttu-id="fbc4f-277">O cmdlet 'Get-AzureRmServiceBusNamespaceKey' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-277">The 'Get-AzureRmServiceBusNamespaceKey' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-278">Use o cmdlet 'Get-AzureRmServiceBusKey'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-278">Please use the 'Get-AzureRmServiceBusKey' cmdlet.</span></span>

### <a name="new-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-279">**New-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-279">**New-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-280">O cmdlet 'New-AzureRmServiceBusNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-280">The 'New-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-281">Use o cmdlet 'New-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-281">Please use the 'New-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="remove-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-282">**Remove-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-282">**Remove-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-283">O cmdlet 'Remove-AzureRmServiceBusNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-283">The 'Remove-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-284">Use o cmdlet 'Remove-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-284">Please use the 'Remove-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="set-azurermservicebusnamespaceauthorizationrule"></a><span data-ttu-id="fbc4f-285">**Set-AzureRmServiceBusNamespaceAuthorizationRule**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-285">**Set-AzureRmServiceBusNamespaceAuthorizationRule**</span></span>
- <span data-ttu-id="fbc4f-286">O cmdlet 'Set-AzureRmServiceBusNamespaceAuthorizationRule' foi removido.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-286">The 'Set-AzureRmServiceBusNamespaceAuthorizationRule' cmdlet has been removed.</span></span> <span data-ttu-id="fbc4f-287">Use o cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.</span><span class="sxs-lookup"><span data-stu-id="fbc4f-287">Please use the 'Set-AzureRmServiceBusAuthorizationRule' cmdlet.</span></span>

### <a name="type-namespaceattributes"></a><span data-ttu-id="fbc4f-288">**Tipo NamespaceAttributes**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-288">**Type NamespaceAttributes**</span></span>
- <span data-ttu-id="fbc4f-289">As propriedades a seguir foram removidas</span><span class="sxs-lookup"><span data-stu-id="fbc4f-289">The following properties have been removed</span></span>
    - <span data-ttu-id="fbc4f-290">habilitado</span><span class="sxs-lookup"><span data-stu-id="fbc4f-290">Enabled</span></span>
    - <span data-ttu-id="fbc4f-291">Status</span><span class="sxs-lookup"><span data-stu-id="fbc4f-291">Status</span></span>
   
```powershell
# Old
# The $namespace has Status and Enabled property 
$namespace = Get-AzureRmServiceBusNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Enabled and Status properties    
$namespace = Get-AzureRmServiceBusNamespace <parameters>
```

### <a name="type-queueattribute"></a><span data-ttu-id="fbc4f-292">**Tipo QueueAttribute**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-292">**Type QueueAttribute**</span></span>
- <span data-ttu-id="fbc4f-293">As seguintes propriedades foram marcadas como obsoletas:</span><span class="sxs-lookup"><span data-stu-id="fbc4f-293">The following properties are marked as obsolete:</span></span>
    - <span data-ttu-id="fbc4f-294">EnableBatchedOperations</span><span class="sxs-lookup"><span data-stu-id="fbc4f-294">EnableBatchedOperations</span></span>
    - <span data-ttu-id="fbc4f-295">EntityAvailabilityStatus</span><span class="sxs-lookup"><span data-stu-id="fbc4f-295">EntityAvailabilityStatus</span></span>
    - <span data-ttu-id="fbc4f-296">IsAnonymousAccessible</span><span class="sxs-lookup"><span data-stu-id="fbc4f-296">IsAnonymousAccessible</span></span>
    - <span data-ttu-id="fbc4f-297">SupportOrdering</span><span class="sxs-lookup"><span data-stu-id="fbc4f-297">SupportOrdering</span></span>

```powershell
# Old
# The $queue has EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties
$queue = Get-AzureRmServiceBusQueue <parameters>
$queue.EntityAvailabilityStatus
$queue.EnableBatchedOperations
$queue.IsAnonymousAccessible
$queue.SupportOrdering  

# New
# The call remains the same, but the returned values Queue object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties    
$queue = Get-AzureRmServiceBusQueue <parameters>
```
   
### <a name="type-topicattribute"></a><span data-ttu-id="fbc4f-298">**Tipo TopicAttribute**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-298">**Type TopicAttribute**</span></span>
- <span data-ttu-id="fbc4f-299">As seguintes propriedades foram marcadas como obsoletas:</span><span class="sxs-lookup"><span data-stu-id="fbc4f-299">The following properties are marked as obsolete:</span></span>
    - <span data-ttu-id="fbc4f-300">Local padrão</span><span class="sxs-lookup"><span data-stu-id="fbc4f-300">Location</span></span>
    - <span data-ttu-id="fbc4f-301">IsExpress</span><span class="sxs-lookup"><span data-stu-id="fbc4f-301">IsExpress</span></span>
    - <span data-ttu-id="fbc4f-302">IsAnonymousAccessible</span><span class="sxs-lookup"><span data-stu-id="fbc4f-302">IsAnonymousAccessible</span></span>
    - <span data-ttu-id="fbc4f-303">FilteringMessagesBeforePublishing</span><span class="sxs-lookup"><span data-stu-id="fbc4f-303">FilteringMessagesBeforePublishing</span></span>
    - <span data-ttu-id="fbc4f-304">EnableSubscriptionPartitioning</span><span class="sxs-lookup"><span data-stu-id="fbc4f-304">EnableSubscriptionPartitioning</span></span>
    - <span data-ttu-id="fbc4f-305">EntityAvailabilityStatus</span><span class="sxs-lookup"><span data-stu-id="fbc4f-305">EntityAvailabilityStatus</span></span>

```powershell
# Old
# The $topic has EntityAvailabilityStatus, EnableSubscriptionPartitioning, IsAnonymousAccessible, IsExpress, Location and FilteringMessagesBeforePublishing properties
$topic = Get-AzureRmServiceBusTopic <parameters>
$topic.EntityAvailabilityStatus
$topic.EnableSubscriptionPartitioning
$topic.IsAnonymousAccessible
$topic.IsExpress
$topic.FilteringMessagesBeforePublishing
$topic.Location

# New
# The call remains the same, but the returned values Topic object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties    
$topic = Get-AzureRmServiceBusTopic <parameters>
```
   
### <a name="type-subscriptionattribute"></a><span data-ttu-id="fbc4f-306">**Tipo SubscriptionAttribute**</span><span class="sxs-lookup"><span data-stu-id="fbc4f-306">**Type SubscriptionAttribute**</span></span>
- <span data-ttu-id="fbc4f-307">As seguintes propriedades foram marcadas como obsoletas</span><span class="sxs-lookup"><span data-stu-id="fbc4f-307">The following properties are marked as obsolete</span></span>
    - <span data-ttu-id="fbc4f-308">DeadLetteringOnFilterEvaluationExceptions</span><span class="sxs-lookup"><span data-stu-id="fbc4f-308">DeadLetteringOnFilterEvaluationExceptions</span></span>
    - <span data-ttu-id="fbc4f-309">EntityAvailabilityStatus</span><span class="sxs-lookup"><span data-stu-id="fbc4f-309">EntityAvailabilityStatus</span></span>
    - <span data-ttu-id="fbc4f-310">IsReadOnly</span><span class="sxs-lookup"><span data-stu-id="fbc4f-310">IsReadOnly</span></span>
    - <span data-ttu-id="fbc4f-311">Local padrão</span><span class="sxs-lookup"><span data-stu-id="fbc4f-311">Location</span></span>
   
```powershell
# Old
# The $subscription has EntityAvailabilityStatus, EnableSubscriptionPartitioning, IsAnonymousAccessible, IsExpress, Location and FilteringMessagesBeforePublishing properties
$subscription = Get-AzureRmServiceBussubscription <parameters>
$subscription.EntityAvailabilityStatus
$subscription.EnableSubscriptionPartitioning
$subscription.IsAnonymousAccessible
$subscription.IsExpress
$subscription.FilteringMessagesBeforePublishing
$subscription.Location

# New
# The call remains the same, but the returned values Topic object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties    
$subscription = Get-AzureRmServiceBussubscription <parameters>
```