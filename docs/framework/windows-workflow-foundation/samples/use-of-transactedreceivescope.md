---
title: 使用 TransactedReceiveScope
ms.date: 03/30/2017
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
ms.openlocfilehash: bc1c418f3fa116f5e1c1647af3543a38122842f5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501637"
---
# <a name="use-of-transactedreceivescope"></a><span data-ttu-id="48789-102">使用 TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="48789-102">Use of TransactedReceiveScope</span></span>
<span data-ttu-id="48789-103">此示例演示如何使用 <xref:System.Activities.Statements.TransactionScope> 将事务从客户端流动到服务器，以在客户端上创建一个新的事务和一个 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，从而接收具有流动的事务的消息，并确定事务在服务器上的生存期范围。</span><span class="sxs-lookup"><span data-stu-id="48789-103">This sample shows how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span> <span data-ttu-id="48789-104">此示例由充当客户端和服务器角色的两个项目组成。</span><span class="sxs-lookup"><span data-stu-id="48789-104">The sample consists of two projects that fill the roles of client and server.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="48789-105">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="48789-105">Client Application</span></span>  
 <span data-ttu-id="48789-106">客户端应用程序运行一个工作流，该工作流输出分布式事务 ID，向服务器发送消息，流动事务，接收回复，再次输出分布式事务 ID 并完成操作。</span><span class="sxs-lookup"><span data-stu-id="48789-106">The client application runs a workflow that prints the distributed transaction ID, sends a message to the server, flows the transaction, receives the reply, prints the distributed transaction ID again and completes.</span></span> <span data-ttu-id="48789-107">最初输出分布式事务 ID 时，它是一个空 GUID，因为事务仍然仅为本地事务。</span><span class="sxs-lookup"><span data-stu-id="48789-107">When the distributed transaction ID is initially prints, it is an empty GUID as the transaction is still only local.</span></span>  
  
## <a name="server-application"></a><span data-ttu-id="48789-108">服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="48789-108">Server Application</span></span>  
 <span data-ttu-id="48789-109">服务器项目与客户端项目相似，不过，工作流承载于 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 中，因为它必须在一个终结点上侦听来自客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="48789-109">The server project is similar, however, the workflow is hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> because it must listen on an endpoint for the message from the client.</span></span> <span data-ttu-id="48789-110">工作流位于 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 的中心，后者从客户端接收流动的事务，输出已发送的消息，输出分布式事务 ID 并向客户端发送回复。</span><span class="sxs-lookup"><span data-stu-id="48789-110">The workflow is centered on the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, which receives the flowed transaction from the client, prints the message that was sent, prints the distributed transaction ID and sends the reply to the client.</span></span> <span data-ttu-id="48789-111">分布式事务 ID 现在为非空 GUID，如果已在 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 的主体中添加了一个识别事务的活动，则它将在流动的事务下执行。</span><span class="sxs-lookup"><span data-stu-id="48789-111">The distributed transaction ID is now a non-empty GUID and if a transaction-aware activity was added to the body of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, it would execute under the flowed transaction.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="48789-112">运行示例</span><span class="sxs-lookup"><span data-stu-id="48789-112">To run the sample</span></span>  
  
1.  <span data-ttu-id="48789-113">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 TransactedReceiveScope.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="48789-113">Open the TransactedReceiveScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="48789-114">若要生成解决方案，请按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="48789-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="48789-115">成功生成之后，右键单击解决方案并选择**设置启动项目**。</span><span class="sxs-lookup"><span data-stu-id="48789-115">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="48789-116">从对话框中，选择**多个启动项目**，并确保这两个项目的操作是**启动**。</span><span class="sxs-lookup"><span data-stu-id="48789-116">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="48789-117">按 F5 或选择**开始调试**从**调试**菜单。</span><span class="sxs-lookup"><span data-stu-id="48789-117">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="48789-118">或者，可以按 CTRL + F5 或选择**启动但不调试**从**调试**菜单运行而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="48789-118">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48789-119">在启动客户端之前，服务器必须正在运行。</span><span class="sxs-lookup"><span data-stu-id="48789-119">The server must be running prior to starting the client.</span></span> <span data-ttu-id="48789-120">承载服务的控制台窗口的输出将指示它启动的时间。</span><span class="sxs-lookup"><span data-stu-id="48789-120">The output from the console window hosting the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="48789-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="48789-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="48789-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="48789-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="48789-123">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="48789-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="48789-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="48789-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`