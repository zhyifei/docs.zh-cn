---
title: 事务队列范围
ms.date: 03/30/2017
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
ms.openlocfilehash: fa1da6df5ad5256665610c9b3c2df7d706cef63c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000422"
---
# <a name="transaction-convoy-scope"></a><span data-ttu-id="f2c8e-102">事务队列范围</span><span class="sxs-lookup"><span data-stu-id="f2c8e-102">Transaction Convoy Scope</span></span>
<span data-ttu-id="f2c8e-103">此示例演示如何创建“并行保护”消息传递活动模式与 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，以便构建一个协议，允许很多操作在同一事务下按任意顺序执行。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-103">This sample demonstrates how to create a Parallel Convoy messaging activity pattern in conjunction with a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to model a protocol where a number of operations can happen in any order all under the same transaction.</span></span> <span data-ttu-id="f2c8e-104">此示例还演示 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 如何在某个事务无法流向服务器时自动创建新的事务，以便客户端不使用任何事务。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-104">This sample also demonstrates how a <xref:System.ServiceModel.Activities.TransactedReceiveScope> automatically creates a new transaction when one is not flowed to the server, so the client does not make use of any transactions.</span></span>  
  
 <span data-ttu-id="f2c8e-105">该示例由两个表示客户端和服务器的工作流项目组成。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-105">The sample consists of two workflow projects that represent the client and server.</span></span> <span data-ttu-id="f2c8e-106">客户端项目运行一个工作流，此工作流在开始时会发送一条消息来启动服务器工作流，服务器工作流将初始化一个关联并为其余的消息传递活动启动一个事务范围。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-106">The client project runs a workflow that begins by sending a message to bootstrap the server workflow, which initializes a correlation and starts a transactional scope for the remainder of the messaging activities.</span></span> <span data-ttu-id="f2c8e-107">客户端 <xref:System.Activities.Statements.Sequence> 活动包含一个初始 <xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.ReceiveReply> 对，之后是一个带三个分支的 <xref:System.Activities.Statements.Parallel> 活动。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-107">The client <xref:System.Activities.Statements.Sequence> activity contains an initial <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> pair and then a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="f2c8e-108">每个分支都向服务器发送单向消息。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-108">Each branch sends a one-way message to the server.</span></span> <span data-ttu-id="f2c8e-109"><xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 活动的 <xref:System.Activities.Statements.Parallel> 属性设置为 `false`，以便完成所有三个分支。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-109">The <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> property of the <xref:System.Activities.Statements.Parallel> activity is set to `false` so that all three branches complete.</span></span>  
  
 <span data-ttu-id="f2c8e-110">服务器工作流与客户端工作流类似，只不过消息传递活动面向的是通信的服务器端且包含在 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 活动中，以便在同一个事务下执行所有工作。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-110">The server workflow is similar to the client workflow except the messaging activities are oriented towards the server side of the communication and they are contained within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity so that all work done executes under the same transaction.</span></span> <span data-ttu-id="f2c8e-111">当服务器上收到第一条消息时，将创建一个事务，然后使该事务成为 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 正文范围的环境事务，以便此范围中的任何活动都可以访问该事务。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-111">When the first message is received on the server, a transaction is created and is made ambient for the scope of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body so that any activity within this scope can access the transaction.</span></span> <span data-ttu-id="f2c8e-112">之后，将并行执行所有接收。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-112">After this, all receives execute in parallel.</span></span> <span data-ttu-id="f2c8e-113">所有接收必须刚好执行一次，如并行活动的完成条件所述。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-113">All receives must execute exactly once as described by the completion condition on the parallel activity.</span></span> <span data-ttu-id="f2c8e-114"><xref:System.ServiceModel.Activities.TransactedReceiveScope> 正文的末尾有一个隐式持久性点，并且还将在同一事务下执行持久性操作。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-114">An implicit persistence point exists at the end of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body and the persistence operation is also executed under the same transaction.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f2c8e-115">使用此示例</span><span class="sxs-lookup"><span data-stu-id="f2c8e-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="f2c8e-116">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 ParallelConvoySample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-116">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ParallelConvoySample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f2c8e-117">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-117">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f2c8e-118">确保两个项目都设置为启动。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-118">Ensure both projects are set to start.</span></span>  
  
    1.  <span data-ttu-id="f2c8e-119">在中**解决方案资源管理器**，右键单击解决方案并选择**设置启动项目**。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-119">In **Solution Explorer**, right-click the solution and select **Set Startup Projects**.</span></span>  
  
    2.  <span data-ttu-id="f2c8e-120">选择**多个启动项目**并确保这两个项目的操作设置为**启动**。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-120">Select **Multiple Startup Projects** and ensure the action for both projects is set to **Start**.</span></span>  
  
4.  <span data-ttu-id="f2c8e-121">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-121">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="f2c8e-122">服务器将输出 `Server is running`，它指示服务器已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-122">The server prints `Server is running`, which indicates the server is ready.</span></span>  
  
     <span data-ttu-id="f2c8e-123">在客户端控制台窗口中按任意键以启动示例。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-123">Press any key in the client console window to start the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f2c8e-124">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f2c8e-125">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f2c8e-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f2c8e-126">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="f2c8e-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f2c8e-127">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f2c8e-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`