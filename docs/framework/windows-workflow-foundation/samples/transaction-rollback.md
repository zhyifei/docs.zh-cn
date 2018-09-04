---
title: 事务回滚
ms.date: 03/30/2017
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
ms.openlocfilehash: 8134623248b072ec5a095ab9b10840e94a09243c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528972"
---
# <a name="transaction-rollback"></a><span data-ttu-id="31fbd-102">事务回滚</span><span class="sxs-lookup"><span data-stu-id="31fbd-102">Transaction Rollback</span></span>
<span data-ttu-id="31fbd-103">此示例演示如何创建一个自定义 <xref:System.Activities.NativeActivity>，用于访问环境 <xref:System.Activities.RuntimeTransactionHandle> 以获取环境事务并显式回滚它。</span><span class="sxs-lookup"><span data-stu-id="31fbd-103">This sample shows how to create a custom <xref:System.Activities.NativeActivity> that accesses the ambient <xref:System.Activities.RuntimeTransactionHandle> to get the ambient transaction and explicitly roll it back.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="31fbd-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="31fbd-104">Sample Details</span></span>  
 <span data-ttu-id="31fbd-105">在工作流中，当最外面的 <xref:System.Activities.Statements.TransactionScope> 或 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 完成时，将会自动完成一个事务。</span><span class="sxs-lookup"><span data-stu-id="31fbd-105">In workflow, a transaction is automatically completed when the outermost <xref:System.Activities.Statements.TransactionScope> or <xref:System.ServiceModel.Activities.TransactedReceiveScope> completes.</span></span>  <span data-ttu-id="31fbd-106">当未经处理的异常跨过范围边界传播时，将会隐式回滚一个事务。</span><span class="sxs-lookup"><span data-stu-id="31fbd-106">A transaction implicitly rolls back when an unhandled exception propagates across the scope boundary.</span></span> <span data-ttu-id="31fbd-107">但是，您有时可能有必要显式回滚一个事务，而不必引发异常。</span><span class="sxs-lookup"><span data-stu-id="31fbd-107">However, there may be times when it makes sense to explicitly roll back a transaction without having to throw an exception.</span></span> <span data-ttu-id="31fbd-108">在这种情况下，您可以使用此示例中的类似的自定义回滚活动，显式中止环境事务并提供一个可选的异常原因。</span><span class="sxs-lookup"><span data-stu-id="31fbd-108">In this case, you can use the custom rollback activity like the one in this sample to explicitly abort the ambient transaction and provide an optional exception reason.</span></span>  
  
 <span data-ttu-id="31fbd-109">`RollbackActivity` 是一个 <xref:System.Activities.NativeActivity>， 因为它需要访问执行属性以获取环境 <xref:System.Activities.RuntimeTransactionHandle>。</span><span class="sxs-lookup"><span data-stu-id="31fbd-109">The `RollbackActivity` is a <xref:System.Activities.NativeActivity> as it requires access to the execution properties to get the ambient <xref:System.Activities.RuntimeTransactionHandle>.</span></span> <span data-ttu-id="31fbd-110">在 `Execute` 方法中，它包含 <xref:System.Activities.RuntimeTransactionHandle> 并检查它是否为 `null`，null 表示没有通过环境运行时事务来使用该活动。</span><span class="sxs-lookup"><span data-stu-id="31fbd-110">In the `Execute` method, it obtains the <xref:System.Activities.RuntimeTransactionHandle> and checks whether it is `null`, which indicates that the activity was used without an ambient run-time transaction.</span></span> <span data-ttu-id="31fbd-111">然后，它获取该事务，并再次检查是否存在 `null`。</span><span class="sxs-lookup"><span data-stu-id="31fbd-111">It then obtains the transaction, again checking whether `null` is present.</span></span> <span data-ttu-id="31fbd-112">即使没有初始化运行时事务，也可能会有一个环境 <xref:System.Activities.RuntimeTransactionHandle>。</span><span class="sxs-lookup"><span data-stu-id="31fbd-112">It is possible to have an ambient <xref:System.Activities.RuntimeTransactionHandle> without ever initializing a run-time transaction.</span></span> <span data-ttu-id="31fbd-113">最后，它通过调用 <xref:System.Transactions.Transaction.Rollback%2A> 并指定用户提供的异常或表明活动已回滚事务的一般异常，中止事务。</span><span class="sxs-lookup"><span data-stu-id="31fbd-113">Finally it aborts the transaction by calling <xref:System.Transactions.Transaction.Rollback%2A> and specifying either a user-provided exception or a generic exception that states that the activity rolled back the transaction.</span></span>  
  
 <span data-ttu-id="31fbd-114">演示工作流包含一个 <xref:System.Activities.Statements.TransactionScope>，它的主体在 `RollbackActivity` 执行前后输出事务状态。</span><span class="sxs-lookup"><span data-stu-id="31fbd-114">The demonstration workflow consists of a <xref:System.Activities.Statements.TransactionScope> whose body prints the transaction status before and after the `RollbackActivity` executes.</span></span> <span data-ttu-id="31fbd-115">请注意，即使已回滚事务，<xref:System.Activities.Statements.TransactionScope> 也会完成执行操作，并且在主体完成之前不会中止工作流。</span><span class="sxs-lookup"><span data-stu-id="31fbd-115">Note that even though the transaction has been rolled back, the <xref:System.Activities.Statements.TransactionScope> executes to completion and does not abort the workflow until the body completes.</span></span> <span data-ttu-id="31fbd-116">工作流中止的原因是 <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> 属性默认设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="31fbd-116">The workflow is aborted because the <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> property defaults to `true`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="31fbd-117">使用此示例</span><span class="sxs-lookup"><span data-stu-id="31fbd-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="31fbd-118">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载 TransactionRollback.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="31fbd-118">Load the TransactionRollback.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="31fbd-119">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="31fbd-119">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="31fbd-120">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="31fbd-120">Press CTRL+F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="31fbd-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="31fbd-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="31fbd-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="31fbd-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="31fbd-123">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="31fbd-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="31fbd-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="31fbd-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## <a name="see-also"></a><span data-ttu-id="31fbd-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="31fbd-125">See Also</span></span>  
 [<span data-ttu-id="31fbd-126">事务</span><span class="sxs-lookup"><span data-stu-id="31fbd-126">Transactions</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)
