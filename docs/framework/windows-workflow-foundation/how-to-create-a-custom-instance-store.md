---
title: "如何：创建自定义实例存储"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e820815a7047d91065db5308cc289f063191511
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-instance-store"></a><span data-ttu-id="694ae-102">如何：创建自定义实例存储</span><span class="sxs-lookup"><span data-stu-id="694ae-102">How to: Create a Custom Instance Store</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="694ae-103"> 包含 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>，它是使用 SQL Server 保存工作流数据的实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-103"> contains <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, an instance store that uses SQL Server to persist workflow data.</span></span> <span data-ttu-id="694ae-104">如果您的应用程序需要将工作流数据保存到其他介质，例如不同的数据库或文件系统，则可以实现自定义实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-104">If your application is required to persist workflow data to another medium, such as a different database or a file system, you can implement a custom instance store.</span></span> <span data-ttu-id="694ae-105">通过扩展抽象 <xref:System.Runtime.DurableInstancing.InstanceStore> 类并且实现完成自定义实例存储区所需的方法，创建自定义实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-105">A custom instance store is created by extending the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class and implementing the methods that are required for the implementation.</span></span> <span data-ttu-id="694ae-106">有关自定义实例存储的完整实现，请参阅[企业采购过程](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)示例。</span><span class="sxs-lookup"><span data-stu-id="694ae-106">For a complete implementation of a custom instance store, see the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span>  
  
## <a name="implementing-the-begintrycommand-method"></a><span data-ttu-id="694ae-107">实现 BeginTryCommand 方法</span><span class="sxs-lookup"><span data-stu-id="694ae-107">Implementing the BeginTryCommand method</span></span>  
 <span data-ttu-id="694ae-108"><xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> 由持久性引擎发送给实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-108">The <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> is sent to the instance store by the persistence engine.</span></span> <span data-ttu-id="694ae-109">`command` 参数的类型指示要执行的命令；此参数可以是以下类型：</span><span class="sxs-lookup"><span data-stu-id="694ae-109">The type of the `command` parameter indicates which command is being executed; this parameter can be of the following types:</span></span>  
  
-   <span data-ttu-id="694ae-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>：在工作流要保存到存储介质时，持久性引擎将此命令发送到实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be persisted to the storage medium.</span></span> <span data-ttu-id="694ae-111">工作流持久性数据将提供给在 <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> 参数的 `command` 成员中的方法。 </span><span class="sxs-lookup"><span data-stu-id="694ae-111">The workflow persistence data is provided to the method in the <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> member of the `command` parameter.</span></span>  
  
-   <span data-ttu-id="694ae-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>：要从存储介质中加载工作流时，持久性引擎将此命令发送到实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be loaded from the storage medium.</span></span> <span data-ttu-id="694ae-113">将要加载的工作流的实例 ID 提供给 `instanceId` 参数的 <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> 属性的 `context` 参数中的方法。 </span><span class="sxs-lookup"><span data-stu-id="694ae-113">The instance ID of the workflow to be loaded is provided to the method in the `instanceId` parameter of the <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> property of the `context` parameter.</span></span>  
  
-   <span data-ttu-id="694ae-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>：持久性引擎在 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 必须注册为锁所有者时将此命令发送给实例存储区。 </span><span class="sxs-lookup"><span data-stu-id="694ae-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when a <xref:System.ServiceModel.Activities.WorkflowServiceHost> must be registered as a lock owner.</span></span> <span data-ttu-id="694ae-115">应使用 <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> 参数的 `context` 方法将当前工作流的实例 ID 提供给实例存储区。 </span><span class="sxs-lookup"><span data-stu-id="694ae-115">The instance ID of the current workflow should be provided to the instance store using <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> method of the `context` parameter.</span></span>  
  
     <span data-ttu-id="694ae-116">下面的代码段演示如何实现 CreateWorkflowOwner 命令来分配显式锁所有者。</span><span class="sxs-lookup"><span data-stu-id="694ae-116">The following code snippet demonstrates how to implement the CreateWorkflowOwner command to assign an explicit lock owner.</span></span>  
  
    ```  
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");  
    ...  
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()  
    {  
        InstanceOwnerMetadata =  
        {  
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },  
        }  
    };  
    InstanceHandle ownerHandle = store.CreateInstanceHandle();  
    store.DefaultInstanceOwner = store.Execute(  
                                   ownerHandle,  
                                   createCommand,  
                                   TimeSpan.FromSeconds(30)).InstanceOwner;  
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });  
    ```  
  
-   <span data-ttu-id="694ae-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>：在从实例存储区中移除锁所有者的实例 ID 时持久性引擎将此命令发送到实例存储区。 </span><span class="sxs-lookup"><span data-stu-id="694ae-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when the instance ID of a lock owner can be removed from the instance store.</span></span> <span data-ttu-id="694ae-118">像 <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand> 一样，锁所有者的 ID 应由应用程序提供。 </span><span class="sxs-lookup"><span data-stu-id="694ae-118">As with <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, the ID of the lock owner should be provided by the application.</span></span>  
  
     <span data-ttu-id="694ae-119">下面的代码段演示如何使用 <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand> 释放锁。</span><span class="sxs-lookup"><span data-stu-id="694ae-119">The following code snippet demonstrates how to release a lock using <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.</span></span>  
  
    ```  
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)  
    {  
        handle.Free();  
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);  
        try  
        {  
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.  
            Thread.Sleep(10000);  
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));  
        }  
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }  
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }  
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }  
        catch (Exception ex) { Log.Inform(ex.Message); }  
        finally  
        {  
            handle.Free();  
            store.DefaultInstanceOwner = null;  
        }  
    }  
    ```  
  
     <span data-ttu-id="694ae-120">上述方法应在子实例运行时在 Try/Catch 块中调用。</span><span class="sxs-lookup"><span data-stu-id="694ae-120">The above method should be called in a Try/Catch block when a child instance is run.</span></span>  
  
    ```  
    try  
    {  
        childInstance.Run();  
    }  
    catch (Exception)  
    {  
        throw ;  
    }  
    finally  
    {  
        FreeHandleAndDeleteOwner(store, ownerHandle);  
    }  
    ```  
  
-   <span data-ttu-id="694ae-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>：在使用工作流的实例键加载工作流实例时，持久性引擎将此命令发送到实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: The persistence engine sends this command to the instance store when a workflow instance is to be loaded using the workflow’s instance key.</span></span> <span data-ttu-id="694ae-122">使用命令的 <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> 参数可以确定该实例键的 ID。  </span><span class="sxs-lookup"><span data-stu-id="694ae-122">The ID of the instance key can be determined by using the <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> parameter of the command.</span></span>  
  
-   <span data-ttu-id="694ae-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>：持久性引擎将此命令发送到实例存储区来检索持久性工作流的激活参数，以便创建可在之后加载工作流的工作流主机。</span><span class="sxs-lookup"><span data-stu-id="694ae-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: The persistence engine sends this command to the instance store to retrieve activation parameters for persisted workflows in order to create a workflow host that can then load workflows.</span></span> <span data-ttu-id="694ae-124">在找到可以激活的实例时，引擎为响应对主机引发 <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> 的实例存储区而发送此命令。</span><span class="sxs-lookup"><span data-stu-id="694ae-124">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> to the host when it locates an instance that can be activated.</span></span> <span data-ttu-id="694ae-125">应对实例存储区进行轮询，以便确定是否存在可激活的工作流。</span><span class="sxs-lookup"><span data-stu-id="694ae-125">The instance store should be polled to determine if there are workflows that can be activated.</span></span>  
  
-   <span data-ttu-id="694ae-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>：持久性引擎将此命令发送到实例存储区，以便加载可运行的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="694ae-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: The persistence engine sends this command to the instance store to load runnable workflow instances.</span></span> <span data-ttu-id="694ae-127">在找到可以运行的实例时，引擎为响应对主机引发 <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> 的实例存储区而发送此命令。</span><span class="sxs-lookup"><span data-stu-id="694ae-127">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> to the host when it locates an instance that can be run.</span></span> <span data-ttu-id="694ae-128">实例存储区应轮询可以运行的工作流。</span><span class="sxs-lookup"><span data-stu-id="694ae-128">The instance store should poll for workflows that can be run.</span></span> <span data-ttu-id="694ae-129">下面的代码段演示如何对实例存储区进行轮询以便获得可运行或激活的工作流。</span><span class="sxs-lookup"><span data-stu-id="694ae-129">The following code snippet demonstrates polling an instance store for workflows that can be run or activated.</span></span>  
  
    ```  
    public void PollForEvents()  
    {  
        InstanceOwner[] storeOwners = this.GetInstanceOwners();  
  
        foreach (InstanceOwner owner in storeOwners)  
        {  
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))  
            {  
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))  
                {  
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivable);  
                    if (hasRunnable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))  
                {  
                   bool hasActivable = GetActivableEvents(this.StoreId, owner.InstanceOwnerId);  
                   if (hasActivable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="694ae-130">在上面的代码段中，实例存储区将查询可用事件，并对每个事件进行检查，以确该事件是否为 <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> 事件。</span><span class="sxs-lookup"><span data-stu-id="694ae-130">In the above code snippet, the instance store queries the events available and examines each one to determine if it is a <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> event.</span></span> <span data-ttu-id="694ae-131">如果找到了这样的事件，则对 <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> 进行调用，以便通知主机将命令发送到实例存储区。</span><span class="sxs-lookup"><span data-stu-id="694ae-131">If one is found, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> is called to signal the host to send a command to the instance store.</span></span>  <span data-ttu-id="694ae-132">下面的代码段演示如何为此命令实现处理程序。</span><span class="sxs-lookup"><span data-stu-id="694ae-132">The following code snippet demonstrates an implementation of a handler for this command.</span></span>  
  
    ```  
    If (command is TryLoadRunnableWorkflowCommand)  
    {  
        Owner owner;  
        CheckOwner(context, command.Name, out owner);                          
        // Checking instance.Owner is like an InstanceLockQueryResult.  
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));  
  
        XName ownerService = null;  
        InstanceValue value;  
        Instance runnableInstance = default(Instance);  
        bool foundRunnableInstance = false;  
  
        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);  
        if (value != null && value.Value is XName)  
        {  
            ownerService = (XName)value.Value;  
        }  
  
        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)  
        {  
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)  
            {  
                continue;  
            }  
  
            if (ownerService != null)  
            {  
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);  
                if (value == null || ((XName)value.Value) != ownerService)  
                {  
                    continue;  
                }  
            }  
  
            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);  
            if (value != null && value.Value != null && value.Value is string)  
            {  
                continue;  
            }  
  
            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);  
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")  
            {  
                runnableInstance = instance.Value;  
                foundRunnableInstance = true;  
            }  
  
            if (!foundRunnableInstance)  
            {  
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);  
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)  
                {                          
                    runnableInstance = instance.Value;  
                    foundRunnableInstance = true;  
                }  
            }  
  
            if (foundRunnableInstance)  
            {  
                runnableInstance.LockVersion++;  
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;  
                MemoryStore.instances[instance.Key] = runnableInstance;  
                context.BindInstance(instance.Key);  
                context.BindAcquiredLock(runnableInstance.LockVersion);  
  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)  
                {  
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)  
                {  
                    if (keyEntry.Value.Completed)  
                    {  
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                    else  
                    {  
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                }  
            }  
  
            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);  
            break;  
        }  
    }  
    ```  
  
     <span data-ttu-id="694ae-133">在上面的代码段中，实例存储区搜索可运行实例。</span><span class="sxs-lookup"><span data-stu-id="694ae-133">In the above code snippet, the instance store searches for runnable instances.</span></span> <span data-ttu-id="694ae-134">如果找到了一个实例，则该实例将绑定到执行上下文并加载。</span><span class="sxs-lookup"><span data-stu-id="694ae-134">If an instance is found, it is bound to the execution context and loaded.</span></span>  
  
## <a name="using-a-custom-instance-store"></a><span data-ttu-id="694ae-135">使用自定义实例存储区</span><span class="sxs-lookup"><span data-stu-id="694ae-135">Using a custom instance store</span></span>  
 <span data-ttu-id="694ae-136">若要实现自定义实例存储区，请将实例存储区的实例分配给 <xref:System.Activities.WorkflowApplication.InstanceStore%2A>，然后执行 <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> 方法。 </span><span class="sxs-lookup"><span data-stu-id="694ae-136">To implement a custom instance store, assign an instance of the instance store to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A>, and implement the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> method.</span></span>  <span data-ttu-id="694ae-137">请参阅[如何： 创建和运行长时间运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)教程有关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="694ae-137">See the [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) tutorial for specifics.</span></span>  
  
## <a name="a-sample-instance-store"></a><span data-ttu-id="694ae-138">示例实例存储区</span><span class="sxs-lookup"><span data-stu-id="694ae-138">A sample instance store</span></span>  
 <span data-ttu-id="694ae-139">下面的代码示例是完整的实例存储区实现，摘自[企业采购过程](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)示例。</span><span class="sxs-lookup"><span data-stu-id="694ae-139">The following code sample is a complete instance store implementation, taken from the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span> <span data-ttu-id="694ae-140">该实例存储区使用 XML 将工作流数据保存到某一文件。</span><span class="sxs-lookup"><span data-stu-id="694ae-140">This instance store persists workflow data to a file using XML.</span></span>  
  
```  
using System;  
using System.Activities.DurableInstancing;  
using System.Collections.Generic;  
using System.IO;  
using System.Runtime.DurableInstancing;  
using System.Runtime.Serialization;  
using System.ServiceModel.Persistence;  
using System.Xml;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.WF.PurchaseProcess  
{  
  
    public class XmlWorkflowInstanceStore : InstanceStore  
    {  
        Guid ownerInstanceID;  
  
        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())  
        {  
  
        }  
  
        public XmlWorkflowInstanceStore(Guid id)  
        {  
            ownerInstanceID = id;  
        }  
  
        //Synchronous version of the Begin/EndTryCommand functions  
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)  
        {  
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));  
        }  
  
        //The persistence engine will send a variety of commands to the configured InstanceStore,  
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.  
        //This method is where we will handle those commands  
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)  
        {  
            IDictionary<XName, InstanceValue> data = null;  
  
            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle  
            if (command is CreateWorkflowOwnerCommand)  
            {  
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());  
            }  
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key  
            else if (command is SaveWorkflowCommand)  
            {  
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;  
                data = saveCommand.InstanceData;  
  
                Save(data);  
            }  
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle  
            else if (command is LoadWorkflowCommand)  
            {  
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
  
                try  
                {  
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))  
                    {  
                        data = LoadInstanceDataFromFile(inputStream);  
                        //load the data into the persistence Context  
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);  
                    }  
                }  
                catch (Exception exception)  
                {  
                    throw new PersistenceException(exception.Message);  
                }  
            }  
  
            return new CompletedAsyncResult<bool>(true, callback, state);  
        }  
  
        protected override bool EndTryCommand(IAsyncResult result)  
        {  
            return CompletedAsyncResult<bool>.End(result);  
        }  
  
        //Reads data from xml file and creates a dictionary based off of that.  
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)  
        {  
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();  
  
            NetDataContractSerializer s = new NetDataContractSerializer();  
  
            XmlReader rdr = XmlReader.Create(inputStream);  
            XmlDocument doc = new XmlDocument();  
            doc.Load(rdr);  
  
            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");  
            foreach (XmlElement instanceElement in instances)  
            {  
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");  
                XName key = (XName)DeserializeObject(s, keyElement);  
  
                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");  
                object value = DeserializeObject(s, valueElement);  
                InstanceValue instVal = new InstanceValue(value);  
  
                data.Add(key, instVal);  
            }  
  
            return data;  
        }  
  
        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)  
        {  
            object deserializedObject = null;  
  
            MemoryStream stm = new MemoryStream();  
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);  
            element.WriteContentTo(wtr);  
            wtr.Flush();  
            stm.Position = 0;  
  
            deserializedObject = serializer.Deserialize(stm);  
  
            return deserializedObject;  
        }  
  
        //Saves the persistence data to an xml file.  
        void Save(IDictionary<XName, InstanceValue> instanceData)  
        {  
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
            XmlDocument doc = new XmlDocument();  
            doc.LoadXml("<InstanceValues/>");  
  
            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)  
            {  
                XmlElement newInstance = doc.CreateElement("InstanceValue");  
  
                XmlElement newKey = SerializeObject("key", valPair.Key, doc);  
                newInstance.AppendChild(newKey);  
  
                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);  
                newInstance.AppendChild(newValue);  
  
                doc.DocumentElement.AppendChild(newInstance);  
            }  
            doc.Save(fileName);  
       }  
  
        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)  
        {  
            NetDataContractSerializer s = new NetDataContractSerializer();  
            XmlElement newElement = doc.CreateElement(elementName);  
            MemoryStream stm = new MemoryStream();  
  
            s.Serialize(stm, o);  
            stm.Position = 0;  
            StreamReader rdr = new StreamReader(stm);  
            newElement.InnerXml = rdr.ReadToEnd();  
  
            return newElement;  
        }  
    }  
}  
```
