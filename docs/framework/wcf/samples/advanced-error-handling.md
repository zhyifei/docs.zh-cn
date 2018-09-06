---
title: 高级错误处理
ms.date: 03/30/2017
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
ms.openlocfilehash: 72fb9885408759f5781501b548f81625d258d13c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745246"
---
# <a name="advanced-error-handling"></a><span data-ttu-id="9983f-102">高级错误处理</span><span class="sxs-lookup"><span data-stu-id="9983f-102">Advanced Error Handling</span></span>
<span data-ttu-id="9983f-103">此示例演示 Windows Communication Foundation (WCF) 路由服务。</span><span class="sxs-lookup"><span data-stu-id="9983f-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="9983f-104">路由服务是一个 WCF 组件，它可以轻松地在应用程序中包含基于内容的路由器。</span><span class="sxs-lookup"><span data-stu-id="9983f-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="9983f-105">此示例使用事务和其他更加复杂的消息传递概念（如多播）演示如何智能地将路由服务从错误中恢复过来。</span><span class="sxs-lookup"><span data-stu-id="9983f-105">This sample shows how the routing service intelligently recovers from errors, using transactions and other more complex messaging concepts such as multicasting.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9983f-106">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9983f-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9983f-107">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9983f-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9983f-108">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="9983f-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9983f-109">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9983f-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a><span data-ttu-id="9983f-110">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="9983f-110">Sample Details</span></span>  
 <span data-ttu-id="9983f-111">在此示例中，路由服务配置为从 MSMQ 队列读取一个消息并将此消息多播到两个队列列表。</span><span class="sxs-lookup"><span data-stu-id="9983f-111">In this sample, the routing service is configured to read a message from an MSMQ queue and multicast this message to two lists of queues.</span></span> <span data-ttu-id="9983f-112">一个列表用于服务队列，另一个用于日志记录队列。</span><span class="sxs-lookup"><span data-stu-id="9983f-112">One list is used for service queues and another is used for logging queues.</span></span>  
  
 <span data-ttu-id="9983f-113">因为在默认情况下，为路由服务配置的 MSMQ 绑定支持使用事务，所以路由服务可确保在向入站队列 (`InQ`) 报告消息已成功路由之前，消息是事务性的且由每个列表中的至少一个队列接收。</span><span class="sxs-lookup"><span data-stu-id="9983f-113">Because, by default, the MSMQ binding that the routing service is configured to use supports the use of transactions, the routing service makes sure that the message is transactional and received by at least one queue in each list before reporting to the Inbound Queue (`InQ`) that the message was successfully routed.</span></span> <span data-ttu-id="9983f-114">因此，在两个服务队列或两个日志记录队列都不可用时，路由服务报告消息无法路由，入站队列应采取某种操作。</span><span class="sxs-lookup"><span data-stu-id="9983f-114">Thus, in the case where both of the service queues or both of the logging queues are unavailable, the routing service reports that the message could not be routed and the inbound queue should take some action.</span></span> <span data-ttu-id="9983f-115">此操作包含将消息移动至系统死信队列。</span><span class="sxs-lookup"><span data-stu-id="9983f-115">This action consists of moving the message to the system dead letter queue.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9983f-116">使用此示例</span><span class="sxs-lookup"><span data-stu-id="9983f-116">To use this sample</span></span>  
  
1.  > [!IMPORTANT]
    >  <span data-ttu-id="9983f-117">在运行此示例之前安装 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="9983f-117">Install MSMQ before running this sample.</span></span> <span data-ttu-id="9983f-118">如果未安装 MSMQ，会在运行该示例时返回异常消息。</span><span class="sxs-lookup"><span data-stu-id="9983f-118">If MSMQ is not installed, an exception message is returned when running the sample.</span></span> <span data-ttu-id="9983f-119">有关安装 MSMQ 的说明可从[安装消息队列 (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437)。</span><span class="sxs-lookup"><span data-stu-id="9983f-119">Instructions for installing MSMQ can be found at [Installing Message Queuing (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).</span></span>  
  
     <span data-ttu-id="9983f-120">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 AdvancedErrorHandling.sln。</span><span class="sxs-lookup"><span data-stu-id="9983f-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="9983f-121">按**F5**或**CTRL + SHIFT + B** Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="9983f-121">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="9983f-122">如果使用 Ctrl+Shift+B 生成应用程序，则必须用 ./RoutingService/bin/debug/RoutingService.exe 启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="9983f-122">If you build the application with CTRL+SHIFT+B, you must start the application at ./RoutingService/bin/debug/RoutingService.exe.</span></span>  
  
3.  <span data-ttu-id="9983f-123">在控制台窗口中，按 Enter 启动客户端。</span><span class="sxs-lookup"><span data-stu-id="9983f-123">In the console window, press ENTER to start the client.</span></span>  
  
4.  <span data-ttu-id="9983f-124">客户端针对每种情况返回不同的有关队列的统计信息。</span><span class="sxs-lookup"><span data-stu-id="9983f-124">The client returns different statistics about the queues for each case.</span></span>  
  
    1.  <span data-ttu-id="9983f-125">下面是针对情况 1（无故障）返回的输出。</span><span class="sxs-lookup"><span data-stu-id="9983f-125">The following is the output returned for case 1 (no failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  <span data-ttu-id="9983f-126">下面是针对情况 3（主服务和日志记录队列故障）返回的输出。</span><span class="sxs-lookup"><span data-stu-id="9983f-126">The following is the output returned for case 3 (primary service and logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  <span data-ttu-id="9983f-127">下面是针对情况 4（主服务队列以及主和备份日志记录队列故障）返回的输出。</span><span class="sxs-lookup"><span data-stu-id="9983f-127">The following is the output returned for case 4 (primary service queue and primary and backup logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  <span data-ttu-id="9983f-128">下面是针对情况 2（主服务队列故障）返回的输出。</span><span class="sxs-lookup"><span data-stu-id="9983f-128">The following is the output returned for case 2 (primary service queue failure).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="9983f-129">可通过代码或 App.config 配置</span><span class="sxs-lookup"><span data-stu-id="9983f-129">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="9983f-130">所提供的示例配置为使用 App.config 文件来定义路由器行为。</span><span class="sxs-lookup"><span data-stu-id="9983f-130">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="9983f-131">还可以将 RoutingService\App.config 文件的名称更改为其他名称，使之无法识别，并在 RoutingService\Program.cs 中将 `configDriven` 字段的值更改为 `false`，以便使用代码中定义的配置。</span><span class="sxs-lookup"><span data-stu-id="9983f-131">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and change the value of the `configDriven` field in RoutingService\Program.cs to `false` to use the configuration defined in the code.</span></span> <span data-ttu-id="9983f-132">以上任一方法都可产生相同的路由器行为。</span><span class="sxs-lookup"><span data-stu-id="9983f-132">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="9983f-133">方案</span><span class="sxs-lookup"><span data-stu-id="9983f-133">Scenario</span></span>  
 <span data-ttu-id="9983f-134">此示例演示路由服务可以处理高级消息传递功能（如事务和接收上下文），并且可以将这些功能用作正确处理错误方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="9983f-134">This sample demonstrates that the routing service can handle advanced messaging capabilities, such as transactions and receive context, and that it can utilize these capabilities as a part of correctly handling error scenarios.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="9983f-135">实际方案</span><span class="sxs-lookup"><span data-stu-id="9983f-135">Real World Scenario</span></span>  
 <span data-ttu-id="9983f-136">Contoso 希望通过路由服务利用事务性接收，以确保即使在出现错误的情况下，所有必要服务也可接收信息。</span><span class="sxs-lookup"><span data-stu-id="9983f-136">Contoso wants to utilize transactional receives through the routing service to ensure that all necessary services receive information even during error conditions.</span></span> <span data-ttu-id="9983f-137">此外，还希望在无法传递消息时，即使利用错误处理逻辑，也可自动地正确处理错误并报告失败。</span><span class="sxs-lookup"><span data-stu-id="9983f-137">Furthermore, they would like errors to be handled correctly and automatically and failures to be reported in the case that a message is undeliverable even when error handling logic is utilized.</span></span> <span data-ttu-id="9983f-138">为此，将路由服务配置为按预期方式故障转移到特定终结点，并且路由服务处理错误情况，具体包括根据需要创建、完成和回滚/中止事务/接收上下文。</span><span class="sxs-lookup"><span data-stu-id="9983f-138">For this purpose, they configure the routing service to fail over to specific endpoints as expected and the routing service handles the error situations, which includes the creation, completion, and rollback/aborting of transactions/receive contexts as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9983f-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="9983f-139">See Also</span></span>  
 [<span data-ttu-id="9983f-140">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="9983f-140">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
