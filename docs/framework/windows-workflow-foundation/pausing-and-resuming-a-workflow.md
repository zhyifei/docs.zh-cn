---
title: "暂停和继续工作流"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11f38339-79c7-4295-b610-24a7223bbf6d
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 31e3bdf501a88e78c5ae251499baf2512f73579d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="pausing-and-resuming-a-workflow"></a><span data-ttu-id="7d2d5-102">暂停和继续工作流</span><span class="sxs-lookup"><span data-stu-id="7d2d5-102">Pausing and Resuming a Workflow</span></span>
<span data-ttu-id="7d2d5-103">工作流将暂停并恢复以响应书签和阻止活动（如 <xref:System.Activities.Statements.Delay>），但也可使用持久性来显式暂停、卸载和恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-103">Workflows will pause and resume in response to bookmarks and blocking activities such as <xref:System.Activities.Statements.Delay>, but a workflow can also be explicitly paused, unloaded, and resumed by using persistence.</span></span>  
  
## <a name="pausing-a-workflow"></a><span data-ttu-id="7d2d5-104">暂停工作流</span><span class="sxs-lookup"><span data-stu-id="7d2d5-104">Pausing a Workflow</span></span>  
 <span data-ttu-id="7d2d5-105">若要暂停工作流，请使用 <xref:System.Activities.WorkflowApplication.Unload%2A>。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-105">To pause a workflow, use <xref:System.Activities.WorkflowApplication.Unload%2A>.</span></span>  <span data-ttu-id="7d2d5-106">此方法请求保留和卸载工作流，并将在工作流未在 30 秒内卸载时引发 <xref:System.TimeoutException>。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-106">This method requests that the workflow persist and unload, and will throw a <xref:System.TimeoutException> if the workflow does not unload in 30 seconds.</span></span>  
  
```csharp  
try  
{  
    // attempt to unload will fail if the workflow is idle within a NoPersistZone  
    application.Unload(TimeSpan.FromSeconds(5));  
}  
catch (TimeoutException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
## <a name="resuming-a-workflow"></a><span data-ttu-id="7d2d5-107">恢复工作流</span><span class="sxs-lookup"><span data-stu-id="7d2d5-107">Resuming a Workflow</span></span>  
 <span data-ttu-id="7d2d5-108">若要恢复之前已暂停且已卸载的工作流，请使用 <xref:System.Activities.WorkflowApplication.Load%2A>。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-108">To resume a previously paused and unloaded workflow, use <xref:System.Activities.WorkflowApplication.Load%2A>.</span></span> <span data-ttu-id="7d2d5-109">此方法会将工作流从持久性存储加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-109">This method loads a workflow from a persistence store into memory.</span></span>  
  
```csharp  
WorkflowApplication application = new WorkflowApplication(activity);  
application.InstanceStore = instanceStore;  
application.Load(id);  
```  
  
## <a name="example"></a><span data-ttu-id="7d2d5-110">示例</span><span class="sxs-lookup"><span data-stu-id="7d2d5-110">Example</span></span>  
 <span data-ttu-id="7d2d5-111">下面的代码示例演示如何使用持久性来暂停和恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="7d2d5-111">The following code sample demonstrates how to pause and resume a workflow by using persistence.</span></span>  
  
```csharp  
static string bkName = "bkName";  
static void Main(string[] args)   
{  
    StartAndUnloadInstance();  
}  
  
static void StartAndUnloadInstance()   
{  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(GetDelayedWF());  
    SqlWorkflowInstanceStore instanceStore = SetupSqlpersistenceStore();  
    wfApp.InstanceStore = instanceStore;  
    wfApp.Extensions.Add(SetupMyFileTrackingParticipant);  
    wfApp.PersistableIdle = (e) => {          ///persists application state and remove it from memory   
    return PersistableIdleAction.Unload;  
    };  
    wfApp.Unloaded = (e) => {  
        waitHandler.Set();  
    };  
    Guid id = wfApp.Id;  
    wfApp.Run();  
    waitHandler.WaitOne();  
    LoadAndCompleteInstance(id);  
}  
  
static void LoadAndCompleteInstance(Guid id)   
{            
    Console.WriteLine("Press <enter> to load the persisted workflow");  
    Console.ReadLine();  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(new Workflow1());  
    wfApp.InstanceStore =  
        new SqlWorkflowInstanceStore(ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString());  
    wfApp.Completed = (workflowApplicationCompletedEventArgs) => {  
        Console.WriteLine("\nWorkflowApplication has Completed in the {0} state.",  
            workflowApplicationCompletedEventArgs.CompletionState);  
    };  
    wfApp.Unloaded = (workflowApplicationEventArgs) => {  
        Console.WriteLine("WorkflowApplication has Unloaded\n");  
        waitHandler.Set();  
    };  
    wfApp.Load(id);  
    wfApp.Run();  
    waitHandler.WaitOne();  
}  
  
public static Activity GetDelayedWF()   
{  
    return new Sequence {  
        Activities ={  
            new WriteLine{Text="Workflow Started"},  
            new Delay{Duration=TimeSpan.FromSeconds(10)},  
            new WriteLine{Text="Workflow Ended"}  
        }  
    };  
}  
  
private static SqlWorkflowInstanceStore SetupSqlpersistenceStore()   
{   
     string connectionString = ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString();  
    SqlWorkflowInstanceStore sqlWFInstanceStore = new SqlWorkflowInstanceStore(connectionString);  
    sqlWFInstanceStore.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;  
    InstanceHandle handle = sqlWFInstanceStore.CreateInstanceHandle();  
    InstanceView view = sqlWFInstanceStore.Execute(handle, new CreateWorkflowOwnerCommand(), TimeSpan.FromSeconds(5));  
    handle.Free();  
    sqlWFInstanceStore.DefaultInstanceOwner = view.InstanceOwner;  
    return sqlWFInstanceStore;  
}  
```
