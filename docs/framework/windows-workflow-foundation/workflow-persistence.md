---
title: 工作流持久性
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
ms.openlocfilehash: 0a938f2f4d4cc790fe03db1e2b57862e54af48a7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748562"
---
# <a name="workflow-persistence"></a><span data-ttu-id="c6a8f-102">工作流持久性</span><span class="sxs-lookup"><span data-stu-id="c6a8f-102">Workflow Persistence</span></span>
<span data-ttu-id="c6a8f-103">工作流持久性是指独立于进程或计算机信息持续捕获工作流实例的状态。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-103">Workflow persistence is the durable capture of a workflow instance's state, independent of process or computer information.</span></span> <span data-ttu-id="c6a8f-104">其目的在于：在发生系统故障时为工作流实例提供一个已知恢复点，通过卸载当前未主动执行工作的工作流实例来节省内存，或者将工作流实例状态从服务器场中的一个节点移至另一个节点。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-104">This is done to provide a well-known point of recovery for the workflow instance in the event of system failure, or to preserve memory by unloading workflow instances that are not actively doing work, or to move the state of the workflow instance from one node to another node in a server farm.</span></span>  
  
 <span data-ttu-id="c6a8f-105">持久性支持进程灵活性、可扩展性、故障恢复以及更有效地管理内存的功能。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-105">Persistence enables process agility, scalability, recovery in the face of failure, and the ability to manage memory more efficiently.</span></span> <span data-ttu-id="c6a8f-106">持久性进程包括标识持久点、收集要保存的数据以及将数据实际存储最终委托给持久性提供程序。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-106">The persistence process includes the identification of a persistence point, the gathering of the data to be saved, and finally the delegation of the actual storage of the data to a persistence provider.</span></span>  
  
 <span data-ttu-id="c6a8f-107">若要启用工作流的持久性，您需要将实例存储与相关联**WorkflowApplication**或**WorkflowServiceHost**中所述[如何： 启用持久性工作流和工作流服务](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-107">To enable persistence for a workflow, you need to associate an instance store with the **WorkflowApplication** or **WorkflowServiceHost** as mentioned in [How to: Enable Persistence for Workflows and Workflow Services](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="c6a8f-108">**WorkflowApplication**并**WorkflowServiceHost**使用与其关联的实例存储到持久性存储区中，并加载到工作流实例将工作流实例基于存储在持久性存储区中的工作流实例数据的内存。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-108">The **WorkflowApplication** and **WorkflowServiceHost** use the instance store associated with them to enable persisting workflow instances into a persistence store and loading workflow instances into memory based on the workflow instance data stored in the persistence store.</span></span>  
  
 <span data-ttu-id="c6a8f-109">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]附带**SqlWorkflowInstanceStore**类，该类允许的数据和有关在 SQL Server 2005 或 SQL Server 2008 数据库的工作流实例的元数据持久性。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-109">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with the **SqlWorkflowInstanceStore** class, which allows persistence of data and metadata about workflow instances into a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="c6a8f-110">请参阅[SQL 工作流实例存储](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-110">See [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) for more details.</span></span>  
  
 <span data-ttu-id="c6a8f-111">若要存储和加载应用程序特定数据以及与工作流实例相关的信息，您可以创建用于扩展 <xref:System.Activities.Persistence.PersistenceParticipant> 类的持久性参与者。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-111">To store and load your application-specific data along with the workflow instance-related information, you can create persistence participants that extend the <xref:System.Activities.Persistence.PersistenceParticipant> class.</span></span> <span data-ttu-id="c6a8f-112">持久性参与者参与持久性进程的目的是：将可序列化的自定义数据保存到持久性存储中，将实例存储中的数据加载到内存中，以及在持久性事务下执行任何其他逻辑。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-112">A persistence participant participates in the persistence process to save custom serializable data into the persistence store, to load the data from the instance store into memory, and to perform any additional logic under a persistence transaction.</span></span> <span data-ttu-id="c6a8f-113">有关详细信息，请参阅[持久性参与者](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-113">For more information, see [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span></span>  
  
 <span data-ttu-id="c6a8f-114">Windows Server App Fabric 大大简化了配置持久性的过程。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-114">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> <span data-ttu-id="c6a8f-115">有关详细信息，请参阅[Windows Server App Fabric 的持久性概念](https://go.microsoft.com/fwlink/?LinkId=201200)</span><span class="sxs-lookup"><span data-stu-id="c6a8f-115">For more information, see [Persistence Concepts with Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201200)</span></span>  
  
## <a name="implicit-persistence-points"></a><span data-ttu-id="c6a8f-116">隐式持久点</span><span class="sxs-lookup"><span data-stu-id="c6a8f-116">Implicit Persistence Points</span></span>  
 <span data-ttu-id="c6a8f-117">以下列表包含当实例存储与工作流关联时持久化工作流所依据的条件的示例。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-117">The following list contains examples of the conditions upon which a workflow is persisted when an instance store is associated with a workflow.</span></span>  
  
-   <span data-ttu-id="c6a8f-118">当**TransactionScope**活动完成或**TransactedReceiveScope**活动完成。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-118">When a **TransactionScope** activity completes or a **TransactedReceiveScope** activity completes.</span></span>  
  
-   <span data-ttu-id="c6a8f-119">当工作流实例变为空闲状态并**WorkflowIdleBehavior**对工作流主机设置。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-119">When a workflow instance becomes idle and the **WorkflowIdleBehavior** is set on workflow host.</span></span> <span data-ttu-id="c6a8f-120">发生这种情况，例如，当使用消息传递活动或**延迟**活动。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-120">This occurs, for example, when you use messaging activities or a **Delay** activity.</span></span>  
  
-   <span data-ttu-id="c6a8f-121">当 WorkflowApplication 变为空闲状态并**PersistableIdle**应用程序的属性设置为**PersistableIdleAction.Persist**。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-121">When a WorkflowApplication becomes idle and the **PersistableIdle** property of the application is set to **PersistableIdleAction.Persist**.</span></span>  
  
-   <span data-ttu-id="c6a8f-122">当指示主机应用程序保存或卸载工作流实例时。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-122">When a host application is instructed to persist or unload a workflow instance.</span></span>  
  
-   <span data-ttu-id="c6a8f-123">当中止工作流实例或工作流实例结束时。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-123">When a workflow instance is terminated or finishes.</span></span>  
  
-   <span data-ttu-id="c6a8f-124">当**Persist**活动执行。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-124">When a **Persist** activity executes.</span></span>  
  
-   <span data-ttu-id="c6a8f-125">当使用 Windows Workflow Foundation 的早期版本开发的工作流实例在可互操作执行过程中遇到持久点时。</span><span class="sxs-lookup"><span data-stu-id="c6a8f-125">When an instance of a workflow developed using a previous version of Windows Workflow Foundation encounters a persistence point during interoperable execution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6a8f-126">本节内容</span><span class="sxs-lookup"><span data-stu-id="c6a8f-126">In This Section</span></span>  
  
-   [<span data-ttu-id="c6a8f-127">SQL 工作流实例存储</span><span class="sxs-lookup"><span data-stu-id="c6a8f-127">SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="c6a8f-128">实例存储</span><span class="sxs-lookup"><span data-stu-id="c6a8f-128">Instance Stores</span></span>](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [<span data-ttu-id="c6a8f-129">暂留参与者</span><span class="sxs-lookup"><span data-stu-id="c6a8f-129">Persistence Participants</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [<span data-ttu-id="c6a8f-130">暂留最佳做法</span><span class="sxs-lookup"><span data-stu-id="c6a8f-130">Persistence Best Practices</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [<span data-ttu-id="c6a8f-131">非暂留工作流实例</span><span class="sxs-lookup"><span data-stu-id="c6a8f-131">Non-Persisted Workflow Instances</span></span>](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [<span data-ttu-id="c6a8f-132">暂停和继续工作流</span><span class="sxs-lookup"><span data-stu-id="c6a8f-132">Pausing and Resuming a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
