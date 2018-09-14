---
title: 动态重新配置
ms.date: 03/30/2017
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
ms.openlocfilehash: a147a1d6cf61001832661376363ecc850ecad309
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45508189"
---
# <a name="dynamic-reconfiguration"></a><span data-ttu-id="bc383-102">动态重新配置</span><span class="sxs-lookup"><span data-stu-id="bc383-102">Dynamic Reconfiguration</span></span>
<span data-ttu-id="bc383-103">此示例演示 Windows Communication Foundation (WCF) 路由服务。</span><span class="sxs-lookup"><span data-stu-id="bc383-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="bc383-104">路由服务是一个 WCF 组件，它可以轻松地在应用程序中包含基于内容的路由器。</span><span class="sxs-lookup"><span data-stu-id="bc383-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="bc383-105">此示例采用标准的 WCF 计算器示例，用于使用路由服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="bc383-105">This sample adapts the standard WCF Calculator Sample to communicate using the routing service.</span></span> <span data-ttu-id="bc383-106">此示例演示如何在运行时动态重新配置路由服务。</span><span class="sxs-lookup"><span data-stu-id="bc383-106">This sample shows how the routing service can be dynamically reconfigured during runtime.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bc383-107">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="bc383-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bc383-108">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="bc383-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bc383-109">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="bc383-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bc383-110">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="bc383-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="bc383-111">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="bc383-111">Sample Details</span></span>  
 <span data-ttu-id="bc383-112">为在运行时动态重新配置路由服务，此示例每五秒触发一次计时器以创建新的 <xref:System.ServiceModel.Routing.RoutingConfiguration> 对象并应用该对象。</span><span class="sxs-lookup"><span data-stu-id="bc383-112">To dynamically reconfigure the routing service during runtime, this sample fires a timer every five seconds that creates a new <xref:System.ServiceModel.Routing.RoutingConfiguration> object and applies it.</span></span> <span data-ttu-id="bc383-113">此配置引用常规计算器终结点或舍入计算器终结点。</span><span class="sxs-lookup"><span data-stu-id="bc383-113">This configuration references either the regular Calculator endpoint or the Rounding Calculator endpoint.</span></span> <span data-ttu-id="bc383-114">计算器客户端应用程序的消息从其中一个服务返回，具体取决于路由服务当时配置为路由到哪个服务。</span><span class="sxs-lookup"><span data-stu-id="bc383-114">The Calculator Client application has its messages returned from one service or the other, depending on which one the routing service is configured to route to at that time.</span></span>  
  
 <span data-ttu-id="bc383-115">会使用路由服务通过自定义行为动态重新配置的功能。</span><span class="sxs-lookup"><span data-stu-id="bc383-115">The routing service’s capabilitiy for dynamic reconfiguration through a custom behavior is used.</span></span> <span data-ttu-id="bc383-116">此自定义行为附加一个服务扩展，该扩展包含的简单线程计时器每五秒触发一次，从而形成对 `UpdateRules` 方法的一次回调。</span><span class="sxs-lookup"><span data-stu-id="bc383-116">This custom behavior attaches a service extension, which contains a simple thread timer that fires every five seconds, which results in a callback to the `UpdateRules` method.</span></span> <span data-ttu-id="bc383-117">此回调创建并应用新的路由配置。</span><span class="sxs-lookup"><span data-stu-id="bc383-117">This callback creates and applies the new routing configuration.</span></span> <span data-ttu-id="bc383-118">在实际部署中，此回调可能会作为某些其他类型事件（如 SQL-Event 通知或 WS-Discovery 公告）的结果实现。</span><span class="sxs-lookup"><span data-stu-id="bc383-118">In an actual deployment, this callback would likely be accomplished as a result of some other type of event, such as a SQL-Event notification, or a WS-Discovery announcement.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bc383-119">使用此示例</span><span class="sxs-lookup"><span data-stu-id="bc383-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="bc383-120">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 DynamicReconfiguration.sln。</span><span class="sxs-lookup"><span data-stu-id="bc383-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open DynamicReconfiguration.sln.</span></span>  
  
2.  <span data-ttu-id="bc383-121">若要打开**解决方案资源管理器**，选择**解决方案资源管理器**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="bc383-121">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="bc383-122">按**F5**或**CTRL + SHIFT + B** Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="bc383-122">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="bc383-123">如果你想要自动启动所需的项目时，按**F5**，右键单击解决方案并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="bc383-123">If you would like to auto-launch the necessary projects when you press **F5**, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="bc383-124">选择**启动项目**节点下的**通用属性**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="bc383-124">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="bc383-125">选择**多个启动项目**单选按钮并设置的所有项目具有**启动**操作。</span><span class="sxs-lookup"><span data-stu-id="bc383-125">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="bc383-126">如果生成该项目**CTRL + SHIFT + B**，则必须启动以下应用程序：</span><span class="sxs-lookup"><span data-stu-id="bc383-126">If you build the project with **CTRL+SHIFT+B**, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="bc383-127">计算器客户端 (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="bc383-127">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="bc383-128">计算器服务 (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="bc383-128">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="bc383-129">路由计算器服务 (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="bc383-129">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="bc383-130">路由服务 (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="bc383-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="bc383-131">在计算器客户端的控制台窗口中，按 Enter 启动客户端并调用计算器服务操作。</span><span class="sxs-lookup"><span data-stu-id="bc383-131">In the console window of the Calculator Client, press ENTER to start the client and to call the Calculator service operations.</span></span>  
  
     <span data-ttu-id="bc383-132">随着路由配置每五秒动态更改一次，路由服务将消息交替路由到舍入计算器和常规计算器。</span><span class="sxs-lookup"><span data-stu-id="bc383-132">The routing service routes messages to the Rounding Calculator and to the regular Calculator alternately as the routing configuration changes dynamically every five seconds.</span></span> <span data-ttu-id="bc383-133">根据路由服务器配置为将消息发送到哪个终结点，客户端控制台窗口中会显示不同的输出。</span><span class="sxs-lookup"><span data-stu-id="bc383-133">Depending on which endpoint the routing service is configured to send messages to there are different outputs in the client console window.</span></span>  
  
5.  <span data-ttu-id="bc383-134">继续反复按 Enter 超过五秒，观察服务结果的更改。</span><span class="sxs-lookup"><span data-stu-id="bc383-134">Continue pressing ENTER repeatedly over more than five seconds and observe the change in the results from the service.</span></span>  
  
    1.  <span data-ttu-id="bc383-135">下面是路由器服务配置为将消息路由到舍入计算器服务时返回的输出。</span><span class="sxs-lookup"><span data-stu-id="bc383-135">The following is the output returned if the Router Service is configured to route messages to the Rounding Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="bc383-136">下面是路由服务配置为将消息路由到常规计算器服务时返回的输出。</span><span class="sxs-lookup"><span data-stu-id="bc383-136">The following is the output returned if the routing service is configured to route messages to the regular Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  <span data-ttu-id="bc383-137">计算器服务和舍入计算器服务也会向其各自的控制台窗口输出调用的操作的日志。</span><span class="sxs-lookup"><span data-stu-id="bc383-137">The Calculator Service and the Rounding Calculator Service also print out a log of the operations invoked to their respective console windows.</span></span>  
  
7.  <span data-ttu-id="bc383-138">在客户端控制台窗口中，键入"quit"并按 ENTER 退出。</span><span class="sxs-lookup"><span data-stu-id="bc383-138">In the client console window, type "quit" and press ENTER to exit.</span></span>  
  
8.  <span data-ttu-id="bc383-139">在服务控制台窗口中按 ENTER 终止服务。</span><span class="sxs-lookup"><span data-stu-id="bc383-139">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="bc383-140">方案</span><span class="sxs-lookup"><span data-stu-id="bc383-140">Scenario</span></span>  
 <span data-ttu-id="bc383-141">此示例演示的路由器充当基于内容的路由器，从而可以通过一个终结点公开多种服务类型或实现。</span><span class="sxs-lookup"><span data-stu-id="bc383-141">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="bc383-142">实际方案</span><span class="sxs-lookup"><span data-stu-id="bc383-142">Real World Scenario</span></span>  
 <span data-ttu-id="bc383-143">Contoso 希望虚拟化其所有服务以仅公开一个终结点，这些服务通过该终结点可提供对多种不同类型的服务的访问。</span><span class="sxs-lookup"><span data-stu-id="bc383-143">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="bc383-144">在这种情况下，这些服务利用路由服务的基于内容的路由功能，以确定应将传入请求发送到哪个位置。</span><span class="sxs-lookup"><span data-stu-id="bc383-144">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc383-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc383-145">See Also</span></span>  
 [<span data-ttu-id="bc383-146">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="bc383-146">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
