---
title: "可靠服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], reliable messaging
- Windows Communication Foundation [WCF], reliable messaging
- WCF [WCF], reliable sessions
- Windows Communication Foundation [WCF], reliable sessions
- service contracts [WCF], reliable services
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f8bc4e68e705691db0c6fcd0e8be0447af73ec42
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-services"></a><span data-ttu-id="f3b09-102">可靠服务</span><span class="sxs-lookup"><span data-stu-id="f3b09-102">Reliable Services</span></span>
<span data-ttu-id="f3b09-103">队列和可靠会话是 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 用于实现可靠消息传递的功能。</span><span class="sxs-lookup"><span data-stu-id="f3b09-103">Queues and reliable sessions are the [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] features that implement reliable messaging.</span></span> <span data-ttu-id="f3b09-104">本主题说明 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 的可靠消息传递功能。</span><span class="sxs-lookup"><span data-stu-id="f3b09-104">This topic explains the reliable messaging features of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="f3b09-105">*可靠消息传递*是指可靠消息源 (称为*源*) 将消息可靠地传送到可靠的消息目标 (称为*目标*)。</span><span class="sxs-lookup"><span data-stu-id="f3b09-105">*Reliable messaging* is how a reliable messaging source (called the *source*) transfers messages reliably to a reliable messaging destination (called the *destination*).</span></span>  
  
 <span data-ttu-id="f3b09-106">可靠消息传递执行以下功能：</span><span class="sxs-lookup"><span data-stu-id="f3b09-106">Reliable messaging performs the following functions:</span></span>  
  
-   <span data-ttu-id="f3b09-107">传送从源发送到目标的消息的保证，而不管消息传送或传输是否失败。</span><span class="sxs-lookup"><span data-stu-id="f3b09-107">Transfers assurances for messages sent from a source to a destination regardless of message transfer or transport failures.</span></span>  
  
-   <span data-ttu-id="f3b09-108">使源和目标相互分离。</span><span class="sxs-lookup"><span data-stu-id="f3b09-108">Separates the source and the destination from each other.</span></span> <span data-ttu-id="f3b09-109">即使源或目标不可用，此功能也能为源和目标提供独立的故障与恢复，以及消息的可靠传送和传输。</span><span class="sxs-lookup"><span data-stu-id="f3b09-109">This provides independent failure and recovery of the source and the destination, as well as reliable transfer and delivery of messages, even when the source or destination is unavailable.</span></span>  
  
 <span data-ttu-id="f3b09-110">可靠消息传递经常伴随高延迟成本。</span><span class="sxs-lookup"><span data-stu-id="f3b09-110">Reliable messaging frequently comes at the cost of high latency.</span></span> <span data-ttu-id="f3b09-111">*延迟*是到达从源目的地的消息所需要的时间。</span><span class="sxs-lookup"><span data-stu-id="f3b09-111">*Latency* is the time it takes for the message to reach the destination from the source.</span></span> <span data-ttu-id="f3b09-112">因此，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 提供了以下类型的可靠消息传递：</span><span class="sxs-lookup"><span data-stu-id="f3b09-112">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)], therefore, provides the following types of reliable messaging:</span></span>  
  
-   <span data-ttu-id="f3b09-113">[可靠会话](../../../docs/framework/wcf/feature-details/reliable-sessions.md)，它提供可靠的传输，而无需的高延迟成本。</span><span class="sxs-lookup"><span data-stu-id="f3b09-113">[Reliable Sessions](../../../docs/framework/wcf/feature-details/reliable-sessions.md), which offers reliable transfer without the cost of high latency.</span></span>  
  
-   <span data-ttu-id="f3b09-114">[WCF 中的队列](../../../docs/framework/wcf/feature-details/queues-in-wcf.md)，它提供了可靠传送和源和目标之间的分离。</span><span class="sxs-lookup"><span data-stu-id="f3b09-114">[Queues in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md), which offers both reliable transfers and separation between the source and the destination.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="f3b09-115">可靠会话</span><span class="sxs-lookup"><span data-stu-id="f3b09-115">Reliable Sessions</span></span>  
 <span data-ttu-id="f3b09-116">可靠会话使用 WS 可靠消息传递协议提供源和目标之间的端到端可靠消息传送，而不管分隔消息（源和目标）终结点的中介的数量和类型如何。</span><span class="sxs-lookup"><span data-stu-id="f3b09-116">Reliable sessions provide end-to-end reliable transfer of messages between a source and a destination using the WS-Reliable Messaging protocol, regardless of the number or type of intermediaries that separate the messaging (source and destination) endpoints.</span></span> <span data-ttu-id="f3b09-117">这包括不使用 SOAP 的任何传输中介（例如 HTTP 代理）或在终结点之间流动所必需的使用 SOAP 的中介（例如基于 SOAP 的路由器或网桥）。</span><span class="sxs-lookup"><span data-stu-id="f3b09-117">This includes any transport intermediaries that do not use SOAP (for example, HTTP proxies) or intermediaries that use SOAP (for example, SOAP-based routers or bridges) that are required for messages to flow between the endpoints.</span></span> <span data-ttu-id="f3b09-118">可靠会话使用内存中的传送窗口屏蔽 SOAP 消息级别的失败并在传输失败时重新建立连接。</span><span class="sxs-lookup"><span data-stu-id="f3b09-118">Reliable sessions use an in-memory transfer window to mask SOAP message-level failures and re-establish connections in the case of transport failures.</span></span>  
  
 <span data-ttu-id="f3b09-119">可靠会话提供低延迟可靠消息传送。</span><span class="sxs-lookup"><span data-stu-id="f3b09-119">Reliable sessions provide low-latency reliable message transfers.</span></span> <span data-ttu-id="f3b09-120">可靠会话通过任何代理或中介为 SOAP 消息提供的功能相当于 TCP 通过 IP 网桥为数据包提供的功能。</span><span class="sxs-lookup"><span data-stu-id="f3b09-120">They provide for SOAP messages over any proxies or intermediaries, equivalent to what TCP provides for packets over IP bridges.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="f3b09-121">可靠会话，请参阅[可靠会话](../../../docs/framework/wcf/feature-details/reliable-sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="f3b09-121"> reliable sessions, see [Reliable Sessions](../../../docs/framework/wcf/feature-details/reliable-sessions.md).</span></span>  
  
### <a name="queues"></a><span data-ttu-id="f3b09-122">队列</span><span class="sxs-lookup"><span data-stu-id="f3b09-122">Queues</span></span>  
 <span data-ttu-id="f3b09-123">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中的队列以高延迟为代价提供可靠的消息传送和源与目标之间的分离。</span><span class="sxs-lookup"><span data-stu-id="f3b09-123">Queues in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] provide both reliable transfers of messages and separation between sources and destinations at the cost of high latency.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="f3b09-124"> 排队的通信建立在消息队列 (MSMQ) 的基础之上。</span><span class="sxs-lookup"><span data-stu-id="f3b09-124"> queued communication is built on top of Message Queuing (MSMQ).</span></span>  
  
 <span data-ttu-id="f3b09-125">MSMQ 作为可选组件随 Windows 提供。</span><span class="sxs-lookup"><span data-stu-id="f3b09-125">MSMQ ships as an optional component with Windows.</span></span> <span data-ttu-id="f3b09-126">MSMQ 服务作为 Windows 服务运行。</span><span class="sxs-lookup"><span data-stu-id="f3b09-126">The MSMQ service runs as a Windows Service.</span></span> <span data-ttu-id="f3b09-127">它捕获代表源的传输队列中要传输的消息，并将消息传递到目标队列。</span><span class="sxs-lookup"><span data-stu-id="f3b09-127">It captures messages for transmission in a transmission queue on behalf of the source and delivers it to a target queue.</span></span> <span data-ttu-id="f3b09-128">目标队列代表目标接受消息，待以后目标请求消息时传递。</span><span class="sxs-lookup"><span data-stu-id="f3b09-128">The target queue accepts messages on behalf of the destination for later delivery whenever the destination requests messages.</span></span> <span data-ttu-id="f3b09-129">MSMQ 管理器实现可靠消息传递协议，使消息不会在传输中丢失。</span><span class="sxs-lookup"><span data-stu-id="f3b09-129">The MSMQ managers implement a reliable message-transfer protocol so that messages are not lost in transmission.</span></span> <span data-ttu-id="f3b09-130">此协议可以是本机的，也可以是基于 SOAP 的协议（称为 SOAP 可靠消息传递协议 (SRMP)）。</span><span class="sxs-lookup"><span data-stu-id="f3b09-130">The protocol can be native or a SOAP-based protocol called SOAP Reliable Messaging Protocol (SRMP).</span></span>  
  
 <span data-ttu-id="f3b09-131">在队列之间与可靠消息传送相耦合的分离，使松耦合的应用程序能够可靠地通信。</span><span class="sxs-lookup"><span data-stu-id="f3b09-131">The separation, coupled with reliable message transfers between queues, enables applications that are loosely coupled to communicate reliably.</span></span> <span data-ttu-id="f3b09-132">与可靠会话不同，源和目标不必同时运行。</span><span class="sxs-lookup"><span data-stu-id="f3b09-132">Unlike reliable sessions, the source and destination do not have to be running at the same time.</span></span> <span data-ttu-id="f3b09-133">这暗示可以出现这种情况：当源产生消息的速率和目标使用消息的速率不匹配时，队列实际上用作一种负载平衡机制。</span><span class="sxs-lookup"><span data-stu-id="f3b09-133">This implicitly enables scenarios where queues are, in effect, used as a load-leveling mechanism when the source's rate of message production and the destination's rate of the message consumption do not match.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="f3b09-134">队列，请参阅[WCF 中的队列](../../../docs/framework/wcf/feature-details/queues-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="f3b09-134"> queues, see [Queues in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b09-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3b09-135">See Also</span></span>  
 [<span data-ttu-id="f3b09-136">可靠会话概述</span><span class="sxs-lookup"><span data-stu-id="f3b09-136">Reliable Sessions Overview</span></span>](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 [<span data-ttu-id="f3b09-137">在 WCF 中排队</span><span class="sxs-lookup"><span data-stu-id="f3b09-137">Queuing in WCF</span></span>](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
