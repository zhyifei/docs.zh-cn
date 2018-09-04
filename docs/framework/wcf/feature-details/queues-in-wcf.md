---
title: Windows Communication Foundation 中的队列
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
ms.openlocfilehash: 46d70a0b0ccc33755666867240be8778b5638947
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43537795"
---
# <a name="queues-in-windows-communication-foundation"></a><span data-ttu-id="a20b0-102">Windows Communication Foundation 中的队列</span><span class="sxs-lookup"><span data-stu-id="a20b0-102">Queues in Windows Communication Foundation</span></span>
<span data-ttu-id="a20b0-103">在本部分中的主题讨论对队列的 Windows Communication Foundation (WCF) 支持。</span><span class="sxs-lookup"><span data-stu-id="a20b0-103">The topics in this section discuss Windows Communication Foundation (WCF) support for queues.</span></span> <span data-ttu-id="a20b0-104">WCF 利用 Microsoft 消息队列 （以前称为 MSMQ） 作为传输机制来提供支持，并支持以下方案：</span><span class="sxs-lookup"><span data-stu-id="a20b0-104">WCF provides support for queuing by leveraging Microsoft Message Queuing (previously known as MSMQ) as a transport and enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="a20b0-105">松耦合应用程序。</span><span class="sxs-lookup"><span data-stu-id="a20b0-105">Loosely coupled applications.</span></span> <span data-ttu-id="a20b0-106">发送应用程序可以将消息发送到队列，而无需知道接收应用程序是否可用于处理该消息。</span><span class="sxs-lookup"><span data-stu-id="a20b0-106">Sending applications can send messages to queues without needing to know whether the receiving application is available to process the message.</span></span> <span data-ttu-id="a20b0-107">队列提供了处理独立性，它允许发送应用程序将消息以一定的速率发送到队列，该速率不依赖于接收应用程序的消息处理速度。</span><span class="sxs-lookup"><span data-stu-id="a20b0-107">The queue provides processing independence that allows a sending application to send messages to the queue at a rate that does not depend on how fast the receiving applications can process the messages.</span></span> <span data-ttu-id="a20b0-108">如果向队列发送消息的操作与消息处理的操作不是紧密耦合的，则会提高系统的整体可用性。</span><span class="sxs-lookup"><span data-stu-id="a20b0-108">Overall system availability increases when sending messages to a queue is not tightly coupled to message processing.</span></span>  
  
-   <span data-ttu-id="a20b0-109">故障隔离。</span><span class="sxs-lookup"><span data-stu-id="a20b0-109">Failure isolation.</span></span> <span data-ttu-id="a20b0-110">应用程序与队列之间发送或接收消息如果失败，两种操作互不影响。</span><span class="sxs-lookup"><span data-stu-id="a20b0-110">Applications sending or receiving messages to a queue can fail without affecting each other.</span></span> <span data-ttu-id="a20b0-111">例如，如果接收应用程序失败，发送应用程序可以继续向队列发送消息。</span><span class="sxs-lookup"><span data-stu-id="a20b0-111">If, for example, the receiving application fails, the sending application can continue to send messages to the queue.</span></span> <span data-ttu-id="a20b0-112">接收方再次启动时，即可处理队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="a20b0-112">When the receiver is up again, it can process the messages from the queue.</span></span> <span data-ttu-id="a20b0-113">故障隔离提高了整体系统的可靠性和可用性。</span><span class="sxs-lookup"><span data-stu-id="a20b0-113">Failure isolation increases the overall system reliability and availability.</span></span>  
  
-   <span data-ttu-id="a20b0-114">负载调节。</span><span class="sxs-lookup"><span data-stu-id="a20b0-114">Load leveling.</span></span> <span data-ttu-id="a20b0-115">发送应用程序发出的消息可能使接收应用程序过载。</span><span class="sxs-lookup"><span data-stu-id="a20b0-115">Sending applications can overwhelm receiving applications with messages.</span></span> <span data-ttu-id="a20b0-116">队列可以管理不匹配的消息生成率和处理率，以使接收方不会过载。</span><span class="sxs-lookup"><span data-stu-id="a20b0-116">Queues can manage mismatched message production and consumption rates so that a receiver is not overwhelmed.</span></span>  
  
-   <span data-ttu-id="a20b0-117">断开连接的操作。</span><span class="sxs-lookup"><span data-stu-id="a20b0-117">Disconnected operations.</span></span> <span data-ttu-id="a20b0-118">在高延迟网络或有限可用性网络上通信（例如，在移动设备中）时，发送、接收和处理操作可能会断开连接。</span><span class="sxs-lookup"><span data-stu-id="a20b0-118">Sending, receiving, and processing operations can become disconnected when communicating over high-latency networks or limited-availability networks, such as in the case of mobile devices.</span></span> <span data-ttu-id="a20b0-119">队列允许这些操作继续执行，即使终结点断开连接也是如此。</span><span class="sxs-lookup"><span data-stu-id="a20b0-119">Queues allow these operations to continue, even when the endpoints are disconnected.</span></span> <span data-ttu-id="a20b0-120">重新建立连接后，队列将消息转发到接收应用程序。</span><span class="sxs-lookup"><span data-stu-id="a20b0-120">When the connection is reestablished, the queue forwards messages to the receiving application.</span></span>  
  
 <span data-ttu-id="a20b0-121">若要在 WCF 应用程序中使用队列功能，可以使用一个标准绑定，或如果标准绑定之一不满足你的要求，可以创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="a20b0-121">To use the queues feature in a WCF application, you can use one of the standard bindings, or you can create a custom binding if one of the standard bindings does not satisfy your requirements.</span></span> <span data-ttu-id="a20b0-122">有关相关标准绑定和如何进行选择的详细信息，请参阅[如何： 使用 WCF 终结点和消息队列应用程序交换消息](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="a20b0-122">For more information about relevant standard bindings and how to choose one, see [How to: Exchange Messages with WCF Endpoints and Message Queuing Applications](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md).</span></span> <span data-ttu-id="a20b0-123">有关创建自定义绑定的详细信息，请参阅[自定义绑定](../../../../docs/framework/wcf/extending/custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="a20b0-123">For more information about creating custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a20b0-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="a20b0-124">In This Section</span></span>  
 [<span data-ttu-id="a20b0-125">队列概述</span><span class="sxs-lookup"><span data-stu-id="a20b0-125">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 <span data-ttu-id="a20b0-126">消息队列概念概述。</span><span class="sxs-lookup"><span data-stu-id="a20b0-126">An overview of message queuing concepts.</span></span>  
  
 [<span data-ttu-id="a20b0-127">在 WCF 中排队</span><span class="sxs-lookup"><span data-stu-id="a20b0-127">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 <span data-ttu-id="a20b0-128">WCF 队列支持的概述。</span><span class="sxs-lookup"><span data-stu-id="a20b0-128">An overview of WCF queue support.</span></span>  
  
 [<span data-ttu-id="a20b0-129">如何：使用 WCF 终结点交换排队消息</span><span class="sxs-lookup"><span data-stu-id="a20b0-129">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 <span data-ttu-id="a20b0-130">说明如何使用<xref:System.ServiceModel.NetMsmqBinding>类 WCF 客户端和 WCF 服务之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="a20b0-130">Explains how to use the <xref:System.ServiceModel.NetMsmqBinding> class to communicate between a WCF client and WCF service.</span></span>  
  
 [<span data-ttu-id="a20b0-131">如何：与 WCF 终结点和消息队列应用程序交换消息</span><span class="sxs-lookup"><span data-stu-id="a20b0-131">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 <span data-ttu-id="a20b0-132">说明如何使用<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>WCF 和消息队列应用程序之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="a20b0-132">Explains how to use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> to communicate between WCF and Message Queuing applications.</span></span>  
  
 [<span data-ttu-id="a20b0-133">在会话中对排队消息进行分组</span><span class="sxs-lookup"><span data-stu-id="a20b0-133">Grouping Queued Messages in a Session</span></span>](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 <span data-ttu-id="a20b0-134">说明如何对队列中的消息分组，以便单个接收应用程序加速处理相关消息。</span><span class="sxs-lookup"><span data-stu-id="a20b0-134">Explains how to group messages in a queue to facilitate correlated message processing by a single receiving application.</span></span>  
  
 [<span data-ttu-id="a20b0-135">在事务中对消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="a20b0-135">Batching Messages in a Transaction</span></span>](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 <span data-ttu-id="a20b0-136">说明如何在事务中对消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="a20b0-136">Explains how to batch messages in a transaction.</span></span>  
  
 [<span data-ttu-id="a20b0-137">使用死信队列处理消息传输故障</span><span class="sxs-lookup"><span data-stu-id="a20b0-137">Using Dead-Letter Queues to Handle Message Transfer Failures</span></span>](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 <span data-ttu-id="a20b0-138">说明如何使用死信队列来处理消息传输和传送故障，以及如何处理死信队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="a20b0-138">Explains how to handle message transfer and delivery failures using dead letter queues and how to process messages from the dead letter queue.</span></span>  
  
 [<span data-ttu-id="a20b0-139">有害消息处理</span><span class="sxs-lookup"><span data-stu-id="a20b0-139">Poison Message Handling</span></span>](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 <span data-ttu-id="a20b0-140">说明如何处理病毒消息（向接收应用程序尝试传送的次数超出最大次数的消息）。</span><span class="sxs-lookup"><span data-stu-id="a20b0-140">Explains how to handle poison messages (messages that have exceeded the maximum number of delivery attempts to the receiving application).</span></span>  
  
 [<span data-ttu-id="a20b0-141">Windows Vista、Windows Server 2003 和 Windows XP 在排队功能方面的差异</span><span class="sxs-lookup"><span data-stu-id="a20b0-141">Differences in Queuing Features in Windows Vista, Windows Server 2003, and Windows XP</span></span>](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 <span data-ttu-id="a20b0-142">总结了在 WCF 队列功能之间的差异[!INCLUDE[wv](../../../../includes/wv-md.md)]， [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]，和[!INCLUDE[wxp](../../../../includes/wxp-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a20b0-142">Summarizes the differences in the WCF queues feature between [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>  
  
 [<span data-ttu-id="a20b0-143">使用传输安全性保护消息</span><span class="sxs-lookup"><span data-stu-id="a20b0-143">Securing Messages Using Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 <span data-ttu-id="a20b0-144">介绍如何使用传输安全来保护排队消息。</span><span class="sxs-lookup"><span data-stu-id="a20b0-144">Describes how to use transport security to secure queued messages.</span></span>  
  
 [<span data-ttu-id="a20b0-145">使用消息安全性保护消息</span><span class="sxs-lookup"><span data-stu-id="a20b0-145">Securing Messages Using Message Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 <span data-ttu-id="a20b0-146">介绍如何使用消息安全来保护排队消息。</span><span class="sxs-lookup"><span data-stu-id="a20b0-146">Describes how to use message security to secure queued messages.</span></span>  
  
 [<span data-ttu-id="a20b0-147">排队消息处理疑难解答</span><span class="sxs-lookup"><span data-stu-id="a20b0-147">Troubleshooting Queued Messaging</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)  
 <span data-ttu-id="a20b0-148">说明如何解决常见队列问题。</span><span class="sxs-lookup"><span data-stu-id="a20b0-148">Explains how to troubleshoot common queuing problems.</span></span>  
  
 [<span data-ttu-id="a20b0-149">排队通信的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a20b0-149">Best Practices for Queued Communication</span></span>](../../../../docs/framework/wcf/feature-details/best-practices-for-queued-communication.md)  
 <span data-ttu-id="a20b0-150">介绍了使用 WCF 的最佳实践排队通信。</span><span class="sxs-lookup"><span data-stu-id="a20b0-150">Explains best practices for using WCF queued communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a20b0-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="a20b0-151">See Also</span></span>  
 [<span data-ttu-id="a20b0-152">消息队列</span><span class="sxs-lookup"><span data-stu-id="a20b0-152">Message Queuing</span></span>](https://msdn.microsoft.com/library/ff917e87-05d5-478f-9430-0f560675ece1)
