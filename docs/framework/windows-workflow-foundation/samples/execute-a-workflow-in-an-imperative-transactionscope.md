---
title: 在命令式 TransactionScope 中执行工作流
ms.date: 03/30/2017
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
ms.openlocfilehash: 2744434e807664ca93b4f5bc27a1f3b89716ce87
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520165"
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a><span data-ttu-id="d5f41-102">在命令式 TransactionScope 中执行工作流</span><span class="sxs-lookup"><span data-stu-id="d5f41-102">Execute a Workflow in an Imperative TransactionScope</span></span>
<span data-ttu-id="d5f41-103">此示例演示如何利用命令性 C# 代码，在 <xref:System.Activities.WorkflowInvoker> 中使用 <xref:System.Transactions.Transaction> 来执行工作流。</span><span class="sxs-lookup"><span data-stu-id="d5f41-103">This sample shows how to execute a workflow using <xref:System.Activities.WorkflowInvoker> under a <xref:System.Transactions.Transaction> from imperative C# code.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="d5f41-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="d5f41-104">Sample Details</span></span>  
 <span data-ttu-id="d5f41-105">在命令性 C# 代码中，使用 <xref:System.Transactions.TransactionScope> 封装在同一个事务中执行的工作集。</span><span class="sxs-lookup"><span data-stu-id="d5f41-105">In imperative C# code, the <xref:System.Transactions.TransactionScope> is used to encapsulate a set of work that executes under the same transaction.</span></span> <span data-ttu-id="d5f41-106"><xref:System.Transactions.TransactionScope> 采用以下工作方式：创建一个环境事务并初始化 <xref:System.Transactions.Transaction.Current%2A> 属性，对该线程执行的任何工作然后可以访问该属性。</span><span class="sxs-lookup"><span data-stu-id="d5f41-106">The <xref:System.Transactions.TransactionScope> works by creating an ambient transaction and initializing the <xref:System.Transactions.Transaction.Current%2A> property, which can then be accessed by any work being executed on that thread.</span></span>  
  
 <span data-ttu-id="d5f41-107">若要在工作流中实现等效行为，在执行各项活动之前，运行时必须完成初始化 <xref:System.Transactions.Transaction.Current%2A> 的额外工作，因为工作流在各活动之间不会维护线程关联。</span><span class="sxs-lookup"><span data-stu-id="d5f41-107">To get equivalent behavior in workflow, the runtime has to do the extra work of initializing <xref:System.Transactions.Transaction.Current%2A> before executing each activity because a workflow does not maintain thread affinity between activities.</span></span> <span data-ttu-id="d5f41-108">利用此运行时支持，获得的行为是：当在 <xref:System.Activities.WorkflowInvoker> 内使用 <xref:System.Transactions.TransactionScope> 执行工作流时，必须确保所有活动在由 <xref:System.Transactions.TransactionScope> 创建的环境事务上下文下运行。</span><span class="sxs-lookup"><span data-stu-id="d5f41-108">With this runtime support, the resulting behavior is that when executing a workflow with <xref:System.Activities.WorkflowInvoker> inside a <xref:System.Transactions.TransactionScope>, all activities are guaranteed to run under the context of the ambient transaction created by the <xref:System.Transactions.TransactionScope>.</span></span>  
  
 <span data-ttu-id="d5f41-109">对于每个工作流实例，一个工作流只能有一个环境事务；不可使用嵌套事务。</span><span class="sxs-lookup"><span data-stu-id="d5f41-109">A workflow can have only a single ambient transaction for each workflow instance; nested transactions are not available.</span></span> <span data-ttu-id="d5f41-110">即使工作流包含一个 <xref:System.Activities.Statements.TransactionScope> 活动，这也不会创建一个新的内部事务，</span><span class="sxs-lookup"><span data-stu-id="d5f41-110">Even if the workflow contains a <xref:System.Activities.Statements.TransactionScope> activity, this does not create a new inner transaction.</span></span> <span data-ttu-id="d5f41-111">而是重用在工作流外部创建的环境事务。</span><span class="sxs-lookup"><span data-stu-id="d5f41-111">Instead, this reuses the ambient transaction that was created outside the workflow.</span></span>  
  
 <span data-ttu-id="d5f41-112">此示例开始一个新的 <xref:System.Transactions.TransactionScope>，输出事务 ID 并使用 <xref:System.Activities.WorkflowInvoker> 开始一个工作流。</span><span class="sxs-lookup"><span data-stu-id="d5f41-112">The sample begins a new <xref:System.Transactions.TransactionScope>, prints the transaction ID and begins a workflow using <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="d5f41-113">该工作流再次输出事务 ID 以表明这是同一个事务，然后运行一个 <xref:System.Activities.Statements.TransactionScope>，最后完成操作。</span><span class="sxs-lookup"><span data-stu-id="d5f41-113">The workflow prints the transaction ID again, showing that it is the same transaction, then runs a <xref:System.Activities.Statements.TransactionScope>, then completes.</span></span> <span data-ttu-id="d5f41-114">由于 <xref:System.Activities.WorkflowInvoker.Invoke%2A> 上的 <xref:System.Activities.WorkflowInvoker> 调用是同步的，因此，原始线程在工作流完成之前将一直阻塞。</span><span class="sxs-lookup"><span data-stu-id="d5f41-114">The <xref:System.Activities.WorkflowInvoker.Invoke%2A> call on <xref:System.Activities.WorkflowInvoker> is synchronous so the original thread blocks until the workflow completes.</span></span> <span data-ttu-id="d5f41-115">在工作流完成之后，相应的事务也会随之完成并释放资源。</span><span class="sxs-lookup"><span data-stu-id="d5f41-115">Once the workflow is complete, the transaction is completed and resources disposed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d5f41-116">使用此示例</span><span class="sxs-lookup"><span data-stu-id="d5f41-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="d5f41-117">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 ImperativeTransactionSample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d5f41-117">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ImperativeTransactionSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d5f41-118">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="d5f41-118">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d5f41-119">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="d5f41-119">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5f41-120">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="d5f41-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d5f41-121">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="d5f41-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d5f41-122">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="d5f41-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d5f41-123">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="d5f41-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`