---
title: "桥接和错误处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eec60855dc8ce3c611fa0fe3c8668973b43099b4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="bridging-and-error-handling"></a><span data-ttu-id="585f9-102">桥接和错误处理</span><span class="sxs-lookup"><span data-stu-id="585f9-102">Bridging and Error Handling</span></span>
<span data-ttu-id="585f9-103">此示例演示 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 路由服务如何用于在使用不同绑定的客户端和服务之间桥接通信。</span><span class="sxs-lookup"><span data-stu-id="585f9-103">This sample demonstrates how the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service is used for bridging communication between a client and a service that use different bindings.</span></span> <span data-ttu-id="585f9-104">此示例还演示如何将备份服务用于故障转移方案。</span><span class="sxs-lookup"><span data-stu-id="585f9-104">This sample also shows how to use a back-up service for failover scenarios.</span></span> <span data-ttu-id="585f9-105">路由服务是一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 组件，使用该组件可方便地在应用程序中包含基于内容的路由器。</span><span class="sxs-lookup"><span data-stu-id="585f9-105">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="585f9-106">此示例采用标准的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 计算器示例，用于使用路由服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="585f9-106">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator Sample to communicate using the routing service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="585f9-107">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="585f9-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="585f9-108">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="585f9-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="585f9-109">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="585f9-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="585f9-110">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="585f9-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a><span data-ttu-id="585f9-111">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="585f9-111">Sample Details</span></span>  
 <span data-ttu-id="585f9-112">在此示例中，计算器客户端配置为将消息发送到由路由器公开的一个终结点。</span><span class="sxs-lookup"><span data-stu-id="585f9-112">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="585f9-113">路由服务配置为接受发送给它的所有消息，然后将这些消息转发至与计算器服务对应的终结点。</span><span class="sxs-lookup"><span data-stu-id="585f9-113">The routing service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="585f9-114">下面几点介绍了主要计算器服务、备份计算器服务和计算器客户端的配置，以及客户端和服务之间如何使用路由服务进行通信：</span><span class="sxs-lookup"><span data-stu-id="585f9-114">The following points describe the configuration of the primary Calculator service, the back-up Calculator service, and the Calculator client and how the communication between the client and the service happens using the routing service:</span></span>  
  
-   <span data-ttu-id="585f9-115">计算器客户端配置为使用 BasicHttpBinding，而计算器服务配置为使用 NetTcpBinding。</span><span class="sxs-lookup"><span data-stu-id="585f9-115">The Calculator client is configured to use BasicHttpBinding while the Calculator service is configured to use NetTcpBinding.</span></span> <span data-ttu-id="585f9-116">将消息发送到计算器服务之前，路由服务将根据需要自动转换这些消息，同时还会转换响应，以便计算器客户端可对它们进行访问。</span><span class="sxs-lookup"><span data-stu-id="585f9-116">The routing service automatically converts the messages as necessary before sending them to the Calculator service and it also converts the responses so that the Calculator client can access them.</span></span>  
  
-   <span data-ttu-id="585f9-117">路由服务知道两种计算器服务：主要计算器服务和备份计算器服务。</span><span class="sxs-lookup"><span data-stu-id="585f9-117">The routing service knows about two Calculator services: the primary Calculator service and the back-up Calculator service.</span></span> <span data-ttu-id="585f9-118">路由服务首先尝试与主要计算器服务终结点通信。</span><span class="sxs-lookup"><span data-stu-id="585f9-118">The routing service first attempts to communicate with the primary Calculator service endpoint.</span></span> <span data-ttu-id="585f9-119">如果此尝试因该终结点关闭而失败，则路由服务尝试与备份计算器服务终结点通信。</span><span class="sxs-lookup"><span data-stu-id="585f9-119">If this attempt fails due to the endpoint being down, the routing service then tries to communicate with the back-up Calculator service endpoint.</span></span>  
  
 <span data-ttu-id="585f9-120">因此，从客户端发送的消息将由路由器接收，并重新路由到实际的计算器服务。</span><span class="sxs-lookup"><span data-stu-id="585f9-120">Thus messages sent from the client are received by the router and are rerouted to the actual Calculator service.</span></span> <span data-ttu-id="585f9-121">如果计算器服务终结点关闭，则路由服务将消息路由到备份计算器服务终结点。</span><span class="sxs-lookup"><span data-stu-id="585f9-121">If the Calculator service endpoint is down, the routing service routes the message to the back-up Calculator service endpoint.</span></span> <span data-ttu-id="585f9-122">来自备份计算器服务的消息将发送回服务路由器，后者将这些消息传递回计算器客户端。</span><span class="sxs-lookup"><span data-stu-id="585f9-122">Messages from the back-up Calculator service are sent back to the service router, which in turn passes them back to the Calculator client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="585f9-123">一个备份列表中可具有多个定义的终结点。</span><span class="sxs-lookup"><span data-stu-id="585f9-123">A back-up list can have more than one endpoint defined.</span></span> <span data-ttu-id="585f9-124">在此情况下，如果备份服务终结点关闭，则路由服务尝试连接到列表中的下一个备份终结点，直到成功进行连接。</span><span class="sxs-lookup"><span data-stu-id="585f9-124">In this case if the back-up service endpoint is down, the routing service attempts to connect to the next back-up endpoint in the list until a successful connection occurs.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="585f9-125">使用此示例</span><span class="sxs-lookup"><span data-stu-id="585f9-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="585f9-126">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 RouterBridgingAndErrorHandling.sln。</span><span class="sxs-lookup"><span data-stu-id="585f9-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open RouterBridgingAndErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="585f9-127">在 Visual Studio 中按 F5 或 Ctrl+Shift+B</span><span class="sxs-lookup"><span data-stu-id="585f9-127">Press F5 or CTRL+SHIFT+B in Visual Studio</span></span>  
  
    1.  <span data-ttu-id="585f9-128">如果你想要自动启动所需的项目，按 F5 时，右键单击该解决方案，请选择**属性**，然后在**启动项目**节点下的**通用属性**，选择**多启动项目**，并将所有项目都设置为**启动**。</span><span class="sxs-lookup"><span data-stu-id="585f9-128">If you would like to auto-launch the necessary projects when you press F5, right-click the solution, select **Properties**, and in the **Startup Project** node under **Common Properties**, select **Multiple Startup Projects**, and set all projects to **Start**.</span></span>  
  
    2.  <span data-ttu-id="585f9-129">如果使用 Ctrl+Shift+B 生成项目，则必须启动以下应用程序：</span><span class="sxs-lookup"><span data-stu-id="585f9-129">If you build the project with CTRL+SHIFT+B, start the following applications:</span></span>  
  
        1.  <span data-ttu-id="585f9-130">计算器客户端 (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="585f9-130">Calculator client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="585f9-131">计算器服务 (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="585f9-131">Calculator service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="585f9-132">路由服务 (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="585f9-132">Routing Service (./RoutingService/bin/RoutingService.exe)</span></span>  
  
3.  <span data-ttu-id="585f9-133">在计算器客户端中，按 Enter 启动客户端。</span><span class="sxs-lookup"><span data-stu-id="585f9-133">In the Calculator Client, press ENTER to start the client.</span></span>  
  
     <span data-ttu-id="585f9-134">您应看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="585f9-134">You should see the following output:</span></span>  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="585f9-135">可通过代码或 App.config 配置</span><span class="sxs-lookup"><span data-stu-id="585f9-135">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="585f9-136">所提供的示例配置为使用 App.config 文件来定义路由器行为。</span><span class="sxs-lookup"><span data-stu-id="585f9-136">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="585f9-137">也可将 App.config 文件的名称更改为无法识别的其他名称，并将对 `ConfigureRouterViaCode()` 的方法调用取消注释。</span><span class="sxs-lookup"><span data-stu-id="585f9-137">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()`.</span></span> <span data-ttu-id="585f9-138">以上任一方法都可产生相同的路由器行为。</span><span class="sxs-lookup"><span data-stu-id="585f9-138">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="585f9-139">方案</span><span class="sxs-lookup"><span data-stu-id="585f9-139">Scenario</span></span>  
 <span data-ttu-id="585f9-140">此示例演示作为协议桥和错误处理程序的服务路由器。</span><span class="sxs-lookup"><span data-stu-id="585f9-140">This sample demonstrates the service router acting as a protocol bridge and error handler.</span></span> <span data-ttu-id="585f9-141">在此方案中，没有发生基于内容的路由；路由服务充当一个透明的代理节点，该节点配置为将消息直接传递到目标终结点的预配置集。</span><span class="sxs-lookup"><span data-stu-id="585f9-141">In this scenario, no content-based routing occurs; the routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span> <span data-ttu-id="585f9-142">该路由服务还执行一些附加步骤，以透明方式处理在其尝试发送到已配置为与之通信的终结点时发生的错误。</span><span class="sxs-lookup"><span data-stu-id="585f9-142">The routing service also performs the additional steps of transparently handling errors that occur when it tries to send to the endpoints that it is configured to communicate with.</span></span> <span data-ttu-id="585f9-143">通过充当协议桥，路由服务使用户能够为外部通信定义一个协议，并为内部通信定义另一个协议。</span><span class="sxs-lookup"><span data-stu-id="585f9-143">By acting as a protocol bridge, the routing service enables the user to define one protocol for external communication and another for internal communication.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="585f9-144">实际方案</span><span class="sxs-lookup"><span data-stu-id="585f9-144">Real World Scenario</span></span>  
 <span data-ttu-id="585f9-145">Contoso 希望在内部优化性能的同时，向外界提供一个可互操作的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="585f9-145">Contoso wants to provide an interoperable service endpoint to the world, while optimizing performance internally.</span></span> <span data-ttu-id="585f9-146">因此，它通过一个使用 BasicHttpBinding 的终结点向外界公开其服务，而在内部使用路由服务将该连接桥接到使用 NetTcpBinding（由其服务使用）的终结点。</span><span class="sxs-lookup"><span data-stu-id="585f9-146">Thus it exposes its services to the world through an endpoint using the BasicHttpBinding, while internally using the routing service to bridge that connection to the endpoint using NetTcpBinding, which its services use.</span></span> <span data-ttu-id="585f9-147">而且，Contoso 还希望其提供的服务能够容许他们的任何一个生产服务发生暂时中断，从而通过使用错误处理功能来虚拟化路由器服务后面的多个终结点，以便在必要时自动故障转移到备份终结点。</span><span class="sxs-lookup"><span data-stu-id="585f9-147">Furthermore, Contoso wants its service offering to be tolerant of temporary outages in any one of their production services and thus virtualizes multiple endpoints behind the router service using the ’s error handling capabilities to automatically failover to back-up endpoints when necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585f9-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="585f9-148">See Also</span></span>  
 [<span data-ttu-id="585f9-149">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="585f9-149">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
