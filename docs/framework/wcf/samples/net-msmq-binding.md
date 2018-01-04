---
title: "网络 MSMQ 绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bb696-f57c-4cb3-9b7e-9d95fe6b8323
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f6282dfbf5e67f91167e5abf0640641000994d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="net-msmq-binding"></a><span data-ttu-id="a4e75-102">网络 MSMQ 绑定</span><span class="sxs-lookup"><span data-stu-id="a4e75-102">Net MSMQ Binding</span></span>
<span data-ttu-id="a4e75-103">本节包含演示如何使用终结点元素的 MSMQ 绑定特性的示例。</span><span class="sxs-lookup"><span data-stu-id="a4e75-103">This section contains samples that demonstrate using MSMQ binding attributes of an endpoint element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4e75-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="a4e75-104">In This Section</span></span>  
 [<span data-ttu-id="a4e75-105">已进行事务处理的 MSMQ 绑定</span><span class="sxs-lookup"><span data-stu-id="a4e75-105">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 <span data-ttu-id="a4e75-106">演示如何使用消息队列 (MSMQ) 执行已经过事务处理的排队通信。</span><span class="sxs-lookup"><span data-stu-id="a4e75-106">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>  
  
 [<span data-ttu-id="a4e75-107">可变排队通信</span><span class="sxs-lookup"><span data-stu-id="a4e75-107">Volatile Queued Communication</span></span>](../../../../docs/framework/wcf/samples/volatile-queued-communication.md)  
 <span data-ttu-id="a4e75-108">演示如何通过消息队列 (MSMQ) 传输来执行可变排队通信。</span><span class="sxs-lookup"><span data-stu-id="a4e75-108">Demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="a4e75-109">死信队列</span><span class="sxs-lookup"><span data-stu-id="a4e75-109">Dead Letter Queues</span></span>](../../../../docs/framework/wcf/samples/dead-letter-queues.md)  
 <span data-ttu-id="a4e75-110">演示如何处理传递失败的消息。</span><span class="sxs-lookup"><span data-stu-id="a4e75-110">Demonstrates how to handle and process messages that have failed delivery.</span></span>  
  
 [<span data-ttu-id="a4e75-111">MSMQ 4.0 中的病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="a4e75-111">Poison Message Handling in MSMQ 4.0</span></span>](../../../../docs/framework/wcf/samples/poison-message-handling-in-msmq-4-0.md)  
 <span data-ttu-id="a4e75-112">演示如何使用 MSMQ 4.0 在服务中执行病毒消息处理。</span><span class="sxs-lookup"><span data-stu-id="a4e75-112">Demonstrates how to perform poison message handling in a service using MSMQ 4.0.</span></span>  
  
 [<span data-ttu-id="a4e75-113">会话和队列</span><span class="sxs-lookup"><span data-stu-id="a4e75-113">Sessions and Queues</span></span>](../../../../docs/framework/wcf/samples/sessions-and-queues.md)  
 <span data-ttu-id="a4e75-114">演示如何通过消息队列 (MSMQ) 传输来发送和接收排队通信中的一组相关消息。</span><span class="sxs-lookup"><span data-stu-id="a4e75-114">Demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="a4e75-115">双向通信</span><span class="sxs-lookup"><span data-stu-id="a4e75-115">Two-Way Communication</span></span>](../../../../docs/framework/wcf/samples/two-way-communication.md)  
 <span data-ttu-id="a4e75-116">演示如何通过 MSMQ 执行事务处理双向排队通信。</span><span class="sxs-lookup"><span data-stu-id="a4e75-116">Demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span>  
  
 [<span data-ttu-id="a4e75-117">事务处理批处理</span><span class="sxs-lookup"><span data-stu-id="a4e75-117">Transacted Batching</span></span>](../../../../docs/framework/wcf/samples/transacted-batching.md)  
 <span data-ttu-id="a4e75-118">演示如何通过使用消息队列 (MSMQ) 来批处理事务处理读取。</span><span class="sxs-lookup"><span data-stu-id="a4e75-118">Demonstrates how to batch transacted reads by using Message Queuing (MSMQ).</span></span>  
  
 [<span data-ttu-id="a4e75-119">SRMP</span><span class="sxs-lookup"><span data-stu-id="a4e75-119">SRMP</span></span>](../../../../docs/framework/wcf/samples/srmp.md)  
 <span data-ttu-id="a4e75-120">演示如何使用 HTTP 上的消息队列 (MSMQ) 执行已经过事务处理的排队通信。</span><span class="sxs-lookup"><span data-stu-id="a4e75-120">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 [<span data-ttu-id="a4e75-121">基于消息队列的消息安全性</span><span class="sxs-lookup"><span data-stu-id="a4e75-121">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
 <span data-ttu-id="a4e75-122">演示如何实现使用 WS-Security 的应用程序，此应用程序使用 X.509v3 证书对客户端进行身份验证，并要求通过 MSMQ 使用服务器的 X.509v3 证书的服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="a4e75-122">Demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span>  
  
 [<span data-ttu-id="a4e75-123">ReceiveContext 乘积生成器</span><span class="sxs-lookup"><span data-stu-id="a4e75-123">ReceiveContext Product Generator</span></span>](../../../../docs/framework/wcf/samples/receivecontext-enabled-wcf-channels.md)  
 <span data-ttu-id="a4e75-124">演示启用了 <xref:System.ServiceModel.Channels.ReceiveContext> 的 WCF 通道的用处。</span><span class="sxs-lookup"><span data-stu-id="a4e75-124">Demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span>
