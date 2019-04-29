---
title: 执行恢复
ms.date: 03/30/2017
ms.assetid: 6dd17bf6-ba42-460a-a44b-8046f52b10d0
ms.openlocfilehash: 149ac6b6162893de830f59b3d18008d8298eab56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793609"
---
# <a name="performing-recovery"></a>执行恢复
资源管理器通过在资源失败之后重新登记事务参与者来促进事务中的持久登记的解决。  
  
## <a name="the-recovery-process"></a>恢复过程  
 若要持久登记以后可恢复的资源（由 <xref:System.Transactions.IEnlistmentNotification> 接口的实现描述），应调用 <xref:System.Transactions.Transaction.EnlistDurable%2A> 方法。 此外，还必须使用资源管理器标识符 (<xref:System.Transactions.Transaction.EnlistDurable%2A>) 提供 <xref:System.Guid> 方法，资源管理器标识符可用于在资源失败时统一标记事务参与者。 出于此原因，<xref:System.Guid>提供给初始登记调用应为相同*resourceManagerIdentifier*中的参数<xref:System.Transactions.TransactionManager.Reenlist%2A>在恢复过程中调用。 否则，会引发 <xref:System.Transactions.TransactionException>。 有关持久登记的详细信息，请参阅[将资源登记为参与者在事务中](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)。  
  
 在 2PC 协议的准备阶段（第 1 阶段），当持久资源管理器的实现接收到 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 通知时，它应记录其在此阶段中的准备记录。 该记录应包含提交时完成事务所需的所有信息。 准备记录更高版本可在恢复期间通过检索<xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>的属性*preparingEnlistment*回调。 无需在 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 方法中执行记录，因为 RM 可在辅助线程上执行此操作。  
  
 恢复过程分为以下两步：  
  
### <a name="step-1---reenlist"></a>第 1 步 – 重新登记  
 资源管理器检查状态不确定的每个登记的准备信息记录。 通过检查 <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> 回调的 <xref:System.Transactions.PreparingEnlistment> 属性来执行该操作，该回调在第 1 阶段用 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 通知传递给资源管理器。  
  
 对于所检查的每个此类登记，它都会对事务管理器调用 <xref:System.Transactions.TransactionManager.Reenlist%2A>。 此方法会传递一个唯一的标识资源管理器的 <xref:System.Guid>，还会在字节数组中传递登记信息。 此时，将返回一个新的 <xref:System.Transactions.Enlistment> 对象。 如果重新登记失败并引发异常，则资源管理器将需要在以后重试。  
  
 当资源管理器从故障中重新启动时，只应调用 <xref:System.Transactions.TransactionManager.Reenlist%2A> 方法。 此外，应该仅重新登记在两阶段提交的初始准备阶段中由资源管理器记录的未解决事务。 在无效的时间调用此方法的任何尝试都可能产生错误的结果。  
  
 当使用此方法重新登记参与者时，将相应地调用对应于事务结果的 <xref:System.Transactions.IEnlistmentNotification> 的第 2 阶段方法（即 <xref:System.Transactions.IEnlistmentNotification.Commit%2A>、<xref:System.Transactions.IEnlistmentNotification.Rollback%2A> 或 <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A>）。  
  
### <a name="step-2---completing-the-recovery"></a>第 2 步 – 完成恢复  
 完成所有重新登记后，资源管理器会调用 <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> 方法。 此方法将完成恢复，并向事务管理器通知资源管理器不再有状态不确定的事务。 通过这样做，资源管理器可保证它不会再次调用 <xref:System.Transactions.TransactionManager.Reenlist%2A> 方法。  
  
 资源管理器在新事务中进行登记之前，无需解决所有状态不确定的事务。 可在资源管理器与事务管理器，但在建立关系后，随时执行第一步<xref:System.Transactions.TransactionManager.RecoveryComplete%2A>已被调用 （步骤 2）; 不能再次执行步骤 1。 可多次执行第 2 步，并且不会影响事务的结果。
