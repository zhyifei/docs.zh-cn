---
title: 非持久工作流实例
ms.date: 03/30/2017
ms.assetid: 5e01af77-6b14-4964-91a5-7dfd143449c0
ms.openlocfilehash: 410451f0dfeb91111e77634245aa786c4afc5b04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644260"
---
# <a name="non-persisted-workflow-instances"></a><span data-ttu-id="7a751-102">非持久工作流实例</span><span class="sxs-lookup"><span data-stu-id="7a751-102">Non-Persisted Workflow Instances</span></span>
<span data-ttu-id="7a751-103">在创建工作流的新实例（该实例在 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 中保留其状态）时，服务主机将在实例存储中为该服务实例创建一个项。</span><span class="sxs-lookup"><span data-stu-id="7a751-103">When a new instance of a workflow is created that persists its state in the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, the service host creates an entry for that service in the instance store.</span></span> <span data-ttu-id="7a751-104">随后，当第一次持久化工作流实例时，<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 将存储当前实例状态。</span><span class="sxs-lookup"><span data-stu-id="7a751-104">Subsequently, when the workflow instance is persisted for the first time, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> stores the current instance state.</span></span> <span data-ttu-id="7a751-105">如果工作流承载于 Windows 进程激活服务中，则服务部署数据也将在第一次持久化实例时写入实例存储中。</span><span class="sxs-lookup"><span data-stu-id="7a751-105">If the workflow is hosted in the Windows Process Activation Service, the service deployment data is also written to the instance store when the instance is persisted for the first time.</span></span>  
  
 <span data-ttu-id="7a751-106">只要工作流实例未保持不变，是在**非持久化**状态。</span><span class="sxs-lookup"><span data-stu-id="7a751-106">As long as the workflow instance has not been persisted, it is in a **non-persisted** state.</span></span> <span data-ttu-id="7a751-107">当处于此状态时，将无法在发生应用程序域回收、主机故障或计算机故障后恢复工作流实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-107">While in this state, the workflow instance cannot be recovered after an application domain recycle, host failure, or computer failure.</span></span>  
  
## <a name="the-non-persisted-state"></a><span data-ttu-id="7a751-108">非持久状化态</span><span class="sxs-lookup"><span data-stu-id="7a751-108">The Non-Persisted State</span></span>  
 <span data-ttu-id="7a751-109">尚未持久化的持久工作流实例在下列情况下将保持非持久化状态：</span><span class="sxs-lookup"><span data-stu-id="7a751-109">Durable workflow instances that have not been persisted remain in a non-persisted state in the following cases:</span></span>  
  
- <span data-ttu-id="7a751-110">在第一次持久化工作流实例之前，服务主机发生崩溃。</span><span class="sxs-lookup"><span data-stu-id="7a751-110">The service host crashes before the workflow instance is persisted for the first time.</span></span> <span data-ttu-id="7a751-111">工作流实例将保留在实例存储中且未恢复。</span><span class="sxs-lookup"><span data-stu-id="7a751-111">The workflow instance remains in the instance store and is not recovered.</span></span> <span data-ttu-id="7a751-112">如果获得关联的消息，则该工作流实例会再一次进入活动状态。</span><span class="sxs-lookup"><span data-stu-id="7a751-112">If a correlated message arrives, the workflow instance becomes active again.</span></span>  
  
- <span data-ttu-id="7a751-113">该工作流实例第一次持久化之前遇到异常。</span><span class="sxs-lookup"><span data-stu-id="7a751-113">The workflow instance experiences an exception before it is persisted for the first time.</span></span> <span data-ttu-id="7a751-114">将发生以下情况，具体取决于返回的 <xref:System.Activities.UnhandledExceptionAction>：</span><span class="sxs-lookup"><span data-stu-id="7a751-114">Depending on the <xref:System.Activities.UnhandledExceptionAction> returned, the following scenarios occur:</span></span>  
  
    - <span data-ttu-id="7a751-115"><xref:System.Activities.UnhandledExceptionAction> 设置为<xref:System.Activities.UnhandledExceptionAction.Abort>:异常发生时，将服务部署信息写入实例存储区，和是从内存中卸载工作流实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-115"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Abort>: When an exception occurs, service deployment information is written to the instance store, and the workflow instance is unloaded from memory.</span></span> <span data-ttu-id="7a751-116">工作流实例将保持非持久化状态且无法重新加载。</span><span class="sxs-lookup"><span data-stu-id="7a751-116">The workflow instance remains in a non-persisted state and cannot be reloaded.</span></span>  
  
    - <span data-ttu-id="7a751-117"><xref:System.Activities.UnhandledExceptionAction> 设置为<xref:System.Activities.UnhandledExceptionAction.Cancel>或<xref:System.Activities.UnhandledExceptionAction.Terminate>:当发生异常，将服务部署信息写入实例存储区，且活动实例状态设置为<xref:System.Activities.ActivityInstanceState.Closed>。</span><span class="sxs-lookup"><span data-stu-id="7a751-117"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Cancel> or <xref:System.Activities.UnhandledExceptionAction.Terminate>: When an exception occurs, service deployment information is written to the instance store, and the activity instance state is set to <xref:System.Activities.ActivityInstanceState.Closed>.</span></span>  
  
 <span data-ttu-id="7a751-118">若要最大程度地降低遇到已卸载非持久化工作流实例的风险，建议您在工作流生命周期的早期持久化工作流。</span><span class="sxs-lookup"><span data-stu-id="7a751-118">To minimize the risk of encountering unloaded non-persisted workflow instances, we recommend persisting the workflow early in its life cycle.</span></span>  
  
## <a name="detection-and-removal-of-non-persisted-instances"></a><span data-ttu-id="7a751-119">非持久化实例的检测和移除</span><span class="sxs-lookup"><span data-stu-id="7a751-119">Detection and Removal of Non-Persisted Instances</span></span>  
 <span data-ttu-id="7a751-120"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 将不移除实例存储中的任何非持久化工作流实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-120">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> does not remove any non-persisted workflow instances from the instance store.</span></span> <span data-ttu-id="7a751-121">它也不会移除任何具有关联的非持久化工作流实例的已过期锁定所有者。</span><span class="sxs-lookup"><span data-stu-id="7a751-121">It also does not remove any expired lock owners that have non-persisted workflow instances associated with them.</span></span>  
  
 <span data-ttu-id="7a751-122">建议管理员定期检查实例存储中的非持久化实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-122">We recommend that the administrator periodically checks the instance store for non-persisted instances.</span></span> <span data-ttu-id="7a751-123">只要管理员知道此工作流将不接收关联消息，就可以从实例存储中移除这些实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-123">Administrators can remove those instances from the instance store as long as they know that this workflow will not receive correlated messages.</span></span> <span data-ttu-id="7a751-124">例如，如果某个实例在数据库中已经存在了数月，并且知道工作流通常只有几天的生存期，则可以放心地认为这是一个已经崩溃的已初始化的实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-124">For example, if the instance has been in the database for several months and it is known that the workflow typically has a lifetime of several days, it would be safe to assume that this was an initialized instance that had crashed.</span></span>  
  
 <span data-ttu-id="7a751-125">若要在 SQL 工作流实例存储中查找非持久化实例，可使用以下 SQL 查询：</span><span class="sxs-lookup"><span data-stu-id="7a751-125">To find non-persisted instances in the SQL Workflow Instance Store you can use the following SQL queries:</span></span>  
  
- <span data-ttu-id="7a751-126">此查询将查找所有未持久化的实例，并返回这些实例的 ID 和创建时间（用 UTC 时间格式存储）。</span><span class="sxs-lookup"><span data-stu-id="7a751-126">This query finds all instances that have not been persisted, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0  
    ```  
  
- <span data-ttu-id="7a751-127">此查询将查找所有未持久化且未加载的实例，并返回这些实例的 ID 和创建时间（用 UTC 时间格式存储）。</span><span class="sxs-lookup"><span data-stu-id="7a751-127">This query finds all instances that have not been persisted, and that are not loaded, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and CurrentMachine is NULL  
    ```  
  
- <span data-ttu-id="7a751-128">此查询将查找所有未持久化的且挂起的实例，并返回这些实例的 ID、创建时间（用 UTC 时间格式存储）、挂起原因和异常名称。</span><span class="sxs-lookup"><span data-stu-id="7a751-128">This query finds all suspended instances that have not been persisted, and returns the ID, creation time (stored in UTC time), suspension reason, and exception name for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and IsSuspended = 1  
    ```  
  
 <span data-ttu-id="7a751-129">删除非持久化实例时务必小心。</span><span class="sxs-lookup"><span data-stu-id="7a751-129">Use care when you are deleting non-persisted instances.</span></span> <span data-ttu-id="7a751-130">通常，移除由 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 创建的已挂起或未加载的非持久化实例是安全的。</span><span class="sxs-lookup"><span data-stu-id="7a751-130">In general, it is safe to remove non-persisted instances created by <xref:System.ServiceModel.Activities.WorkflowServiceHost> that are suspended or are not loaded.</span></span> <span data-ttu-id="7a751-131">可通过使用以下 SQL 命令（替换正确的实例 ID）将这些特定实例从 `[System.Activities.DurableInstancing].[Instances]` 视图中删除，从而从存储中删除这些实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-131">Those specific instances can be deleted from the store by deleting them from the `[System.Activities.DurableInstancing].[Instances]` view by using the following SQL command, substituting the correct instance ID.</span></span>  
  
```sql  
delete [System.Activities.DurableInstancing].[Instances]   
    where InstanceId=’078a9bc4-ada5-4f9e-8cce-b0eb0009995f’  
```  
  
> [!WARNING]
>  <span data-ttu-id="7a751-132">建议不要移除所有非持久化实例，因为其中包括那些刚刚创建且尚未持久化的实例。</span><span class="sxs-lookup"><span data-stu-id="7a751-132">We do not recommend removing all non-persisted instances because this includes instances that have just been created and have not yet been persisted.</span></span>
