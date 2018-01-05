---
title: "Windows Communication Foundation 中的传输"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62eb27919e762004667b3d5179c35cb04d9a9422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="373ea-102">Windows Communication Foundation 中的传输</span><span class="sxs-lookup"><span data-stu-id="373ea-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="373ea-103">传输层是通道堆栈的最低层。</span><span class="sxs-lookup"><span data-stu-id="373ea-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="373ea-104">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中使用的主要传输有 HTTP、HTTPS、TCP 和命名管道。</span><span class="sxs-lookup"><span data-stu-id="373ea-104">The main transports used in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="373ea-105">本节中的主题讨论如何选择传输、配置传输和设置优化属性。</span><span class="sxs-lookup"><span data-stu-id="373ea-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="373ea-106"> 包括其他传输。</span><span class="sxs-lookup"><span data-stu-id="373ea-106"> includes additional transports.</span></span> <span data-ttu-id="373ea-107">有关消息队列 (也称为 MSMQ) 传输的信息，请参阅[队列和可靠会话](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="373ea-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="373ea-108">有关对等传输的信息，请参阅[对等网络](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="373ea-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="373ea-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="373ea-109">In This Section</span></span>  
 [<span data-ttu-id="373ea-110">选择传输</span><span class="sxs-lookup"><span data-stu-id="373ea-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="373ea-111">说明三种主要传输和选择其中一种传输时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="373ea-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="373ea-112">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="373ea-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="373ea-113">说明选择消息编码绑定元素时要考虑的因素。</span><span class="sxs-lookup"><span data-stu-id="373ea-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="373ea-114">流消息传输</span><span class="sxs-lookup"><span data-stu-id="373ea-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="373ea-115">说明如何配置传输层进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="373ea-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="373ea-116">配置 HTTP 和 HTTPS</span><span class="sxs-lookup"><span data-stu-id="373ea-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="373ea-117">说明如何配置 HTTP 和 HTTPS 传输绑定元素。</span><span class="sxs-lookup"><span data-stu-id="373ea-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="373ea-118">如何：用受限保留项替换 WCF URL 保留项</span><span class="sxs-lookup"><span data-stu-id="373ea-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="373ea-119">说明如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 受限保留项。</span><span class="sxs-lookup"><span data-stu-id="373ea-119">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]URL restricted reservations.</span></span>  
  
 [<span data-ttu-id="373ea-120">传输配额</span><span class="sxs-lookup"><span data-stu-id="373ea-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="373ea-121">说明设置传输层中可用配额时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="373ea-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="373ea-122">使用 NAT 和防火墙</span><span class="sxs-lookup"><span data-stu-id="373ea-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="373ea-123">说明在防火墙后发送或接收消息时或存在网络地址转换 (NAT) 时如何配置传输层。</span><span class="sxs-lookup"><span data-stu-id="373ea-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="373ea-124">Net.TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="373ea-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="373ea-125">说明如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的 Net.TCP 端口共享组件。</span><span class="sxs-lookup"><span data-stu-id="373ea-125">Describes how to use the Net.TCP Port Sharing component of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="373ea-126">参考</span><span class="sxs-lookup"><span data-stu-id="373ea-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="373ea-127">相关章节</span><span class="sxs-lookup"><span data-stu-id="373ea-127">Related Sections</span></span>  
 [<span data-ttu-id="373ea-128">绑定</span><span class="sxs-lookup"><span data-stu-id="373ea-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="373ea-129">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="373ea-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
