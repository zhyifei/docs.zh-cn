---
title: 高级筛选器
ms.date: 03/30/2017
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
ms.openlocfilehash: de8577be2d56ec3c942fd8736e350234daf6a35a
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805611"
---
# <a name="advanced-filters"></a><span data-ttu-id="ce69c-102">高级筛选器</span><span class="sxs-lookup"><span data-stu-id="ce69c-102">Advanced Filters</span></span>
<span data-ttu-id="ce69c-103">此示例演示 Windows Communication Foundation (WCF) 路由服务。</span><span class="sxs-lookup"><span data-stu-id="ce69c-103">This sample demonstrates a Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="ce69c-104">路由服务是可以轻松地在你的应用程序中包含基于内容的路由器的 WCF 组件。</span><span class="sxs-lookup"><span data-stu-id="ce69c-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="ce69c-105">此示例采用标准的 WCF 计算器示例，用于使用路由服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="ce69c-105">This sample adapts the standard WCF Calculator sample to communicate using the routing service.</span></span> <span data-ttu-id="ce69c-106">此示例演示如何使用消息筛选器和消息筛选器表定义基于内容的路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="ce69c-106">This sample shows how to define content-based routing logic through the use of message filters and message filter tables.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce69c-107">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="ce69c-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ce69c-108">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ce69c-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ce69c-109">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="ce69c-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ce69c-110">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ce69c-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## <a name="sample-details"></a><span data-ttu-id="ce69c-111">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="ce69c-111">Sample Details</span></span>  
 <span data-ttu-id="ce69c-112">下表显示添加到路由服务的消息筛选器表的消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce69c-112">The following table shows the message filters that are added to the message filter table of the routing service.</span></span>  
  
|<span data-ttu-id="ce69c-113">筛选器</span><span class="sxs-lookup"><span data-stu-id="ce69c-113">Filter</span></span>|<span data-ttu-id="ce69c-114">规则</span><span class="sxs-lookup"><span data-stu-id="ce69c-114">Rule</span></span>|<span data-ttu-id="ce69c-115">优先级</span><span class="sxs-lookup"><span data-stu-id="ce69c-115">Priority</span></span>|  
|------------|----------|--------------|  
|<span data-ttu-id="ce69c-116">是否（具有标头）</span><span class="sxs-lookup"><span data-stu-id="ce69c-116">If (has header)</span></span>|<span data-ttu-id="ce69c-117">舍入</span><span class="sxs-lookup"><span data-stu-id="ce69c-117">Rounding</span></span>|<span data-ttu-id="ce69c-118">2</span><span class="sxs-lookup"><span data-stu-id="ce69c-118">2</span></span>|  
|<span data-ttu-id="ce69c-119">是否（在 Ep2 上出现）</span><span class="sxs-lookup"><span data-stu-id="ce69c-119">If (showed up on Ep2)</span></span>|<span data-ttu-id="ce69c-120">规则</span><span class="sxs-lookup"><span data-stu-id="ce69c-120">Regular</span></span>|<span data-ttu-id="ce69c-121">1</span><span class="sxs-lookup"><span data-stu-id="ce69c-121">1</span></span>|  
|<span data-ttu-id="ce69c-122">是否（出现时带有 Address2）</span><span class="sxs-lookup"><span data-stu-id="ce69c-122">If (showed up with Address2)</span></span>|<span data-ttu-id="ce69c-123">舍入</span><span class="sxs-lookup"><span data-stu-id="ce69c-123">Rounding</span></span>|<span data-ttu-id="ce69c-124">1</span><span class="sxs-lookup"><span data-stu-id="ce69c-124">1</span></span>|  
|<span data-ttu-id="ce69c-125">是否 (RoundRobin1)</span><span class="sxs-lookup"><span data-stu-id="ce69c-125">If (RoundRobin1)</span></span>|<span data-ttu-id="ce69c-126">规则</span><span class="sxs-lookup"><span data-stu-id="ce69c-126">Regular</span></span>|<span data-ttu-id="ce69c-127">0</span><span class="sxs-lookup"><span data-stu-id="ce69c-127">0</span></span>|  
|<span data-ttu-id="ce69c-128">是否 (RoundRobin2)</span><span class="sxs-lookup"><span data-stu-id="ce69c-128">If (RoundRobin2)</span></span>|<span data-ttu-id="ce69c-129">舍入</span><span class="sxs-lookup"><span data-stu-id="ce69c-129">Rounding</span></span>|<span data-ttu-id="ce69c-130">0</span><span class="sxs-lookup"><span data-stu-id="ce69c-130">0</span></span>|  
  
 <span data-ttu-id="ce69c-131">这些消息筛选器和消息筛选器表可通过代码创建和配置，也可在应用程序配置文件中创建和配置。</span><span class="sxs-lookup"><span data-stu-id="ce69c-131">The message filters and message filter tables can be created and configured either through code or in the application configuration file.</span></span> <span data-ttu-id="ce69c-132">对于此示例，你可找到通过 RoutingService\routing.cs 文件中的代码定义或在 RoutingService\App.config 应用程序配置文件中定义的消息筛选器和消息筛选器表。</span><span class="sxs-lookup"><span data-stu-id="ce69c-132">For this sample, you can find the message filters and message filter tables defined through code in the RoutingService\routing.cs file, or defined in the application configuration file in the RoutingService\App.config file.</span></span> <span data-ttu-id="ce69c-133">以下各段介绍如何通过代码为此示例创建消息筛选器和消息筛选器表。</span><span class="sxs-lookup"><span data-stu-id="ce69c-133">The following paragraphs describe how the message filters and message filter tables are created for this sample through code.</span></span>  
  
 <span data-ttu-id="ce69c-134">首先，<xref:System.ServiceModel.Dispatcher.XPathMessageFilter> 会查找自定义标头。</span><span class="sxs-lookup"><span data-stu-id="ce69c-134">First, an <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> looks for the custom header.</span></span> <span data-ttu-id="ce69c-135">请注意，<xref:System.ServiceModel.WSHttpBinding> 会产生使用 SOAP 1.2 的信封版本，因此会 XPath 语句会定义为使用 SOAP 1.2 命名空间。</span><span class="sxs-lookup"><span data-stu-id="ce69c-135">Note that <xref:System.ServiceModel.WSHttpBinding> results in an envelope version using SOAP 1.2, so the XPath statement is defined to use the SOAP 1.2 namespace.</span></span> <span data-ttu-id="ce69c-136"><xref:System.ServiceModel.Dispatcher.XPathMessageFilter> 的默认命名空间管理器已为 SOAP 1.2 命名空间定义了一个可以使用的前缀 /s12。</span><span class="sxs-lookup"><span data-stu-id="ce69c-136">The default namespace manager for <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>s already defines a prefix for the SOAP 1.2 namespace, /s12, which can be used.</span></span> <span data-ttu-id="ce69c-137">但是，默认命名空间管理器没有客户端用于定义实际标头值的自定义命名空间，因此必须定义前缀。</span><span class="sxs-lookup"><span data-stu-id="ce69c-137">However, the default namespace manager does not have the custom namespace that the client uses to define the actual header value, so that prefix must be defined.</span></span> <span data-ttu-id="ce69c-138">出现时带有此标头的任何消息都与此筛选器匹配。</span><span class="sxs-lookup"><span data-stu-id="ce69c-138">Any message that shows up with this header matches this filter.</span></span>  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
```  
  
 <span data-ttu-id="ce69c-139">第二个筛选器是 <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>，与在 `calculatorEndpoint` 上接收到的任何消息匹配。</span><span class="sxs-lookup"><span data-stu-id="ce69c-139">The second filter is an <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, which matches any message that was received on the `calculatorEndpoint`.</span></span> <span data-ttu-id="ce69c-140">创建服务终结点对象时会定义终结点名称。</span><span class="sxs-lookup"><span data-stu-id="ce69c-140">The endpoint name is defined when a service endpoint object is created.</span></span>  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
```  
  
 <span data-ttu-id="ce69c-141">第三个筛选器是 <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>。</span><span class="sxs-lookup"><span data-stu-id="ce69c-141">The third filter is a <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>.</span></span> <span data-ttu-id="ce69c-142">此筛选器与在地址匹配于所提供地址前缀（或前面部分）的终结点上出现的所有消息都匹配。</span><span class="sxs-lookup"><span data-stu-id="ce69c-142">This matches any message that showed up on an endpoint with an address that matches the address prefix (or the front portion) provided.</span></span> <span data-ttu-id="ce69c-143">在此示例中的地址前缀定义为"http://localhost/routingservice/router/rounding/"。</span><span class="sxs-lookup"><span data-stu-id="ce69c-143">In this example the address prefix is defined as "http://localhost/routingservice/router/rounding/".</span></span> <span data-ttu-id="ce69c-144">这意味着，任何传入的消息发送到"http://localhost/routingservice/router/rounding/\*"匹配此筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce69c-144">This means that any incoming messages that are addressed to "http://localhost/routingservice/router/rounding/\*" are matched by this filter.</span></span> <span data-ttu-id="ce69c-145">在这种情况下，它是在舍入计算器终结点显示的消息具有的地址"http://localhost/routingservice/router/rounding/calculator"。</span><span class="sxs-lookup"><span data-stu-id="ce69c-145">In this case, it is messages that show up on the Rounding Calculator endpoint, which has the address of "http://localhost/routingservice/router/rounding/calculator".</span></span>  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
```  
  
 <span data-ttu-id="ce69c-146">最后两个消息筛选器是自定义 <xref:System.ServiceModel.Dispatcher.MessageFilter>。</span><span class="sxs-lookup"><span data-stu-id="ce69c-146">The last two message filters are custom <xref:System.ServiceModel.Dispatcher.MessageFilter>s.</span></span> <span data-ttu-id="ce69c-147">在此示例中，使用“RoundRobin”消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce69c-147">In this example, a "RoundRobin" message filter is used.</span></span> <span data-ttu-id="ce69c-148">此消息筛选器在提供的 RoutingService\RoundRobinMessageFilter.cs 文件中创建。</span><span class="sxs-lookup"><span data-stu-id="ce69c-148">This message filter is created in the provided RoutingService\RoundRobinMessageFilter.cs file.</span></span> <span data-ttu-id="ce69c-149">这些筛选器设置为同一个组时，会交替报告它们与消息匹配以及不匹配，这样，每次只有其中一个筛选器进行 `true` 响应。</span><span class="sxs-lookup"><span data-stu-id="ce69c-149">These filters, when set to the same group, alternate between reporting that they match the message and that they do not, such that only one of them responds `true` at a time.</span></span>  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
```  
  
 <span data-ttu-id="ce69c-150">接下来，所有这些消息都会添加到 <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>。</span><span class="sxs-lookup"><span data-stu-id="ce69c-150">Next, all of those messages are added to a <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>.</span></span> <span data-ttu-id="ce69c-151">这样做可指定优先级，以影响消息筛选器表执行筛选器的顺序。</span><span class="sxs-lookup"><span data-stu-id="ce69c-151">In doing so, priorities are specified to influence the order in which the message filter table executes the filters.</span></span> <span data-ttu-id="ce69c-152">筛选器的优先级越高，就会越早执行；筛选器优先级越低，就会越晚执行。</span><span class="sxs-lookup"><span data-stu-id="ce69c-152">The higher the priority, the sooner the filter is executed; the lower the priority, the later a filter is executed.</span></span> <span data-ttu-id="ce69c-153">因此优先级为 2 的筛选器会在优先级为 1 的筛选器之前执行。</span><span class="sxs-lookup"><span data-stu-id="ce69c-153">Thus a filter at priority 2 runs before a filter at priority 1.</span></span> <span data-ttu-id="ce69c-154">如果未指定优先级，则默认优先级为 0。</span><span class="sxs-lookup"><span data-stu-id="ce69c-154">The default priority level if none is specified is 0.</span></span> <span data-ttu-id="ce69c-155">消息筛选器表会先执行给定优先级别的所有筛选器，然后再移动到下一个较低优先级别。</span><span class="sxs-lookup"><span data-stu-id="ce69c-155">A message filter table executes all of the filters at a given priority level before moving to the next lowest priority level.</span></span> <span data-ttu-id="ce69c-156">如果在特定优先级发现匹配项，则消息筛选器表不会继续尝试在下一个较低优先级查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="ce69c-156">If a match is found at a particular priority, then the message filter table does not continue trying to find matches at the next lower priority.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce69c-157">虽然此示例演示如何使用消息筛选器优先级，但一般而言，设计和配置筛选器使之不需要设置优先顺序便可正常运行，这样的设计性能更高且效果更好。</span><span class="sxs-lookup"><span data-stu-id="ce69c-157">While this example shows how to use message filter priorities, in general it is more performant and better design to design and configure your filters such that they do not require prioritization to function correctly.</span></span>  
  
 <span data-ttu-id="ce69c-158">要添加的第一个筛选器是 XPath 筛选器，其优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="ce69c-158">The first filter to be added is the XPath filter and its priority is set to 2.</span></span> <span data-ttu-id="ce69c-159">这是执行的第一个消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce69c-159">This is the first message filter that executes.</span></span> <span data-ttu-id="ce69c-160">如果该筛选器发现自定义标头，则无论其他筛选器的筛选结果如何，都会将消息路由到舍入计算器终结点。</span><span class="sxs-lookup"><span data-stu-id="ce69c-160">If it finds the custom header, regardless of what the results of the other filters would be, the message is routed to the Rounding Calculator endpoint.</span></span>  
  
 <span data-ttu-id="ce69c-161">添加两个优先级为 1 的筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce69c-161">At priority 1, two filters are added.</span></span> <span data-ttu-id="ce69c-162">同样，仅当优先级为 2 的 XPath 筛选器与消息不匹配时，才会运行这两个筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce69c-162">Again, these only run if the XPath filter at priority 2 does not match the message.</span></span> <span data-ttu-id="ce69c-163">这两个筛选器演示在消息出现时确定其目标位置的两种不同方法。</span><span class="sxs-lookup"><span data-stu-id="ce69c-163">These two filters show two different ways to determine where the message was addressed when it showed up.</span></span> <span data-ttu-id="ce69c-164">因为这两个筛选器可以有效地检查消息是否到达两个终结点中的一个，所以它们可以按相同优先级别运行，原因是它们不会同时返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="ce69c-164">Because the two filters effectively check to see whether the message arrived at one of the two endpoints, they can be run at the same priority level because they do not both return `true` at the same time.</span></span>  
  
 <span data-ttu-id="ce69c-165">最后，按优先级 0（最低优先级）运行 RoundRobin 消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce69c-165">Finally, at Priority 0 (the lowest priority) run the RoundRobin message filters.</span></span> <span data-ttu-id="ce69c-166">因为这些筛选器配置有相同组名，所以每次只有其中一个筛选器匹配。</span><span class="sxs-lookup"><span data-stu-id="ce69c-166">Because the filters are configured with the same group name, only one of them matches at a time.</span></span> <span data-ttu-id="ce69c-167">因为具有自定义标头的所有消息都已路由并发送到特定的虚拟化终结点，所以 RoundRobin 消息筛选器仅处理发送到没有自定义标头的默认路由器终结点的消息。</span><span class="sxs-lookup"><span data-stu-id="ce69c-167">Because all messages with the custom header have been routed and all those addressed to the specific virtualized endpoints, messages handled by the RoundRobin message filters are only messages that were addressed to the default router endpoint without the custom header.</span></span> <span data-ttu-id="ce69c-168">因为这些消息在每次调用时都会启用一个消息，所以一半操作会转到常规计算器终结点，另一半操作会转到舍入计算器终结点。</span><span class="sxs-lookup"><span data-stu-id="ce69c-168">Because these messages switch on a message for each call, half of the operations go to the Regular Calculator endpoint and the other half go to the Rounding Calculator endpoint.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ce69c-169">使用此示例</span><span class="sxs-lookup"><span data-stu-id="ce69c-169">To use this sample</span></span>  
  
1.  <span data-ttu-id="ce69c-170">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 AdvancedFilters.sln。</span><span class="sxs-lookup"><span data-stu-id="ce69c-170">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedFilters.sln.</span></span>  
  
2.  <span data-ttu-id="ce69c-171">若要打开**解决方案资源管理器**，选择**解决方案资源管理器**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="ce69c-171">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="ce69c-172">在 Visual Studio 中按 F5 或 CTRL + SHIFT + B。</span><span class="sxs-lookup"><span data-stu-id="ce69c-172">Press F5 or CTRL+SHIFT+B in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="ce69c-173">如果你想要自动启动所需的项目，按 F5 时，右键单击该解决方案并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ce69c-173">If you would like to auto-launch the necessary projects when you press F5, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="ce69c-174">选择**启动项目**节点下的**通用属性**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="ce69c-174">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="ce69c-175">选择**多启动项目**单选按钮，设置所有项目具有**启动**操作。</span><span class="sxs-lookup"><span data-stu-id="ce69c-175">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="ce69c-176">如果使用 Ctrl+Shift+B 生成项目，则必须启动以下应用程序：</span><span class="sxs-lookup"><span data-stu-id="ce69c-176">If you build the project with CTRL+SHIFT+B, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="ce69c-177">计算器客户端 (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="ce69c-177">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="ce69c-178">计算器服务 (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="ce69c-178">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="ce69c-179">路由计算器服务 (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="ce69c-179">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="ce69c-180">路由服务 (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="ce69c-180">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="ce69c-181">在计算器客户端的控制台窗口中，按 Enter 启动客户端。</span><span class="sxs-lookup"><span data-stu-id="ce69c-181">In the console window of the Calculator client, press ENTER to start the client.</span></span> <span data-ttu-id="ce69c-182">客户端将返回可供选择的目标终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="ce69c-182">The client returns a list of destination endpoints to choose from.</span></span>  
  
5.  <span data-ttu-id="ce69c-183">键入目标终结点的对应字母并按 ENTER 以选择该终结点。</span><span class="sxs-lookup"><span data-stu-id="ce69c-183">Choose a destination endpoint by typing its corresponding letter and press ENTER.</span></span>  
  
6.  <span data-ttu-id="ce69c-184">接下来，客户端将询问您是否要添加自定义标头。</span><span class="sxs-lookup"><span data-stu-id="ce69c-184">Next, the client asks you if you want to add a custom header.</span></span> <span data-ttu-id="ce69c-185">按 Y 表示“是”，或按 N 表示“否”，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ce69c-185">Press Y for Yes or N for No, then press ENTER.</span></span>  
  
7.  <span data-ttu-id="ce69c-186">根据进行的选择，应看到不同的输出。</span><span class="sxs-lookup"><span data-stu-id="ce69c-186">Depending on the selections you made, you should see different outputs.</span></span>  
  
    1.  <span data-ttu-id="ce69c-187">如果将自定义标头添加到消息中，则会返回以下输出。</span><span class="sxs-lookup"><span data-stu-id="ce69c-187">The following is the output returned if you added a custom header to the messages.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="ce69c-188">如果选择没有自定义标头的舍入计算器终结点，则会返回以下输出。</span><span class="sxs-lookup"><span data-stu-id="ce69c-188">The following is the output returned if you chose the Rounding Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    3.  <span data-ttu-id="ce69c-189">如果选择没有自定义标头的常规计算器终结点，则会返回以下输出。</span><span class="sxs-lookup"><span data-stu-id="ce69c-189">The following is the output returned if you chose the Regular Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68. 46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
    4.  <span data-ttu-id="ce69c-190">如果选择没有自定义标头的默认路由器终结点，则会返回以下输出。</span><span class="sxs-lookup"><span data-stu-id="ce69c-190">The following is the output returned if you chose the Default Router endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.14285714285714  
        ```  
  
8.  <span data-ttu-id="ce69c-191">计算器服务和舍入计算器服务也会向其各自的控制台窗口输出调用的操作的日志。</span><span class="sxs-lookup"><span data-stu-id="ce69c-191">The Calculator Service and the Rounding Calculator Service also prints out a log of the operations invoked to their respective console windows.</span></span>  
  
9. <span data-ttu-id="ce69c-192">在客户端控制台窗口中，键入`quit`然后按 ENTER 以退出。</span><span class="sxs-lookup"><span data-stu-id="ce69c-192">In the client console window, type `quit` and press ENTER to exit.</span></span>  
  
10. <span data-ttu-id="ce69c-193">在服务控制台窗口中按 ENTER 终止服务。</span><span class="sxs-lookup"><span data-stu-id="ce69c-193">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="ce69c-194">可通过代码或 App.config 配置</span><span class="sxs-lookup"><span data-stu-id="ce69c-194">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="ce69c-195">所提供的示例配置为使用 App.config 文件来定义路由器行为。</span><span class="sxs-lookup"><span data-stu-id="ce69c-195">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="ce69c-196">也可将 RoutingService\App.config 文件的名称更改为另一个名称，使之无法识别，并在 RoutingService\routing.cs 中取消对 `ConfigureRouterViaCode()` 的方法调用的注释。</span><span class="sxs-lookup"><span data-stu-id="ce69c-196">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()` in RoutingService\routing.cs.</span></span> <span data-ttu-id="ce69c-197">以上任一方法都可产生相同的路由器行为。</span><span class="sxs-lookup"><span data-stu-id="ce69c-197">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="ce69c-198">方案</span><span class="sxs-lookup"><span data-stu-id="ce69c-198">Scenario</span></span>  
 <span data-ttu-id="ce69c-199">此示例演示的路由器充当基于内容的路由器，从而可以通过一个终结点公开多种服务类型或实现。</span><span class="sxs-lookup"><span data-stu-id="ce69c-199">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="ce69c-200">实际方案</span><span class="sxs-lookup"><span data-stu-id="ce69c-200">Real World Scenario</span></span>  
 <span data-ttu-id="ce69c-201">Contoso 希望虚拟化其所有服务以仅公开一个终结点，这些服务通过该终结点可提供对多种不同类型的服务的访问。</span><span class="sxs-lookup"><span data-stu-id="ce69c-201">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="ce69c-202">在这种情况下，这些服务利用路由服务的基于内容的路由功能，以确定应将传入请求发送到哪个位置。</span><span class="sxs-lookup"><span data-stu-id="ce69c-202">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce69c-203">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce69c-203">See Also</span></span>  
 [<span data-ttu-id="ce69c-204">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="ce69c-204">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
