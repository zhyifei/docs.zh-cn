---
title: "可靠消息传送协议版本 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5657b48a648603f24e89c0eebd1285ed9a505e54
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="f2031-102">可靠消息传送协议版本 1.0</span><span class="sxs-lookup"><span data-stu-id="f2031-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="f2031-103">本主题介绍使用 HTTP 传输进行互操作所需的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] WS-Reliable Messaging 2005 年 2 月（版本 1.0）协议的实现细节。</span><span class="sxs-lookup"><span data-stu-id="f2031-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-104"> 遵循 WS-Reliable Messaging 规范以及本主题中解释的约束和声明。</span><span class="sxs-lookup"><span data-stu-id="f2031-104"> follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="f2031-105">请注意，WS-ReliableMessaging 版本 1.0 协议是从 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 开始实现的。</span><span class="sxs-lookup"><span data-stu-id="f2031-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="f2031-106">通过 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> 中实现 WS-Reliable Messaging February 2005 协议。</span><span class="sxs-lookup"><span data-stu-id="f2031-106">The WS-Reliable Messaging February 2005 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="f2031-107">为方便起见，本主题使用以下角色：</span><span class="sxs-lookup"><span data-stu-id="f2031-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="f2031-108">发起方：启动 WS-Reliable Message 序列创建的客户端</span><span class="sxs-lookup"><span data-stu-id="f2031-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
-   <span data-ttu-id="f2031-109">响应方：接收发起方的请求的服务</span><span class="sxs-lookup"><span data-stu-id="f2031-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="f2031-110">本文档使用下表中的前缀和命名空间。</span><span class="sxs-lookup"><span data-stu-id="f2031-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="f2031-111">前缀</span><span class="sxs-lookup"><span data-stu-id="f2031-111">Prefix</span></span>|<span data-ttu-id="f2031-112">命名空间</span><span class="sxs-lookup"><span data-stu-id="f2031-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="f2031-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="f2031-113">wsrm</span></span>|<span data-ttu-id="f2031-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span><span class="sxs-lookup"><span data-stu-id="f2031-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span></span>|  
|<span data-ttu-id="f2031-115">netrm</span><span class="sxs-lookup"><span data-stu-id="f2031-115">netrm</span></span>|<span data-ttu-id="f2031-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="f2031-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="f2031-117">s</span><span class="sxs-lookup"><span data-stu-id="f2031-117">s</span></span>|<span data-ttu-id="f2031-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="f2031-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="f2031-119">wsa</span><span class="sxs-lookup"><span data-stu-id="f2031-119">wsa</span></span>|<span data-ttu-id="f2031-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="f2031-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="f2031-121">wsse</span><span class="sxs-lookup"><span data-stu-id="f2031-121">wsse</span></span>|<span data-ttu-id="f2031-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="f2031-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="f2031-123">消息传送</span><span class="sxs-lookup"><span data-stu-id="f2031-123">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="f2031-124">序列建立消息</span><span class="sxs-lookup"><span data-stu-id="f2031-124">Sequence Establishment Messages</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-125"> 实现 `CreateSequence` 和 `CreateSequenceResponse` 消息以建立可靠的消息序列。</span><span class="sxs-lookup"><span data-stu-id="f2031-125"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="f2031-126">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="f2031-126">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="f2031-127">B1101：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 `CreateSequence` 消息中或者在 `CreateSequence` 消息包含 `Offer` 元素（`Expires` 元素中的可选 `Offer` 元素）的情况下，不会生成可选的 Expires 元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-127">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
-   <span data-ttu-id="f2031-128">B1102：当访问 `CreateSequence` 消息时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` 将发送和接收两个 `Expires` 元素（若存在），但不使用这两个元素的值。</span><span class="sxs-lookup"><span data-stu-id="f2031-128">B1102: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="f2031-129">WS-Reliable Messaging 引入了 `Offer` 机制来建立两个形成会话的反向相关的序列。</span><span class="sxs-lookup"><span data-stu-id="f2031-129">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="f2031-130">R1103：如果 `CreateSequence` 包含一个 `Offer` 元素，则可靠消息响应方要么必须接受序列并使用包含形成两个相关反向序列的 `CreateSequenceResponse` 元素的 `wsrm:Accept` 进行响应，要么必须拒绝 `CreateSequence` 请求。</span><span class="sxs-lookup"><span data-stu-id="f2031-130">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
-   <span data-ttu-id="f2031-131">R1104：在反向序列上流动的 `SequenceAcknowledgement` 和应用程序消息必须发送到 `ReplyTo` 的 `CreateSequence` 终结点引用。</span><span class="sxs-lookup"><span data-stu-id="f2031-131">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="f2031-132">R1105：`AcksTo` 中的 `ReplyTo` 和 `CreateSequence` 终结点引用必须具有与八进制识别匹配的地址值。</span><span class="sxs-lookup"><span data-stu-id="f2031-132">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="f2031-133">创建序列之前，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方验证 `AcksTo` 的 URI 部分与 `ReplyTo` EPR 是否相同。</span><span class="sxs-lookup"><span data-stu-id="f2031-133">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="f2031-134">R1106：`AcksTo` 中的 `ReplyTo` 和 `CreateSequence` 终结点引用应具有相同的引用参数集。</span><span class="sxs-lookup"><span data-stu-id="f2031-134">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-135"> 不强制但假定 `AcksTo` 上的 `ReplyTo` 和 `CreateSequence` 的 [reference parameters] 相同，并且从确认消息和反向序列消息的 `ReplyTo` 终结点引用中使用 [reference parameters]。</span><span class="sxs-lookup"><span data-stu-id="f2031-135"> does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="f2031-136">R1107：在使用 `Offer` 机制建立两个反向序列时，在反向序列上流动的 `SequenceAcknowledgement` 和应用程序消息必须发送到 `ReplyTo` 的 `CreateSequence` 终结点引用。</span><span class="sxs-lookup"><span data-stu-id="f2031-136">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="f2031-137">R1108：使用 Offer 机制建立两个反向序列时，`[address]` 的 `wsrm:AcksTo` 元素的 `wsrm:Accept` 终结点引用子元素的 `CreateSequenceResponse` 属性必须与 `CreateSequence` 的识别字节的目标 URI 相匹配。</span><span class="sxs-lookup"><span data-stu-id="f2031-137">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="f2031-138">R1109：在使用 `Offer` 机制建立两个反向序列时，发起方发送的消息和响应方的消息确认必须发送到同一个终结点引用。</span><span class="sxs-lookup"><span data-stu-id="f2031-138">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-139"> 使用 WS-Reliable Messaging 在发起方和响应方之间建立可靠会话。</span><span class="sxs-lookup"><span data-stu-id="f2031-139"> uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-140"> 的 WS-Reliable Messaging 实现提供单向、请求-答复和完全双工消息传递模式的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="f2031-140">'s WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="f2031-141">Ws-reliable Messaging`Offer`上的机制`CreateSequence` / `CreateSequenceResponse`使您可以建立两个相关的相反序列，并提供适合于所有消息终结点的会话协议。</span><span class="sxs-lookup"><span data-stu-id="f2031-141">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="f2031-142">由于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 为此类会话提供安全保证（包括端到端的会话完整性保护），因此确保发送到相同方的消息到达同一目标是可行的。</span><span class="sxs-lookup"><span data-stu-id="f2031-142">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="f2031-143">这也允许在应用程序消息上捎带序列确认消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-143">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="f2031-144">因此，约束 R1104、R1105 和 R1108 适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f2031-144">Therefore, constraints R1104, R1105, and R1108 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="f2031-145">`CreateSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="f2031-145">An example of a `CreateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence  
    </a:Action>  
    <a:ReplyTo>  
      <a:Address>          
         http://Business456.com/clientA        
      </a:Address>  
    </a:ReplyTo>  
    <a:MessageID>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:MessageID>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
       <wsa:Address>  
         http://Business456.com/clientA  
       </wsa:Address>  
     </wsrm:AcksTo>  
     <wsrm:Offer>  
      <wsrm:Identifier>  
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496  
      </wsrm:Identifier>  
     </wsrm:Offer>  
   </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="f2031-146">`CreateSequenceResponse` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="f2031-146">An example of a `CreateSequenceResponse` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse  
    </a:Action>  
    <a:RelatesTo>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:RelatesTo>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
   <wsrm:CreateSequenceResponse>  
    <Identifier>  
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386  
    </Identifier>  
    <Accept>  
    <AcksTo>  
      <a:Address>  
        http://BusinessABC.com/serviceA  
      </a:Address>  
    </AcksTo>  
    </Accept>  
   </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence"></a><span data-ttu-id="f2031-147">序列</span><span class="sxs-lookup"><span data-stu-id="f2031-147">Sequence</span></span>  
 <span data-ttu-id="f2031-148">以下是适用于序列的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="f2031-148">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="f2031-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]生成，并访问序列号不高于`xs:long`的最大非独占值，9223372036854775807。</span><span class="sxs-lookup"><span data-stu-id="f2031-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
-   <span data-ttu-id="f2031-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]始终生成 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage 中的操作 URI 的正文为空的最后一个消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates an empty-bodied last message with the action URI of http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
-   <span data-ttu-id="f2031-151">B1203：只要操作 URI 不是 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 就会接收和传送一条带有包含 `LastMessage` 元素的序列标头的消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
 <span data-ttu-id="f2031-152">Sequence 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="f2031-152">An example of a Sequence Header.</span></span>  
  
```xml  
<wsrm:Sequence>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
  <wsrm:MessageNumber>  
    10  
  </wsrm:MessageNumber>  
  <wsrm:LastMessage/>  
 </wsrm:Sequence>  
```  
  
### <a name="ackrequested-header"></a><span data-ttu-id="f2031-153">AckRequested 标头</span><span class="sxs-lookup"><span data-stu-id="f2031-153">AckRequested Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-154"> 将 `AckRequested` 标头作为一种“保持活动状态”机制。</span><span class="sxs-lookup"><span data-stu-id="f2031-154"> uses `AckRequested` Header as a keep-alive mechanism.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-155"> 不生成可选的 `MessageNumber` 元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-155"> does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="f2031-156">在接收到带有包含 `AckRequested` 元素的 `MessageNumber` 标头的消息时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将忽略 `MessageNumber` 元素的值，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="f2031-156">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="f2031-157">SequenceAcknowledgement 标头</span><span class="sxs-lookup"><span data-stu-id="f2031-157">SequenceAcknowledgement Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-158"> 将“非法携带”机制用于在 WS-Reliable Messaging 中提供的序列确认。</span><span class="sxs-lookup"><span data-stu-id="f2031-158"> uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="f2031-159">R1401：使用 `Offer` 机制建立两个相反序列时，`SequenceAcknowledgement` 头可能包括在传输到预期接收方的任何应用程序消息中。</span><span class="sxs-lookup"><span data-stu-id="f2031-159">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
-   <span data-ttu-id="f2031-160">B1402：当 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 必须在接收任何序列消息之前生成确认消息时（例如，满足 `AckRequested` 消息），[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将生成包含 0-0 范围的 `SequenceAcknowledgement` 标头，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="f2031-160">B1402: When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="f2031-161">B1403：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不生成包含 `SequenceAcknowledgement` 元素的 `Nack` 标头，但支持 `Nack` 元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="f2031-162">WS-ReliableMessaging 错误</span><span class="sxs-lookup"><span data-stu-id="f2031-162">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="f2031-163">下面列出了适用于 WS-Reliable Messaging 的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 实现错误的约束：</span><span class="sxs-lookup"><span data-stu-id="f2031-163">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-Reliable Messaging faults:</span></span>  
  
-   <span data-ttu-id="f2031-164">B1501：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不生成 `MessageNumberRollover` 错误。</span><span class="sxs-lookup"><span data-stu-id="f2031-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="f2031-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]终结点可能会生成`CreateSequenceRefused`错误规范中所述。</span><span class="sxs-lookup"><span data-stu-id="f2031-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
-   <span data-ttu-id="f2031-166">B1503:When 服务终结点达到其连接限制，因此无法处理新的连接，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]生成附加`CreateSequenceRefused`错误子代码`netrm:ConnectionLimitReached`，下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f2031-166">B1503:When the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
    ```xml  
    <s:Envelope>  
      <s:Header>  
        <wsa:Action>  
          http://schemas.xmlsoap.org/ws/2005/08/addressing/fault  
        </wsa:Action>  
      </s:Header>  
      <s:Body>  
        <s:Fault>  
          <s:Code>  
            <s:Value>  
              s:Receiver  
            </s:Value>  
            <s:Subcode>  
              <s:Value>  
                wsrm:CreateSequenceRefused  
              </s:Value>  
              <s:Subcode>  
                <s:Value>  
                  netrm:ConnectionLimitReached  
                </s:Value>  
              </s:Subcode>  
            </s:Subcode>  
          </s:Code>  
          <s:Reason>  
            <s:Text xml:lang="en">  
              [Reason]  
            </s:Text>  
          </s:Reason>  
        </s:Fault>  
      </s:Body>  
    </s:Envelope>  
    ```  
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="f2031-167">WS-Addressing 错误</span><span class="sxs-lookup"><span data-stu-id="f2031-167">WS-Addressing Faults</span></span>  
 <span data-ttu-id="f2031-168">因为 WS-Reliable Messaging 使用 WS-Addressing，所以 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging 实现可能生成 WS-Addressing 错误。</span><span class="sxs-lookup"><span data-stu-id="f2031-168">Because WS-Reliable Messaging uses WS-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="f2031-169">本节介绍了 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在 WS-Reliable Messaging 层显式生成的 WS-Addressing 错误。</span><span class="sxs-lookup"><span data-stu-id="f2031-169">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
-   <span data-ttu-id="f2031-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]下列情况之一时将生成消息寻址标头所需的错误：</span><span class="sxs-lookup"><span data-stu-id="f2031-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="f2031-171">消息缺少 `Sequence` 标头和 `Action` 标头。</span><span class="sxs-lookup"><span data-stu-id="f2031-171">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    -   <span data-ttu-id="f2031-172">`CreateSequence` 消息缺少 `MessageId` 标头。</span><span class="sxs-lookup"><span data-stu-id="f2031-172">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="f2031-173">`CreateSequence` 消息缺少 `ReplyTo` 标头。</span><span class="sxs-lookup"><span data-stu-id="f2031-173">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
-   <span data-ttu-id="f2031-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]生成错误操作不支持以一条消息，缺少回复`Sequence`标头和具有`Action`不是可识别的 Ws-reliable Messaging 规范中的标头。</span><span class="sxs-lookup"><span data-stu-id="f2031-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
-   <span data-ttu-id="f2031-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]生成终结点不可用，以指示终结点不会处理基于检查序列错误`CreateSequence`消息的寻址标头。</span><span class="sxs-lookup"><span data-stu-id="f2031-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="f2031-176">协议组合</span><span class="sxs-lookup"><span data-stu-id="f2031-176">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="f2031-177">与 WS-Addressing 组合</span><span class="sxs-lookup"><span data-stu-id="f2031-177">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-178"> 支持 WS-Addressing 的两种版本：WS-Addressing 2004/08 [WS-ADDR] 以及 W3C WS-Addressing 1.0 建议 [WS-ADDR-CORE] 和 [WS-ADDR-SOAP]。</span><span class="sxs-lookup"><span data-stu-id="f2031-178"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="f2031-179">尽管 WS-Reliable Messaging 规范只提及 WS-Addressing 2004/08，它并未限制要使用的 WS-Addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="f2031-179">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="f2031-180">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="f2031-180">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="f2031-181">R2101： 这两个可以与 Ws-reliable Messaging 使用 Ws-addressing 2004/08 和 Ws-addressing 1.0。</span><span class="sxs-lookup"><span data-stu-id="f2031-181">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="f2031-182">必须在给定 Ws-reliablemessaging 序列或通过使用相关的相反序列对整个使用 R2102:A 单个版本的 Ws-addressing`wsrm:Offer`机制。</span><span class="sxs-lookup"><span data-stu-id="f2031-182">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="f2031-183">与 SOAP 组合</span><span class="sxs-lookup"><span data-stu-id="f2031-183">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-184"> 支持将 SOAP 1.1 和 SOAP 1.2 与 WS-Reliable Messaging 组合使用。</span><span class="sxs-lookup"><span data-stu-id="f2031-184"> supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="f2031-185">与 WS-Security 和 WS-SecureConversation 组合</span><span class="sxs-lookup"><span data-stu-id="f2031-185">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-186"> 通过使用安全传输协议 (HTTPS)、与 WS-Security 的组合以及与 WS-Secure Conversation 的组合，为 WS-Reliable Messaging 序列提供保护。</span><span class="sxs-lookup"><span data-stu-id="f2031-186"> provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="f2031-187">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="f2031-187">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="f2031-188">R2301： 若要保护的各条消息，除了完整性 Ws-reliable Messaging 序列的完整性和保密性[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]要求必须使用 Ws-secure Conversation。</span><span class="sxs-lookup"><span data-stu-id="f2031-188">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="f2031-189">R2302:AWS-必须建立 Ws-reliable Messaging sequence(s) 前建立安全对话会话。</span><span class="sxs-lookup"><span data-stu-id="f2031-189">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
-   <span data-ttu-id="f2031-190">R2303：如果 WS-Reliable Messaging 序列生存期超过了 WS-Secure Conversation 会话的生存期，则通过使用 WS-Secure Conversation 建立的 `SecurityContextToken` 必须通过使用相应的 WS-Secure Conversation 续订绑定来进行续订。</span><span class="sxs-lookup"><span data-stu-id="f2031-190">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="f2031-191">B2304:WS 的可靠消息传递序列或一对相关的反向序列始终被绑定到单个 Ws-secureconversation 会话。</span><span class="sxs-lookup"><span data-stu-id="f2031-191">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="f2031-192">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 源在 `wsse:SecurityTokenReference` 消息的元素扩展性节中生成 `CreateSequence` 元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-192">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="f2031-193">与 Ws-secure Conversation 组合 R2305:When`CreateSequence`消息必须包含`wsse:SecurityTokenReference`元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-193">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="f2031-194">WS-Reliable Messaging WS-Policy 断言</span><span class="sxs-lookup"><span data-stu-id="f2031-194">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-195"> 使用 WS-Reliable Messaging WS-Policy 断言 `wsrm:RMAssertion` 来描述终结点功能。</span><span class="sxs-lookup"><span data-stu-id="f2031-195"> uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="f2031-196">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="f2031-196">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="f2031-197">B3001：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将 `wsrm:RMAssertion` WS-Policy 断言附加到 `wsdl:binding` 元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-198"> 同时支持附加到 `wsdl:binding` 和 `wsdl:port` 元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-198"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="f2031-199">B3002：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 支持 WS-Reliable Messaging 断言的以下可选属性，并在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement` 上提供对这些属性的控制：</span><span class="sxs-lookup"><span data-stu-id="f2031-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:</span></span>  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="f2031-200">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="f2031-200">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="f2031-201">流控制 WS-Reliable Messaging 扩展</span><span class="sxs-lookup"><span data-stu-id="f2031-201">Flow Control WS-Reliable Messaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-202"> 使用 WS-Reliable Messaging 扩展性提供对序列消息流的其他可选的更紧密控制。</span><span class="sxs-lookup"><span data-stu-id="f2031-202"> uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="f2031-203">通过设置启用流控制`ReliableSessionBindingElement`的`FlowControlEnabled``bool`属性`true`。</span><span class="sxs-lookup"><span data-stu-id="f2031-203">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``bool` property to `true`.</span></span> <span data-ttu-id="f2031-204">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="f2031-204">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="f2031-205">B4001：在启用可靠消息传递流控制时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在 `netrm:BufferRemaining` 标头的元素扩展性中生成 `SequenceAcknowledgement` 元素。</span><span class="sxs-lookup"><span data-stu-id="f2031-205">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="f2031-206">B4002：在启用可靠消息传递流控制时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不要求 `netrm:BufferRemaining` 标头中存在 `SequenceAcknowledgement` 元素，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="f2031-206">B4002: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        http://fabrikam123.com/abc  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>  
        8  
      </netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="f2031-207">B4003：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 使用 `netrm:BufferRemaining` 来指示可靠消息传递目标可以缓冲多少条新消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
-   <span data-ttu-id="f2031-208">B4004:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]可靠消息传递服务限制的传输时可靠消息传递目标应用程序不能快速接收消息的消息数量。</span><span class="sxs-lookup"><span data-stu-id="f2031-208">B4004:The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="f2031-209">可靠消息传递目标将缓冲消息，而该元素的值将下降为 0。</span><span class="sxs-lookup"><span data-stu-id="f2031-209">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
-   <span data-ttu-id="f2031-210">B4005：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 生成介于 0 和 4096（包括这两个值）之间的 `netrm:BufferRemaining` 整数值，并读取介于 0 和 `xs:int` 的 `maxInclusive` 值 214748364（包括这两个值）之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="f2031-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="f2031-211">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="f2031-211">Message Exchange Patterns</span></span>  
 <span data-ttu-id="f2031-212">本节描述了将 WS-Reliable Messaging 用于不同的消息交换模式时的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的行为。</span><span class="sxs-lookup"><span data-stu-id="f2031-212">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="f2031-213">对于每个消息交换模式，可以考虑下面的两个部署方案：</span><span class="sxs-lookup"><span data-stu-id="f2031-213">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="f2031-214">不可寻址发起方：发起方位于防火墙后面；响应方仅可以通过 HTTP 响应向发起方传递消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-214">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="f2031-215">可寻址的发起方：发起方和响应方都可以发送 HTTP 请求；换句话说，可以建立两个相反的 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="f2031-215">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="f2031-216">单向、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="f2031-216">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="f2031-217">绑定</span><span class="sxs-lookup"><span data-stu-id="f2031-217">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-218"> 通过在一个 HTTP 通道上使用一个序列的方式，提供单向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="f2031-218"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-219"> 使用 HTTP 请求将所有消息从 RMS 传输到 RMD，并使用 HTTP 响应将所有消息从 RMD 传输到 RMS。</span><span class="sxs-lookup"><span data-stu-id="f2031-219"> uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="f2031-220">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="f2031-220">CreateSequence Exchange</span></span>  
 <span data-ttu-id="f2031-221">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方生成未包含提议的 `CreateSequence` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-221">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="f2031-222">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保在创建序列之前 `CreateSequence` 不包含提议。</span><span class="sxs-lookup"><span data-stu-id="f2031-222">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="f2031-223">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方使用 `CreateSequence` 消息答复 `CreateSequenceResponse` 请求。</span><span class="sxs-lookup"><span data-stu-id="f2031-223">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="f2031-224">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="f2031-224">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="f2031-225">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方处理除 `CreateSequence` 消息和错误消息之外的所有消息答复的确认消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-225">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="f2031-226">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方总是在对序列消息和 `AckRequested` 消息的响应中生成一个独立的确认消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-226">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="f2031-227">TerminateSequence 消息</span><span class="sxs-lookup"><span data-stu-id="f2031-227">TerminateSequence message</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-228"> 将 `TerminateSequence` 视为单向操作，这意味着，HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="f2031-228"> treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="f2031-229">单向、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="f2031-229">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="f2031-230">绑定</span><span class="sxs-lookup"><span data-stu-id="f2031-230">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-231"> 提供了一种单向消息交换模式，这种模式在入站和出站 Http 通道上使用一个序列。</span><span class="sxs-lookup"><span data-stu-id="f2031-231"> provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-232"> 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-232"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="f2031-233">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="f2031-233">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="f2031-234">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="f2031-234">CreateSequence Exchange</span></span>  
 <span data-ttu-id="f2031-235">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方生成未包含提议的 `CreateSequence` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-235">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="f2031-236">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保在创建序列之前 `CreateSequence` 不包含提议。</span><span class="sxs-lookup"><span data-stu-id="f2031-236">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="f2031-237">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方在使用 `CreateSequenceResponse` 终结点引用寻址的 HTTP 请求上传输 `ReplyTo` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-237">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="f2031-238">双工、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="f2031-238">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="f2031-239">绑定</span><span class="sxs-lookup"><span data-stu-id="f2031-239">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-240"> 提供通过一个入站和一个出站 HTTP 通道使用两个序列的完全异步的双向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="f2031-240"> provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-241"> 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-241"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="f2031-242">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="f2031-242">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="f2031-243">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="f2031-243">CreateSequence Exchange</span></span>  
 <span data-ttu-id="f2031-244">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方生成包含提议的 `CreateSequence` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-244">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="f2031-245">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保在创建序列之前 `CreateSequence` 包含提议。</span><span class="sxs-lookup"><span data-stu-id="f2031-245">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-246"> 在寻址到 `CreateSequenceResponse`的 `CreateSequence` 终结点引用的 HTTP 请求上发送 `ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="f2031-246"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="f2031-247">序列生存期</span><span class="sxs-lookup"><span data-stu-id="f2031-247">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-248"> 将两个序列视为一个全双工会话。</span><span class="sxs-lookup"><span data-stu-id="f2031-248"> treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="f2031-249">生成使一个序列出错的错误时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 期望远程终结点使这两个序列出错。</span><span class="sxs-lookup"><span data-stu-id="f2031-249">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="f2031-250">读取使一个序列出错的错误时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 会使这两个序列出错。</span><span class="sxs-lookup"><span data-stu-id="f2031-250">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-251"> 可以关闭其出站序列并继续处理其入站序列上的消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-251"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="f2031-252">相反，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可以处理入站序列的关闭，并在其出站序列上继续发送消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-252">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="f2031-253">请求-答复、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="f2031-253">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="f2031-254">绑定</span><span class="sxs-lookup"><span data-stu-id="f2031-254">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-255"> 通过在一个 HTTP 通道上使用两个序列的方式，提供了单向和请求-答复消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="f2031-255"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-256"> 使用 HTTP 请求来传输请求序列的消息，并使用 HTTP 响应传输答复序列的消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-256"> uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="f2031-257">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="f2031-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="f2031-258">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方生成包含提议的 `CreateSequence` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="f2031-259">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保在创建序列之前 `CreateSequence` 包含提议。</span><span class="sxs-lookup"><span data-stu-id="f2031-259">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="f2031-260">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方使用 `CreateSequence` 消息答复 `CreateSequenceResponse` 请求。</span><span class="sxs-lookup"><span data-stu-id="f2031-260">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="f2031-261">单向消息</span><span class="sxs-lookup"><span data-stu-id="f2031-261">One-way Message</span></span>  
 <span data-ttu-id="f2031-262">为了成功地完成单向消息交换协议，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输请求序列消息，并在 HTTP 响应上接收独立的 `SequenceAcknowledgement` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-262">To complete a one-way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="f2031-263">`SequenceAcknowledgement` 必须确认已传输的消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-263">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="f2031-264">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方可以使用确认消息、错误或正文为空且具有 HTTP 202 状态代码的响应来答复请求。</span><span class="sxs-lookup"><span data-stu-id="f2031-264">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="f2031-265">双向消息</span><span class="sxs-lookup"><span data-stu-id="f2031-265">Two Way Messages</span></span>  
 <span data-ttu-id="f2031-266">为了成功地完成双向消息交换协议，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输请求序列消息，并在 HTTP 响应上接收答复序列消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-266">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="f2031-267">响应必须包含一个确认已传输的请求序列消息的 `SequenceAcknowledgement`。</span><span class="sxs-lookup"><span data-stu-id="f2031-267">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="f2031-268">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方可以使用应用程序答复、错误或正文为空且具有 HTTP 202 状态代码的响应来答复请求。</span><span class="sxs-lookup"><span data-stu-id="f2031-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="f2031-269">由于存在单向消息和应用程序答复的计时，因此请求序列消息的序列号与响应消息的序列号不相关联。</span><span class="sxs-lookup"><span data-stu-id="f2031-269">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="f2031-270">重试答复</span><span class="sxs-lookup"><span data-stu-id="f2031-270">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-271"> 依赖于 HTTP 请求-答复关联来进行双向消息交换协议关联。</span><span class="sxs-lookup"><span data-stu-id="f2031-271"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="f2031-272">因此，在确认请求序列消息时（而不是在 HTTP 响应携带确认消息、用户消息或错误时），[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方不会停止重试请求序列消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-272">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="f2031-273">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方重试次数依赖于与答复相关联的请求的 HTTP 请求路线。</span><span class="sxs-lookup"><span data-stu-id="f2031-273">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="f2031-274">LastMessage 交换</span><span class="sxs-lookup"><span data-stu-id="f2031-274">LastMessage Exchange</span></span>  
 <span data-ttu-id="f2031-275">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求路线上生成并传输正文为空的最后一条消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-276"> 需要一个响应，但忽略实际响应消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-276"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="f2031-277">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方使用答复序列的正文为空的最后一条消息答复请求序列的正文为空的最后一条消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-277">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="f2031-278">如果 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方接收到最后一条消息并且其中的操作 URI 不为 http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage 中，则 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 使用最后一条消息进行答复。</span><span class="sxs-lookup"><span data-stu-id="f2031-278">If the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder receives a last message in which the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] replies with a last message.</span></span> <span data-ttu-id="f2031-279">在双向消息交换协议中，最后一条消息携带应用程序消息；在单向消息交换协议中，最后一条消息为空。</span><span class="sxs-lookup"><span data-stu-id="f2031-279">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="f2031-280">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方不要求确认答复序列的正文为空的最后一条消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-280">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="f2031-281">TerminateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="f2031-281">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="f2031-282">在所有请求已接收一个有效答复时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求路线上生成并传输请求序列的 `TerminateSequence` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-282">When all requests have received a valid reply, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-283"> 需要一个响应，但忽略实际响应消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-283"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="f2031-284">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方使用答复序列的 `TerminateSequence` 消息答复请求序列的 `TerminateSequence` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-284">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="f2031-285">在正常的关闭序列中，两个 `TerminateSequence` 消息都携带一个完整范围的 `SequenceAcknowledgement`。</span><span class="sxs-lookup"><span data-stu-id="f2031-285">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="f2031-286">请求/答复、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="f2031-286">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="f2031-287">绑定</span><span class="sxs-lookup"><span data-stu-id="f2031-287">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-288"> 提供了通过一个入站和一个出站 HTTP 通道使用两个序列的请求-答复消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="f2031-288"> provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-289"> 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-289"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="f2031-290">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="f2031-290">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="f2031-291">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="f2031-291">CreateSequence Exchange</span></span>  
 <span data-ttu-id="f2031-292">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方生成包含提议的 `CreateSequence` 消息。</span><span class="sxs-lookup"><span data-stu-id="f2031-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="f2031-293">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保在创建序列之前 `CreateSequence` 包含提议。</span><span class="sxs-lookup"><span data-stu-id="f2031-293">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f2031-294"> 在寻址到 `CreateSequenceResponse`的 `CreateSequence` 终结点引用的 HTTP 请求上发送 `ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="f2031-294"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="f2031-295">请求/答复关联</span><span class="sxs-lookup"><span data-stu-id="f2031-295">Request/Reply Correlation</span></span>  
 <span data-ttu-id="f2031-296">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方确保所有应用程序请求消息都具有一个 `MessageId` 和一个 `ReplyTo` 终结点引用。</span><span class="sxs-lookup"><span data-stu-id="f2031-296">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="f2031-297">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在每个应用程序请求消息上应用 `CreateSequence` 消息的 `ReplyTo` 终结点引用。</span><span class="sxs-lookup"><span data-stu-id="f2031-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="f2031-298">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方要求传入的请求消息具有一个 `MessageId` 和一个 `ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="f2031-298">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="f2031-299">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保两个 `CreateSequence` 的终结点引用的 URI 与所有应用程序请求消息相同。</span><span class="sxs-lookup"><span data-stu-id="f2031-299">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
