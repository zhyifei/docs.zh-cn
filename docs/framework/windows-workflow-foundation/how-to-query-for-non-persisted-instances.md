---
title: 如何：查询非持有化实例
ms.date: 03/30/2017
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
ms.openlocfilehash: 000342013be4380e1a038fb8233050523f6bc758
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009781"
---
# <a name="how-to-query-for-non-persisted-instances"></a><span data-ttu-id="71a1d-102">如何：查询非持有化实例</span><span class="sxs-lookup"><span data-stu-id="71a1d-102">How to: Query for Non-persisted Instances</span></span>
<span data-ttu-id="71a1d-103">创建某个服务的新实例时，如果该服务已定义 SQL 工作流实例存储行为，则服务主机将在实例存储区中为该服务实例创建一个初始项。</span><span class="sxs-lookup"><span data-stu-id="71a1d-103">When a new instance of a service is created and the service has the SQL Workflow Instance Store behavior defined, the service host creates a initial entry for that service instance in the instance store.</span></span> <span data-ttu-id="71a1d-104">随后，当该服务实例第一次持久化时，SQL 工作流实例存储行为会将当前实例状态与执行激活、恢复和控制操作所需的其他数据一起存储。</span><span class="sxs-lookup"><span data-stu-id="71a1d-104">Subsequently when the service instance persists for the first time, the SQL Workflow Instance Store behavior stores the current instance state together with additional data that is required for activation, recovery, and control.</span></span>  
  
 <span data-ttu-id="71a1d-105">如果在创建某个实例的初始项后没有持久化该实例，则认为该服务实例处于非持久化状态。 </span><span class="sxs-lookup"><span data-stu-id="71a1d-105">If an instance is not persisted after the initial entry for the instance is created, the service instance is said to be in the non-persisted state.</span></span> <span data-ttu-id="71a1d-106">可以查询和控制所有持久化服务实例。</span><span class="sxs-lookup"><span data-stu-id="71a1d-106">All the persisted service instances can be queried and controlled.</span></span> <span data-ttu-id="71a1d-107">不能查询和控制非持久化服务实例。</span><span class="sxs-lookup"><span data-stu-id="71a1d-107">Non-persisted service instances can neither be queried nor controlled.</span></span> <span data-ttu-id="71a1d-108">如果由于未处理的异常而挂起非持久化实例，则可以对该实例进行查询，但不能对它控制。</span><span class="sxs-lookup"><span data-stu-id="71a1d-108">If a non-persisted instance is suspended due to an unhandled exception it can be queried but not controlled.</span></span>  
  
 <span data-ttu-id="71a1d-109">尚未持久化的持久服务实例在下列情况中将保持非持久化状态：</span><span class="sxs-lookup"><span data-stu-id="71a1d-109">Durable service instances that are not yet persisted remain in a non-persisted state in the following scenarios:</span></span>  
  
- <span data-ttu-id="71a1d-110">在第一次持久化实例之前，服务主机出现故障。</span><span class="sxs-lookup"><span data-stu-id="71a1d-110">The service host crashes before the instance persisted for the first time.</span></span> <span data-ttu-id="71a1d-111">实例的初始项保留在实例存储区中。</span><span class="sxs-lookup"><span data-stu-id="71a1d-111">The initial entry for the instance remains in the instance store.</span></span> <span data-ttu-id="71a1d-112">该实例不可恢复。</span><span class="sxs-lookup"><span data-stu-id="71a1d-112">The instance is not recoverable.</span></span> <span data-ttu-id="71a1d-113">如果获得关联的消息，则该实例再一次进入活动状态。</span><span class="sxs-lookup"><span data-stu-id="71a1d-113">If a correlated message arrives, the instance becomes active again.</span></span>  
  
- <span data-ttu-id="71a1d-114">该实例第一次持久化之前遇到未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="71a1d-114">The instance experiences an unhandled exception before it persisted for the first time.</span></span> <span data-ttu-id="71a1d-115">出现下列情况</span><span class="sxs-lookup"><span data-stu-id="71a1d-115">The following scenarios arise</span></span>  
  
    - <span data-ttu-id="71a1d-116">如果的值**UnhandledExceptionAction**属性设置为**放弃**，服务部署信息写入实例存储区并实例从内存中卸载。</span><span class="sxs-lookup"><span data-stu-id="71a1d-116">If the value of the **UnhandledExceptionAction** property is set to **Abandon**, the service deployment information is written to the instance store and the instance is unloaded from memory.</span></span> <span data-ttu-id="71a1d-117">在持久性数据库中，该实例保持非持久化状态。</span><span class="sxs-lookup"><span data-stu-id="71a1d-117">The instance remains in non-persisted state in the persistence database.</span></span>  
  
    - <span data-ttu-id="71a1d-118">如果的值**UnhandledExceptionAction**属性设置为**AbandonAndSuspsend**、 服务部署信息写入到持久性数据库和实例状态设置为**挂起**。</span><span class="sxs-lookup"><span data-stu-id="71a1d-118">If the value of the **UnhandledExceptionAction** property is set to **AbandonAndSuspsend**, the service deployment information is written to the persistence database and the instance state is set to **Suspended**.</span></span> <span data-ttu-id="71a1d-119">无法恢复、取消或终止该实例。</span><span class="sxs-lookup"><span data-stu-id="71a1d-119">The instance cannot be resumed, canceled, or terminated.</span></span> <span data-ttu-id="71a1d-120">由于该实例尚未持久化，服务主机无法加载该实例，因此该实例的数据库项不完整。</span><span class="sxs-lookup"><span data-stu-id="71a1d-120">The service host cannot load the instance because the instance hasn't persisted yet and, hence the database entry for the instance is not complete.</span></span>  
  
    - <span data-ttu-id="71a1d-121">如果的值**UnhandledExceptionAction**属性设置为**取消**或**终止**，服务部署信息写入实例存储区和实例状态设置为**已完成**。</span><span class="sxs-lookup"><span data-stu-id="71a1d-121">If the value of the **UnhandledExceptionAction** property is set to **Cancel** or **Terminate**, the service deployment information is written to the instance store and the instance state is set to **Completed**.</span></span>  
  
 <span data-ttu-id="71a1d-122">下面的部分提供一些示例查询，用于在 SQL 持久性数据库中查找未持久化实例并从数据库删除这些实例。</span><span class="sxs-lookup"><span data-stu-id="71a1d-122">The following sections provide sample queries to find non-persisted instances in the SQL persistence database and to delete these instances from the database.</span></span>  
  
## <a name="to-find-all-instances-not-persisted-yet"></a><span data-ttu-id="71a1d-123">查找所有尚未持久化的实例</span><span class="sxs-lookup"><span data-stu-id="71a1d-123">To find all instances not persisted yet</span></span>  
 <span data-ttu-id="71a1d-124">下面的 SQL 查询返回所有尚未保存到持久性数据库的实例的 ID 和创建时间。</span><span class="sxs-lookup"><span data-stu-id="71a1d-124">The following SQL query returns the ID and creation time for all instances that are not persisted in to the persistence database yet.</span></span>  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;  
```  
  
## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a><span data-ttu-id="71a1d-125">查找所有尚未持久化并且未加载的实例</span><span class="sxs-lookup"><span data-stu-id="71a1d-125">To find all instances not persisted yet and also not loaded</span></span>  
 <span data-ttu-id="71a1d-126">下面的 SQL 查询返回所有未持久化且未加载的实例的 ID 和创建时间。</span><span class="sxs-lookup"><span data-stu-id="71a1d-126">The following SQL query returns ID and creation time for all instances that are not persisted and also are not loaded.</span></span>  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;  
```  
  
## <a name="to-find-all-suspended-instances-not-persisted-yet"></a><span data-ttu-id="71a1d-127">查找所有尚未持久化的挂起的实例</span><span class="sxs-lookup"><span data-stu-id="71a1d-127">To find all suspended instances not persisted yet</span></span>  
 <span data-ttu-id="71a1d-128">下面的 SQL 查询返回所有未持久化且处于挂起状态的实例的 ID、创建时间、挂起原因和挂起异常名称。</span><span class="sxs-lookup"><span data-stu-id="71a1d-128">The following SQL query returns ID, creation time, suspension reason, and suspension exception name for all instances that are not persisted and also in a suspended state.</span></span>  
  
```  
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;  
```  
  
## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a><span data-ttu-id="71a1d-129">从持久性数据库中删除非持久化实例</span><span class="sxs-lookup"><span data-stu-id="71a1d-129">To delete non-persisted instances from the persistence database</span></span>  
 <span data-ttu-id="71a1d-130">应定期检查实例存储区中的非持久化实例，如果确认该实例将不会接收到关联的消息，则从实例存储区中移除该实例。</span><span class="sxs-lookup"><span data-stu-id="71a1d-130">You should periodically check the instance store for non-persisted instances and remove instances from the instance store if you are sure that the instance will not receive a correlated message.</span></span> <span data-ttu-id="71a1d-131">如果某个实例在数据库中已经存在了数月，并且您知道工作流通常只有几天的生存期，则可以放心地认为这是一个已经崩溃的未初始化的实例。</span><span class="sxs-lookup"><span data-stu-id="71a1d-131">For example, if the instance has been in the database for several months and you know that the workflow typically has a lifetime of a few days, it would be safe to assume that this is an uninitialized instance that had crashed.</span></span>  
  
 <span data-ttu-id="71a1d-132">通常，删除未挂起或未加载的非持久化实例是安全的。</span><span class="sxs-lookup"><span data-stu-id="71a1d-132">In general, it is safe to delete non-persisted instances that are not suspended or not loaded.</span></span> <span data-ttu-id="71a1d-133">不应删除**所有**非持久化实例因为此实例集还包括那些刚刚创建但不是实例尚未持久化的。</span><span class="sxs-lookup"><span data-stu-id="71a1d-133">You should not delete **all** the non-persisted instances because this instance set includes instances that are just created but are not persisted yet.</span></span> <span data-ttu-id="71a1d-134">只应删除那些因加载实例的工作流服务主机引发了异常或实例本身引发了异常而留下的非持久化实例。</span><span class="sxs-lookup"><span data-stu-id="71a1d-134">You should only delete non-persisted instances that are left over because the workflow service host that had the instance loaded caused an exception or the instance itself caused an exception.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="71a1d-135">从实例存储区删除非持久化实例可减少存储的大小，并可能提高存储操作的性能。</span><span class="sxs-lookup"><span data-stu-id="71a1d-135">Deleting non-persisted instances from the instance store decreases the size of the store and may improve the performance of store operations.</span></span>
