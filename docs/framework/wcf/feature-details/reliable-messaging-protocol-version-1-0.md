---
title: 可靠消息传送协议版本 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: 857bbbf9ffa1311c38cfc007e0cdc6bde06d6284
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617569"
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="bb1e2-102">可靠消息传送协议版本 1.0</span><span class="sxs-lookup"><span data-stu-id="bb1e2-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="bb1e2-103">本主题介绍 Windows Communication Foundation (WCF) 实现的详细信息，为 Ws-reliable Messaging 2005 年 2 月 （版本 1.0） 协议需要使用 HTTP 传输进行互操作。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="bb1e2-104">WCF 遵循 Ws-reliable Messaging 规范的约束和澄清，本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-104">WCF follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="bb1e2-105">请注意，WS-ReliableMessaging 版本 1.0 协议是从 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 开始实现的。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="bb1e2-106">Ws-reliable Messaging February 2005 协议实现中情况下，WCF <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-106">The WS-Reliable Messaging February 2005 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="bb1e2-107">为方便起见，本主题使用以下角色：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-107">For convenience, the topic uses the following roles:</span></span>  
  
- <span data-ttu-id="bb1e2-108">发起方：启动 WS-Reliable Message 序列创建的客户端</span><span class="sxs-lookup"><span data-stu-id="bb1e2-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
- <span data-ttu-id="bb1e2-109">响应方：接收发起方的请求的服务</span><span class="sxs-lookup"><span data-stu-id="bb1e2-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="bb1e2-110">本文档使用下表中的前缀和命名空间。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="bb1e2-111">前缀</span><span class="sxs-lookup"><span data-stu-id="bb1e2-111">Prefix</span></span>|<span data-ttu-id="bb1e2-112">命名空间</span><span class="sxs-lookup"><span data-stu-id="bb1e2-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="bb1e2-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="bb1e2-113">wsrm</span></span>|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|<span data-ttu-id="bb1e2-114">netrm</span><span class="sxs-lookup"><span data-stu-id="bb1e2-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="bb1e2-115">秒</span><span class="sxs-lookup"><span data-stu-id="bb1e2-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="bb1e2-116">wsa</span><span class="sxs-lookup"><span data-stu-id="bb1e2-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="bb1e2-117">wsse</span><span class="sxs-lookup"><span data-stu-id="bb1e2-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a><span data-ttu-id="bb1e2-118">消息</span><span class="sxs-lookup"><span data-stu-id="bb1e2-118">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="bb1e2-119">序列建立消息</span><span class="sxs-lookup"><span data-stu-id="bb1e2-119">Sequence Establishment Messages</span></span>  
 <span data-ttu-id="bb1e2-120">WCF 实现`CreateSequence`和`CreateSequenceResponse`消息以建立可靠的消息序列。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-120">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="bb1e2-121">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-121">The following constraints apply:</span></span>  
  
- <span data-ttu-id="bb1e2-122">B1101:WCF 发起方不会生成可选的 Expires 元素`CreateSequence`消息，或者在情况时`CreateSequence`消息中包含`Offer`元素中，可选`Expires`中的元素`Offer`元素。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-122">B1101: The WCF Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
- <span data-ttu-id="bb1e2-123">B1102:访问时`CreateSequence`消息，WCF`Responder`发送和接收都`Expires`元素如果它们存在，但不使用它们的值。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-123">B1102: When accessing the `CreateSequence` message, the WCF`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="bb1e2-124">WS-Reliable Messaging 引入了 `Offer` 机制来建立两个形成会话的反向相关的序列。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-124">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
- <span data-ttu-id="bb1e2-125">R1103:如果`CreateSequence`包含`Offer`元素中，可靠消息响应方必须接受序列并使用响应`CreateSequenceResponse`，其中包含`wsrm:Accept`元素形成两个相关反向序列或拒绝`CreateSequence`请求。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-125">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
- <span data-ttu-id="bb1e2-126">R1104：在反向序列上流动的 `SequenceAcknowledgement` 和应用程序消息必须发送到 `ReplyTo` 的 `CreateSequence` 终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-126">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
- <span data-ttu-id="bb1e2-127">R1105：`AcksTo` 中的 `ReplyTo` 和 `CreateSequence` 终结点引用必须具有与八进制识别匹配的地址值。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-127">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="bb1e2-128">WCF 响应方验证的 URI 部分`AcksTo`和`ReplyTo`创建序列之前 Epr 是否相同。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-128">The WCF Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
- <span data-ttu-id="bb1e2-129">R1106：`AcksTo` 中的 `ReplyTo` 和 `CreateSequence` 终结点引用应具有相同的引用参数集。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-129">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     <span data-ttu-id="bb1e2-130">WCF 不强制但假定的该 [引用参数]`AcksTo`并`ReplyTo`上`CreateSequence`相同，并且使用 [reference parameters] 从`ReplyTo`确认和相反序列消息的终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-130">WCF does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
- <span data-ttu-id="bb1e2-131">R1107:使用建立的两个相反序列时`Offer`机制`SequenceAcknowledgement`和反向序列上流动的应用程序消息必须发送到`ReplyTo`终结点引用`CreateSequence`。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-131">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
- <span data-ttu-id="bb1e2-132">R1108:使用 Offer 机制建立两个相反序列时`[address]`的属性`wsrm:AcksTo`终结点引用的子元素`wsrm:Accept`元素的`CreateSequenceResponse`必须匹配识别字节的目标URI`CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="bb1e2-132">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
- <span data-ttu-id="bb1e2-133">R1109:使用建立的两个相反序列时`Offer`机制、 发送的发起方和响应方的消息的确认消息必须发送到相同的终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-133">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     <span data-ttu-id="bb1e2-134">WCF 使用 Ws-reliable Messaging 在发起方和响应方之间建立可靠会话。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-134">WCF uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="bb1e2-135">WCF 的 Ws-reliable Messaging 实现提供了可靠会话为单向、 请求-答复和完全双工消息传递模式。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-135">WCF's WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="bb1e2-136">Ws-reliable Messaging`Offer`上的机制`CreateSequence` / `CreateSequenceResponse` ，便可以建立两个相关的相反序列，并提供适合于所有消息终结点的会话协议。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-136">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="bb1e2-137">因为 WCF 提供了会话包括会话完整性的端到端保护的安全保障，是用于确保适用于同一参与方的消息到达同一目标。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-137">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="bb1e2-138">这也允许在应用程序消息上捎带序列确认消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-138">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="bb1e2-139">因此，约束 R1104、 R1105 和 R1108 适用于 WCF。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-139">Therefore, constraints R1104, R1105, and R1108 apply to WCF.</span></span>  
  
 <span data-ttu-id="bb1e2-140">`CreateSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-140">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="bb1e2-141">`CreateSequenceResponse` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-141">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="sequence"></a><span data-ttu-id="bb1e2-142">序列</span><span class="sxs-lookup"><span data-stu-id="bb1e2-142">Sequence</span></span>  
 <span data-ttu-id="bb1e2-143">以下是适用于序列的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-143">The following is a list of constraints that apply to sequences:</span></span>  
  
- <span data-ttu-id="bb1e2-144">B1201:WCF 生成，并访问序列号不高于`xs:long`的最大包含值 9223372036854775807。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-144">B1201:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
- <span data-ttu-id="bb1e2-145">B1202:WCF 始终会生成正文为空的最后一个消息使用的操作 URI 的`http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-145">B1202:WCF always generates an empty-bodied last message with the action URI of `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>  
  
- <span data-ttu-id="bb1e2-146">B1203:WCF 接收和传送一条带有包含的序列标头`LastMessage`元素，只要操作 URI 不是`http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-146">B1203: WCF receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>  
  
 <span data-ttu-id="bb1e2-147">Sequence 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-147">An example of a Sequence Header.</span></span>  
  
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
  
### <a name="ackrequested-header"></a><span data-ttu-id="bb1e2-148">AckRequested 标头</span><span class="sxs-lookup"><span data-stu-id="bb1e2-148">AckRequested Header</span></span>  
 <span data-ttu-id="bb1e2-149">WCF 使用`AckRequested`标头，因为保持活动状态的机制。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-149">WCF uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="bb1e2-150">WCF 不会生成可选`MessageNumber`元素。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-150">WCF does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="bb1e2-151">收到的消息`AckRequested`包含的标头`MessageNumber`元素中，WCF 将忽略`MessageNumber`元素的值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-151">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, WCF ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="bb1e2-152">SequenceAcknowledgement 标头</span><span class="sxs-lookup"><span data-stu-id="bb1e2-152">SequenceAcknowledgement Header</span></span>  
 <span data-ttu-id="bb1e2-153">WCF 将非法携带机制用于在 Ws-reliable Messaging 中提供的序列确认。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-153">WCF uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
- <span data-ttu-id="bb1e2-154">R1401:使用建立的两个相反序列时`Offer`机制，`SequenceAcknowledgement`可能传输到目标接收方的任何应用程序消息中包括标头。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-154">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
- <span data-ttu-id="bb1e2-155">B1402:当 WCF 必须之前生成确认消息接收任何序列消息 (例如，若要满足`AckRequested`消息)，WCF 生成`SequenceAcknowledgement`标题，其中包含范围 0-0，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-155">B1402: When WCF must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), WCF generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
- <span data-ttu-id="bb1e2-156">B1403:WCF 不会生成`SequenceAcknowledgement`包含的标头`Nack`元素，但支持`Nack`元素。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-156">B1403: WCF does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="bb1e2-157">WS-ReliableMessaging 错误</span><span class="sxs-lookup"><span data-stu-id="bb1e2-157">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="bb1e2-158">下面是适用于 WCF 实现的 WS 可靠消息传送错误的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-158">The following is a list of constraints that apply to the WCF implementation of WS-Reliable Messaging faults:</span></span>  
  
- <span data-ttu-id="bb1e2-159">B1501:WCF 不会生成`MessageNumberRollover`故障。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-159">B1501: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
- <span data-ttu-id="bb1e2-160">B1502:WCF 终结点可能生成`CreateSequenceRefused`错误，如规范中所述。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-160">B1502:WCF endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
- <span data-ttu-id="bb1e2-161">B1503:When 服务终结点达到其连接限制，无法处理新连接时，WCF 将生成额外`CreateSequenceRefused`错误子代码`netrm:ConnectionLimitReached`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-161">B1503:When the service endpoint reaches its connection limit and cannot process new connections, WCF generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="bb1e2-162">WS-Addressing 错误</span><span class="sxs-lookup"><span data-stu-id="bb1e2-162">WS-Addressing Faults</span></span>  
 <span data-ttu-id="bb1e2-163">因为 Ws-reliable Messaging 使用 Ws-addressing，所以 WCF Ws-reliable Messaging 实现可能生成 Ws-addressing 错误。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-163">Because WS-Reliable Messaging uses WS-Addressing, WCF WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="bb1e2-164">本部分介绍了在 Ws-reliable Messaging 层显式生成 WCF Ws-addressing 错误：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-164">This section covers the WS-Addressing faults that WCF explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
- <span data-ttu-id="bb1e2-165">B1601:WCF 生成错误消息寻址标头需要以下项之一为 true 时：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-165">B1601:WCF generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    - <span data-ttu-id="bb1e2-166">消息缺少 `Sequence` 标头和 `Action` 标头。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-166">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    - <span data-ttu-id="bb1e2-167">`CreateSequence` 消息缺少 `MessageId` 标头。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-167">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    - <span data-ttu-id="bb1e2-168">`CreateSequence` 消息缺少 `ReplyTo` 标头。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-168">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
- <span data-ttu-id="bb1e2-169">B1602:WCF 生成缺少的消息的操作不受支持容错`Sequence`标头和具有`Action`不是可识别的 Ws-reliable Messaging 规范中的标头。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-169">B1602:WCF generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
- <span data-ttu-id="bb1e2-170">B1603:WCF 生成终结点不可用来指示终结点不会处理序列基于检查错误`CreateSequence`消息的寻址标头。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-170">B1603:WCF generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="bb1e2-171">协议组合</span><span class="sxs-lookup"><span data-stu-id="bb1e2-171">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="bb1e2-172">与 WS-Addressing 组合</span><span class="sxs-lookup"><span data-stu-id="bb1e2-172">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="bb1e2-173">WCF 支持两个版本的 Ws-addressing:的 Ws-addressing 2004/08 [WS-ADDR] 以及 W3C Ws-addressing 1.0 建议 [WS ADDR 核] 和 [WS ADDR SOAP]。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-173">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="bb1e2-174">尽管 WS-Reliable Messaging 规范只提及 WS-Addressing 2004/08，它并未限制要使用的 WS-Addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-174">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="bb1e2-175">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-175">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="bb1e2-176">R2101： 这两个可以与 Ws-reliable Messaging 使用 Ws-addressing 2004/08 和 Ws-addressing 1.0。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-176">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
- <span data-ttu-id="bb1e2-177">R2102:A 单一版本的 Ws-addressing 必须在整个给定的 Ws-reliable Messaging 序列或通过使用相关的反向序列对`wsrm:Offer`机制。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-177">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="bb1e2-178">与 SOAP 组合</span><span class="sxs-lookup"><span data-stu-id="bb1e2-178">Composition with SOAP</span></span>  
 <span data-ttu-id="bb1e2-179">WCF 支持使用 SOAP 1.1 和 SOAP 1.2 与 Ws-reliable Messaging。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-179">WCF supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="bb1e2-180">与 WS-Security 和 WS-SecureConversation 组合</span><span class="sxs-lookup"><span data-stu-id="bb1e2-180">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="bb1e2-181">WCF 提供了通过使用 Ws-secure Conversation 使用安全传输协议 (HTTPS)、 与 Ws-security 的组合和组合的 Ws-reliable Messaging 序列的保护。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-181">WCF provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="bb1e2-182">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-182">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="bb1e2-183">R2301： 为了保护单个消息的 Ws-reliable Messaging 序列的完整性的完整性和保密性，WCF 需要必须使用 Ws-secure Conversation。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-183">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
- <span data-ttu-id="bb1e2-184">R2302:AWS-必须在建立 Ws-reliable Messaging 序列之前建立安全对话会话中。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-184">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
- <span data-ttu-id="bb1e2-185">R2303:如果 Ws-reliable Messaging 序列生存期超过了 Ws-secure Conversation 会话的生存期，`SecurityContextToken`建立通过使用 Ws-secure Conversation 必须续订通过使用相应的 Ws-secure Conversation 续订绑定。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-185">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
- <span data-ttu-id="bb1e2-186">B2304:WS-Reliable Messaging 序列或一对相关的相反序列始终绑定到单个 Ws-secureconversation 会话。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-186">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="bb1e2-187">WCF 源生成`wsse:SecurityTokenReference`元素中的元素扩展性节`CreateSequence`消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-187">The WCF source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
- <span data-ttu-id="bb1e2-188">与 Ws-secure Conversation R2305:When`CreateSequence`消息必须包含`wsse:SecurityTokenReference`元素。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-188">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="bb1e2-189">WS-Reliable Messaging WS-Policy 断言</span><span class="sxs-lookup"><span data-stu-id="bb1e2-189">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="bb1e2-190">WCF 使用 Ws-reliable Messaging Ws-policy 断言`wsrm:RMAssertion`来描述终结点功能。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-190">WCF uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="bb1e2-191">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-191">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="bb1e2-192">B3001:WCF 将附加`wsrm:RMAssertion`Ws-policy 断言到`wsdl:binding`元素。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-192">B3001: WCF attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="bb1e2-193">WCF 支持这两个附件`wsdl:binding`和`wsdl:port`元素。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-193">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
- <span data-ttu-id="bb1e2-194">B3002:WCF 支持 Ws-reliable Messaging 断言的以下可选属性，并在 WCF 提供对它们的控制`ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="bb1e2-194">B3002: WCF supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the WCF`ReliableMessagingBindingElement`:</span></span>  
  
    - `wsrm:InactivityTimeout`  
  
    - `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="bb1e2-195">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-195">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="bb1e2-196">流控制 WS-Reliable Messaging 扩展</span><span class="sxs-lookup"><span data-stu-id="bb1e2-196">Flow Control WS-Reliable Messaging Extension</span></span>  
 <span data-ttu-id="bb1e2-197">WCF 使用 Ws-reliable Messaging 扩展性提供对序列消息流的可选更紧密控制。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-197">WCF uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="bb1e2-198">设置启用流控制<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-198">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="bb1e2-199">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-199">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="bb1e2-200">B4001:当启用可靠消息流控制时，WCF 生成`netrm:BufferRemaining`元素的元素扩展性中`SequenceAcknowledgement`标头。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-200">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
- <span data-ttu-id="bb1e2-201">B4002:启用可靠消息流控制时，WCF 不需要`netrm:BufferRemaining`元素出现在`SequenceAcknowledgement`标头，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-201">B4002: When Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
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
  
- <span data-ttu-id="bb1e2-202">B4003:WCF 使用`netrm:BufferRemaining`以指示多少新消息的可靠消息传递目标可以缓冲。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-202">B4003: WCF uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
- <span data-ttu-id="bb1e2-203">B4004: WCF 可靠消息传递服务限制的可靠消息传递目标应用程序不能快速接收消息时，传输的消息数。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-203">B4004:The WCF Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="bb1e2-204">可靠消息传递目标将缓冲消息，而该元素的值将下降为 0。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-204">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
- <span data-ttu-id="bb1e2-205">B4005:WCF 将生成`netrm:BufferRemaining`整数值介于 0 和 4096 （含)，并读取介于 0 的整数值和`xs:int`的`maxInclusive`值 214748364 （含)。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-205">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="bb1e2-206">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="bb1e2-206">Message Exchange Patterns</span></span>  
 <span data-ttu-id="bb1e2-207">Ws-reliable Messaging 用于不同消息交换模式时，本部分将介绍 WCF 的行为。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-207">This section describes WCF's behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="bb1e2-208">对于每个消息交换模式，可以考虑下面的两个部署方案：</span><span class="sxs-lookup"><span data-stu-id="bb1e2-208">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
- <span data-ttu-id="bb1e2-209">不可寻址的发起方：发起方位于防火墙;响应方可以将消息传递到发起方，仅在 HTTP 响应上。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-209">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
- <span data-ttu-id="bb1e2-210">可寻址的发起方：发起方和响应方都可以发送 HTTP 请求;换而言之，可以建立两个反向 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-210">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="bb1e2-211">单向、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="bb1e2-211">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="bb1e2-212">绑定</span><span class="sxs-lookup"><span data-stu-id="bb1e2-212">Binding</span></span>  
 <span data-ttu-id="bb1e2-213">WCF 提供了通过一个 HTTP 通道使用一个序列的单向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-213">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="bb1e2-214">WCF 使用 HTTP 请求传输所有消息从 RMS 到 RMD，并在 HTTP 响应向 RMS 的所有消息从 RMD 都都传输。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-214">WCF uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="bb1e2-215">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="bb1e2-215">CreateSequence Exchange</span></span>  
 <span data-ttu-id="bb1e2-216">WCF 发起方生成`CreateSequence`与任何产品/服务的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-216">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="bb1e2-217">WCF 响应方确保`CreateSequence`不包含提议创建序列之前。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-217">The WCF Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="bb1e2-218">WCF 响应方答复`CreateSequence`请求与`CreateSequenceResponse`消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-218">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="bb1e2-219">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="bb1e2-219">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="bb1e2-220">WCF 发起方处理除之外的所有消息的确认答复`CreateSequence`消息和错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-220">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="bb1e2-221">WCF 响应方始终对这两个序列的响应中生成一个独立的确认和`AckRequested`消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-221">The WCF Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="bb1e2-222">TerminateSequence 消息</span><span class="sxs-lookup"><span data-stu-id="bb1e2-222">TerminateSequence message</span></span>  
 <span data-ttu-id="bb1e2-223">WCF 将`TerminateSequence`为单向操作，这意味着在 HTTP 响应具有空的正文和 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-223">WCF treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="bb1e2-224">单向、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="bb1e2-224">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="bb1e2-225">绑定</span><span class="sxs-lookup"><span data-stu-id="bb1e2-225">Binding</span></span>  
 <span data-ttu-id="bb1e2-226">WCF 提供了一个序列通过一个入站和出站 Http 通道使用的单向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-226">WCF provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> <span data-ttu-id="bb1e2-227">WCF 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-227">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="bb1e2-228">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-228">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="bb1e2-229">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="bb1e2-229">CreateSequence Exchange</span></span>  
 <span data-ttu-id="bb1e2-230">WCF 发起方生成`CreateSequence`与任何产品/服务的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-230">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="bb1e2-231">WCF 响应方确保`CreateSequence`不包含提议创建序列之前。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-231">The WCF Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="bb1e2-232">WCF 响应方传输`CreateSequenceResponse`HTTP 请求上的消息发送与`ReplyTo`终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-232">The WCF Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="bb1e2-233">双工、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="bb1e2-233">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="bb1e2-234">绑定</span><span class="sxs-lookup"><span data-stu-id="bb1e2-234">Binding</span></span>  
 <span data-ttu-id="bb1e2-235">WCF 提供了通过一个入站和出站 HTTP 通道使用两个序列的完全异步的双向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-235">WCF provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="bb1e2-236">WCF 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-236">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="bb1e2-237">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-237">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="bb1e2-238">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="bb1e2-238">CreateSequence Exchange</span></span>  
 <span data-ttu-id="bb1e2-239">WCF 发起方生成`CreateSequence`与产品/服务的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-239">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="bb1e2-240">WCF 响应方确保`CreateSequence`具有创建序列之前的产品/服务。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-240">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="bb1e2-241">WCF 发送`CreateSequenceResponse`HTTP 请求上往`CreateSequence`的`ReplyTo`终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-241">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="bb1e2-242">序列生存期</span><span class="sxs-lookup"><span data-stu-id="bb1e2-242">Sequence Lifetime</span></span>  
 <span data-ttu-id="bb1e2-243">WCF 将两个序列视为一个全双工会话。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-243">WCF treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="bb1e2-244">在生成的错误，使一个序列，WCF 需要要故障这两个序列的远程终结点。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-244">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="bb1e2-245">在读取的错误，使一个序列，WCF 会使故障这两个序列。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-245">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="bb1e2-246">WCF 可以关闭其出站序列并继续处理其入站序列上的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-246">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="bb1e2-247">相反，WCF 可以处理入站序列的关闭和继续其出站序列上发送消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-247">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="bb1e2-248">请求-答复、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="bb1e2-248">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="bb1e2-249">绑定</span><span class="sxs-lookup"><span data-stu-id="bb1e2-249">Binding</span></span>  
 <span data-ttu-id="bb1e2-250">WCF 提供了单向和请求-答复消息交换模式使用两个序列通过一个 HTTP 通道。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-250">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="bb1e2-251">WCF 使用 HTTP 请求来传输请求序列消息，并使用 HTTP 响应传输答复序列的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-251">WCF uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="bb1e2-252">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="bb1e2-252">CreateSequence Exchange</span></span>  
 <span data-ttu-id="bb1e2-253">WCF 发起方生成`CreateSequence`与产品/服务的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-253">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="bb1e2-254">WCF 响应方确保`CreateSequence`具有创建序列之前的产品/服务。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-254">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="bb1e2-255">WCF 响应方答复`CreateSequence`请求与`CreateSequenceResponse`消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-255">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="bb1e2-256">单向消息</span><span class="sxs-lookup"><span data-stu-id="bb1e2-256">One-way Message</span></span>  
 <span data-ttu-id="bb1e2-257">若要成功完成单向消息交换协议，WCF 发起方传输请求序列消息在 HTTP 请求和接收独立`SequenceAcknowledgement`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-257">To complete a one-way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="bb1e2-258">`SequenceAcknowledgement` 必须确认已传输的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-258">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="bb1e2-259">WCF 响应来答复请求确认、 错误或正文为空且 HTTP 202 状态代码的响应。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-259">The WCF Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="bb1e2-260">双向消息</span><span class="sxs-lookup"><span data-stu-id="bb1e2-260">Two Way Messages</span></span>  
 <span data-ttu-id="bb1e2-261">若要成功地完成双向消息交换协议，WCF 发起方传输请求序列消息在 HTTP 请求和接收答复序列消息在 HTTP 响应上。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-261">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="bb1e2-262">响应必须包含一个确认已传输的请求序列消息的 `SequenceAcknowledgement`。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-262">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="bb1e2-263">WCF 响应来答复请求与应用程序答复、 错误或正文为空且 HTTP 202 状态代码的响应。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-263">The WCF Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="bb1e2-264">由于存在单向消息和应用程序答复的计时，因此请求序列消息的序列号与响应消息的序列号不相关联。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-264">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="bb1e2-265">重试答复</span><span class="sxs-lookup"><span data-stu-id="bb1e2-265">Retrying Replies</span></span>  
 <span data-ttu-id="bb1e2-266">WCF 依赖于双向消息交换协议关联的 HTTP 请求-答复相关。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-266">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="bb1e2-267">因此，WCF 发起方不会停止重试请求序列消息，而不是在 HTTP 响应携带确认、 用户消息或错误时确认请求序列消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-267">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="bb1e2-268">WCF 响应方重试向其答复相关联的请求的 HTTP 请求路线上的答复。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-268">The WCF Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="bb1e2-269">LastMessage 交换</span><span class="sxs-lookup"><span data-stu-id="bb1e2-269">LastMessage Exchange</span></span>  
 <span data-ttu-id="bb1e2-270">WCF 发起方生成并传输空的最后一条 HTTP 请求路线上。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-270">The WCF Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> <span data-ttu-id="bb1e2-271">WCF 需要一个响应，但忽略实际响应消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-271">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="bb1e2-272">WCF 响应方答复请求序列的正文为空的最后一个消息使用答复序列的正文为空的最后一条消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-272">The WCF Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="bb1e2-273">如果 WCF 响应方接收在其中操作 URI 不是最后一条消息`http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`，WCF 使用最后一条消息进行回复。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-273">If the WCF Responder receives a last message in which the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF replies with a last message.</span></span> <span data-ttu-id="bb1e2-274">在双向消息交换协议中，最后一条消息携带应用程序消息；在单向消息交换协议中，最后一条消息为空。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-274">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="bb1e2-275">WCF 响应方不需要确认答复序列的正文为空的最后一条消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-275">The WCF Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="bb1e2-276">TerminateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="bb1e2-276">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="bb1e2-277">在所有请求已都接收一个有效答复时，WCF 发起方生成并传输请求序列的`TerminateSequence`HTTP 请求路线上的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-277">When all requests have received a valid reply, the WCF Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> <span data-ttu-id="bb1e2-278">WCF 需要一个响应，但忽略实际响应消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-278">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="bb1e2-279">WCF 响应方答复请求序列`TerminateSequence`使用答复序列消息`TerminateSequence`消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-279">The WCF Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="bb1e2-280">在正常的关闭序列中，两个 `TerminateSequence` 消息都携带一个完整范围的 `SequenceAcknowledgement`。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-280">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="bb1e2-281">请求/答复、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="bb1e2-281">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="bb1e2-282">绑定</span><span class="sxs-lookup"><span data-stu-id="bb1e2-282">Binding</span></span>  
 <span data-ttu-id="bb1e2-283">WCF 提供了两个序列通过一个入站和出站 HTTP 通道使用的请求-答复消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-283">WCF provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="bb1e2-284">WCF 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-284">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="bb1e2-285">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-285">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="bb1e2-286">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="bb1e2-286">CreateSequence Exchange</span></span>  
 <span data-ttu-id="bb1e2-287">WCF 发起方生成`CreateSequence`与产品/服务的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-287">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="bb1e2-288">WCF 响应方确保`CreateSequence`具有创建序列之前的产品/服务。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-288">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="bb1e2-289">WCF 发送`CreateSequenceResponse`HTTP 请求上往`CreateSequence`的`ReplyTo`终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-289">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="bb1e2-290">请求/答复关联</span><span class="sxs-lookup"><span data-stu-id="bb1e2-290">Request/Reply Correlation</span></span>  
 <span data-ttu-id="bb1e2-291">WCF 发起方确保所有应用程序请求消息都具有`MessageId`和一个`ReplyTo`终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-291">The WCF Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="bb1e2-292">WCF 发起方适用`CreateSequence`消息的`ReplyTo`上每个应用程序请求消息的终结点引用。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-292">The WCF Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="bb1e2-293">WCF 响应方要求传入的请求消息具有`MessageId`和一个`ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-293">The WCF Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="bb1e2-294">WCF 响应方确保两个终结点引用的 URI`CreateSequence`和应用程序请求的所有消息都都完全相同。</span><span class="sxs-lookup"><span data-stu-id="bb1e2-294">The WCF Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
