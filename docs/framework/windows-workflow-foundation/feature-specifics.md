---
title: "Windows Workflow Foundation 功能详细信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 369c8738addeb083b42063161957cf9f97e2cd1c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="windows-workflow-foundation-feature-specifics"></a><span data-ttu-id="b209f-102">Windows Workflow Foundation 功能详细信息</span><span class="sxs-lookup"><span data-stu-id="b209f-102">Windows Workflow Foundation Feature Specifics</span></span>
[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]<span data-ttu-id="b209f-103"> 向 Windows Workflow Foundation 添加了大量功能。</span><span class="sxs-lookup"><span data-stu-id="b209f-103"> adds a number of features to Windows Workflow Foundation.</span></span> <span data-ttu-id="b209f-104">本文档介绍了大量新的功能，并详述了这些功能可用于的方案。</span><span class="sxs-lookup"><span data-stu-id="b209f-104">This document describes a number of the new features, and gives details about scenarios in which they may be useful.</span></span>  
  
## <a name="messaging-activities"></a><span data-ttu-id="b209f-105">消息传递活动</span><span class="sxs-lookup"><span data-stu-id="b209f-105">Messaging Activities</span></span>  
 <span data-ttu-id="b209f-106">消息传递活动 (<xref:System.ServiceModel.Activities.Receive>， <xref:System.ServiceModel.Activities.SendReply>， <xref:System.ServiceModel.Activities.Send>， <xref:System.ServiceModel.Activities.ReceiveReply>) 用于发送和接收[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]从工作流的消息。</span><span class="sxs-lookup"><span data-stu-id="b209f-106">The messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) are used to send and receive [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] messages from your workflow.</span></span>  <span data-ttu-id="b209f-107"><xref:System.ServiceModel.Activities.Receive>和<xref:System.ServiceModel.Activities.SendReply>活动来形成[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]服务就像标准一样通过 WSDL 公开的操作[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]web 服务。</span><span class="sxs-lookup"><span data-stu-id="b209f-107"><xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities are used to form a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service operation that is exposed via WSDL just like standard [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] web services.</span></span>  <span data-ttu-id="b209f-108"><xref:System.ServiceModel.Activities.Send>和<xref:System.ServiceModel.Activities.ReceiveReply>用于使用类似于 WCF web 服务<xref:System.ServiceModel.ChannelFactory>;**添加服务引用**体验还存在生成预配置的活动的 Workflow Foundation。</span><span class="sxs-lookup"><span data-stu-id="b209f-108"><xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> are used to consume a web service similar to a WCF <xref:System.ServiceModel.ChannelFactory>; an **Add Service Reference** experience also exists for Workflow Foundation that generates pre-configured activities.</span></span>  
  
### <a name="getting-started-with-messaging-activities"></a><span data-ttu-id="b209f-109">消息传递活动入门</span><span class="sxs-lookup"><span data-stu-id="b209f-109">Getting Started with Messaging Activities</span></span>  
  
-   <span data-ttu-id="b209f-110">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个 WCF 工作流服务应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="b209f-110">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="b209f-111"><xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 对将置于画布上。</span><span class="sxs-lookup"><span data-stu-id="b209f-111">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas.</span></span>  
  
-   <span data-ttu-id="b209f-112">右键单击项目并选择**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="b209f-112">Right-click on the project and select **Add Service Reference**.</span></span>  <span data-ttu-id="b209f-113">指向现有 web 服务 WSDL，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b209f-113">Point to an existing web service WSDL and click **OK**.</span></span>  <span data-ttu-id="b209f-114">生成项目以显示所生成的活动 (使用实现<xref:System.ServiceModel.Activities.Send>和<xref:System.ServiceModel.Activities.ReceiveReply>) 在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="b209f-114">Build your project to show the generated activities (implemented using <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply>) in your toolbox.</span></span>  
  
-   <span data-ttu-id="b209f-115">这些活动的示例可在以下部分找到：</span><span class="sxs-lookup"><span data-stu-id="b209f-115">Samples for these activities can be found in the following sections:</span></span>  
  
    -   <span data-ttu-id="b209f-116">Basic:[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-116">Basic: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="b209f-117">方案：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-117">Scenarios: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
-   [<span data-ttu-id="b209f-118">概念文档</span><span class="sxs-lookup"><span data-stu-id="b209f-118">Conceptual documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204801)  
  
-   [<span data-ttu-id="b209f-119">消息传递活动设计器文档</span><span class="sxs-lookup"><span data-stu-id="b209f-119">Messaging activities designer documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204802)  
  
### <a name="messaging-activities-example-scenario"></a><span data-ttu-id="b209f-120">消息传递活动示例方案</span><span class="sxs-lookup"><span data-stu-id="b209f-120">Messaging Activities Example Scenario</span></span>  
 <span data-ttu-id="b209f-121">A`BestPriceFinder`服务调用多个航班服务来查找最佳的票证价格为特定的路由。</span><span class="sxs-lookup"><span data-stu-id="b209f-121">A `BestPriceFinder` service calls out to multiple airline services to find the best ticket price for a particular route.</span></span>  <span data-ttu-id="b209f-122">实施此方案会要求你使用消息活动来接收价格请求、 从后端服务中，检索价格和答复到最佳的价格的价格请求。</span><span class="sxs-lookup"><span data-stu-id="b209f-122">Implementing this scenario would require you to use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span>  <span data-ttu-id="b209f-123">它还将要求你使用其他现成的活动来创建用于计算的最佳价格的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="b209f-123">It would also require you to use other out-of-box activities to create the business logic for calculating the best price.</span></span>  
  
## <a name="workflowservicehost"></a><span data-ttu-id="b209f-124">WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="b209f-124">WorkflowServiceHost</span></span>  
 <span data-ttu-id="b209f-125"><xref:System.ServiceModel.WorkflowServiceHost>是现成的工作流主机，可支持多个实例配置中，和[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]消息传送 （尽管工作流无需使用消息传递即可进行承载）。</span><span class="sxs-lookup"><span data-stu-id="b209f-125">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-box workflow host that supports multiple instances, configuration, and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="b209f-126">它还通过一组服务行为集成了持久性、跟踪和实例控件。</span><span class="sxs-lookup"><span data-stu-id="b209f-126">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="b209f-127">就像[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]的<xref:System.ServiceModel.ServiceHost>、<xref:System.ServiceModel.WorkflowServiceHost>可以自承载于控制台/WinForms/WPF 应用程序或 Windows 服务或 web 承载 （作为.xamlx 文件） 在 IIS 或 WAS。</span><span class="sxs-lookup"><span data-stu-id="b209f-127">Just like [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in a console/WinForms/WPF application or Windows service, or web-hosted (as a .xamlx file) in IIS or WAS.</span></span>  
  
### <a name="getting-started-with-workflow-service-host"></a><span data-ttu-id="b209f-128">工作流服务主机入门</span><span class="sxs-lookup"><span data-stu-id="b209f-128">Getting Started with Workflow Service Host</span></span>  
  
-   <span data-ttu-id="b209f-129">在 Visual Studio 2010 中，创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 工作流服务应用程序项目：此项目将设置为在 Web 承载环境中使用 <xref:System.ServiceModel.WorkflowServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="b209f-129">In Visual Studio 2010, create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Workflow Service Application project: this project will be set up to use <xref:System.ServiceModel.WorkflowServiceHost> in a web-host environment.</span></span>  
  
-   <span data-ttu-id="b209f-130">若要承载非消息传递工作流，请添加一个自定义 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>，它将创建基于消息的实例。</span><span class="sxs-lookup"><span data-stu-id="b209f-130">In order to host a non-messaging workflow, add a custom <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> that will create the instance based on a message.</span></span>  
  
-   <span data-ttu-id="b209f-131">可通过将 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> 添加到 <xref:System.ServiceModel.WorkflowServiceHost>，然后使用 <xref:System.ServiceModel.Activities.WorkflowControlClient> 来控制工作流实例（例如，已挂起或已终止）。</span><span class="sxs-lookup"><span data-stu-id="b209f-131">Workflow instances can be controlled (e.g. suspended or terminated) by adding a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> to the <xref:System.ServiceModel.WorkflowServiceHost> and then using a <xref:System.ServiceModel.Activities.WorkflowControlClient>.</span></span>  
  
-   <span data-ttu-id="b209f-132"><xref:System.ServiceModel.WorkflowServiceHost> 的示例可在以下部分找到：</span><span class="sxs-lookup"><span data-stu-id="b209f-132">Samples for the <xref:System.ServiceModel.WorkflowServiceHost> can be found in the following sections:</span></span>  
  
    -   [<span data-ttu-id="b209f-133">执行</span><span class="sxs-lookup"><span data-stu-id="b209f-133">Execution</span></span>](../../../docs/framework/windows-workflow-foundation/samples/execution.md)  
  
    -   <span data-ttu-id="b209f-134">Basic:[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-134">Basic: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="b209f-135">方案：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-135">Scenarios: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="b209f-136">应用程序：[挂起实例管理](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-136">Application: [Suspended Instance Management](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)</span></span>  
  
-   [<span data-ttu-id="b209f-137">WorkflowServiceHost 概念文档</span><span class="sxs-lookup"><span data-stu-id="b209f-137">WorkflowServiceHost Conceptual Documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204807)  
  
### <a name="workflowservicehost-scenario"></a><span data-ttu-id="b209f-138">WorkflowServiceHost 方案</span><span class="sxs-lookup"><span data-stu-id="b209f-138">WorkflowServiceHost Scenario</span></span>  
 <span data-ttu-id="b209f-139">BestPriceFinder 服务调用多个航班服务来查找最佳的票证价格为特定的路由。</span><span class="sxs-lookup"><span data-stu-id="b209f-139">A BestPriceFinder service calls out to multiple airline services to find the best ticket price for a particular route.</span></span>  <span data-ttu-id="b209f-140">实施此方案需要你来承载工作流中的<xref:System.ServiceModel.WorkflowServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="b209f-140">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  <span data-ttu-id="b209f-141">它还将使用消息活动接收的价格请求、 从后端服务中，检索价格和回复最佳价格的价格请求。</span><span class="sxs-lookup"><span data-stu-id="b209f-141">It would also use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span>  
  
## <a name="correlation"></a><span data-ttu-id="b209f-142">相关性</span><span class="sxs-lookup"><span data-stu-id="b209f-142">Correlation</span></span>  
 <span data-ttu-id="b209f-143">相关性具有以下两种含义：</span><span class="sxs-lookup"><span data-stu-id="b209f-143">A correlation is one of two things:</span></span>  
  
-   <span data-ttu-id="b209f-144">将消息组合在一起的方法；即，请求消息与其答复之间的关系。</span><span class="sxs-lookup"><span data-stu-id="b209f-144">A way of grouping messages together; that is, the relationship between a request message and its reply.</span></span>  
  
-   <span data-ttu-id="b209f-145">将一段数据映射到一个服务实例的方法</span><span class="sxs-lookup"><span data-stu-id="b209f-145">A way of mapping a piece of data to a service instance</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-146">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-146">Getting Started</span></span>  
  
-   <span data-ttu-id="b209f-147">若要开始学习相关性，请在 Visual Studio 中创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="b209f-147">To get started with correlation, create a new project in Visual Studio.</span></span> <span data-ttu-id="b209f-148">创建一个类型为 <xref:System.ServiceModel.Activities.CorrelationHandle> 的变量。</span><span class="sxs-lookup"><span data-stu-id="b209f-148">Create a variable of type <xref:System.ServiceModel.Activities.CorrelationHandle>.</span></span>  
  
-   <span data-ttu-id="b209f-149">例如，将消息组合在一起的请求-答复相关性就是用于将消息组合在一起的相关性。</span><span class="sxs-lookup"><span data-stu-id="b209f-149">An example of correlation used to group messages together is a Request-Reply correlation that groups messages together.</span></span>  
  
    -   <span data-ttu-id="b209f-150">在 <xref:System.ServiceModel.Activities.Receive> 活动上单击 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 属性，并使用上一个步骤中创建的 CorrelationHandle 添加 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>。</span><span class="sxs-lookup"><span data-stu-id="b209f-150">On a <xref:System.ServiceModel.Activities.Receive> activity, click on the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> property and add a a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> using the CorrelationHandle created in the first step above.</span></span>  
  
    -   <span data-ttu-id="b209f-151">创建<xref:System.ServiceModel.Activities.SendReply>通过右键单击活动<xref:System.ServiceModel.Activities.Receive>并单击"创建 SendReply"。</span><span class="sxs-lookup"><span data-stu-id="b209f-151">Create a <xref:System.ServiceModel.Activities.SendReply> activity by right-clicking on the <xref:System.ServiceModel.Activities.Receive> and clicking "Create SendReply".</span></span> <span data-ttu-id="b209f-152">将其粘贴到工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动后。</span><span class="sxs-lookup"><span data-stu-id="b209f-152">Paste it into your workflow after the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>  
  
-   <span data-ttu-id="b209f-153">将一段数据映射到一个服务实例的示例为基于内容的相关性，它将一段数据（例如，订单 ID）映射到一个特定的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="b209f-153">An example of mapping a piece of data to a service instance is content-based correlation which maps a piece of data (for example, an order ID) to a particular workflow instance.</span></span>  
  
    -   <span data-ttu-id="b209f-154">在任何消息传递活动上，单击 `CorrelationInitializers` 属性，并使用上面创建的 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 变量添加 <xref:System.ServiceModel.Activities.CorrelationHandle>。</span><span class="sxs-lookup"><span data-stu-id="b209f-154">On any messaging activity, click on the `CorrelationInitializers` property and add a <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> using the <xref:System.ServiceModel.Activities.CorrelationHandle> variable created above.</span></span> <span data-ttu-id="b209f-155">从下拉菜单中，双击消息上的所需属性（如 OrderID）。</span><span class="sxs-lookup"><span data-stu-id="b209f-155">Double-click on the desired property on the message (e.g. OrderID) from the drop-down menu.</span></span> <span data-ttu-id="b209f-156">将 `CorrelatesWith` 属性设置为上面使用的 <xref:System.ServiceModel.Activities.CorrelationHandle> 变量。</span><span class="sxs-lookup"><span data-stu-id="b209f-156">Set the `CorrelatesWith` property to the <xref:System.ServiceModel.Activities.CorrelationHandle> variable used above.</span></span>  
  
-   <span data-ttu-id="b209f-157">示例：</span><span class="sxs-lookup"><span data-stu-id="b209f-157">Samples:</span></span>  
  
    -   <span data-ttu-id="b209f-158">Basic:[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-158">Basic: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   <span data-ttu-id="b209f-159">方案：[服务](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-159">Scenarios: [Services](../../../docs/framework/windows-workflow-foundation/samples/services.md)</span></span>  
  
    -   [<span data-ttu-id="b209f-160">相关性概念文档</span><span class="sxs-lookup"><span data-stu-id="b209f-160">Correlation Conceptual Documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204939)  
  
### <a name="correlation-scenario"></a><span data-ttu-id="b209f-161">相关性方案</span><span class="sxs-lookup"><span data-stu-id="b209f-161">Correlation Scenario</span></span>  
 <span data-ttu-id="b209f-162">订单处理工作流用于处理新的顺序创建和更新现有的订单，在过程中。</span><span class="sxs-lookup"><span data-stu-id="b209f-162">An order-processing workflow is used to handle new order creation and updating existing orders that are in process.</span></span>  <span data-ttu-id="b209f-163">实施此方案需要你来承载工作流中的<xref:System.ServiceModel.WorkflowServiceHost>和使用消息传递活动。</span><span class="sxs-lookup"><span data-stu-id="b209f-163">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost> and use the messaging activities.</span></span>  <span data-ttu-id="b209f-164">这还将需要基于相关`orderId`以确保对正确的工作流进行更新。</span><span class="sxs-lookup"><span data-stu-id="b209f-164">It would also require correlation based on the `orderId` to ensure that updates are made to the correct workflow.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="b209f-165">简化配置</span><span class="sxs-lookup"><span data-stu-id="b209f-165">Simplified Configuration</span></span>  
 <span data-ttu-id="b209f-166">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 配置架构比较复杂，导致用户难以查找功能。</span><span class="sxs-lookup"><span data-stu-id="b209f-166">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration schema is complex and provides users with many hard to find features.</span></span> <span data-ttu-id="b209f-167">在 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中，我们侧重于帮助 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 用户使用以下功能来配置其服务：</span><span class="sxs-lookup"><span data-stu-id="b209f-167">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], we have focused on helping [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] users configure their services with the following features:</span></span>  
  
-   <span data-ttu-id="b209f-168">使用户不需要为每个服务进行显式配置。</span><span class="sxs-lookup"><span data-stu-id="b209f-168">Removing the need for explicit per-service configuration.</span></span> <span data-ttu-id="b209f-169">如果未配置任何\<服务 > 你的服务，以及你的服务的元素未定义以编程方式任何终结点，则一组终结点将自动添加到你的服务，一个每个服务基址和协定服务实现的。</span><span class="sxs-lookup"><span data-stu-id="b209f-169">If you do not configure any \<service> elements for your service, and your service does not define programmatically any endpoint, then a set of endpoints will be automatically added to your service, one per service base address and per contract implemented by your service.</span></span>  
  
-   <span data-ttu-id="b209f-170">使用户能够为 WCF 绑定和行为定义默认值，这些默认值将应用于无显示配置的服务。</span><span class="sxs-lookup"><span data-stu-id="b209f-170">Enables the user to define default values for WCF bindings and behaviors, which will be applied to services with no explicit configuration.</span></span>  
  
-   <span data-ttu-id="b209f-171">标准终结点定义了可重用的预配置终结点，这些终结点具有一个或多个终结点属性（地址、绑定和协定）的固定值，并允许定义自定义属性。</span><span class="sxs-lookup"><span data-stu-id="b209f-171">Standard endpoints define reusable preconfigured endpoints, which have fixed values for one or more of the endpoint properties (address, binding and contract), and allow defining custom properties.</span></span>  
  
-   <span data-ttu-id="b209f-172">最后，<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 允许您对 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端配置进行集中管理，这在应用程序域加载时间后选择或更改配置的方案中很有用。</span><span class="sxs-lookup"><span data-stu-id="b209f-172">Finally, the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows you to do central management of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client configuration, useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-173">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-173">Getting Started</span></span>  
  
-   [<span data-ttu-id="b209f-174">WCF 4.0 开发人员指南</span><span class="sxs-lookup"><span data-stu-id="b209f-174">A Developer's Guide to WCF 4.0</span></span>](http://go.microsoft.com/fwlink/?LinkId=204940)  
  
-   [<span data-ttu-id="b209f-175">配置通道工厂</span><span class="sxs-lookup"><span data-stu-id="b209f-175">Configuration Channel Factory</span></span>](http://go.microsoft.com/fwlink/?LinkId=204941)  
  
-   [<span data-ttu-id="b209f-176">标准终结点元素</span><span class="sxs-lookup"><span data-stu-id="b209f-176">Standard Endpoint Element</span></span>](http://go.microsoft.com/fwlink/?LinkId=204942)  
  
-   [<span data-ttu-id="b209f-177">服务配置改进在.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="b209f-177">Service configuration improvements in .Net Framework 4</span></span>](http://go.microsoft.com/fwlink/?LinkId=204943)  
  
-   [<span data-ttu-id="b209f-178">.NET 4 中的常见用户错误： 键入错误 WF/WCF 服务配置名称</span><span class="sxs-lookup"><span data-stu-id="b209f-178">Common User Mistake in .NET 4: Mistyping the WF/WCF Service Configuration Name</span></span>](http://go.microsoft.com/fwlink/?LinkId=204944)  
  
### <a name="simplified-configuration-scenarios"></a><span data-ttu-id="b209f-179">简化配置方案</span><span class="sxs-lookup"><span data-stu-id="b209f-179">Simplified Configuration Scenarios</span></span>  
  
-   <span data-ttu-id="b209f-180">一位经验丰富的 ASMX 开发人员希望开始使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b209f-180">An experienced ASMX developer wants to start using [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="b209f-181">但是，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 看起来太复杂了！</span><span class="sxs-lookup"><span data-stu-id="b209f-181">However, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] seems way too complicated!</span></span> <span data-ttu-id="b209f-182">我需要在配置文件中编写哪些信息呢？</span><span class="sxs-lookup"><span data-stu-id="b209f-182">What is all that information that I need to write in a configuration file?</span></span> <span data-ttu-id="b209f-183">在 .NET 4 中，您甚至可以决定完全不使用配置文件。</span><span class="sxs-lookup"><span data-stu-id="b209f-183">In .NET 4, you can even decide to not have a configuration file at all.</span></span>  
  
-   <span data-ttu-id="b209f-184">现有的一组 WCF 服务难以进行配置和维护。</span><span class="sxs-lookup"><span data-stu-id="b209f-184">An existing set of WCF services are very difficult to configure and maintain.</span></span> <span data-ttu-id="b209f-185">配置文件具有数千行 XML 代码，操作这些代码会产生很大的风险。</span><span class="sxs-lookup"><span data-stu-id="b209f-185">The configuration file has thousands of lines of XML code that are extremely dangerous to touch.</span></span> <span data-ttu-id="b209f-186">需要获得帮助以减少代码量，来提高可管理性。</span><span class="sxs-lookup"><span data-stu-id="b209f-186">Help is needed to reduce that amount of code to something more manageable.</span></span>  
  
## <a name="data-contract-resolver"></a><span data-ttu-id="b209f-187">数据协定解析程序</span><span class="sxs-lookup"><span data-stu-id="b209f-187">Data Contract Resolver</span></span>  
 <span data-ttu-id="b209f-188">.NET 3.5 中包含对已知类型的设计的几个限制：</span><span class="sxs-lookup"><span data-stu-id="b209f-188">In .NET 3.5, there were a few limitations in the design of known types:</span></span>  
  
-   <span data-ttu-id="b209f-189">在序列化或反序列化过程中不能动态添加已知类型。</span><span class="sxs-lookup"><span data-stu-id="b209f-189">Adding known types dynamically, during serialization or deserialization, was not possible.</span></span>  
  
-   <span data-ttu-id="b209f-190">序列化程序无法处理未知的 xsi:type 信息。</span><span class="sxs-lookup"><span data-stu-id="b209f-190">Serializers could not deal with unknown xsi:type information.</span></span>  
  
-   <span data-ttu-id="b209f-191">用户无法指定他们想要在网络上显示的 xsi:type，例如，使网络上的序列化实例更小一些。</span><span class="sxs-lookup"><span data-stu-id="b209f-191">It was not possible for users to specify what xsi:type they would like to have appear on the wire to, for instance, make the size of a serialization instance on the wire smaller.</span></span>  
  
 <span data-ttu-id="b209f-192">[DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md)解决了.NET 4.5 中的这些问题。</span><span class="sxs-lookup"><span data-stu-id="b209f-192">The [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md) solves these issues in .NET 4.5.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-193">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-193">Getting Started</span></span>  
  
-   [<span data-ttu-id="b209f-194">数据协定解析程序 API 文档</span><span class="sxs-lookup"><span data-stu-id="b209f-194">Data Contract Resolver API documentation</span></span>](http://go.microsoft.com/fwlink/?LinkId=204946)  
  
-   [<span data-ttu-id="b209f-195">引入数据协定解析程序</span><span class="sxs-lookup"><span data-stu-id="b209f-195">Introducing the Data Contract Resolver</span></span>](http://go.microsoft.com/fwlink/?LinkId=204947)  
  
-   <span data-ttu-id="b209f-196">示例：</span><span class="sxs-lookup"><span data-stu-id="b209f-196">Samples:</span></span>  
  
    -   [<span data-ttu-id="b209f-197">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="b209f-197">DataContractResolver</span></span>](../../../docs/framework/wcf/samples/datacontractresolver.md)  
  
    -   [<span data-ttu-id="b209f-198">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="b209f-198">KnownAssemblyAttribute</span></span>](../../../docs/framework/wcf/samples/knownassemblyattribute.md)  
  
### <a name="data-contract-resolver-scenarios"></a><span data-ttu-id="b209f-199">数据协定解析程序方案</span><span class="sxs-lookup"><span data-stu-id="b209f-199">Data Contract Resolver Scenarios</span></span>  
  
-   <span data-ttu-id="b209f-200">无需在服务中声明数十个 <xref:System.Runtime.Serialization.KnownTypeAttribute> 对象。</span><span class="sxs-lookup"><span data-stu-id="b209f-200">Avoiding having to declare tens of <xref:System.Runtime.Serialization.KnownTypeAttribute> objects in a service.</span></span>  
  
-   <span data-ttu-id="b209f-201">减小 XML Blob 的大小。</span><span class="sxs-lookup"><span data-stu-id="b209f-201">Reducing the size of the XML blob.</span></span>  
  
## <a name="flowchart"></a><span data-ttu-id="b209f-202">流程图</span><span class="sxs-lookup"><span data-stu-id="b209f-202">Flowchart</span></span>  
 <span data-ttu-id="b209f-203">流程图是用于以可视方式表示域问题的已知范例。</span><span class="sxs-lookup"><span data-stu-id="b209f-203">Flowchart is a well-known paradigm to visually represent domain problems.</span></span> <span data-ttu-id="b209f-204">它是我们在 .NET 4 中引入的新控制流样式。</span><span class="sxs-lookup"><span data-stu-id="b209f-204">It is a new control flow style we’re introducing in .NET 4.</span></span> <span data-ttu-id="b209f-205">流程图的核心特点是，在任何给定时间只能执行一个活动。</span><span class="sxs-lookup"><span data-stu-id="b209f-205">A core characteristic of Flowchart is that only one activity is executed at any given time.</span></span> <span data-ttu-id="b209f-206">流程图可以表示循环和备选结果，但无法表示多个节点的并发执行。</span><span class="sxs-lookup"><span data-stu-id="b209f-206">Flowcharts can express loops and alternative outcomes, but cannot natively express concurrent execution of multiple nodes.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-207">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-207">Getting Started</span></span>  
  
-   <span data-ttu-id="b209f-208">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="b209f-208">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="b209f-209">在工作流设计器中添加流程图。</span><span class="sxs-lookup"><span data-stu-id="b209f-209">Add a Flowchart in the workflow designer.</span></span>  
  
-   <span data-ttu-id="b209f-210">流程图功能使用以下类：</span><span class="sxs-lookup"><span data-stu-id="b209f-210">The flowchart feature uses the following classes:</span></span>  
  
    -   <xref:System.Activities.Statements.Flowchart>  
  
    -   <xref:System.Activities.Statements.FlowNode>  
  
    -   <xref:System.Activities.Statements.FlowDecision>  
  
    -   <xref:System.Activities.Statements.FlowStep>  
  
    -   <xref:System.Activities.Statements.FlowSwitch%601>  
  
-   <span data-ttu-id="b209f-211">示例：</span><span class="sxs-lookup"><span data-stu-id="b209f-211">Samples:</span></span>  
  
    -   [<span data-ttu-id="b209f-212">在使用 TryCatch Flowchart 活动中处理的错误</span><span class="sxs-lookup"><span data-stu-id="b209f-212">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    -   [<span data-ttu-id="b209f-213">使用 FlowChart 与 Pick 的组合的 StateMachine 方案</span><span class="sxs-lookup"><span data-stu-id="b209f-213">StateMachine Scenario Using a Combination of FlowChart and Pick</span></span>](../../../docs/framework/windows-workflow-foundation/samples/statemachine-scenario-using-a-combination-of-flowchart-and-pick.md)  
  
    -   [<span data-ttu-id="b209f-214">招聘流程</span><span class="sxs-lookup"><span data-stu-id="b209f-214">Hiring Process</span></span>](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
-   <span data-ttu-id="b209f-215">设计器文档：</span><span class="sxs-lookup"><span data-stu-id="b209f-215">Designer Documentation:</span></span>  
  
    -   [<span data-ttu-id="b209f-216">Flowchart 活动设计器</span><span class="sxs-lookup"><span data-stu-id="b209f-216">Flowchart Activity Designers</span></span>](/visualstudio/workflow-designer/flowchart-activity-designers)  
  
### <a name="flowchart-scenarios"></a><span data-ttu-id="b209f-217">流程图方案</span><span class="sxs-lookup"><span data-stu-id="b209f-217">Flowchart Scenarios</span></span>  
 <span data-ttu-id="b209f-218">流程图活动可用于实现猜谜游戏。</span><span class="sxs-lookup"><span data-stu-id="b209f-218">A flowchart activity can be used to implement a guessing game.</span></span> <span data-ttu-id="b209f-219">猜谜游戏非常简单：计算机选择一个随机数，然后玩家必须猜出该数字。</span><span class="sxs-lookup"><span data-stu-id="b209f-219">The guessing game is very simple: the computer selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="b209f-220">当玩家提交每个猜测时，计算机会给出提示 （即"尝试使用较小的数字"）。</span><span class="sxs-lookup"><span data-stu-id="b209f-220">When the player submits each guess, the computer shows him a hint (i.e. "try a lower number").</span></span> <span data-ttu-id="b209f-221">如果玩家在 7 次之内猜出该数字，则计算机将为其显示特定的祝贺语。</span><span class="sxs-lookup"><span data-stu-id="b209f-221">If the player finds the number in less than 7 attempts, he receives a special congratulation from the computer.</span></span> <span data-ttu-id="b209f-222">可使用以下过程活动组合来实现此游戏：</span><span class="sxs-lookup"><span data-stu-id="b209f-222">This game can be implemented with a combination of the following procedural activities:</span></span>  
  
-   <xref:System.Activities.Statements.Sequence>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.TryCatch>  
  
-   <xref:System.Activities.Statements.Assign%601>  
  
-   <xref:System.Activities.Statements.If>  
  
## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a><span data-ttu-id="b209f-223">过程活动（Sequence、If、ForEach、Switch、Assign、DoWhile 和 While）</span><span class="sxs-lookup"><span data-stu-id="b209f-223">Procedural activities (Sequence, If, ForEach, Switch, Assign, DoWhile, While)</span></span>  
 <span data-ttu-id="b209f-224">过程活动提供了一种机制，该机制使用程序员熟悉的概念为顺序控制流建模。</span><span class="sxs-lookup"><span data-stu-id="b209f-224">Procedural activities provide a mechanism to model sequential control flow using concepts that are familiar to programmers.</span></span> <span data-ttu-id="b209f-225">这些活动会启用传统结构化编程语言构造，并在适当时提供采用公共过程语言（如 C#/VB）的语言奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="b209f-225">These activities enable traditionally structured programming language constructs and, when appropriate, provide language parity with common procedural languages such as C#/VB.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-226">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-226">Getting Started</span></span>  
  
-   <span data-ttu-id="b209f-227">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="b209f-227">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="b209f-228">在工作流设计器中添加过程活动。</span><span class="sxs-lookup"><span data-stu-id="b209f-228">Add procedural activities in the workflow designer.</span></span>  
  
-   <span data-ttu-id="b209f-229">示例：</span><span class="sxs-lookup"><span data-stu-id="b209f-229">Samples:</span></span>  
  
    -   [<span data-ttu-id="b209f-230">招聘流程</span><span class="sxs-lookup"><span data-stu-id="b209f-230">Hiring Process</span></span>](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
    -   [<span data-ttu-id="b209f-231">企业采购过程</span><span class="sxs-lookup"><span data-stu-id="b209f-231">Corporate Purchase Process</span></span>](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)  
  
-   <span data-ttu-id="b209f-232">设计器文档：</span><span class="sxs-lookup"><span data-stu-id="b209f-232">Designer Documentation:</span></span>  
  
    -   [<span data-ttu-id="b209f-233">Parallel 活动设计器</span><span class="sxs-lookup"><span data-stu-id="b209f-233">Parallel Activity Designer</span></span>](/visualstudio/workflow-designer/parallel-activity-designer)  
  
    -   [<span data-ttu-id="b209f-234">ParallelForEach\<T > 活动设计器</span><span class="sxs-lookup"><span data-stu-id="b209f-234">ParallelForEach\<T> Activity Designer</span></span>](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)  
  
### <a name="procedural-activity-scenarios"></a><span data-ttu-id="b209f-235">过程活动方案</span><span class="sxs-lookup"><span data-stu-id="b209f-235">Procedural Activity Scenarios</span></span>  
  
-   <span data-ttu-id="b209f-236"><xref:System.Activities.Statements.Parallel>： 的 intranet 文档管理系统具有文档审批工作流。</span><span class="sxs-lookup"><span data-stu-id="b209f-236"><xref:System.Activities.Statements.Parallel>: An intranet document management system has a document approval workflow.</span></span> <span data-ttu-id="b209f-237">文档需要先经过多个部门人员的审批，然后才能发布到 Intranet。</span><span class="sxs-lookup"><span data-stu-id="b209f-237">Documents need to be approved by people in several departments before they can be published to the intranet.</span></span> <span data-ttu-id="b209f-238">没有审批; 建立的顺序它们可以在文档处于"审批挂起"阶段时，在任何时候出现。</span><span class="sxs-lookup"><span data-stu-id="b209f-238">There isn’t an established order for the approvals; they can occur at any time while the document is in the "approval pending" phase.</span></span> <span data-ttu-id="b209f-239">当用户提交文档以供审阅时，该文档必须先由用户的直属经理、Intranet 管理员和内部通信经理审批。</span><span class="sxs-lookup"><span data-stu-id="b209f-239">When a user submits a document for review it must be approved by her direct manager, the intranet administrator, and the internal communications manager.</span></span>  
  
-   <span data-ttu-id="b209f-240"><xref:System.Activities.Statements.ParallelForEach%601>：WF 应用程序将管理大型公司内的公司采购。</span><span class="sxs-lookup"><span data-stu-id="b209f-240"><xref:System.Activities.Statements.ParallelForEach%601>: A WF application manages corporate buys within a large company.</span></span> <span data-ttu-id="b209f-241">公司规则指明，在计划任何采购操作前需要评估三个不同的供应商。</span><span class="sxs-lookup"><span data-stu-id="b209f-241">The corporate rules dictate that before planning any purchase operation, the valuations of three different vendors is required.</span></span> <span data-ttu-id="b209f-242">采购部员工将从公司的供应商列表中选择三个供应商。</span><span class="sxs-lookup"><span data-stu-id="b209f-242">An employee from the buying department selects three vendors from the company’s vendor list.</span></span> <span data-ttu-id="b209f-243">在选择这些供应商并向他们发送通知后，公司将等待他们提出经济实惠的建议。</span><span class="sxs-lookup"><span data-stu-id="b209f-243">After these vendors have been selected and notified, the company will wait for their economic proposals.</span></span> <span data-ttu-id="b209f-244">这些建议会以任意顺序出现。</span><span class="sxs-lookup"><span data-stu-id="b209f-244">The proposals can come in any order.</span></span> <span data-ttu-id="b209f-245">为了在 WF 中实现此方案，我们使用了 <xref:System.Activities.Statements.ParallelForEach%601>，它会循环访问供应商集合并要求他们提供经济建议。</span><span class="sxs-lookup"><span data-stu-id="b209f-245">To implement this scenario in WF, we use a <xref:System.Activities.Statements.ParallelForEach%601> that will iterate through our collection of vendors and ask for their economic proposals.</span></span> <span data-ttu-id="b209f-246">收集完所有建议后，选择并显示最好的建议。</span><span class="sxs-lookup"><span data-stu-id="b209f-246">After all offers are gathered, the best one is selected and displayed.</span></span>  
  
## <a name="invokemethod"></a><span data-ttu-id="b209f-247">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b209f-247">InvokeMethod</span></span>  
 <span data-ttu-id="b209f-248"><xref:System.Activities.Statements.InvokeMethod> 活动允许在范围内的对象或类型中调用公共方法。</span><span class="sxs-lookup"><span data-stu-id="b209f-248">The <xref:System.Activities.Statements.InvokeMethod> activity allows invoking public methods in objects or types in scope.</span></span> <span data-ttu-id="b209f-249">它支持调用实例和带有或不带参数（包括参数数组）的静态方法以及泛型方法。</span><span class="sxs-lookup"><span data-stu-id="b209f-249">It supports invoking instance and static methods with or without parameters (including parameter arrays), and generic methods.</span></span> <span data-ttu-id="b209f-250">它还允许以同步方式和异步方式执行方法。</span><span class="sxs-lookup"><span data-stu-id="b209f-250">It also allows executing method synchronously and asynchronously.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-251">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-251">Getting Started</span></span>  
  
-   <span data-ttu-id="b209f-252">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="b209f-252">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="b209f-253">在工作流设计器中添加一个 <xref:System.Activities.Statements.InvokeMethod> 活动，并对该活动配置静态和实例方法。</span><span class="sxs-lookup"><span data-stu-id="b209f-253">Add an <xref:System.Activities.Statements.InvokeMethod> activity in the workflow designer, and configure static and instance methods on it.</span></span>  
  
-   <span data-ttu-id="b209f-254">示例：</span><span class="sxs-lookup"><span data-stu-id="b209f-254">Samples:</span></span>  
  
    -   [<span data-ttu-id="b209f-255">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b209f-255">InvokeMethod</span></span>](../../../docs/framework/windows-workflow-foundation/samples/invokemethod.md)  
  
-   <span data-ttu-id="b209f-256">设计器文档： [InvokeMethod 活动设计器](/visualstudio/workflow-designer/invokemethod-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="b209f-256">Designer Documentation: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)</span></span>  
  
### <a name="invokemethod-scenarios"></a><span data-ttu-id="b209f-257">InvokeMethod 方案</span><span class="sxs-lookup"><span data-stu-id="b209f-257">InvokeMethod Scenarios</span></span>  
  
-   <span data-ttu-id="b209f-258">需要调用范围内的对象中的方法。</span><span class="sxs-lookup"><span data-stu-id="b209f-258">A method in an object in scope needs to be invoked.</span></span> <span data-ttu-id="b209f-259">例如，需要将值添加到词典。</span><span class="sxs-lookup"><span data-stu-id="b209f-259">For example, a value needs to be added to a dictionary.</span></span> <span data-ttu-id="b209f-260">调用词典实例的 Add 方法并提供键和值。</span><span class="sxs-lookup"><span data-stu-id="b209f-260">The Add method of the instance of the dictionary is invoked, and the key and value are provided.</span></span>  
  
-   <span data-ttu-id="b209f-261">需要对旧 CLR 对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="b209f-261">A method needs to be invoked on a legacy CLR object.</span></span> <span data-ttu-id="b209f-262">如果旧类在工作流执行过程中位于范围内，则可以使用 <xref:System.Activities.Statements.InvokeMethod>，而不是创建将包装对该旧类的调用的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="b209f-262">Instead of creating a custom activity to wrap the call to that legacy class, if it is in scope during the workflow execution, <xref:System.Activities.Statements.InvokeMethod> can be used.</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="b209f-263">错误处理活动</span><span class="sxs-lookup"><span data-stu-id="b209f-263">Error handling activities</span></span>  
 <span data-ttu-id="b209f-264"><xref:System.Activities.Statements.TryCatch> 活动提供了一种机制，用于捕获在执行一组包含的活动的过程中发生的异常（类似于 C#/VB 中的 Try/Catch 构造）。</span><span class="sxs-lookup"><span data-stu-id="b209f-264">The <xref:System.Activities.Statements.TryCatch> activity provides a mechanism for catching exceptions that occur during the execution of a set of contained activities (similar to the Try/Catch construct in C#/VB).</span></span> <span data-ttu-id="b209f-265"><xref:System.Activities.Statements.TryCatch> 提供了工作流级别的异常处理。</span><span class="sxs-lookup"><span data-stu-id="b209f-265"><xref:System.Activities.Statements.TryCatch> provides exception handling at the workflow level.</span></span> <span data-ttu-id="b209f-266">在引发未处理的异常时，系统将终止工作流，并且不会执行 Finally 块。</span><span class="sxs-lookup"><span data-stu-id="b209f-266">When an unhandled exception is thrown, the workflow is aborted and the Finally block won’t be executed.</span></span> <span data-ttu-id="b209f-267">此行为与 C# 一致。</span><span class="sxs-lookup"><span data-stu-id="b209f-267">This behavior is consistent with C#.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-268">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-268">Getting Started</span></span>  
  
-   <span data-ttu-id="b209f-269">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="b209f-269">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="b209f-270">在工作流设计器中添加 <xref:System.Activities.Statements.TryCatch> 活动。</span><span class="sxs-lookup"><span data-stu-id="b209f-270">Add a <xref:System.Activities.Statements.TryCatch> activity in the workflow designer.</span></span>  
  
-   <span data-ttu-id="b209f-271">示例：</span><span class="sxs-lookup"><span data-stu-id="b209f-271">Samples:</span></span>  
  
    1.  [<span data-ttu-id="b209f-272">在使用 TryCatch Flowchart 活动中处理的错误</span><span class="sxs-lookup"><span data-stu-id="b209f-272">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    2.  [<span data-ttu-id="b209f-273">使用过程性活动</span><span class="sxs-lookup"><span data-stu-id="b209f-273">Using Procedural Activities</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-procedural-activities.md)  
  
-   <span data-ttu-id="b209f-274">设计器文档：[错误处理活动设计器](/visualstudio/workflow-designer/error-handling-activity-designers)</span><span class="sxs-lookup"><span data-stu-id="b209f-274">Designer Documentation: [Error Handling Activity Designers](/visualstudio/workflow-designer/error-handling-activity-designers)</span></span>  
  
### <a name="error-handling-scenarios"></a><span data-ttu-id="b209f-275">错误处理方案</span><span class="sxs-lookup"><span data-stu-id="b209f-275">Error handling scenarios</span></span>  
 <span data-ttu-id="b209f-276">需要执行一组活动，并且需要在发生错误时执行特定的逻辑。</span><span class="sxs-lookup"><span data-stu-id="b209f-276">A set of activities needs to be executed, and specific logic needs to be executed when an error occurs.</span></span> <span data-ttu-id="b209f-277">如果在执行错误处理逻辑的过程中发现该错误是不可恢复的，则会重新引发该异常，并且父活动（或主机）将处理该问题。</span><span class="sxs-lookup"><span data-stu-id="b209f-277">If during that error handling logic it is found that the error is not recoverable, the exception will be rethrown, and the parent activity (or the host) will deal with the problem.</span></span>  
  
## <a name="pick-activity"></a><span data-ttu-id="b209f-278">Pick 活动</span><span class="sxs-lookup"><span data-stu-id="b209f-278">Pick activity</span></span>  
 <span data-ttu-id="b209f-279"><xref:System.Activities.Statements.Pick> 活动在 WF 中提供基于事件的控制流建模。</span><span class="sxs-lookup"><span data-stu-id="b209f-279">The <xref:System.Activities.Statements.Pick> Activity provides event-based control flow modeling in WF.</span></span> <span data-ttu-id="b209f-280"><xref:System.Activities.Statements.Pick> 包含多个分支，其中每个分支均要等到特定事件发生后才会运行。</span><span class="sxs-lookup"><span data-stu-id="b209f-280"><xref:System.Activities.Statements.Pick> contains many branches where each branch waits for a particular event to occur before running.</span></span> <span data-ttu-id="b209f-281">在此设置中，<xref:System.Activities.Statements.Pick> 的行为类似于 <xref:System.Activities.Statements.Switch%601>，该活动将只对其执行正在侦听的一组事件中的某个事件。</span><span class="sxs-lookup"><span data-stu-id="b209f-281">In this setup, a <xref:System.Activities.Statements.Pick> behaves similar to a <xref:System.Activities.Statements.Switch%601> to which the Activity will execute only one of the set of events it is listening.</span></span> <span data-ttu-id="b209f-282">每个分支都是事件驱动的，并且发生的事件将先运行对应的分支。</span><span class="sxs-lookup"><span data-stu-id="b209f-282">Each branch is event driven and the event that occurs runs the corresponding branch first.</span></span> <span data-ttu-id="b209f-283">所有其他分支会取消并停止侦听事件。</span><span class="sxs-lookup"><span data-stu-id="b209f-283">All other branches cancel and stop listening for events.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-284">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-284">Getting Started</span></span>  
  
-   <span data-ttu-id="b209f-285">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个工作流控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="b209f-285">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a workflow console application.</span></span> <span data-ttu-id="b209f-286">在工作流设计器中添加 <xref:System.Activities.Statements.Pick> 活动。</span><span class="sxs-lookup"><span data-stu-id="b209f-286">Add a <xref:System.Activities.Statements.Pick> activity in the workflow designer.</span></span>  
  
-   <span data-ttu-id="b209f-287">示例：[使用 Pick 活动](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-287">Sample: [Using the Pick Activity](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)</span></span>  
  
-   <span data-ttu-id="b209f-288">设计器文档： [Pick 活动设计器](/visualstudio/workflow-designer/pick-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="b209f-288">Designer documentation: [Pick Activity Designer](/visualstudio/workflow-designer/pick-activity-designer)</span></span>  
  
### <a name="pick-scenario"></a><span data-ttu-id="b209f-289">Pick 方案</span><span class="sxs-lookup"><span data-stu-id="b209f-289">Pick Scenario</span></span>  
 <span data-ttu-id="b209f-290">系统需要提示用户进行输入。</span><span class="sxs-lookup"><span data-stu-id="b209f-290">A user needs to be prompted for input.</span></span> <span data-ttu-id="b209f-291">在正常情况下，开发人员将使用类似于 <xref:System.Console.ReadLine%2A> 这样的方法调用来提示用户进行输入。</span><span class="sxs-lookup"><span data-stu-id="b209f-291">Under normal circumstances, the developer would use a method call like <xref:System.Console.ReadLine%2A> to prompt for a user’s input.</span></span> <span data-ttu-id="b209f-292">此设置的问题是，程序会一直等到用户输入后才运行。</span><span class="sxs-lookup"><span data-stu-id="b209f-292">The problem with this setup is that the program waits until the user enters something.</span></span> <span data-ttu-id="b209f-293">在此方案中，需要超时来取消对阻止活动的阻止。</span><span class="sxs-lookup"><span data-stu-id="b209f-293">In this scenario, a time-out is needed to unblock a blocking activity.</span></span> <span data-ttu-id="b209f-294">常见的方案会要求在给定持续时间内完成任务。</span><span class="sxs-lookup"><span data-stu-id="b209f-294">A common scenario is one that requires a task to be completed within a given time duration.</span></span> <span data-ttu-id="b209f-295">在阻止活动超时的方案中，Pick 将添加大量值。</span><span class="sxs-lookup"><span data-stu-id="b209f-295">Timing out a blocking activity is a scenario where Pick adds a lot of value.</span></span>  
  
## <a name="wcf-routing-service"></a><span data-ttu-id="b209f-296">WCF 路由服务</span><span class="sxs-lookup"><span data-stu-id="b209f-296">WCF Routing Service</span></span>  
 <span data-ttu-id="b209f-297">路由服务旨在作为一般的软件路由器，它允许你控制如何[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]消息客户端和服务之间的流。</span><span class="sxs-lookup"><span data-stu-id="b209f-297">The Routing Service is designed to be a generic software Router that allows you to control how [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]messages flow in between your clients and services.</span></span>  <span data-ttu-id="b209f-298">路由服务可以分离你的客户端从你的服务，这将使您在配置方面的更自由可以支持和灵活性必须考虑如何承载服务时。</span><span class="sxs-lookup"><span data-stu-id="b209f-298">The Routing Service allows you to decouple your clients from your services, which gives you much more freedom in terms of the configurations that you can support and the flexibility you have when considering how to host your services.</span></span>  <span data-ttu-id="b209f-299">在.NET 3.5 中，客户端和服务紧密结合在一起;客户端必须了解的有关的所有服务，它需要进行对话，其中原来所在。</span><span class="sxs-lookup"><span data-stu-id="b209f-299">In .NET 3.5, clients and services were tightly coupled; a client had to know about all of the services it needed to talk to and where they were located.</span></span> <span data-ttu-id="b209f-300">此外，.Net Framework 3.5 中的 WCF 具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="b209f-300">In addition, WCF in .Net Framework 3.5 had the following limitations:</span></span>  
  
-   <span data-ttu-id="b209f-301">错误处理较为复杂，因为必须将此逻辑硬编码到客户端中。</span><span class="sxs-lookup"><span data-stu-id="b209f-301">Error handling was complex, as this logic had to be hard-coded into the client.</span></span>  
  
-   <span data-ttu-id="b209f-302">客户端和服务必须始终使用同一绑定。</span><span class="sxs-lookup"><span data-stu-id="b209f-302">Clients and services had to always use the same bindings.</span></span>  
  
-   <span data-ttu-id="b209f-303">服务很少能适当地分解：让客户端与一个能实现所有操作的服务进行通信而不必在多个服务之间选择，这样的做法更简单一些。</span><span class="sxs-lookup"><span data-stu-id="b209f-303">Services were rarely well factored: it is easier to have the client talk to one service which implements everything, rather than needing to choose between multiple services.</span></span>  
  
 <span data-ttu-id="b209f-304">.Net 4 中的路由服务旨在更轻松地处理这些问题。</span><span class="sxs-lookup"><span data-stu-id="b209f-304">The routing service in .Net 4 is designed to make these problems easier to solve.</span></span> <span data-ttu-id="b209f-305">新的路由服务具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="b209f-305">The new routing service has the following features:</span></span>  
  
1.  <span data-ttu-id="b209f-306">基于内容的路由（<xref:System.ServiceModel.Dispatcher.MessageFilter> 对象会检查消息以确定其发送位置。）</span><span class="sxs-lookup"><span data-stu-id="b209f-306">Content based routing (<xref:System.ServiceModel.Dispatcher.MessageFilter> objects examine a message to determine where it should be sent.)</span></span>  
  
2.  <span data-ttu-id="b209f-307">协议桥接（传输和消息）</span><span class="sxs-lookup"><span data-stu-id="b209f-307">Protocol bridging (transport & message)</span></span>  
  
3.  <span data-ttu-id="b209f-308">错误处理（路由器将捕获通信异常并将故障转移到备份终结点）</span><span class="sxs-lookup"><span data-stu-id="b209f-308">Error handling (the router catches communication exceptions and fails over to backup endpoints)</span></span>  
  
4.  <span data-ttu-id="b209f-309"><xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> 和路由配置的动态（内存中）更新。</span><span class="sxs-lookup"><span data-stu-id="b209f-309">Dynamic (in memory) update of <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> and Routing Configuration.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-310">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-310">Getting Started</span></span>  
  
1.  <span data-ttu-id="b209f-311">文档：[路由](../../../docs/framework/wcf/feature-details/routing.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-311">Documentation: [Routing](../../../docs/framework/wcf/feature-details/routing.md)</span></span>  
  
2.  <span data-ttu-id="b209f-312">示例：[路由服务和 #91;WCF 示例 &#93;](../../../docs/framework/wcf/samples/routing-services.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-312">Samples: [Routing Services &#91;WCF Samples&#93;](../../../docs/framework/wcf/samples/routing-services.md)</span></span>  
  
3.  <span data-ttu-id="b209f-313">博客：[路由规则 ！](http://go.microsoft.com/fwlink/?LinkId=204956)</span><span class="sxs-lookup"><span data-stu-id="b209f-313">Blog: [Routing Rules!](http://go.microsoft.com/fwlink/?LinkId=204956)</span></span>  
  
### <a name="routing-scenarios"></a><span data-ttu-id="b209f-314">路由方案</span><span class="sxs-lookup"><span data-stu-id="b209f-314">Routing Scenarios</span></span>  
 <span data-ttu-id="b209f-315">路由服务在以下方案中很有用：</span><span class="sxs-lookup"><span data-stu-id="b209f-315">The routing service is useful in the following scenarios:</span></span>  
  
-   <span data-ttu-id="b209f-316">客户端可与多个服务通信，而无需直接处理所有这些服务。</span><span class="sxs-lookup"><span data-stu-id="b209f-316">Clients can talk to multiple services without having to address them all directly.</span></span>  
  
-   <span data-ttu-id="b209f-317">客户端可对客户端请求执行其他逻辑以确定其路由位置</span><span class="sxs-lookup"><span data-stu-id="b209f-317">Clients can perform additional logic on a client request to determine where to route it</span></span>  
  
-   <span data-ttu-id="b209f-318">将客户端执行的操作分解为多个服务实现而不重构客户端。</span><span class="sxs-lookup"><span data-stu-id="b209f-318">Decompose the operations a client performs into multiple service implementations without refactoring the client.</span></span>  
  
-   <span data-ttu-id="b209f-319">客户端和服务可与具有不同安全设置的不同绑定进行通信。</span><span class="sxs-lookup"><span data-stu-id="b209f-319">Clients and services can speak different bindings with different security settings.</span></span>  
  
-   <span data-ttu-id="b209f-320">可以使客户端更为可靠一些，从而防止出现故障或服务不可用的情况。</span><span class="sxs-lookup"><span data-stu-id="b209f-320">Clients can be enabled to be more robust against failure or the unavailability of services.</span></span>  
  
## <a name="wcf-discovery"></a><span data-ttu-id="b209f-321">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="b209f-321">WCF Discovery</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="b209f-322"> Discovery 是一种框架技术，允许您将发现机制并入应用程序基础结构中。</span><span class="sxs-lookup"><span data-stu-id="b209f-322"> Discovery is a framework technology that allows you to incorporate a discovery mechanism to your application infrastructure.</span></span> <span data-ttu-id="b209f-323">利用此技术，您可以使服务可发现，并配置客户端以搜索服务。</span><span class="sxs-lookup"><span data-stu-id="b209f-323">You can use this to make your service discoverable, and configure your clients to search for services.</span></span> <span data-ttu-id="b209f-324">不再需要使用终结点对客户端进行硬编码，即可使应用程序的可靠性更高，容错能力更强。</span><span class="sxs-lookup"><span data-stu-id="b209f-324">Clients no longer need to be hard coded with endpoint, making your application more robust and fault tolerant.</span></span> <span data-ttu-id="b209f-325">Discovery 是一个用于将自动配置功能构建到应用程序中的最佳平台。</span><span class="sxs-lookup"><span data-stu-id="b209f-325">Discovery is the perfect platform to build auto-configuration capabilities into your application.</span></span>  
  
 <span data-ttu-id="b209f-326">该产品是基于 WS-Discovery 标准构建的。</span><span class="sxs-lookup"><span data-stu-id="b209f-326">The product is built on top of the WS-Discovery standard.</span></span> <span data-ttu-id="b209f-327">它设计为具有互操作性、可扩展性和通用性。</span><span class="sxs-lookup"><span data-stu-id="b209f-327">It’s designed to be interoperable, extensible, and generic.</span></span> <span data-ttu-id="b209f-328">该产品支持两种操作模式：</span><span class="sxs-lookup"><span data-stu-id="b209f-328">The product supports two modes of operation:</span></span>  
  
1.  <span data-ttu-id="b209f-329">托管：在此模式中，网络上有一个了解现有服务的实体，客户端可直接从该实体查询信息。</span><span class="sxs-lookup"><span data-stu-id="b209f-329">Managed: where there is an entity on the network knowledgeable about existing services, clients query it directly for information.</span></span> <span data-ttu-id="b209f-330">这与 Active Directory 类似。</span><span class="sxs-lookup"><span data-stu-id="b209f-330">This is analogous to Active Directory.</span></span>  
  
2.  <span data-ttu-id="b209f-331">临时：在此模式中，客户端使用多播消息来查找服务。</span><span class="sxs-lookup"><span data-stu-id="b209f-331">Ad-hoc: where clients use multicast messages to locate services.</span></span>  
  
 <span data-ttu-id="b209f-332">此外，发现消息是网络协议不可知的；可以对支持该模式要求的任何协议使用它们。</span><span class="sxs-lookup"><span data-stu-id="b209f-332">Furthermore, discovery messages are network protocol agnostic; you can use them on top any protocol that supports the mode requirements.</span></span> <span data-ttu-id="b209f-333">例如，发现可以通过 UDP 通道或支持多播消息的任何其他网络发送多播的消息。</span><span class="sxs-lookup"><span data-stu-id="b209f-333">For example, discovery multicast messages can be sent over the UDP channel or any other network that supports multicast messaging.</span></span>  <span data-ttu-id="b209f-334">这些设计点，灵活性结合在一起功能，允许你以适应特定于你的解决方案发现。</span><span class="sxs-lookup"><span data-stu-id="b209f-334">These design points, combined with feature flexibility, allow you to adapt the discovery specifically to your solution.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-335">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-335">Getting Started</span></span>  
  
-   <span data-ttu-id="b209f-336">文档： [WCF Discovery](../../../docs/framework/wcf/feature-details/wcf-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-336">Documentation: [WCF Discovery](../../../docs/framework/wcf/feature-details/wcf-discovery.md)</span></span>  
  
-   <span data-ttu-id="b209f-337">示例：[发现 （示例）](../../../docs/framework/wcf/samples/discovery-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-337">Samples: [Discovery (Samples)](../../../docs/framework/wcf/samples/discovery-samples.md)</span></span>  
  
### <a name="discovery-scenarios"></a><span data-ttu-id="b209f-338">Discovery 方案</span><span class="sxs-lookup"><span data-stu-id="b209f-338">Discovery Scenarios</span></span>  
 <span data-ttu-id="b209f-339">开发人员不希望对终结点进行硬编码，因为我的服务的可用时间未知。</span><span class="sxs-lookup"><span data-stu-id="b209f-339">A developer doesn't want to hard code endpoints, since it is unknown when my service will be available.</span></span> <span data-ttu-id="b209f-340">相反，开发人员希望在运行时选择服务。</span><span class="sxs-lookup"><span data-stu-id="b209f-340">Instead, the developer wants to choose a service at runtime.</span></span> <span data-ttu-id="b209f-341">应用程序的各个组件之间需要更大程度的分离、稳定性和自动配置。</span><span class="sxs-lookup"><span data-stu-id="b209f-341">More decoupling, robustness, and auto-configuration is needed between the components in the application.</span></span>  
  
## <a name="tracking"></a><span data-ttu-id="b209f-342">跟踪</span><span class="sxs-lookup"><span data-stu-id="b209f-342">Tracking</span></span>  
 <span data-ttu-id="b209f-343">工作流跟踪深入工作流实例的执行。</span><span class="sxs-lookup"><span data-stu-id="b209f-343">Workflow tracking provides insight into the execution of a workflow instance.</span></span>  <span data-ttu-id="b209f-344">从工作流实例级别的工作流的文件和流内的活动执行时发出的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="b209f-344">The tracking events are emitted from a workflow at the workflow instance level and when activities within the workflow execute.</span></span> <span data-ttu-id="b209f-345">需要将工作流跟踪参与者添加到工作流主机中以订阅跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="b209f-345">A workflow tracking participant needs to be added to the workflow host to subscribe to tracking records.</span></span> <span data-ttu-id="b209f-346">使用跟踪配置文件筛选跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="b209f-346">The tracking records are filtered using a tracking profile.</span></span> <span data-ttu-id="b209f-347">.NET Framework 提供了 ETW（Windows 事件跟踪）跟踪参与者，并在 machine.config 文件中安装了基本配置文件。</span><span class="sxs-lookup"><span data-stu-id="b209f-347">The .Net Framework provides an ETW (Event Tracing for Windows) tracking participant, and a basic profile is installed in the machine.config file.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-348">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-348">Getting Started</span></span>  
  
1.  <span data-ttu-id="b209f-349">在 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 中，创建一个 WCF 工作流服务应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="b209f-349">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="b209f-350"><xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 对将置于画布上以开始操作。</span><span class="sxs-lookup"><span data-stu-id="b209f-350">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas to start.</span></span>  
  
2.  <span data-ttu-id="b209f-351">打开 web.config 并添加一个无配置文件的 ETW 跟踪行为。</span><span class="sxs-lookup"><span data-stu-id="b209f-351">Open the web.config and add an ETW tracking behavior with no profile.</span></span>  
  
    1.  <span data-ttu-id="b209f-352">使用默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="b209f-352">The default profile is used.</span></span>  
  
    2.  <span data-ttu-id="b209f-353">打开事件查看器，并启用以下节点中的分析通道：**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b209f-353">Open event viewer and enable the analytic channel in the following node: **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="b209f-354">右键单击**分析**和选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="b209f-354">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
    3.  <span data-ttu-id="b209f-355">运行工作流服务。</span><span class="sxs-lookup"><span data-stu-id="b209f-355">Run the workflow service.</span></span>  
  
    4.  <span data-ttu-id="b209f-356">在事件查看器中观察工作流跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="b209f-356">Observe the workflow tracking events in event viewer.</span></span>  
  
3.  <span data-ttu-id="b209f-357">示例：[跟踪](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-357">Samples: [Tracking](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)</span></span>  
  
4.  <span data-ttu-id="b209f-358">概念文档：[工作流跟踪](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-358">Conceptual documentation: [Workflow Tracking and Tracing](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)</span></span>  
  
## <a name="sql-workflow-instance-store"></a><span data-ttu-id="b209f-359">SQL 工作流实例存储</span><span class="sxs-lookup"><span data-stu-id="b209f-359">SQL Workflow Instance Store</span></span>  
 <span data-ttu-id="b209f-360"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 是实例存储的基于 SQL Server 的实现。</span><span class="sxs-lookup"><span data-stu-id="b209f-360">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is a SQL Server-based implementation of an instance store.</span></span> <span data-ttu-id="b209f-361">实例存储将存储正在运行的实例的状态以及加载和恢复该实例所需的所有数据。</span><span class="sxs-lookup"><span data-stu-id="b209f-361">An instance store stores the state of a running instance together with all data necessary to load and resume that instance.</span></span> <span data-ttu-id="b209f-362">服务主机将在工作流仍存在时指示实例存储保存实例状态，并在该实例的消息到达或延迟活动过期时指示实例存储加载实例状态。</span><span class="sxs-lookup"><span data-stu-id="b209f-362">The service host instructs the instance store to save the instance state if the workflow persists, and it instructs the instance store to load the instance state when a message arrives for that instance or a delay activity expires.</span></span>  
  
### <a name="getting-started"></a><span data-ttu-id="b209f-363">入门</span><span class="sxs-lookup"><span data-stu-id="b209f-363">Getting Started</span></span>  
  
1.  <span data-ttu-id="b209f-364">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中，创建一个包含隐式或显式 <xref:System.Activities.Statements.Persist> 活动的工作流。</span><span class="sxs-lookup"><span data-stu-id="b209f-364">In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], create a Workflow that contains an implicit or explicit <xref:System.Activities.Statements.Persist> activity.</span></span> <span data-ttu-id="b209f-365">将 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 行为添加到工作流服务主机。</span><span class="sxs-lookup"><span data-stu-id="b209f-365">Add the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> behavior to your workflow service host.</span></span> <span data-ttu-id="b209f-366">这可以在代码或应用程序配置文件中完成。</span><span class="sxs-lookup"><span data-stu-id="b209f-366">This can be done in code or in the application configuration file.</span></span>  
  
2.  <span data-ttu-id="b209f-367">示例：[持久性](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)</span><span class="sxs-lookup"><span data-stu-id="b209f-367">Samples: [Persistence](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)</span></span>  
  
3.  <span data-ttu-id="b209f-368">概念文档： [SQL 工作流实例存储](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)。</span><span class="sxs-lookup"><span data-stu-id="b209f-368">Conceptual documentation: [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>
