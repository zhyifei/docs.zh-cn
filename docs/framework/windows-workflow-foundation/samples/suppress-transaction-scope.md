---
title: "禁止显示事务范围"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fe13a8aae93548eedac2647e2429d66121377aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="suppress-transaction-scope"></a><span data-ttu-id="bde6b-102">禁止显示事务范围</span><span class="sxs-lookup"><span data-stu-id="bde6b-102">Suppress Transaction Scope</span></span>
<span data-ttu-id="bde6b-103">此示例演示如何创作自定义 `SuppressTransactionScope` 活动以禁止环境运行时事务（如果存在的话）。</span><span class="sxs-lookup"><span data-stu-id="bde6b-103">The sample demonstrates how to author a custom `SuppressTransactionScope` activity to suppress the ambient run-time transaction, if present.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bde6b-104">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="bde6b-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bde6b-105">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="bde6b-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bde6b-106">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="bde6b-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bde6b-107">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="bde6b-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="sample-details"></a><span data-ttu-id="bde6b-108">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="bde6b-108">Sample Details</span></span>  
 <span data-ttu-id="bde6b-109">如果在特定方案中不希望出现事务流，则可使用自定义活动防止事务流向其他服务。</span><span class="sxs-lookup"><span data-stu-id="bde6b-109">The custom activity is useful to prevent a transaction from being flowed out to another service if transaction flow is undesirable for the particular scenario.</span></span> <span data-ttu-id="bde6b-110">工作流运行时为禁止 <xref:System.Activities.NativeActivity> 类中的环境事务提供内置支持。不过，要使用这一支持，需要创作此示例中的类似的自定义 <xref:System.Activities.NativeActivity>。</span><span class="sxs-lookup"><span data-stu-id="bde6b-110">The workflow runtime has built-in support for suppressing the ambient transaction in the <xref:System.Activities.NativeActivity> class, but to use this support it is necessary to author a custom <xref:System.Activities.NativeActivity> such as the one in this sample.</span></span>  
  
 <span data-ttu-id="bde6b-111">此方案由三个部分组成。</span><span class="sxs-lookup"><span data-stu-id="bde6b-111">The scenario consists of three parts.</span></span> <span data-ttu-id="bde6b-112">首先，<xref:System.Activities.Statements.TransactionScope> 创建一个成为环境的运行时事务。</span><span class="sxs-lookup"><span data-stu-id="bde6b-112">First, a <xref:System.Activities.Statements.TransactionScope> creates a run-time transaction that becomes ambient.</span></span> <span data-ttu-id="bde6b-113">这可以通过一个输出该事务的本地标识符和分布式标识符的自定义活动来验证。</span><span class="sxs-lookup"><span data-stu-id="bde6b-113">This is verified by a custom activity that prints the local and distributed identifiers of the transaction.</span></span> <span data-ttu-id="bde6b-114">然后，在第二部分开始之前，该事务流到某个远程服务。</span><span class="sxs-lookup"><span data-stu-id="bde6b-114">The transaction is then flowed to a remote service before beginning the second part.</span></span> <span data-ttu-id="bde6b-115">在第二部分中，工作流进入 `SuppressTransactionScope`，并再次重复输出事务标识符并流动事务的过程。</span><span class="sxs-lookup"><span data-stu-id="bde6b-115">During the second part, the workflow enters a `SuppressTransactionScope` and again repeats the process of printing the transaction identifiers and flowing the transaction.</span></span> <span data-ttu-id="bde6b-116">但是，自定义活动不会查找环境事务，并且流动到该服务的消息不会包含该事务。</span><span class="sxs-lookup"><span data-stu-id="bde6b-116">However, the custom activity does not find an ambient transaction and the message flowed to the service does not contain the transaction.</span></span> <span data-ttu-id="bde6b-117">结果，该服务创建一个事务，这意味着，在客户端上输出的分布式 ID 与服务不会匹配。</span><span class="sxs-lookup"><span data-stu-id="bde6b-117">As a result, the service creates a transaction, which means the distributed ID printed on the client and service do not match.</span></span> <span data-ttu-id="bde6b-118">最后一部分发生在 `SuppressTransactionScope` 退出之后，运行时事务再次成为环境，这可以通过发送给该服务的具有与第一条消息的标识符匹配的分布式标识符的另一条消息来验证。</span><span class="sxs-lookup"><span data-stu-id="bde6b-118">The final part occurs after the `SuppressTransactionScope` exits and the run-time transaction again becomes ambient as verified by another message to the service with a distributed identifier that matches the identifier of the first message.</span></span>  
  
 <span data-ttu-id="bde6b-119">该活动本身派生自 <xref:System.Activities.NativeActivity>，因为它必须计划一个子级活动，并添加一个执行属性。</span><span class="sxs-lookup"><span data-stu-id="bde6b-119">The activity itself derives from <xref:System.Activities.NativeActivity> because it must schedule a child activity and add an execution property.</span></span> <span data-ttu-id="bde6b-120">`SuppressTransactionScope` 具有一个 <xref:System.Activities.Variable> 类型的 <xref:System.Activities.RuntimeTransactionHandle>，必须使用它，而不是使用 <xref:System.Activities.RuntimeTransactionHandle> 类型的实例字段，因为必须初始化句柄。</span><span class="sxs-lookup"><span data-stu-id="bde6b-120">The `SuppressTransactionScope` has a <xref:System.Activities.Variable> of type <xref:System.Activities.RuntimeTransactionHandle>, which must be used rather than an instance field of type <xref:System.Activities.RuntimeTransactionHandle> because the handle must be initialized.</span></span> <span data-ttu-id="bde6b-121">将 `Variable<RuntimeTransactionHandle>` 作为一个实现变量添加到活动的元数据，因为它仅在内部使用。</span><span class="sxs-lookup"><span data-stu-id="bde6b-121">The `Variable<RuntimeTransactionHandle>` is added to the activity’s metadata as an implementation variable because it is only used internally.</span></span>  
  
 <span data-ttu-id="bde6b-122">执行活动后，它首先检查是否指定了正文，如果已指定，则设置 `SuppressTransaction` 的 <xref:System.Activities.RuntimeTransactionHandle> 属性。</span><span class="sxs-lookup"><span data-stu-id="bde6b-122">When the activity is executed it first checks to see whether a body was specified and if so, sets the `SuppressTransaction` property on the <xref:System.Activities.RuntimeTransactionHandle>.</span></span> <span data-ttu-id="bde6b-123">设置该属性之后，它即会添加到执行属性中并成为环境。</span><span class="sxs-lookup"><span data-stu-id="bde6b-123">Once the property is set, it is added to the execution properties and becomes ambient.</span></span> <span data-ttu-id="bde6b-124">这意味着，作为 `SuppressTransactionScope` 的子级的任何活动均可以查看该属性，因此将强制禁止运行时事务，并导致嵌套的 <xref:System.Activities.Statements.TransactionScope> 引发异常。</span><span class="sxs-lookup"><span data-stu-id="bde6b-124">This means that any activity that is a child of the `SuppressTransactionScope` is able to see the property and therefore enforces the suppression of the run-time transaction and causes a nested <xref:System.Activities.Statements.TransactionScope> to throw an exception.</span></span> <span data-ttu-id="bde6b-125">在将句柄添加到执行属性之后，即会安排运行正文。</span><span class="sxs-lookup"><span data-stu-id="bde6b-125">Once the handle is added to the execution properties the body is scheduled to run.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bde6b-126">使用此示例</span><span class="sxs-lookup"><span data-stu-id="bde6b-126">To use this sample</span></span>  
  
1.  <span data-ttu-id="bde6b-127">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 SuppressTransactionScope.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="bde6b-127">Open the SuppressTransactionScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="bde6b-128">若要生成解决方案，按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="bde6b-128">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="bde6b-129">成功生成之后，右键单击解决方案并选择**设置启动项目**。</span><span class="sxs-lookup"><span data-stu-id="bde6b-129">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="bde6b-130">在对话框中，选择**多启动项目**并确保这两个项目的操作是**启动**。</span><span class="sxs-lookup"><span data-stu-id="bde6b-130">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="bde6b-131">按 F5，或选择**启动调试**从**调试**菜单。</span><span class="sxs-lookup"><span data-stu-id="bde6b-131">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="bde6b-132">或者，你可以按 CTRL + F5，或选择**启动但不调试**从**调试**菜单运行而不调试。</span><span class="sxs-lookup"><span data-stu-id="bde6b-132">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bde6b-133">在启动客户端之前，服务器必须正在运行。</span><span class="sxs-lookup"><span data-stu-id="bde6b-133">The server must be running prior to starting the client.</span></span> <span data-ttu-id="bde6b-134">承载该服务的控制台窗口的输出将指示它启动的时间。</span><span class="sxs-lookup"><span data-stu-id="bde6b-134">The output from the console window that hosts the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bde6b-135">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="bde6b-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bde6b-136">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="bde6b-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bde6b-137">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="bde6b-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bde6b-138">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="bde6b-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`