---
title: '&lt;sqlWorkflowInstanceStore&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d412e13dc42107d2bfe11c94e51e9690d0c5206b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltsqlworkflowinstancestoregt"></a><span data-ttu-id="d2954-102">&lt;sqlWorkflowInstanceStore&gt;</span><span class="sxs-lookup"><span data-stu-id="d2954-102">&lt;sqlWorkflowInstanceStore&gt;</span></span>
<span data-ttu-id="d2954-103">允许你配置的服务行为<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>功能，支持到 SQL Server 2005 或 SQL Server 2008 数据库的工作流服务实例的保存状态信息。</span><span class="sxs-lookup"><span data-stu-id="d2954-103">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="d2954-104">有关此功能的详细信息，请参阅[SQL 工作流实例存储](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)。</span><span class="sxs-lookup"><span data-stu-id="d2954-104">For more information on this feature, see [SQL Workflow Instance Store](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>  
  
<span data-ttu-id="d2954-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d2954-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d2954-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d2954-106">\<behaviors></span></span>  
<span data-ttu-id="d2954-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d2954-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="d2954-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d2954-108">\<behavior></span></span>  
<span data-ttu-id="d2954-109">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="d2954-109">\<sqlWorkflowInstanceStore></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2954-110">语法</span><span class="sxs-lookup"><span data-stu-id="d2954-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                honstLockRenewalPeriod="TimeSpan" 
                                instanceCompletionAction="DeleteNothing/DeleteAll" 
                                instanceEncodingAction="None/GZip" 
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2954-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2954-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d2954-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d2954-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2954-113">特性</span><span class="sxs-lookup"><span data-stu-id="d2954-113">Attributes</span></span>  
  
|<span data-ttu-id="d2954-114">特性</span><span class="sxs-lookup"><span data-stu-id="d2954-114">Attribute</span></span>|<span data-ttu-id="d2954-115">描述</span><span class="sxs-lookup"><span data-stu-id="d2954-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2954-116">connectionString</span><span class="sxs-lookup"><span data-stu-id="d2954-116">connectionString</span></span>|<span data-ttu-id="d2954-117">包含用于连接到基础持久性数据库的连接字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2954-117">A string that contains a connection string used to connect to an underlying persistence database.</span></span>|  
|<span data-ttu-id="d2954-118">connectionStringName</span><span class="sxs-lookup"><span data-stu-id="d2954-118">connectionStringName</span></span>|<span data-ttu-id="d2954-119">包含数据库服务器的已命名的连接字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2954-119">A string that contains a named connection string to the database server.</span></span> <span data-ttu-id="d2954-120">已命名的连接字符串的示例为"DefaultConnectionString"。</span><span class="sxs-lookup"><span data-stu-id="d2954-120">An example of a named connection string is "DefaultConnectionString".</span></span>|  
|<span data-ttu-id="d2954-121">honstLockRenewalPeriod</span><span class="sxs-lookup"><span data-stu-id="d2954-121">honstLockRenewalPeriod</span></span>|<span data-ttu-id="d2954-122">一个 Timespan 值，指定宿主必须在其间续订对某个实例的锁定的时间段。</span><span class="sxs-lookup"><span data-stu-id="d2954-122">A Timespan value that specifies the time period in which the host must renew the lock on an instance.</span></span> <span data-ttu-id="d2954-123">如果宿主没有在指定的时间段内续订锁定，则会解除锁定此实例，并且另一宿主可能会选取此实例。</span><span class="sxs-lookup"><span data-stu-id="d2954-123">If the host does not renew the lock in the specified time period, the instance is unlocked and may be picked up by another host.</span></span><br /><br /> <span data-ttu-id="d2954-124">卸载一个工作流意味着该工作流已持久保存。</span><span class="sxs-lookup"><span data-stu-id="d2954-124">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="d2954-125">如果此属性设置为零持久保存工作流实例，并后立即卸载工作流进入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="d2954-125">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="d2954-126">此属性设置为 TimeSpan.MaxValue 有效禁用卸载操作。</span><span class="sxs-lookup"><span data-stu-id="d2954-126">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="d2954-127">处于空闲状态的工作流实例永远不会被卸载。</span><span class="sxs-lookup"><span data-stu-id="d2954-127">Idle workflow instances are never unloaded.</span></span>|  
|<span data-ttu-id="d2954-128">instanceCompletionAction</span><span class="sxs-lookup"><span data-stu-id="d2954-128">instanceCompletionAction</span></span>|<span data-ttu-id="d2954-129">一个值，指定在工作流实例完成之后，该工作流实例数据是保留在持久性存储区中还是被删除。</span><span class="sxs-lookup"><span data-stu-id="d2954-129">A value that specifies whether workflow instance data is kept in the persistence store after the workflow instance completes or if it is deleted at that point.</span></span> <span data-ttu-id="d2954-130">此值的类型为 <xref:System.Activities.DurableInstancing.InstanceCompletionAction>。</span><span class="sxs-lookup"><span data-stu-id="d2954-130">This value is of type <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.</span></span><br /><br /> <span data-ttu-id="d2954-131">枚举的操作包括在实例完成其操作后删除持久性存储区中的实例数据或不删除持久性存储区中的实例数据。</span><span class="sxs-lookup"><span data-stu-id="d2954-131">The enumerated actions consist of deleting the instance data from the persistence store or not deleting the instance data from the persistence store, when the instance has completed its operation.</span></span><br /><br /> <span data-ttu-id="d2954-132">完成实例之后保留实例会导致持久性数据库快速增大，这会影响数据库的性能。</span><span class="sxs-lookup"><span data-stu-id="d2954-132">Keeping instances after completion causes the persistence database to grow rapidly and this affects the performance of the database.</span></span> <span data-ttu-id="d2954-133">您应当配置数据库清除策略来定期删除这些记录，以确保数据库的性能水平能够满足性能要求。</span><span class="sxs-lookup"><span data-stu-id="d2954-133">You should configure a database purge policy to delete these records periodically to ensure that the performance of the database is at the level that satisfy your performance requirements.</span></span>|  
|<span data-ttu-id="d2954-134">instanceEncodingOption</span><span class="sxs-lookup"><span data-stu-id="d2954-134">instanceEncodingOption</span></span>|<span data-ttu-id="d2954-135">一个可选值，指定在将实例状态信息保存到持久性存储区之前，是否使用 GZip 算法压缩此信息。</span><span class="sxs-lookup"><span data-stu-id="d2954-135">An optional value that specifies  whether the instance state information is compressed using the GZip algorithm before the information is saved in the persistence store..</span></span> <span data-ttu-id="d2954-136">此值的类型为 `System.Activities.DurableInstancing.InstanceEncodingAction`。</span><span class="sxs-lookup"><span data-stu-id="d2954-136">This value is of type `System.Activities.DurableInstancing.InstanceEncodingAction`.</span></span> <span data-ttu-id="d2954-137">此属性的可能值为"None"，它指定无压缩和"GZip"，指定该实例数据进行压缩，并使用 gzip 算法。</span><span class="sxs-lookup"><span data-stu-id="d2954-137">Possible values for this property are "None", which specifies no compression, and "GZip", which specifies that instance data is compressed and uses the gzip algorithm.</span></span>|  
|<span data-ttu-id="d2954-138">instanceLockedExceptionAction</span><span class="sxs-lookup"><span data-stu-id="d2954-138">instanceLockedExceptionAction</span></span>|<span data-ttu-id="d2954-139">一个值，指定为响应在宿主尝试锁定当前已由另一宿主锁定的实例时引发的异常而发生的操作。</span><span class="sxs-lookup"><span data-stu-id="d2954-139">A value that specifies the action that occurs in response to an exception that is thrown when the host tries to lock an instance because the instance is currently locked by another host.</span></span> <span data-ttu-id="d2954-140">此值的类型为 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>。</span><span class="sxs-lookup"><span data-stu-id="d2954-140">This value is of type <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.</span></span><br /><br /> <span data-ttu-id="d2954-141">此字段的可选选项有：“无”、“基本重试”和“积极重试”。</span><span class="sxs-lookup"><span data-stu-id="d2954-141">The options allowed for this field are: None, Basic Retry, and Aggressive Retry.</span></span> <span data-ttu-id="d2954-142">默认值为 None。</span><span class="sxs-lookup"><span data-stu-id="d2954-142">The default value is None.</span></span> <span data-ttu-id="d2954-143">下面逐一说明上述三个选项：</span><span class="sxs-lookup"><span data-stu-id="d2954-143">The following list provides you with the descriptions for these three options:</span></span><br /><br /> <span data-ttu-id="d2954-144">-   无。</span><span class="sxs-lookup"><span data-stu-id="d2954-144">-   None.</span></span> <span data-ttu-id="d2954-145">服务主机不会尝试锁定实例，并将 <xref:System.Runtime.DurableInstancing.InstanceLockedException> 传递给调用方。</span><span class="sxs-lookup"><span data-stu-id="d2954-145">The service host does not attempt to lock the instance and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller.</span></span><br /><span data-ttu-id="d2954-146">-基本重试。</span><span class="sxs-lookup"><span data-stu-id="d2954-146">-   Basic Retry.</span></span> <span data-ttu-id="d2954-147">服务主机将使用线性重试间隔重新尝试锁定实例，并在序列结尾将异常传递给调用方。</span><span class="sxs-lookup"><span data-stu-id="d2954-147">The service host reattempts to lock the instance with a linear retry interval and passes the exception to the caller at the end of the sequence.</span></span><br /><span data-ttu-id="d2954-148">-积极重试。</span><span class="sxs-lookup"><span data-stu-id="d2954-148">-   Aggressive Retry.</span></span> <span data-ttu-id="d2954-149">服务主机将使用按指数增长的延迟时间重新尝试锁定实例，并在序列结尾将 <xref:System.Runtime.DurableInstancing.InstanceLockedException> 传递给调用方。</span><span class="sxs-lookup"><span data-stu-id="d2954-149">The service host reattempts to lock the instance with an exponentially increasing delay and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller at the end of the sequence.</span></span>|  
|<span data-ttu-id="d2954-150">runnableInstancesDetectionPeriod</span><span class="sxs-lookup"><span data-stu-id="d2954-150">runnableInstancesDetectionPeriod</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="d2954-151">子元素</span><span class="sxs-lookup"><span data-stu-id="d2954-151">Child Elements</span></span>  
 <span data-ttu-id="d2954-152">无。</span><span class="sxs-lookup"><span data-stu-id="d2954-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2954-153">父元素</span><span class="sxs-lookup"><span data-stu-id="d2954-153">Parent Elements</span></span>  
  
|<span data-ttu-id="d2954-154">元素</span><span class="sxs-lookup"><span data-stu-id="d2954-154">Element</span></span>|<span data-ttu-id="d2954-155">描述</span><span class="sxs-lookup"><span data-stu-id="d2954-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2954-156">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d2954-156">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="d2954-157">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="d2954-157">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2954-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2954-158">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>  
 [<span data-ttu-id="d2954-159">SQL 工作流实例存储</span><span class="sxs-lookup"><span data-stu-id="d2954-159">SQL Workflow Instance Store</span></span>](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
