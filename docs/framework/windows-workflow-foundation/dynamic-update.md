---
title: 动态更新
ms.date: 03/30/2017
ms.assetid: 8b6ef19b-9691-4b4b-824c-3c651a9db96e
ms.openlocfilehash: dea930de2103a24aa48b1d0a31a3cbf5fc0ae26c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43455765"
---
# <a name="dynamic-update"></a><span data-ttu-id="06b13-102">动态更新</span><span class="sxs-lookup"><span data-stu-id="06b13-102">Dynamic Update</span></span>
<span data-ttu-id="06b13-103">动态更新为工作流应用程序开发人员提供了一种机制，可用于更新持久化工作流实例的工作流定义。</span><span class="sxs-lookup"><span data-stu-id="06b13-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="06b13-104">操作可以是实施 bug 修复、实施新的要求或适应意外的变化。</span><span class="sxs-lookup"><span data-stu-id="06b13-104">This can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="06b13-105">此主题概述了 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中引入的动态更新功能。</span><span class="sxs-lookup"><span data-stu-id="06b13-105">This topic provides an overview of the dynamic update functionality introduced in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="dynamic-update"></a><span data-ttu-id="06b13-106">动态更新</span><span class="sxs-lookup"><span data-stu-id="06b13-106">Dynamic Update</span></span>  
 <span data-ttu-id="06b13-107">为了将动态更新应用于持久化的工作流实例，会创建一个 <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>，其中包含描述如何修改持久化工作流实例以反映所需更改的运行时说明。</span><span class="sxs-lookup"><span data-stu-id="06b13-107">To apply dynamic updates to a persisted workflow instance, a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> is created that contains instructions for the runtime that describe how to modify the persisted workflow instance to reflect the desired changes.</span></span> <span data-ttu-id="06b13-108">更新映射一旦创建，即应用于所需的持久化工作流实例。</span><span class="sxs-lookup"><span data-stu-id="06b13-108">Once the update map is created, it is applied to the desired persisted workflow instances.</span></span> <span data-ttu-id="06b13-109">应用动态更新后，可能会使用新的更新工作流定义来恢复工作流实例。</span><span class="sxs-lookup"><span data-stu-id="06b13-109">Once the dynamic update is applied, the workflow instance may be resumed using the new updated workflow definition.</span></span> <span data-ttu-id="06b13-110">创建和应用更新映射须执行四个步骤的操作。</span><span class="sxs-lookup"><span data-stu-id="06b13-110">There are four steps required to create and apply an update map.</span></span>  
  
1.  [<span data-ttu-id="06b13-111">准备动态更新工作流定义</span><span class="sxs-lookup"><span data-stu-id="06b13-111">Prepare the workflow definition for dynamic update</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Prepare)  
  
2.  [<span data-ttu-id="06b13-112">更新工作流定义以反映所需的更改</span><span class="sxs-lookup"><span data-stu-id="06b13-112">Update the workflow definition to reflect the desired changes</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Update)  
  
3.  [<span data-ttu-id="06b13-113">创建更新映射</span><span class="sxs-lookup"><span data-stu-id="06b13-113">Create the update map</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Create)  
  
4.  [<span data-ttu-id="06b13-114">将更新映射应用于所需的持久化工作流实例</span><span class="sxs-lookup"><span data-stu-id="06b13-114">Apply the update map to the desired persisted workflow instances</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Apply)  
  
> [!NOTE]
>  <span data-ttu-id="06b13-115">请注意，步骤 1 到 3 涵盖更新映射的创建，可不通过应用更新来执行。</span><span class="sxs-lookup"><span data-stu-id="06b13-115">Note that steps 1 through 3, which cover the creation of the update map, may be performed independently of applying the update.</span></span> <span data-ttu-id="06b13-116">一个常见的方案是工作流开发人员脱机创建更新映射，然后由管理员在以后应用更新。</span><span class="sxs-lookup"><span data-stu-id="06b13-116">A common scenario that that the workflow developer will create the update map offline, and then an administrator will apply the update at a later time.</span></span>  
  
 <span data-ttu-id="06b13-117">本主题将一个新活动添加至已编译 Xaml 工作流的持久性实例中，借此提供对动态更新过程的概述。</span><span class="sxs-lookup"><span data-stu-id="06b13-117">This topic provides an overview of the dynamic update process of adding a new activity to a persisted instance of a compiled Xaml workflow.</span></span>  
  
###  <a name="Prepare"></a> <span data-ttu-id="06b13-118">准备动态更新工作流定义</span><span class="sxs-lookup"><span data-stu-id="06b13-118">Prepare the workflow definition for dynamic update</span></span>  
 <span data-ttu-id="06b13-119">动态更新过程的第一步是准备要更新的工作流定义。</span><span class="sxs-lookup"><span data-stu-id="06b13-119">The first step in the dynamic update process is to prepare the desired workflow definition for update.</span></span> <span data-ttu-id="06b13-120">这是通过调用 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> 方法并传入要修改的工作流定义来实现的。</span><span class="sxs-lookup"><span data-stu-id="06b13-120">This is done by calling the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> method and passing in the workflow definition to modify.</span></span> <span data-ttu-id="06b13-121">方法将验证然后遍历工作流树，以标识所有对象（如需要标记的公共活动和变量），以便稍后将其与修改的工作流定义进行比较。</span><span class="sxs-lookup"><span data-stu-id="06b13-121">This method validates and then walks the workflow tree to identify all of the objects such as public activities and variables that need to be tagged so they can be compared later with the modified workflow definition.</span></span> <span data-ttu-id="06b13-122">完成此操作后，将对工作流树进行克隆并将其附加到原始工作流定义。</span><span class="sxs-lookup"><span data-stu-id="06b13-122">When this is complete, the workflow tree is cloned and attached to the original workflow definition.</span></span> <span data-ttu-id="06b13-123">创建更新映射时，将比较工作流定义的更新版本和原始工作流定义，并根据比较差异生成更新映射。</span><span class="sxs-lookup"><span data-stu-id="06b13-123">When the update map is created, the updated version of the workflow definition is compared with the original workflow definition and the update map is generated based on the differences.</span></span>  
  
 <span data-ttu-id="06b13-124">若要为动态更新准备 Xaml 工作流，可将其加载到 <xref:System.Activities.ActivityBuilder>，然后 <xref:System.Activities.ActivityBuilder> 将传入 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="06b13-124">To prepare a Xaml workflow for dynamic update it may be loaded into an <xref:System.Activities.ActivityBuilder>, and then the <xref:System.Activities.ActivityBuilder> is passed into <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06b13-125">详细了解如何使用序列化工作流和<xref:System.Activities.ActivityBuilder>，请参阅[序列化工作流和活动与 XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="06b13-125">For more information about working with serialized workflows and <xref:System.Activities.ActivityBuilder>, see [Serializing Workflows and Activities to and from XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>  
  
 <span data-ttu-id="06b13-126">在以下示例中，`MortgageWorkflow` 定义（由带有若干子活动的 <xref:System.Activities.Statements.Sequence> 组成）将加载到 <xref:System.Activities.ActivityBuilder> 中，然后准备进行动态更新。</span><span class="sxs-lookup"><span data-stu-id="06b13-126">In the following example, a `MortgageWorkflow` definition (that consists of a <xref:System.Activities.Statements.Sequence> with several child activities) is loaded into an <xref:System.Activities.ActivityBuilder>, and then prepared for dynamic update.</span></span> <span data-ttu-id="06b13-127">该方法返回后，<xref:System.Activities.ActivityBuilder> 包含原始工作流定义以及副本。</span><span class="sxs-lookup"><span data-stu-id="06b13-127">After the method returns, the <xref:System.Activities.ActivityBuilder> contains the original workflow definition as well as a copy.</span></span>  
  
```csharp  
// Load the MortgageWorkflow definition from Xaml into  
// an ActivityBuilder.  
XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()  
{  
    LocalAssembly = Assembly.GetExecutingAssembly()  
};  
  
XamlXmlReader xamlReader = new XamlXmlReader(@"C:\WorkflowDefitinions\MortgageWorkflow.xaml",   
    readerSettings);  
  
ActivityBuilder ab = XamlServices.Load(  
    ActivityXamlServices.CreateBuilderReader(xamlReader)) as ActivityBuilder;  
  
// Prepare the workflow definition for dynamic update.  
DynamicUpdateServices.PrepareForUpdate(ab);  
```  
  
> [!NOTE]
>  <span data-ttu-id="06b13-128">若要下载本主题附带的示例代码，请参阅[动态更新示例代码](https://go.microsoft.com/fwlink/?LinkId=227905)。</span><span class="sxs-lookup"><span data-stu-id="06b13-128">To download the sample code that accompanies this topic, see [Dynamic Update sample code](https://go.microsoft.com/fwlink/?LinkId=227905).</span></span>  
  
###  <a name="Update"></a> <span data-ttu-id="06b13-129">更新工作流定义以反映所需的更改</span><span class="sxs-lookup"><span data-stu-id="06b13-129">Update the workflow definition to reflect the desired changes</span></span>  
 <span data-ttu-id="06b13-130">一旦工作流定义准备好进行更新，就可以作出所需的更改。</span><span class="sxs-lookup"><span data-stu-id="06b13-130">Once the workflow definition has been prepared for updating, the desired changes can be made.</span></span> <span data-ttu-id="06b13-131">您可以添加或删除活动，添加、移动或删除公共变量，添加或删除参数，并对活动委托的签名进行更改。</span><span class="sxs-lookup"><span data-stu-id="06b13-131">You can add or remove activities, add, move or delete public variables, add or remove arguments, and make changes to the signature of activity delegates.</span></span> <span data-ttu-id="06b13-132">您不能删除正在运行的活动或更改正在运行的委托的签名。</span><span class="sxs-lookup"><span data-stu-id="06b13-132">You cannot remove a running activity or change the signature of a running delegate.</span></span> <span data-ttu-id="06b13-133">这些更改可利用代码，或在预先承载的工作流设计器中进行。</span><span class="sxs-lookup"><span data-stu-id="06b13-133">These changes may be made using code, or in a re-hosted workflow designer.</span></span> <span data-ttu-id="06b13-134">在以下示例中，自定义 `VerifyAppraisal` 活动添加到 Sequence，后者构成前例中 `MortgageWorkflow` 的主体。</span><span class="sxs-lookup"><span data-stu-id="06b13-134">In the following example, a custom `VerifyAppraisal` activity is added to the Sequence that makes up the body of the `MortgageWorkflow` from the previous example.</span></span>  
  
```csharp  
// Make desired changes to the definition. In this example, we are  
// inserting a new VerifyAppraisal activity as the 3rd child of the root Sequence.  
VerifyAppraisal va = new VerifyAppraisal  
{  
    Result = new VisualBasicReference<bool>("LoanCriteria")  
};  
  
// Get the Sequence that makes up the body of the workflow.  
Sequence s = ab.Implementation as Sequence;  
  
// Insert the new activity into the Sequence.  
s.Activities.Insert(2, va);  
```  
  
###  <a name="Create"></a> <span data-ttu-id="06b13-135">创建更新映射</span><span class="sxs-lookup"><span data-stu-id="06b13-135">Create the update map</span></span>  
 <span data-ttu-id="06b13-136">修改完准备好进行更新的工作流定义之后，就可以创建更新映射。</span><span class="sxs-lookup"><span data-stu-id="06b13-136">Once the workflow definition that was prepared for update has been modified, the update map can be created.</span></span> <span data-ttu-id="06b13-137">为创建动态更新映射，需调用 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="06b13-137">To create a dynamic update map, the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> method is invoked.</span></span> <span data-ttu-id="06b13-138">这将返回一个 <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>，它包含运行时修改持久化工作流实例所需的信息，以便可以使用新的工作流定义加载和恢复该实例。</span><span class="sxs-lookup"><span data-stu-id="06b13-138">This returns a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> that contains the information the runtime needs to modify a persisted workflow instance so that it may be loaded and resumed with the new workflow definition.</span></span> <span data-ttu-id="06b13-139">在以下示例中，为上例中修改的 `MortgageWorkflow` 定义创建了一个动态映射。</span><span class="sxs-lookup"><span data-stu-id="06b13-139">In the following example, a dynamic map is created for the modified `MortgageWorkflow` definition from the previous example.</span></span>  
  
```csharp  
// Create the update map.  
DynamicUpdateMap map = DynamicUpdateServices.CreateUpdateMap(ab);  
```  
  
 <span data-ttu-id="06b13-140">此更新映射可以立即用于修改持久化工作流实例，或者采用更常见的做法，即进行保存并在以后应用更新。</span><span class="sxs-lookup"><span data-stu-id="06b13-140">This update map can immediately be used to modify persisted workflow instances, or more typically it can be saved and the updates applied later.</span></span> <span data-ttu-id="06b13-141">保存更新映射的一种方法是将它序列化到文件中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="06b13-141">One way to save the update map is to serialize it to a file, as shown in the following example.</span></span>  
  
```csharp  
// Serialize the update map to a file.  
DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));  
using (FileStream fs = System.IO.File.Open(@"C:\WorkflowDefitinions\MortgageWorkflow.map", FileMode.Create))  
{  
    serializer.WriteObject(fs, map);  
}  
```  
  
 <span data-ttu-id="06b13-142">当 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> 返回时，克隆的工作流定义和其他动态更新信息（在调用 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> 时添加）被删除，并且可以保存修改的工作流定义，以便在以后恢复更新工作流实例时使用。</span><span class="sxs-lookup"><span data-stu-id="06b13-142">When <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> returns, the cloned workflow definition and other dynamic update information that was added in the call to <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> is removed, and the modified workflow definition is ready to be saved so that it can be used later when resuming updated workflow instances.</span></span> <span data-ttu-id="06b13-143">在以下示例中，修改的工作流定义保存到 `MortgageWorkflow_v2.xaml` 中。</span><span class="sxs-lookup"><span data-stu-id="06b13-143">In the following example, the modified workflow definition is saved to `MortgageWorkflow_v2.xaml`.</span></span>  
  
```csharp  
// Save the modified workflow definition.  
StreamWriter sw = File.CreateText(@"C:\WorkflowDefitinions\MortgageWorkflow_v1.1.xaml");  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw, ab);  
sw.Close();  
```  
  
###  <a name="Apply"></a> <span data-ttu-id="06b13-144">将更新映射应用于所需的持久化工作流实例</span><span class="sxs-lookup"><span data-stu-id="06b13-144">Apply the update map to the desired persisted workflow instances</span></span>  
 <span data-ttu-id="06b13-145">更新映射创建后在任意时间都可应用。</span><span class="sxs-lookup"><span data-stu-id="06b13-145">Applying the update map can be done at any time after creating it.</span></span> <span data-ttu-id="06b13-146">可以使用 <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> 实例（由 <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> 返回）立即应用，也可以使用保存的更新映射副本在以后应用。</span><span class="sxs-lookup"><span data-stu-id="06b13-146">It can be done right away using the <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> instance that was returned by <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>, or it can be done later using a saved copy of the update map.</span></span> <span data-ttu-id="06b13-147">若要更新工作流实例，可使用 <xref:System.Activities.WorkflowApplicationInstance> 将该实例加载到 <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType> 中。</span><span class="sxs-lookup"><span data-stu-id="06b13-147">To update a workflow instance, load it into a <xref:System.Activities.WorkflowApplicationInstance> using <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="06b13-148">接下来，使用更新的工作流定义和所需 <xref:System.Activities.WorkflowApplication> 创建一个 <xref:System.Activities.WorkflowIdentity>。</span><span class="sxs-lookup"><span data-stu-id="06b13-148">Next, create a <xref:System.Activities.WorkflowApplication> using the updated workflow definition, and the desired <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="06b13-149">此 <xref:System.Activities.WorkflowIdentity> 可能不同于用来持久化保存原始工作流的标识，通常是为了反映持久化保存的实例已修改。</span><span class="sxs-lookup"><span data-stu-id="06b13-149">This <xref:System.Activities.WorkflowIdentity> may be different than the one that was used to persist the original workflow, and typically is in order to reflect that the persisted instance has been modified.</span></span> <span data-ttu-id="06b13-150">一旦创建了 <xref:System.Activities.WorkflowApplication>，即使用 <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType>（采用 <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>）的重载进行加载，然后通过调用 <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType> 将其卸载。</span><span class="sxs-lookup"><span data-stu-id="06b13-150">Once the <xref:System.Activities.WorkflowApplication> is created, it is loaded using the overload of <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> that takes a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>, and then unloaded with a call to <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="06b13-151">这适用于动态更新，并持久化保存更新的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="06b13-151">This applies the dynamic update and persists the updated workflow instance.</span></span>  
  
```csharp  
// Load the serialized update map.  
DynamicUpdateMap map;  
using (FileStream fs = File.Open(@"C:\WorkflowDefitinions\MortgageWorkflow.map", FileMode.Open))  
{  
    DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));  
    object updateMap = serializer.ReadObject(fs);  
    if (updateMap == null)  
    {  
        throw new ApplicationException("DynamicUpdateMap is null.");  
    }  
  
    map = (DynamicUpdateMap)updateMap;  
}  
  
// Retrieve a list of workflow instance ids that corresponds to the  
// workflow instances to update. This step is the responsibility of  
// the application developer.  
List<Guid> ids = GetPersistedWorkflowIds();  
foreach (Guid id in ids)  
{  
    // Get a proxy to the persisted workflow instance.  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
    WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(id, store);  
  
    // If desired, you can inspect the WorkflowIdentity of the instance  
    // using the DefinitionIdentity property to determine whether to apply  
    // the update.  
    Console.WriteLine(instance.DefinitionIdentity);  
  
    // Create a workflow application. You must specify the updated workflow definition, and  
    // you may provide an updated WorkflowIdentity if desired to reflect the update.  
    WorkflowIdentity identity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow v1.1",  
        Version = new Version(1, 1, 0, 0)  
    };  
  
    // Load the persisted workflow instance using the updated workflow definition  
    // and with an updated WorkflowIdentity. In this example the MortgageWorkflow class  
    // contains the updated definition.  
    WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);  
  
    // Apply the dynamic update on the loaded instance.                
    wfApp.Load(instance, map);  
  
    // Unload the updated instance.  
    wfApp.Unload();  
}  
```  
  
### <a name="resuming-an-updated-workflow-instance"></a><span data-ttu-id="06b13-152">恢复更新的工作流实例</span><span class="sxs-lookup"><span data-stu-id="06b13-152">Resuming an Updated Workflow Instance</span></span>  
 <span data-ttu-id="06b13-153">一旦应用了动态更新，即可恢复工作流实例。</span><span class="sxs-lookup"><span data-stu-id="06b13-153">Once dynamic update has been applied, the workflow instance may be resumed.</span></span> <span data-ttu-id="06b13-154">注意，必须使用新更新的定义和 <xref:System.Activities.WorkflowIdentity>。</span><span class="sxs-lookup"><span data-stu-id="06b13-154">Note that the new updated definition and <xref:System.Activities.WorkflowIdentity> must be used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06b13-155">有关使用详细信息<xref:System.Activities.WorkflowApplication>并<xref:System.Activities.WorkflowIdentity>，请参阅[使用 WorkflowIdentity 和版本控制](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="06b13-155">For more information about working with <xref:System.Activities.WorkflowApplication> and <xref:System.Activities.WorkflowIdentity>, see [Using WorkflowIdentity and Versioning](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md).</span></span>  
  
 <span data-ttu-id="06b13-156">在以下示例中，前面示例中的 `MortgageWorkflow_v1.1.xaml` 工作流已经过编译，并使用更新的工作流定义进行加载和恢复。</span><span class="sxs-lookup"><span data-stu-id="06b13-156">In the following example, the `MortgageWorkflow_v1.1.xaml` workflow from the previous example has been compiled, and is loaded and resumed using the updated workflow definition.</span></span>  
  
```csharp  
// Load the persisted workflow instance using the updated workflow definition  
// and updated WorkflowIdentity.  
WorkflowIdentity identity = new WorkflowIdentity  
{  
    Name = "MortgageWorkflow v1.1",  
    Version = new Version(1, 1, 0, 0)  
};  
  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);  
  
// Configure persistence and desired workflow event handlers.  
// (Omitted for brevity.)  
ConfigureWorkflowApplication(wfApp);  
  
// Load the persisted workflow instance.  
wfApp.Load(InstanceId);  
  
// Resume the workflow.  
// wfApp.ResumeBookmark(...);  
```  
  
> [!NOTE]
>  <span data-ttu-id="06b13-157">若要下载本主题附带的示例代码，请参阅[动态更新示例代码](https://go.microsoft.com/fwlink/?LinkId=227905)。</span><span class="sxs-lookup"><span data-stu-id="06b13-157">To download the sample code that accompanies this topic, see [Dynamic Update sample code](https://go.microsoft.com/fwlink/?LinkId=227905).</span></span>
