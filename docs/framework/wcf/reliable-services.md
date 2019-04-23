---
title: 可靠服务
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], reliable messaging
- Windows Communication Foundation [WCF], reliable messaging
- WCF [WCF], reliable sessions
- Windows Communication Foundation [WCF], reliable sessions
- service contracts [WCF], reliable services
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
ms.openlocfilehash: a617100e46d4bcafb9325efa99c255f2f8ee5981
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216764"
---
# <a name="reliable-services"></a><span data-ttu-id="37bfa-102">可靠服务</span><span class="sxs-lookup"><span data-stu-id="37bfa-102">Reliable Services</span></span>
<span data-ttu-id="37bfa-103">队列和可靠会话是实现可靠消息传递的 Windows Communication Foundation (WCF) 功能。</span><span class="sxs-lookup"><span data-stu-id="37bfa-103">Queues and reliable sessions are the Windows Communication Foundation (WCF) features that implement reliable messaging.</span></span> <span data-ttu-id="37bfa-104">本主题介绍 WCF 的可靠消息传送功能。</span><span class="sxs-lookup"><span data-stu-id="37bfa-104">This topic explains the reliable messaging features of WCF.</span></span>  
  
 <span data-ttu-id="37bfa-105">*可靠消息传送*是如何可靠消息源 (称为*源*) 将消息可靠地传输到可靠的消息目标 (称为*目标*)。</span><span class="sxs-lookup"><span data-stu-id="37bfa-105">*Reliable messaging* is how a reliable messaging source (called the *source*) transfers messages reliably to a reliable messaging destination (called the *destination*).</span></span>  
  
 <span data-ttu-id="37bfa-106">可靠消息传递执行以下功能：</span><span class="sxs-lookup"><span data-stu-id="37bfa-106">Reliable messaging performs the following functions:</span></span>  
  
-   <span data-ttu-id="37bfa-107">传送从源发送到目标的消息的保证，而不管消息传送或传输是否失败。</span><span class="sxs-lookup"><span data-stu-id="37bfa-107">Transfers assurances for messages sent from a source to a destination regardless of message transfer or transport failures.</span></span>  
  
-   <span data-ttu-id="37bfa-108">使源和目标相互分离。</span><span class="sxs-lookup"><span data-stu-id="37bfa-108">Separates the source and the destination from each other.</span></span> <span data-ttu-id="37bfa-109">即使源或目标不可用，此功能也能为源和目标提供独立的故障与恢复，以及消息的可靠传送和传输。</span><span class="sxs-lookup"><span data-stu-id="37bfa-109">This provides independent failure and recovery of the source and the destination, as well as reliable transfer and delivery of messages, even when the source or destination is unavailable.</span></span>  
  
 <span data-ttu-id="37bfa-110">可靠消息传递经常伴随高延迟成本。</span><span class="sxs-lookup"><span data-stu-id="37bfa-110">Reliable messaging frequently comes at the cost of high latency.</span></span> <span data-ttu-id="37bfa-111">*延迟*是指消息到达来自源目标所需要的时间。</span><span class="sxs-lookup"><span data-stu-id="37bfa-111">*Latency* is the time it takes for the message to reach the destination from the source.</span></span> <span data-ttu-id="37bfa-112">WCF，因此，提供以下类型的可靠消息传送：</span><span class="sxs-lookup"><span data-stu-id="37bfa-112">WCF, therefore, provides the following types of reliable messaging:</span></span>  
  
-   <span data-ttu-id="37bfa-113">[可靠会话](../../../docs/framework/wcf/feature-details/reliable-sessions.md)，它提供没有高延迟成本的可靠传送。</span><span class="sxs-lookup"><span data-stu-id="37bfa-113">[Reliable Sessions](../../../docs/framework/wcf/feature-details/reliable-sessions.md), which offers reliable transfer without the cost of high latency.</span></span>  
  
-   <span data-ttu-id="37bfa-114">[WCF 中的队列](../../../docs/framework/wcf/feature-details/queues-in-wcf.md)，它提供可靠传送和源与目标之间的分离。</span><span class="sxs-lookup"><span data-stu-id="37bfa-114">[Queues in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md), which offers both reliable transfers and separation between the source and the destination.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="37bfa-115">可靠会话</span><span class="sxs-lookup"><span data-stu-id="37bfa-115">Reliable Sessions</span></span>  
 <span data-ttu-id="37bfa-116">可靠会话使用 WS 可靠消息传递协议提供源和目标之间的端到端可靠消息传送，而不管分隔消息（源和目标）终结点的中介的数量和类型如何。</span><span class="sxs-lookup"><span data-stu-id="37bfa-116">Reliable sessions provide end-to-end reliable transfer of messages between a source and a destination using the WS-Reliable Messaging protocol, regardless of the number or type of intermediaries that separate the messaging (source and destination) endpoints.</span></span> <span data-ttu-id="37bfa-117">这包括不使用 SOAP 的任何传输中介（例如 HTTP 代理）或在终结点之间流动所必需的使用 SOAP 的中介（例如基于 SOAP 的路由器或网桥）。</span><span class="sxs-lookup"><span data-stu-id="37bfa-117">This includes any transport intermediaries that do not use SOAP (for example, HTTP proxies) or intermediaries that use SOAP (for example, SOAP-based routers or bridges) that are required for messages to flow between the endpoints.</span></span> <span data-ttu-id="37bfa-118">可靠会话使用内存中的传送窗口屏蔽 SOAP 消息级别的失败并在传输失败时重新建立连接。</span><span class="sxs-lookup"><span data-stu-id="37bfa-118">Reliable sessions use an in-memory transfer window to mask SOAP message-level failures and re-establish connections in the case of transport failures.</span></span>  
  
 <span data-ttu-id="37bfa-119">可靠会话提供低延迟可靠消息传送。</span><span class="sxs-lookup"><span data-stu-id="37bfa-119">Reliable sessions provide low-latency reliable message transfers.</span></span> <span data-ttu-id="37bfa-120">可靠会话通过任何代理或中介为 SOAP 消息提供的功能相当于 TCP 通过 IP 网桥为数据包提供的功能。</span><span class="sxs-lookup"><span data-stu-id="37bfa-120">They provide for SOAP messages over any proxies or intermediaries, equivalent to what TCP provides for packets over IP bridges.</span></span> <span data-ttu-id="37bfa-121">有关可靠会话的详细信息，请参阅[可靠会话](../../../docs/framework/wcf/feature-details/reliable-sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="37bfa-121">For more information about reliable sessions, see [Reliable Sessions](../../../docs/framework/wcf/feature-details/reliable-sessions.md).</span></span>  
  
### <a name="queues"></a><span data-ttu-id="37bfa-122">队列</span><span class="sxs-lookup"><span data-stu-id="37bfa-122">Queues</span></span>  
 <span data-ttu-id="37bfa-123">WCF 中的队列提供可靠传送消息以及分离的源和目标高延迟成本之间。</span><span class="sxs-lookup"><span data-stu-id="37bfa-123">Queues in WCF provide both reliable transfers of messages and separation between sources and destinations at the cost of high latency.</span></span> <span data-ttu-id="37bfa-124">WCF 排队通信建立基于消息队列 (MSMQ)。</span><span class="sxs-lookup"><span data-stu-id="37bfa-124">WCF queued communication is built on top of Message Queuing (MSMQ).</span></span>  
  
 <span data-ttu-id="37bfa-125">MSMQ 作为可选组件随 Windows 提供。</span><span class="sxs-lookup"><span data-stu-id="37bfa-125">MSMQ ships as an optional component with Windows.</span></span> <span data-ttu-id="37bfa-126">MSMQ 服务作为 Windows 服务运行。</span><span class="sxs-lookup"><span data-stu-id="37bfa-126">The MSMQ service runs as a Windows Service.</span></span> <span data-ttu-id="37bfa-127">它捕获代表源的传输队列中要传输的消息，并将消息传递到目标队列。</span><span class="sxs-lookup"><span data-stu-id="37bfa-127">It captures messages for transmission in a transmission queue on behalf of the source and delivers it to a target queue.</span></span> <span data-ttu-id="37bfa-128">目标队列代表目标接受消息，待以后目标请求消息时传递。</span><span class="sxs-lookup"><span data-stu-id="37bfa-128">The target queue accepts messages on behalf of the destination for later delivery whenever the destination requests messages.</span></span> <span data-ttu-id="37bfa-129">MSMQ 管理器实现可靠消息传递协议，使消息不会在传输中丢失。</span><span class="sxs-lookup"><span data-stu-id="37bfa-129">The MSMQ managers implement a reliable message-transfer protocol so that messages are not lost in transmission.</span></span> <span data-ttu-id="37bfa-130">此协议可以是本机的，也可以是基于 SOAP 的协议（称为 SOAP 可靠消息传递协议 (SRMP)）。</span><span class="sxs-lookup"><span data-stu-id="37bfa-130">The protocol can be native or a SOAP-based protocol called SOAP Reliable Messaging Protocol (SRMP).</span></span>  
  
 <span data-ttu-id="37bfa-131">在队列之间与可靠消息传送相耦合的分离，使松耦合的应用程序能够可靠地通信。</span><span class="sxs-lookup"><span data-stu-id="37bfa-131">The separation, coupled with reliable message transfers between queues, enables applications that are loosely coupled to communicate reliably.</span></span> <span data-ttu-id="37bfa-132">与可靠会话不同，源和目标不必同时运行。</span><span class="sxs-lookup"><span data-stu-id="37bfa-132">Unlike reliable sessions, the source and destination do not have to be running at the same time.</span></span> <span data-ttu-id="37bfa-133">这暗示可以出现这种情况：当源产生消息的速率和目标使用消息的速率不匹配时，队列实际上用作一种负载平衡机制。</span><span class="sxs-lookup"><span data-stu-id="37bfa-133">This implicitly enables scenarios where queues are, in effect, used as a load-leveling mechanism when the source's rate of message production and the destination's rate of the message consumption do not match.</span></span> <span data-ttu-id="37bfa-134">有关队列的详细信息，请参阅[WCF 中的队列](../../../docs/framework/wcf/feature-details/queues-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="37bfa-134">For more information about queues, see [Queues in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37bfa-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="37bfa-135">See also</span></span>

- [<span data-ttu-id="37bfa-136">可靠会话概述</span><span class="sxs-lookup"><span data-stu-id="37bfa-136">Reliable Sessions Overview</span></span>](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)
- [<span data-ttu-id="37bfa-137">在 WCF 中排队</span><span class="sxs-lookup"><span data-stu-id="37bfa-137">Queuing in WCF</span></span>](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
