---
title: 在单阶段和多阶段中提交事务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
ms.openlocfilehash: e90a2f9c5681ffddb2a3ca0312bdd2f3f4078328
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589514"
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a><span data-ttu-id="12145-102">在单阶段和多阶段中提交事务</span><span class="sxs-lookup"><span data-stu-id="12145-102">Committing a Transaction in Single-Phase and Multi-Phase</span></span>
<span data-ttu-id="12145-103">事务中所使用的每个资源都由资源管理器 (RM) 进行管理，而资源管理器的操作则由事务管理器 (TM) 进行协调。</span><span class="sxs-lookup"><span data-stu-id="12145-103">Each resource used in a transaction is managed by a resource manager (RM), whose actions are coordinated by a transaction manager (TM).</span></span> <span data-ttu-id="12145-104">[将资源登记为参与者在事务中](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)主题将讨论如何在事务中登记一个资源 （或多个资源）。</span><span class="sxs-lookup"><span data-stu-id="12145-104">The [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) topic discusses how a resource (or multiple resources) can be enlisted in a transaction.</span></span> <span data-ttu-id="12145-105">本主题讨论如何在已登记的资源之间协调事务提交。</span><span class="sxs-lookup"><span data-stu-id="12145-105">This topic discusses how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
 <span data-ttu-id="12145-106">在事务结束时，应用程序会请求提交或回滚该事务。</span><span class="sxs-lookup"><span data-stu-id="12145-106">At the end of the transaction, the application requests the transaction to be either committed or rolled back.</span></span> <span data-ttu-id="12145-107">事务管理器必须消除类似于以下的风险：有些资源管理器投票决定提交，而有些资源管理器却投票决定回滚事务。</span><span class="sxs-lookup"><span data-stu-id="12145-107">The transaction manager must eliminate risks like some resource managers voting to commit while others voting to roll back the transaction.</span></span>  
  
 <span data-ttu-id="12145-108">如果事务涉及到多个资源，则必须执行两阶段提交 (2PC)。</span><span class="sxs-lookup"><span data-stu-id="12145-108">If your transaction involves more than one resource, you must perform a two-phase commit (2PC).</span></span> <span data-ttu-id="12145-109">两阶段提交协议（准备阶段和提交阶段）可确保在事务结束时，会完全提交或完全回滚对所有资源的所有更改。</span><span class="sxs-lookup"><span data-stu-id="12145-109">The two-phase commit protocol (the prepare phase and the commit phase) ensures that when the transaction ends, all changes to all resources are either totally committed or fully rolled back.</span></span> <span data-ttu-id="12145-110">然后，会向所有参与者通知最终结果。</span><span class="sxs-lookup"><span data-stu-id="12145-110">All the participants are then informed of the final result.</span></span> <span data-ttu-id="12145-111">有关两阶段提交协议的详细讨论，请参阅此书"*事务处理：概念和技术 （数据管理系统中的 Morgan Kaufmann 系列） ISBN:1558601902*"通过 Jim Gray。</span><span class="sxs-lookup"><span data-stu-id="12145-111">For a detailed discussion of the two-phase commit protocol, please consult the book "*Transaction Processing : Concepts and Techniques (Morgan Kaufmann Series in Data Management Systems) ISBN:1558601902*" by Jim Gray.</span></span>  
  
 <span data-ttu-id="12145-112">此外，还可以通过参与单阶段提交协议来优化事务的性能。</span><span class="sxs-lookup"><span data-stu-id="12145-112">You can also optimize your transaction's performance by taking part in the Single Phase Commit protocol.</span></span> <span data-ttu-id="12145-113">有关详细信息，请参阅[优化使用 Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)。</span><span class="sxs-lookup"><span data-stu-id="12145-113">For more information, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="12145-114">如果只希望得到事务结果的通知，而不希望参与投票，则应注册 <xref:System.Transactions.Transaction.TransactionCompleted> 事件。</span><span class="sxs-lookup"><span data-stu-id="12145-114">If you just want to be informed of a transaction's outcome, and do not want to participate in voting, you should register for the <xref:System.Transactions.Transaction.TransactionCompleted> event.</span></span>  
  
## <a name="two-phase-commit-2pc"></a><span data-ttu-id="12145-115">两阶段提交 (2PC)</span><span class="sxs-lookup"><span data-stu-id="12145-115">Two-phase Commit (2PC)</span></span>  
 <span data-ttu-id="12145-116">在第一个事务阶段，事务管理器将查询每个资源以确定是应提交还是回滚事务。</span><span class="sxs-lookup"><span data-stu-id="12145-116">In the first transaction phase, the transaction manager queries each resource to determine whether a transaction should be committed or rolled back.</span></span> <span data-ttu-id="12145-117">在第二个事务阶段，事务管理器会向每个资源通知它的查询结果，以便它可以执行任何必要的清理。</span><span class="sxs-lookup"><span data-stu-id="12145-117">In the second transaction phase, the transaction manager notifies each resource of the outcome of its queries, allowing it to perform any necessary cleanup.</span></span>  
  
 <span data-ttu-id="12145-118">若要参与这种事务，资源管理器必须实现 <xref:System.Transactions.IEnlistmentNotification> 接口，该接口提供在 2PC 期间由 TM 作为通知调用的方法。</span><span class="sxs-lookup"><span data-stu-id="12145-118">To participate in this kind of transaction, a resource manager must implement the <xref:System.Transactions.IEnlistmentNotification> interface, which provides methods that are called by the TM as notifications during a 2PC.</span></span>  <span data-ttu-id="12145-119">下面的示例演示了一个这种实现的示例。</span><span class="sxs-lookup"><span data-stu-id="12145-119">The following sample shows an example of such implementation.</span></span>  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a><span data-ttu-id="12145-120">准备阶段（第 1 阶段）</span><span class="sxs-lookup"><span data-stu-id="12145-120">Prepare phase (Phase 1)</span></span>  
 <span data-ttu-id="12145-121">在从应用程序接收到 <xref:System.Transactions.CommittableTransaction.Commit%2A> 请求时，事务管理器会对每个已登记的资源调用 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 方法来开始所有已登记参与者的准备阶段，以便获取事务上每个资源的投票。</span><span class="sxs-lookup"><span data-stu-id="12145-121">Upon receiving a <xref:System.Transactions.CommittableTransaction.Commit%2A> request from the application, the transaction manager begins the Prepare phase of all the enlisted participants by calling the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method on each enlisted resource, in order to obtain each resource's vote on the transaction.</span></span>  
  
 <span data-ttu-id="12145-122">实现 <xref:System.Transactions.IEnlistmentNotification> 接口的资源管理器应先实现 <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> 方法，如下面的简单示例所示。</span><span class="sxs-lookup"><span data-stu-id="12145-122">Your resource manager that implements the <xref:System.Transactions.IEnlistmentNotification> interface should first implement the <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> method as the following simple example shows.</span></span>  
  
```csharp
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 <span data-ttu-id="12145-123">当持久资源管理器接收到此调用时，它应记录事务的恢复信息（可通过检索 <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> 属性获取）以及在提交时完成事务所需的任何信息。</span><span class="sxs-lookup"><span data-stu-id="12145-123">When the durable resource manager receives this call, it should log the transaction's recovery information (available by retrieving the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> property) and whatever information is necessary to complete the transaction on commit.</span></span> <span data-ttu-id="12145-124">无需在 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 方法中执行这一操作，因为 RM 可在辅助线程上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="12145-124">This does not need to be performed within the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method because the RM can do this on a worker thread.</span></span>  
  
 <span data-ttu-id="12145-125">当 RM 完成其准备工作后，应调用 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> 或 <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> 方法来投票决定是提交还是回滚。</span><span class="sxs-lookup"><span data-stu-id="12145-125">When the RM has finished its prepare work, it should vote to commit or roll back by calling the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> or <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> method.</span></span> <span data-ttu-id="12145-126">请注意，<xref:System.Transactions.PreparingEnlistment> 类从 <xref:System.Transactions.Enlistment.Done%2A> 类继承 <xref:System.Transactions.Enlistment> 方法。</span><span class="sxs-lookup"><span data-stu-id="12145-126">Notice that the <xref:System.Transactions.PreparingEnlistment> class inherits a <xref:System.Transactions.Enlistment.Done%2A> method from the <xref:System.Transactions.Enlistment> class.</span></span> <span data-ttu-id="12145-127">如果在准备阶段在 <xref:System.Transactions.PreparingEnlistment> 回调时调用此方法，则此方法会向 TM 通知这是只读登记（也就是说，资源管理器可读取但不能更新受事务保护的数据），并且 RM 不会再从事务管理器接收到有关第 2 阶段中事务结果的任何通知。</span><span class="sxs-lookup"><span data-stu-id="12145-127">If you call this method on the <xref:System.Transactions.PreparingEnlistment> callback during the Prepare phase, it informs the TM that it is a Read-Only enlistment (that is, resource managers that can read but cannot update transaction-protected data) and the RM receives no further notifications from the transaction manager as to the outcome of the transaction in phase 2.</span></span>  
  
 <span data-ttu-id="12145-128">在所有资源管理器都对 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> 投票后，会向应用程序通知事务已成功提交。</span><span class="sxs-lookup"><span data-stu-id="12145-128">The application is told of the successful commitment of the transaction after all the resource managers vote <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span></span>  
  
### <a name="commit-phase-phase-2"></a><span data-ttu-id="12145-129">提交阶段（第 2 阶段）</span><span class="sxs-lookup"><span data-stu-id="12145-129">Commit phase (Phase 2)</span></span>  
 <span data-ttu-id="12145-130">在事务的第二阶段，如果事务管理器从所有资源管理器均获悉准备成功（所有资源管理器都已在第 1 阶段结束时调用了 <xref:System.Transactions.PreparingEnlistment.Prepared%2A>），则会为每个资源管理器调用 <xref:System.Transactions.IEnlistmentNotification.Commit%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="12145-130">In the second phase of the transaction, if the transaction manager receives successful prepares from all the resource managers (all the resource managers have invoked <xref:System.Transactions.PreparingEnlistment.Prepared%2A> at the end of phase 1), it invokes the <xref:System.Transactions.IEnlistmentNotification.Commit%2A> method for each resource manager.</span></span> <span data-ttu-id="12145-131">这样，资源管理器就可使更改永久固定下来并完成提交。</span><span class="sxs-lookup"><span data-stu-id="12145-131">The resource managers can then make the changes durable and complete the commit.</span></span>  
  
 <span data-ttu-id="12145-132">如果有任何资源管理器报告在第 1 阶段的准备失败，则事务管理器应为每个资源管理器调用 <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> 方法，并向应用程序指出提交失败。</span><span class="sxs-lookup"><span data-stu-id="12145-132">If any resource manager reported a failure to prepare in phase 1, the transaction manager invokes the <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> method for each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="12145-133">因此，资源管理器应实现下列方法。</span><span class="sxs-lookup"><span data-stu-id="12145-133">Thus, your resource manager should implement the following methods.</span></span>  
  
```csharp
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment    
     enlistment.Done();    
}  
```  
  
 <span data-ttu-id="12145-134">RM 应根据通知类型执行完成事务所需的所有工作，并在 <xref:System.Transactions.Enlistment.Done%2A> 参数上调用 <xref:System.Transactions.Enlistment> 方法来向 TM 通知它已完成。</span><span class="sxs-lookup"><span data-stu-id="12145-134">The RM should perform any work necessary to finish the transaction based on the notification type, and inform the TM that it has finished by calling <xref:System.Transactions.Enlistment.Done%2A> method on the <xref:System.Transactions.Enlistment> parameter.</span></span> <span data-ttu-id="12145-135">可在辅助线程上完成此工作。</span><span class="sxs-lookup"><span data-stu-id="12145-135">This work can be done on a worker thread.</span></span> <span data-ttu-id="12145-136">请注意，第 2 阶段的通知可能在第 1 阶段调用了 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> 方法的同一线程上发生内联。</span><span class="sxs-lookup"><span data-stu-id="12145-136">Note that the phase 2 notifications can happen inline on the same thread that called the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> method in phase 1.</span></span> <span data-ttu-id="12145-137">因此，在调用 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> 后，您不应执行任何预计在收到第 2 阶段通知前就可完成的操作（如释放锁定）。</span><span class="sxs-lookup"><span data-stu-id="12145-137">As such, you should not do any work after the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> call (for example, releasing locks) that you would expect to have completed before receiving the phase 2 notifications.</span></span>  
  
### <a name="implementing-indoubt"></a><span data-ttu-id="12145-138">实现 InDoubt</span><span class="sxs-lookup"><span data-stu-id="12145-138">Implementing InDoubt</span></span>  
 <span data-ttu-id="12145-139">最后，应为可变资源管理器实现 <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="12145-139">Finally, you should implement the <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> method for the volatile resource manager.</span></span> <span data-ttu-id="12145-140">如果事务管理器与一个或多个参与者失去联系，以致这些参与者的状态是未知的，则会调用此方法。</span><span class="sxs-lookup"><span data-stu-id="12145-140">This method is called if the transaction manager loses contact with one or more participants, so their status is unknown.</span></span> <span data-ttu-id="12145-141">如果发生这种情况，则应将相关事宜记录下来，以便可在以后调查是否有任何事务参与者事后处于不一致状态。</span><span class="sxs-lookup"><span data-stu-id="12145-141">If this occurs, you should log this fact so that you can investigate later whether any of the transaction participants has been left in an inconsistent state.</span></span>  
  
```csharp
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a><span data-ttu-id="12145-142">单阶段提交优化</span><span class="sxs-lookup"><span data-stu-id="12145-142">Single Phase Commit Optimization</span></span>  
 <span data-ttu-id="12145-143">单阶段提交协议在运行时更有效，因为使用它，无需进行任何显式协调就可执行所有更新。</span><span class="sxs-lookup"><span data-stu-id="12145-143">The Single Phase Commit protocol is more efficient at run time because all updates are done without any explicit coordination.</span></span> <span data-ttu-id="12145-144">有关此协议的详细信息，请参阅[优化使用 Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)。</span><span class="sxs-lookup"><span data-stu-id="12145-144">For more information on this protocol, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12145-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="12145-145">See also</span></span>
- [<span data-ttu-id="12145-146">使用单阶段提交和可提升的单阶段通知进行优化</span><span class="sxs-lookup"><span data-stu-id="12145-146">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)
- [<span data-ttu-id="12145-147">在事务中将资源登记为参与者</span><span class="sxs-lookup"><span data-stu-id="12145-147">Enlisting Resources as Participants in a Transaction</span></span>](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)
