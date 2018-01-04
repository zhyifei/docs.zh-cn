---
title: "排队消息处理疑难解答"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a35de5ea587ad77a13105442f0c47344638b611c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-queued-messaging"></a><span data-ttu-id="44715-102">排队消息处理疑难解答</span><span class="sxs-lookup"><span data-stu-id="44715-102">Troubleshooting Queued Messaging</span></span>
<span data-ttu-id="44715-103">本节包含在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中使用队列时出现的常见问题以及疑难解答帮助。</span><span class="sxs-lookup"><span data-stu-id="44715-103">This section contains common questions and troubleshooting help for using queues in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="common-questions"></a><span data-ttu-id="44715-104">常见问题</span><span class="sxs-lookup"><span data-stu-id="44715-104">Common Questions</span></span>  
 <span data-ttu-id="44715-105">**问：**我使用[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]Beta 1 并且安装了 MSMQ 修补程序。</span><span class="sxs-lookup"><span data-stu-id="44715-105">**Q:** I used [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Beta 1 and I installed the MSMQ hotfix.</span></span> <span data-ttu-id="44715-106">现在，是否需要移除此修补程序？</span><span class="sxs-lookup"><span data-stu-id="44715-106">Do I need to remove the hotfix?</span></span>  
  
 <span data-ttu-id="44715-107">**答：** 可以。</span><span class="sxs-lookup"><span data-stu-id="44715-107">**A:** Yes.</span></span> <span data-ttu-id="44715-108">此修补程序不再受支持。</span><span class="sxs-lookup"><span data-stu-id="44715-108">This hotfix is no longer supported.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="44715-109"> 无需修补程序便可以在 MSMQ 上工作。</span><span class="sxs-lookup"><span data-stu-id="44715-109"> now works on MSMQ without a hotfix requirement.</span></span>  
  
 <span data-ttu-id="44715-110">**问：**有以下两种 MSMQ 绑定：<xref:System.ServiceModel.NetMsmqBinding>和<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>。</span><span class="sxs-lookup"><span data-stu-id="44715-110">**Q:** There are two bindings for MSMQ: <xref:System.ServiceModel.NetMsmqBinding> and <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span> <span data-ttu-id="44715-111">我应该使用哪一种绑定以及在什么情况下使用？</span><span class="sxs-lookup"><span data-stu-id="44715-111">What should I use and when?</span></span>  
  
 <span data-ttu-id="44715-112">**答：**使用<xref:System.ServiceModel.NetMsmqBinding>如果想要将 MSMQ 用作传输用于两个之间的排队通信[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="44715-112">**A:** Use the <xref:System.ServiceModel.NetMsmqBinding> when you want to use MSMQ as a transport for queued communication between two [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span> <span data-ttu-id="44715-113">如果您想要使用现有的 MSMQ 应用程序与新的 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 应用程序进行通信，请使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="44715-113">Use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> when you want to use existing MSMQ applications to communicate with new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
 <span data-ttu-id="44715-114">**问：**我是否必须升级 MSMQ 才能使用<xref:System.ServiceModel.NetMsmqBinding>和`MsmqIntegration`绑定？</span><span class="sxs-lookup"><span data-stu-id="44715-114">**Q:** Do I have to upgrade MSMQ to use the <xref:System.ServiceModel.NetMsmqBinding> and `MsmqIntegration` bindings?</span></span>  
  
 <span data-ttu-id="44715-115">**答：** 否。</span><span class="sxs-lookup"><span data-stu-id="44715-115">**A:** No.</span></span> <span data-ttu-id="44715-116">在 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 和 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 中，这两种绑定都可以与 MSMQ 3.0 一起使用。</span><span class="sxs-lookup"><span data-stu-id="44715-116">Both bindings work with MSMQ 3.0 on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span> <span data-ttu-id="44715-117">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中，只有升级到 MSMQ 4.0，绑定的某些功能才可用。</span><span class="sxs-lookup"><span data-stu-id="44715-117">Certain features of the bindings become available when you upgrade to MSMQ 4.0 in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>  
  
 <span data-ttu-id="44715-118">**问：**的哪些功能<xref:System.ServiceModel.NetMsmqBinding>和<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>绑定是中可用 MSMQ 4.0 但 MSMQ 3.0 中不可用？</span><span class="sxs-lookup"><span data-stu-id="44715-118">**Q:** What features of the <xref:System.ServiceModel.NetMsmqBinding> and <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> bindings are available in MSMQ 4.0 but not in MSMQ 3.0?</span></span>  
  
 <span data-ttu-id="44715-119">**答：**以下功能均可在 MSMQ 4.0，但在 MSMQ 3.0 不中：</span><span class="sxs-lookup"><span data-stu-id="44715-119">**A:** The following features are available in MSMQ 4.0 but not in MSMQ 3.0:</span></span>  
  
-   <span data-ttu-id="44715-120">只有 MSMQ 4.0 才支持自定义死信队列。</span><span class="sxs-lookup"><span data-stu-id="44715-120">Custom dead-letter queue is supported only on MSMQ 4.0.</span></span>  
  
-   <span data-ttu-id="44715-121">MSMQ 3.0 和 MSMQ 4.0 处理病毒消息的方式不同。</span><span class="sxs-lookup"><span data-stu-id="44715-121">MSMQ 3.0 and 4.0 handle poison messages differently.</span></span>  
  
-   <span data-ttu-id="44715-122">只有 MSMQ 4.0 才支持远程事务处理读取。</span><span class="sxs-lookup"><span data-stu-id="44715-122">Only MSMQ 4.0 supports remote transacted read.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="44715-123">[Windows Vista、 Windows Server 2003 和 Windows XP 在排队功能方面的差异](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)。</span><span class="sxs-lookup"><span data-stu-id="44715-123"> [Differences in Queuing Features in Windows Vista, Windows Server 2003, and Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).</span></span>  
  
 <span data-ttu-id="44715-124">**问：**我能 MSMQ 3.0 上使用的排队的通信和 MSMQ 4.0 的另一端上的一侧？</span><span class="sxs-lookup"><span data-stu-id="44715-124">**Q:** Can I use MSMQ 3.0 on one side of a queued communication and MSMQ 4.0 on the other side?</span></span>  
  
 <span data-ttu-id="44715-125">**答：** 可以。</span><span class="sxs-lookup"><span data-stu-id="44715-125">**A:** Yes.</span></span>  
  
 <span data-ttu-id="44715-126">**问：**我想要将现有 MSMQ 应用程序集成使用 new[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端或服务器。</span><span class="sxs-lookup"><span data-stu-id="44715-126">**Q:** I want to integrate existing MSMQ applications with new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients or servers.</span></span> <span data-ttu-id="44715-127">是否需要升级两端的 MSMQ 基础结构？</span><span class="sxs-lookup"><span data-stu-id="44715-127">Do I need to upgrade both sides of my MSMQ infrastructure?</span></span>  
  
 <span data-ttu-id="44715-128">**答：** 否。</span><span class="sxs-lookup"><span data-stu-id="44715-128">**A:** No.</span></span> <span data-ttu-id="44715-129">您不必将任何一端升级到 MSMQ 4.0。</span><span class="sxs-lookup"><span data-stu-id="44715-129">You do not have to upgrade to MSMQ 4.0 on either side.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="44715-130">疑难解答</span><span class="sxs-lookup"><span data-stu-id="44715-130">Troubleshooting</span></span>  
 <span data-ttu-id="44715-131">此部分包含大多数常见疑难问题的答案。</span><span class="sxs-lookup"><span data-stu-id="44715-131">This section contains answers to most common troubleshooting issues.</span></span> <span data-ttu-id="44715-132">某些已知限制问题还将在发行说明中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="44715-132">Some issues that are known limitations are also described in the release notes.</span></span>  
  
 <span data-ttu-id="44715-133">**问：**我正尝试使用专有队列，并且获得以下异常： `System.InvalidOperationException`: URL 无效。</span><span class="sxs-lookup"><span data-stu-id="44715-133">**Q:** I am trying to use a private queue and I get the following exception: `System.InvalidOperationException`: The URL is invalid.</span></span> <span data-ttu-id="44715-134">队列的 URL 不能包含“$”字符。</span><span class="sxs-lookup"><span data-stu-id="44715-134">The URL for the queue cannot contain the '$' character.</span></span> <span data-ttu-id="44715-135">使用 net.msmq://machine/private/queueName 中的语法指定专有队列的地址。</span><span class="sxs-lookup"><span data-stu-id="44715-135">Use the syntax in net.msmq://machine/private/queueName to address a private queue.</span></span>  
  
 <span data-ttu-id="44715-136">**答：**请检查队列的统一资源标识符 (URI) 中配置和代码。</span><span class="sxs-lookup"><span data-stu-id="44715-136">**A:** Please check the queue Uniform Resource Identifier (URI) in your configuration and code.</span></span> <span data-ttu-id="44715-137">不要在 URI 中使用“$”字符。</span><span class="sxs-lookup"><span data-stu-id="44715-137">Do not use the "$" character in the URI.</span></span> <span data-ttu-id="44715-138">例如，若要为名为 OrdersQueue 的专有队列指定地址，可以将 URI 指定为 net.msmq://localhost/private/ordersQueue。</span><span class="sxs-lookup"><span data-stu-id="44715-138">For example, to address a private queue named OrdersQueue, specify the URI as net.msmq://localhost/private/ordersQueue.</span></span>  
  
 <span data-ttu-id="44715-139">**问：**调用`ServiceHost.Open()`我排队的应用程序将引发以下异常： `System.ArgumentException`： 基址中不能包含 URI 查询字符串。</span><span class="sxs-lookup"><span data-stu-id="44715-139">**Q:** Calling `ServiceHost.Open()` on my queued application throws the following exception: `System.ArgumentException`: A base address cannot contain a URI query string.</span></span> <span data-ttu-id="44715-140">为什么？</span><span class="sxs-lookup"><span data-stu-id="44715-140">Why?</span></span>  
  
 <span data-ttu-id="44715-141">**答：**检查配置文件中和在代码中的队列 URI。</span><span class="sxs-lookup"><span data-stu-id="44715-141">**A:** Check the queue URI in your configuration file and in your code.</span></span> <span data-ttu-id="44715-142">虽然 MSMQ 队列支持使用“?”字符，但 URI 将此字符解释为字符串查询的开头。</span><span class="sxs-lookup"><span data-stu-id="44715-142">While MSMQ queues support the use of the '?' character, URIs interpret this character as the beginning of a string query.</span></span> <span data-ttu-id="44715-143">若要避免此问题，请使用不包含“?”字符的队列名称。</span><span class="sxs-lookup"><span data-stu-id="44715-143">To avoid this issue, use queue names that do not contain '?' characters.</span></span>  
  
 <span data-ttu-id="44715-144">**问：**我发送成功但在接收方上调用任何服务操作。</span><span class="sxs-lookup"><span data-stu-id="44715-144">**Q:** My send succeeded but no service operation is invoked on the receiver.</span></span> <span data-ttu-id="44715-145">为什么？</span><span class="sxs-lookup"><span data-stu-id="44715-145">Why?</span></span>  
  
 <span data-ttu-id="44715-146">**答：**若要确定答案，完成以下清单：</span><span class="sxs-lookup"><span data-stu-id="44715-146">**A:** To determine the answer, work through the following check list:</span></span>  
  
-   <span data-ttu-id="44715-147">检查事务性队列需求是否与指定的保证相符。</span><span class="sxs-lookup"><span data-stu-id="44715-147">Check that the transactional queue requirements are compatible with the assurances specified.</span></span> <span data-ttu-id="44715-148">请注意下面的原则：</span><span class="sxs-lookup"><span data-stu-id="44715-148">Note the following principles:</span></span>  
  
    -   <span data-ttu-id="44715-149">你可以发送持久性消息 （数据报和会话） 具有"一次性"保证 (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) 只向事务性队列。</span><span class="sxs-lookup"><span data-stu-id="44715-149">You can send durable messages (datagrams and sessions) with "exactly once" assurances (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) only to a transactional queue.</span></span>  
  
    -   <span data-ttu-id="44715-150">可以发送只具有“一次性”保证的会话。</span><span class="sxs-lookup"><span data-stu-id="44715-150">You can send sessions only with "exactly once" assurances.</span></span>  
  
    -   <span data-ttu-id="44715-151">需要使用事务从事务性队列接收会话中的消息。</span><span class="sxs-lookup"><span data-stu-id="44715-151">A transaction is required to receive messages in a session from a transactional queue.</span></span>  
  
    -   <span data-ttu-id="44715-152">你可以发送或接收可变或持久性消息 （仅限于数据报） 无任何保证 (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) 只与非事务性队列。</span><span class="sxs-lookup"><span data-stu-id="44715-152">You can send or receive volatile or durable messages (datagrams only) with no assurances (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) only to a non-transactional queue.</span></span>  
  
-   <span data-ttu-id="44715-153">检查死信队列。</span><span class="sxs-lookup"><span data-stu-id="44715-153">Check the dead-letter queue.</span></span> <span data-ttu-id="44715-154">如果在此处找到消息，则确定没有传送这些消息的原因。</span><span class="sxs-lookup"><span data-stu-id="44715-154">If you find the messages there, determine why they were not delivered.</span></span>  
  
-   <span data-ttu-id="44715-155">检查传出队列的连通性或寻址问题。</span><span class="sxs-lookup"><span data-stu-id="44715-155">Check the outgoing queues for connectivity or addressing problems.</span></span>  
  
 <span data-ttu-id="44715-156">**问：**我已经指定了一个自定义的死信队列，但是当我启动发送方应用程序，收到异常，找不到死信队列，要么发送应用程序没有死信队列的权限。</span><span class="sxs-lookup"><span data-stu-id="44715-156">**Q:** I have specified a custom dead-letter queue, but when I start the sender application, I get an exception that either the dead-letter queue is not found, or the sending application has no permission to the dead-letter queue.</span></span> <span data-ttu-id="44715-157">为什么会出现这种情况？</span><span class="sxs-lookup"><span data-stu-id="44715-157">Why is this happening?</span></span>  
  
 <span data-ttu-id="44715-158">**答：**自定义死信队列 URI 必须包括"localhost"或计算机名中的第一个段，例如，net.msmq: //localhost/private/myappdead-letter 队列。</span><span class="sxs-lookup"><span data-stu-id="44715-158">**A:** The custom dead-letter queue URI must include a "localhost" or the computer name in the first segment, for example, net.msmq://localhost/private/myAppdead-letter queue.</span></span>  
  
 <span data-ttu-id="44715-159">**问：**不总是需要定义一个自定义的死信队列，或是否存在默认的死信队列？</span><span class="sxs-lookup"><span data-stu-id="44715-159">**Q:** Is it always necessary to define a custom dead-letter queue, or is there a default dead-letter queue?</span></span>  
  
 <span data-ttu-id="44715-160">**答：**如果保证为"一次性"(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`)，如果不指定自定义死信队列，默认值为系统级事务性死信队列。</span><span class="sxs-lookup"><span data-stu-id="44715-160">**A:** If assurances are "exactly once" (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`), and if you do not specify a custom dead-letter queue, the default is a system-wide transactional dead-letter queue.</span></span>  
  
 <span data-ttu-id="44715-161">如果保证为无 (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`)，则默认值是没有死信队列功能。</span><span class="sxs-lookup"><span data-stu-id="44715-161">If assurances are none (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), then the default is no dead-letter queue functionality.</span></span>  
  
 <span data-ttu-id="44715-162">**问：**我的服务引发异常，显示一条消息"EndpointListener 要求无法满足调用"。</span><span class="sxs-lookup"><span data-stu-id="44715-162">**Q:** My service throws on SvcHost.Open with a message "EndpointListener requirements cannot be met by the ListenerFactory".</span></span> <span data-ttu-id="44715-163">为什么？</span><span class="sxs-lookup"><span data-stu-id="44715-163">Why?</span></span>  
  
 <span data-ttu-id="44715-164">答：</span><span class="sxs-lookup"><span data-stu-id="44715-164">A.</span></span> <span data-ttu-id="44715-165">请检查您的服务协定。</span><span class="sxs-lookup"><span data-stu-id="44715-165">Check your service contract.</span></span> <span data-ttu-id="44715-166">你可能忘记将"IsOneWay =`true`"针对所有服务操作。</span><span class="sxs-lookup"><span data-stu-id="44715-166">You may have forgotten to put "IsOneWay=`true`" on all the service operations.</span></span> <span data-ttu-id="44715-167">队列仅支持单向服务操作。</span><span class="sxs-lookup"><span data-stu-id="44715-167">Queues support only one-way service operations.</span></span>  
  
 <span data-ttu-id="44715-168">**问：**队列中存在消息但是不调用任何服务操作。</span><span class="sxs-lookup"><span data-stu-id="44715-168">**Q:** There are messages in the queue but no service operation is invoked.</span></span> <span data-ttu-id="44715-169">有什么问题？</span><span class="sxs-lookup"><span data-stu-id="44715-169">What is the problem?</span></span>  
  
 <span data-ttu-id="44715-170">**答：**确定服务主机是否出现故障。</span><span class="sxs-lookup"><span data-stu-id="44715-170">**A:** Determine if your service host is faulted.</span></span> <span data-ttu-id="44715-171">可以通过查看跟踪情况或实现 `IErrorHandler` 进行检查。</span><span class="sxs-lookup"><span data-stu-id="44715-171">You can check by looking at the trace or implementing `IErrorHandler`.</span></span> <span data-ttu-id="44715-172">默认情况下，如果检测到病毒消息，则服务主机将出现故障。</span><span class="sxs-lookup"><span data-stu-id="44715-172">Service host faults, by default, if a poison message is detected.</span></span>  
  
 <span data-ttu-id="44715-173">**问：**队列中存在消息但是我 Web 承载的排队的服务并未激活。</span><span class="sxs-lookup"><span data-stu-id="44715-173">**Q:** There are messages in the queue but my Web-hosted queued service is not getting activated.</span></span> <span data-ttu-id="44715-174">为什么？</span><span class="sxs-lookup"><span data-stu-id="44715-174">Why?</span></span>  
  
 <span data-ttu-id="44715-175">**答：**最常见原因是权限。</span><span class="sxs-lookup"><span data-stu-id="44715-175">**A:** The most common reason is permissions.</span></span>  
  
1.  <span data-ttu-id="44715-176">确保 `NetMsmqActivator` 进程正在运行，并为 `NetMsmqActivator` 进程的标识提供对此队列的读取和查找权限。</span><span class="sxs-lookup"><span data-stu-id="44715-176">Ensure that the `NetMsmqActivator` process is running and the identity of the `NetMsmqActivator` process is given read and seek permission on the queue.</span></span>  
  
2.  <span data-ttu-id="44715-177">如果 `NetMsmqActivator` 正在监视远程计算机上的队列，请确保 `NetMsmqActivator` 不使用受限制的令牌运行。</span><span class="sxs-lookup"><span data-stu-id="44715-177">If the `NetMsmqActivator` is monitoring queues on a remote machine, ensure that `NetMsmqActivator` does not run under a restricted token.</span></span> <span data-ttu-id="44715-178">若要使用不受限制的令牌运行 `NetMsmqActivator`，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="44715-178">To run the `NetMsmqActivator` with an unrestricted token:</span></span>  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 <span data-ttu-id="44715-179">有关与安全相关的 Web 主机问题，请参阅：[承载排队应用程序的 Web](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)。</span><span class="sxs-lookup"><span data-stu-id="44715-179">For non-security related Web host issues refer to: [Web Hosting a Queued Application](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).</span></span>  
  
 <span data-ttu-id="44715-180">**问：**到访问会话的最简单方法是什么？</span><span class="sxs-lookup"><span data-stu-id="44715-180">**Q:** What is the easiest way to access sessions?</span></span>  
  
 <span data-ttu-id="44715-181">**答：**设置 AutoComplete =`true`对应到最后一个操作消息在会话中，然后设置 AutoComplete =`false`针对所有其余服务操作。</span><span class="sxs-lookup"><span data-stu-id="44715-181">**A:** Set AutoComplete=`true` on the operation that corresponds to the last message in the session, and set AutoComplete=`false` on all remaining service operations.</span></span>  
  
 <span data-ttu-id="44715-182">**问：**哪里可以找到常见问题的答案在 MSMQ 上？</span><span class="sxs-lookup"><span data-stu-id="44715-182">**Q:** Where can I find answers to common questions on MSMQ?</span></span>  
  
 <span data-ttu-id="44715-183">**答：** [!INCLUDE[crabout](../../../../includes/crabout-md.md)] MSMQ，请参阅[Microsoft 消息队列](http://go.microsoft.com/fwlink/?LinkId=87810)。</span><span class="sxs-lookup"><span data-stu-id="44715-183">**A:** [!INCLUDE[crabout](../../../../includes/crabout-md.md)] MSMQ, see [Microsoft Message Queuing](http://go.microsoft.com/fwlink/?LinkId=87810).</span></span>  
  
 <span data-ttu-id="44715-184">**问：**我的服务是为什么引发`ProtocolException`时从同时包含队列中的读取排队会话消息和排队数据报消息？</span><span class="sxs-lookup"><span data-stu-id="44715-184">**Q:** Why does my service throw a `ProtocolException` when reading from a queue that contains both queued session messages and queued datagram messages?</span></span>  
  
 <span data-ttu-id="44715-185">**答：**没有本质上的区别方式排队的会话消息和排队数据报消息的构成。</span><span class="sxs-lookup"><span data-stu-id="44715-185">**A:** There is a fundamental difference in the way queued session messages and queued datagram messages are composed.</span></span> <span data-ttu-id="44715-186">因此，要读取排队会话消息的服务无法接收排队数据报消息，而要读取排队数据报消息的服务也无法接收会话消息。</span><span class="sxs-lookup"><span data-stu-id="44715-186">Because of this, a service that is expecting to read a queued session message cannot receive a queued datagram message and a service expecting to read a queued datagram message cannot receive a session message.</span></span> <span data-ttu-id="44715-187">试图从同一个队列读取这两种消息时将引发以下异常：</span><span class="sxs-lookup"><span data-stu-id="44715-187">Attempting to read both types of messages from the same queue throws the following exception:</span></span>  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 <span data-ttu-id="44715-188">当应用程序从同一台计算机既发送排队会话消息又发送排队数据报消息时，系统死信队列以及任何自定义死信队列对这种问题尤其敏感。</span><span class="sxs-lookup"><span data-stu-id="44715-188">The system dead-letter queue, as well as any custom dead-letter queue, is particularly susceptible to this issue if an application sends both queued session messages and queued datagram messages from the same computer.</span></span> <span data-ttu-id="44715-189">如果消息无法成功发送，则会被移入死信队列。</span><span class="sxs-lookup"><span data-stu-id="44715-189">If a message cannot be sent successfully, it is moved to the dead-letter queue.</span></span> <span data-ttu-id="44715-190">在这些情况下，很有可能将会话消息和数据报消息都移入死信队列。</span><span class="sxs-lookup"><span data-stu-id="44715-190">Under these circumstances, it is possible to have both session and datagram messages in the dead-letter queue.</span></span> <span data-ttu-id="44715-191">从队列进行读取时，无法在运行时将两种消息分开。因此，应用程序不应从同一台计算机既发送排队会话消息又发送排队数据报消息。</span><span class="sxs-lookup"><span data-stu-id="44715-191">There is no way to separate both types of messages at runtime when reading from a queue, therefore, applications should not send both queued session messages and queued datagram messages from the same computer.</span></span>  
  
### <a name="msmq-integration-specific-troubleshooting"></a><span data-ttu-id="44715-192">MSMQ 集成：特定的疑难解答</span><span class="sxs-lookup"><span data-stu-id="44715-192">MSMQ Integration: Specific Troubleshooting</span></span>  
 <span data-ttu-id="44715-193">**问：**发送一条消息，或打开服务主机时，系统报错，指示方案有误。</span><span class="sxs-lookup"><span data-stu-id="44715-193">**Q:** When I send a message, or when I open the service host, I get an error that indicates the scheme is wrong.</span></span> <span data-ttu-id="44715-194">为什么？</span><span class="sxs-lookup"><span data-stu-id="44715-194">Why?</span></span>  
  
 <span data-ttu-id="44715-195">**答：**当你使用 MSMQ 集成绑定时，必须使用 msmq.formatname 方案。</span><span class="sxs-lookup"><span data-stu-id="44715-195">**A:** When you use the MSMQ integration binding, you must use the msmq.formatname scheme.</span></span> <span data-ttu-id="44715-196">例如，msmq.formatname:DIRECT=OS:.\private$\OrdersQueue。</span><span class="sxs-lookup"><span data-stu-id="44715-196">For example, msmq.formatname:DIRECT=OS:.\private$\OrdersQueue.</span></span> <span data-ttu-id="44715-197">但是，如果您指定自定义死信队列，则必须使用 net.msmq 方案。</span><span class="sxs-lookup"><span data-stu-id="44715-197">But when you specify the custom dead-letter queue, you must use the net.msmq scheme.</span></span>  
  
 <span data-ttu-id="44715-198">**问：**时我可使用公共或专用格式名并将其上打开服务主机[!INCLUDE[wv](../../../../includes/wv-md.md)]，出现错误。</span><span class="sxs-lookup"><span data-stu-id="44715-198">**Q:** When I use a public or private format name and open the service host on [!INCLUDE[wv](../../../../includes/wv-md.md)], I get an error.</span></span> <span data-ttu-id="44715-199">为什么？</span><span class="sxs-lookup"><span data-stu-id="44715-199">Why?</span></span>  
  
 <span data-ttu-id="44715-200">**答：** [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]集成通道上的[!INCLUDE[wv](../../../../includes/wv-md.md)]检查以确定是否子队列可以打开以处理病毒消息的主应用程序队列进行。</span><span class="sxs-lookup"><span data-stu-id="44715-200">**A:** The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] integration channel on [!INCLUDE[wv](../../../../includes/wv-md.md)] checks to see if a sub-queue can be opened for the main application queue for handling poison messages.</span></span> <span data-ttu-id="44715-201">子队列名称派生自传递到侦听器的 msmq.formatname URI。</span><span class="sxs-lookup"><span data-stu-id="44715-201">The sub-queue name is derived from an msmq.formatname URI passed to the listener.</span></span> <span data-ttu-id="44715-202">MSMQ 中的子队列名只能是直接格式名。</span><span class="sxs-lookup"><span data-stu-id="44715-202">The sub-queue name in MSMQ can only be a direct format name.</span></span> <span data-ttu-id="44715-203">因此，您会发现以上错误。</span><span class="sxs-lookup"><span data-stu-id="44715-203">So you see the error.</span></span> <span data-ttu-id="44715-204">将队列 URI 改为直接格式名。</span><span class="sxs-lookup"><span data-stu-id="44715-204">Change the queue URI to a direct format name.</span></span>  
  
 <span data-ttu-id="44715-205">**问：**时从 MSMQ 应用程序接收消息，该消息滞留在队列，并不由接收读取[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="44715-205">**Q:** When receiving a message from an MSMQ application, the message sits in the queue and is not read by the receiving [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="44715-206">为什么？</span><span class="sxs-lookup"><span data-stu-id="44715-206">Why?</span></span>  
  
 <span data-ttu-id="44715-207">**答：**检查消息是否有正文。</span><span class="sxs-lookup"><span data-stu-id="44715-207">**A:** Check to see whether the message has a body.</span></span> <span data-ttu-id="44715-208">如果消息没有正文，则 MSMQ 集成通道会忽略此消息。</span><span class="sxs-lookup"><span data-stu-id="44715-208">If the message has no body, the MSMQ integration channel ignores the message.</span></span> <span data-ttu-id="44715-209">实现向其通知异常的 `IErrorHandler` 并检查跟踪情况。</span><span class="sxs-lookup"><span data-stu-id="44715-209">Implement `IErrorHandler` to be notified of exceptions and check the traces.</span></span>  
  
### <a name="security-related-troubleshooting"></a><span data-ttu-id="44715-210">与安全相关的疑难解答</span><span class="sxs-lookup"><span data-stu-id="44715-210">Security-Related Troubleshooting</span></span>  
 <span data-ttu-id="44715-211">**问：**时运行以工作组模式使用默认绑定的示例，消息好像已发送但接收方从未收到。</span><span class="sxs-lookup"><span data-stu-id="44715-211">**Q:** When I run the sample that uses a default binding in workgroup mode, messages seem to get sent but are never received by the receiver.</span></span>  
  
 <span data-ttu-id="44715-212">**答：**默认情况下，消息进行签名使用 MSMQ 内部证书需要 Active Directory 目录服务。</span><span class="sxs-lookup"><span data-stu-id="44715-212">**A:** By default, messages are signed using an MSMQ internal certificate that requires the Active Directory directory service.</span></span> <span data-ttu-id="44715-213">在工作组模式下，因为 Active Directory 不可用，所以对消息的签名会失败。</span><span class="sxs-lookup"><span data-stu-id="44715-213">In workgroup mode, because Active Directory is not available, signing the message fails.</span></span> <span data-ttu-id="44715-214">因此，消息便进入死信队列，并指示失败原因，诸如"签名错误"。</span><span class="sxs-lookup"><span data-stu-id="44715-214">So the message lands in the dead-letter queue and failure cause, such as "Bad signature", is indicated.</span></span>  
  
 <span data-ttu-id="44715-215">解决方法是关闭安全性。</span><span class="sxs-lookup"><span data-stu-id="44715-215">The workaround is to turn off security.</span></span> <span data-ttu-id="44715-216">这可通过设置<xref:System.ServiceModel.NetMsmqSecurity.Mode%2A>  =  <xref:System.ServiceModel.NetMsmqSecurityMode.None>以使其在工作组模式下工作。</span><span class="sxs-lookup"><span data-stu-id="44715-216">This is done by setting <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A> = <xref:System.ServiceModel.NetMsmqSecurityMode.None> to make it work in workgroup mode.</span></span>  
  
 <span data-ttu-id="44715-217">另一个解决方法是从 <xref:System.ServiceModel.MsmqTransportSecurity> 属性获取 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> 并将其设置为 <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>，然后设置客户端证书。</span><span class="sxs-lookup"><span data-stu-id="44715-217">Another workaround is to get the <xref:System.ServiceModel.MsmqTransportSecurity> from the <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> property and set it to <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>, and set the client certificate.</span></span>  
  
 <span data-ttu-id="44715-218">还有一种解决方法就是安装集成了 Active Directory 的 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="44715-218">Yet another workaround is to install MSMQ with Active Directory integration.</span></span>  
  
 <span data-ttu-id="44715-219">**问：**当消息发送具有默认绑定 （传输安全处于打开状态） 到队列的 Active Directory 中收到"找不到内部证书"消息。</span><span class="sxs-lookup"><span data-stu-id="44715-219">**Q:** When I send a message with default binding (transport security turned on) in Active Directory to a queue, I get an "internal certificate not found" message.</span></span> <span data-ttu-id="44715-220">如何修复此问题？</span><span class="sxs-lookup"><span data-stu-id="44715-220">How do I fix this?</span></span>  
  
 <span data-ttu-id="44715-221">**答：**这意味着必须续订发送方在 Active Directory 中的证书。</span><span class="sxs-lookup"><span data-stu-id="44715-221">**A:** This means that the certificate in Active Directory for the sender must be renewed.</span></span> <span data-ttu-id="44715-222">为此，请打开**控制面板**，**管理工具**，**计算机管理**，右键单击**MSMQ**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="44715-222">To do so, open **Control Panel**, **Administrative Tools**, **Computer Management**, right-click **MSMQ**, and select **Properties**.</span></span> <span data-ttu-id="44715-223">选择**用户证书**选项卡，单击**续订**按钮。</span><span class="sxs-lookup"><span data-stu-id="44715-223">Select the **User Certificate** tab and click the **Renew** button.</span></span>  
  
 <span data-ttu-id="44715-224">**问：**时发送消息使用<xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>，并且指定要使用的证书，我遇到"证书无效"消息。</span><span class="sxs-lookup"><span data-stu-id="44715-224">**Q:** When I send a message using <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> and specify the certificate to use, I get an "Invalid certificate" message.</span></span> <span data-ttu-id="44715-225">如何修复此问题？</span><span class="sxs-lookup"><span data-stu-id="44715-225">How do I fix this?</span></span>  
  
 <span data-ttu-id="44715-226">**答：**不能与本地计算机证书存储区使用证书模式。</span><span class="sxs-lookup"><span data-stu-id="44715-226">**A:** You cannot use a local machine certificate store with certificate mode.</span></span> <span data-ttu-id="44715-227">必须使用证书管理单元将证书从计算机证书存储区复制到当前用户存储区。</span><span class="sxs-lookup"><span data-stu-id="44715-227">You have to copy the certificate from the machine certificate store to the current user store using the Certificate snap-in.</span></span> <span data-ttu-id="44715-228">若要打开证书管理单元，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="44715-228">To get the Certificate snap-in:</span></span>  
  
1.  <span data-ttu-id="44715-229">单击**启动**，选择**运行**，类型`mmc`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="44715-229">Click **Start**, select **Run**, type `mmc`, and click **OK**.</span></span>  
  
2.  <span data-ttu-id="44715-230">在**Microsoft 管理控制台**，打开**文件**菜单，然后选择**添加/删除管理单元中**。</span><span class="sxs-lookup"><span data-stu-id="44715-230">In the **Microsoft Management Console**, open the **File** menu and select **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="44715-231">在**添加/删除管理单元中**对话框中，单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="44715-231">In the **Add/Remove Snap-in** dialog box, click the **Add** button.</span></span>  
  
4.  <span data-ttu-id="44715-232">在**添加独立管理单元中**对话框中，选择证书，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="44715-232">In the **Add Standalone Snap-in** dialog box, select Certificates and click **Add**.</span></span>  
  
5.  <span data-ttu-id="44715-233">在**证书**管理单元对话框中，选择**我的用户帐户，**单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="44715-233">In the **Certificates** snap-in dialog box, select **My user account,** and click **Finish**.</span></span>  
  
6.  <span data-ttu-id="44715-234">接下来，添加第二个证书管理单元使用前面的步骤，但这次请选择**计算机帐户**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="44715-234">Next, add a second Certificates snap-in using the previous steps, but this time select **Computer account** and click **Next**.</span></span>  
  
7.  <span data-ttu-id="44715-235">选择**本地计算机**单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="44715-235">Select **Local Computer** and click **Finish**.</span></span> <span data-ttu-id="44715-236">现在，可以将证书从计算机证书存储区拖放到当前用户存储区。</span><span class="sxs-lookup"><span data-stu-id="44715-236">You can now drag and drop certificates from the machine certificate store to the current user store.</span></span>  
  
 <span data-ttu-id="44715-237">**问：**时我的服务从队列中读取在工作组模式下，另一台计算机上收到"拒绝访问"异常。</span><span class="sxs-lookup"><span data-stu-id="44715-237">**Q:** When my service reads from a queue on another computer in workgroup mode, I get an "access denied" exception.</span></span>  
  
 <span data-ttu-id="44715-238">**答：**在工作组模式下，远程应用程序以访问队列，应用程序必须有权访问队列。</span><span class="sxs-lookup"><span data-stu-id="44715-238">**A:** In workgroup mode, for a remote application to gain access to the queue, the application must have permission to access the queue.</span></span> <span data-ttu-id="44715-239">将"匿名登录"添加到队列的访问控制列表 (ACL)，并授予其读权限。</span><span class="sxs-lookup"><span data-stu-id="44715-239">Add "Anonymous login" to the queue's access control list (ACL) and give it read permission.</span></span>  
  
 <span data-ttu-id="44715-240">**问：**发送时的网络服务客户端 （或没有域帐户的任何客户端） 发送排队的消息时，使用无效证书失败。</span><span class="sxs-lookup"><span data-stu-id="44715-240">**Q:** When a network service client (or any client that does not have a domain account) sends a queued message, the send fails with an invalid certificate.</span></span> <span data-ttu-id="44715-241">如何修复此问题？</span><span class="sxs-lookup"><span data-stu-id="44715-241">How do I fix this?</span></span>  
  
 <span data-ttu-id="44715-242">**答：**检查绑定配置。</span><span class="sxs-lookup"><span data-stu-id="44715-242">**A:** Check the binding configuration.</span></span> <span data-ttu-id="44715-243">默认绑定会打开 MSMQ 传输安全以对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="44715-243">The default binding has MSMQ transport security turned on to sign the message.</span></span> <span data-ttu-id="44715-244">关闭该传输安全。</span><span class="sxs-lookup"><span data-stu-id="44715-244">Turn it off.</span></span>  
  
### <a name="remote-transacted-receives"></a><span data-ttu-id="44715-245">远程事务处理接收</span><span class="sxs-lookup"><span data-stu-id="44715-245">Remote Transacted Receives</span></span>  
 <span data-ttu-id="44715-246">**问：**如果我有计算机 A 上的队列和一个[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]读取不从队列中读取的 B （远程事务处理接收方案），消息的计算机上的队列的消息的服务。</span><span class="sxs-lookup"><span data-stu-id="44715-246">**Q:** When I have a queue on machine A, and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that reads messages from a queue on machine B (the remote transacted receive scenario), messages are not read from the queue.</span></span> <span data-ttu-id="44715-247">跟踪信息指示接收失败，出现消息"无法导入事务。"</span><span class="sxs-lookup"><span data-stu-id="44715-247">Tracing information indicates the receive failed with the message "Transaction cannot be imported."</span></span> <span data-ttu-id="44715-248">若要解决此问题，我该做什么？</span><span class="sxs-lookup"><span data-stu-id="44715-248">What can I do to fix this?</span></span>  
  
 <span data-ttu-id="44715-249">**答：**有三个可能的原因：</span><span class="sxs-lookup"><span data-stu-id="44715-249">**A:** There are three possible reasons for this:</span></span>  
  
-   <span data-ttu-id="44715-250">如果处于域模式下，则远程事务处理接收要求 Microsoft 分布式事务协调器 (MSDTC) 网络访问。</span><span class="sxs-lookup"><span data-stu-id="44715-250">If you are in domain mode, remote transacted receive requires Microsoft Distributed Transaction Coordinator (MSDTC) network access.</span></span> <span data-ttu-id="44715-251">你可以启用此使用**添加/删除组件**。</span><span class="sxs-lookup"><span data-stu-id="44715-251">You can enable this using **Add/Remove Components**.</span></span>  
  
     <span data-ttu-id="44715-252">![启用网络 DTC 访问](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")</span><span class="sxs-lookup"><span data-stu-id="44715-252">![Enabling network DTC access](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")</span></span>  
  
-   <span data-ttu-id="44715-253">检查与事务管理器进行通信的身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="44715-253">Check the authentication mode for communicating with the transaction manager.</span></span> <span data-ttu-id="44715-254">如果要在工作组模式下，必须选择"不要求身份验证"。</span><span class="sxs-lookup"><span data-stu-id="44715-254">If you are in workgroup mode, "No Authentication Required" must be selected.</span></span> <span data-ttu-id="44715-255">如果处于域模式下时，必须选择"要求相互身份验证"。</span><span class="sxs-lookup"><span data-stu-id="44715-255">If you are in domain mode, then "Mutual Authentication Required" must be selected.</span></span>  
  
     <span data-ttu-id="44715-256">![启用 XA 事务](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")</span><span class="sxs-lookup"><span data-stu-id="44715-256">![Enabling XA transactions](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")</span></span>  
  
-   <span data-ttu-id="44715-257">请确保 MSDTC 在例外列表中的**Internet 连接防火墙**设置。</span><span class="sxs-lookup"><span data-stu-id="44715-257">Make sure that MSDTC is in the list of exceptions in the **Internet Connection Firewall** settings.</span></span>  
  
-   <span data-ttu-id="44715-258">确保您使用的是 [!INCLUDE[wv](../../../../includes/wv-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="44715-258">Ensure that you are using [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="44715-259">[!INCLUDE[wv](../../../../includes/wv-md.md)] 上的 MSMQ 支持远程事务处理读取。</span><span class="sxs-lookup"><span data-stu-id="44715-259">MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)] supports remote transacted read.</span></span> <span data-ttu-id="44715-260">早期的 Windows 版本上的 MSMQ 不支持远程事务处理读取。</span><span class="sxs-lookup"><span data-stu-id="44715-260">MSMQ on earlier Windows releases does not support remote transacted read.</span></span>  
  
 <span data-ttu-id="44715-261">**问：**时从队列中读取的服务帐户是 network service，例如，Web 宿主中，为什么收到拒绝访问异常引发时从队列中读取？</span><span class="sxs-lookup"><span data-stu-id="44715-261">**Q:** When the service reading from the queue is a network service, for example, in a Web host, why do I get an access-denied exception is raised when reading from the queue?</span></span>  
  
 <span data-ttu-id="44715-262">**答：**必须将网络服务读访问权限添加到队列 ACL 以确保网络服务可以从队列中读取。</span><span class="sxs-lookup"><span data-stu-id="44715-262">**A:** Network service read access must be added to the queue ACL to ensure that a network service can read from the queue.</span></span>  
  
 <span data-ttu-id="44715-263">**问：**我可以使用 MSMQ 激活服务激活基于远程计算机上的一个队列中消息的应用程序？</span><span class="sxs-lookup"><span data-stu-id="44715-263">**Q:** Can I use the MSMQ activation service to activate applications based on messages in a queue on a remote machine?</span></span>  
  
 <span data-ttu-id="44715-264">**答：** 可以。</span><span class="sxs-lookup"><span data-stu-id="44715-264">**A:** Yes.</span></span> <span data-ttu-id="44715-265">为此，您必须将 MSMQ 激活服务配置为以网络服务方式运行，并将网络服务访问权限添加到远程计算机上的队列中。</span><span class="sxs-lookup"><span data-stu-id="44715-265">To do this, you must configure the MSMQ activation service to run as a network service, and add network service access to the queue on the remote machine.</span></span>  
  
## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a><span data-ttu-id="44715-266">使用已启用 ReceiveContext 的自定义 MSMQ 绑定</span><span class="sxs-lookup"><span data-stu-id="44715-266">Using Custom MSMQ Bindings with ReceiveContext Enabled</span></span>  
 <span data-ttu-id="44715-267">当将自定义 MSMQ 绑定用于已启用 <xref:System.ServiceModel.Channels.ReceiveContext> 的处理时，传入消息将使用一个线程池线程，这是因为本机 MSMQ 不支持异步 <xref:System.ServiceModel.Channels.ReceiveContext> 接收的 I/O 完成。</span><span class="sxs-lookup"><span data-stu-id="44715-267">When using a custom MSMQ binding with <xref:System.ServiceModel.Channels.ReceiveContext> enabled processing an incoming message will use a thread pool thread because native MSMQ does not support I/O completion for asynchronous <xref:System.ServiceModel.Channels.ReceiveContext> receives.</span></span> <span data-ttu-id="44715-268">这是因为处理此类消息需使用 <xref:System.ServiceModel.Channels.ReceiveContext> 的内部事务，并且 MSMQ 不支持异步处理。</span><span class="sxs-lookup"><span data-stu-id="44715-268">This is because processing such a message uses internal transactions for <xref:System.ServiceModel.Channels.ReceiveContext> and MSMQ does not support asynchronous processing.</span></span> <span data-ttu-id="44715-269">若要解决此问题，可将 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> 添加到终结点以强制进行同步处理或将 <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> 设置为 1。</span><span class="sxs-lookup"><span data-stu-id="44715-269">To work around this issue you can add a <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> to the endpoint to force synchronous processing or set <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> to 1.</span></span>
