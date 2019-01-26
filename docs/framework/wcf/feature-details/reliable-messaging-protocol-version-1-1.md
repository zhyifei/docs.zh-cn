---
title: 可靠消息传送协议版本 1.1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 6b8732e0b48797c219b53bb8bf70e1ba57e25c42
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55073221"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="74371-102">可靠消息传送协议版本 1.1</span><span class="sxs-lookup"><span data-stu-id="74371-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="74371-103">本主题介绍 Windows Communication Foundation (WCF) 实现的详细信息用于 WS-ReliableMessaging 2007 年 2 月 （版本 1.1） 协议需要使用 HTTP 传输进行互操作。</span><span class="sxs-lookup"><span data-stu-id="74371-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="74371-104">WCF 遵循 WS-ReliableMessaging 规范的约束和澄清，本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="74371-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="74371-105">请注意，从开始实现 WS-ReliableMessaging 版本 1.1 协议[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="74371-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="74371-106">WS-ReliableMessaging 2007 年 2 月在情况下，WCF 中实现协议<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="74371-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="74371-107">为方便起见，本主题使用以下角色：</span><span class="sxs-lookup"><span data-stu-id="74371-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="74371-108">发起方：启动 Ws-reliable Message 序列创建的客户端。</span><span class="sxs-lookup"><span data-stu-id="74371-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="74371-109">响应方：接收发起方的请求的服务。</span><span class="sxs-lookup"><span data-stu-id="74371-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="74371-110">本文档使用下表中的前缀和命名空间。</span><span class="sxs-lookup"><span data-stu-id="74371-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="74371-111">前缀</span><span class="sxs-lookup"><span data-stu-id="74371-111">Prefix</span></span>|<span data-ttu-id="74371-112">命名空间</span><span class="sxs-lookup"><span data-stu-id="74371-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="74371-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="74371-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|<span data-ttu-id="74371-114">netrm</span><span class="sxs-lookup"><span data-stu-id="74371-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="74371-115">秒</span><span class="sxs-lookup"><span data-stu-id="74371-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="74371-116">wsa</span><span class="sxs-lookup"><span data-stu-id="74371-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="74371-117">wsse</span><span class="sxs-lookup"><span data-stu-id="74371-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="74371-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="74371-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|<span data-ttu-id="74371-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="74371-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|<span data-ttu-id="74371-120">wsp</span><span class="sxs-lookup"><span data-stu-id="74371-120">wsp</span></span>|<span data-ttu-id="74371-121">（WS-Policy 1.2 或 WS-Policy 1.5）</span><span class="sxs-lookup"><span data-stu-id="74371-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="74371-122">消息</span><span class="sxs-lookup"><span data-stu-id="74371-122">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="74371-123">序列创建</span><span class="sxs-lookup"><span data-stu-id="74371-123">Sequence Creation</span></span>  
 <span data-ttu-id="74371-124">WCF 实现`CreateSequence`和`CreateSequenceResponse`消息以建立可靠消息序列。</span><span class="sxs-lookup"><span data-stu-id="74371-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="74371-125">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="74371-125">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="74371-126">B1101:WCF 发起方将使用相同的终结点引用作为`CreateSequence`消息的`ReplyTo`，`AcksTo`和`Offer/Endpoint`。</span><span class="sxs-lookup"><span data-stu-id="74371-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="74371-127">R1102:`AcksTo`，`ReplyTo`并`Offer/Endpoint`终结点引用中`CreateSequence`消息必须具有相同的字符串表示形式的地址值，以便它们与八进制形式匹配。</span><span class="sxs-lookup"><span data-stu-id="74371-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="74371-128">WCF 响应方验证的 URI 部分`AcksTo`，`ReplyTo`和`Endpoint`创建序列之前终结点引用是相同。</span><span class="sxs-lookup"><span data-stu-id="74371-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="74371-129">R1103:`AcksTo`，`ReplyTo`并`Offer/Endpoint`终结点引用中`CreateSequence`消息应具有一组相同的引用参数。</span><span class="sxs-lookup"><span data-stu-id="74371-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="74371-130">WCF 并不强制但假定该引用的参数`AcksTo`，`ReplyTo`并`Offer/Endpoint`终结点引用上`CreateSequence`相同，并且使用从引用参数`ReplyTo`终结点引用确认和相反序列消息。</span><span class="sxs-lookup"><span data-stu-id="74371-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="74371-131">B1104:WCF 发起方不会生成可选`Expires`或`Offer/Expires`中的元素`CreateSequence`消息。</span><span class="sxs-lookup"><span data-stu-id="74371-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="74371-132">B1105:访问时`CreateSequence`消息时，WCF 响应方使用`Expires`中的值`CreateSequence`元素作为`Expires`中的值`CreateSequenceResponse`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="74371-133">否则为 WCF 响应方读取并忽略`Expires`和`Offer/Expires`值。</span><span class="sxs-lookup"><span data-stu-id="74371-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="74371-134">B1106:访问时`CreateSequenceResponse`消息时，WCF 发起方读取可选`Expires`值，但不使用它。</span><span class="sxs-lookup"><span data-stu-id="74371-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="74371-135">B1107:WCF 发起方和响应方始终生成可选`IncompleteSequenceBehavior`中的元素`CreateSequence/Offer`和`CreateSequenceResponse`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="74371-136">B1108:仅使用 WCF`DiscardFollowingFirstGap`并`NoDiscard`中的值以`IncompleteSequenceBehavior`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="74371-137">WS-ReliableMessaging 利用 `Offer` 机制建立构成会话的两个相反的相关序列。</span><span class="sxs-lookup"><span data-stu-id="74371-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="74371-138">B1109:如果`CreateSequence`包含`Offer`元素中，一种方法 WCF 响应方拒绝所提供的序列通过`CreateSequenceResponse`而无需`Accept`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="74371-139">B1110:如果可靠消息响应方拒绝所提供的序列，WCF 发起方错误新建立的序列。</span><span class="sxs-lookup"><span data-stu-id="74371-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="74371-140">B1111:如果`CreateSequence`不包含`Offer`元素，双向 WCF 响应方拒绝所提供的序列通过`CreateSequenceRefused`容错。</span><span class="sxs-lookup"><span data-stu-id="74371-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="74371-141">R1112:使用建立的两个相反序列时`Offer`机制`[address]`的属性`CreateSequenceResponse/Accept/AcksTo`终结点引用必须与目标 URI 相匹配的`CreateSequence`字节的消息字节。</span><span class="sxs-lookup"><span data-stu-id="74371-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="74371-142">R1113:使用建立的两个相反序列时`Offer`机制，从发起方流向响应方这两个序列上的所有消息必须都发送到相同的终结点引用。</span><span class="sxs-lookup"><span data-stu-id="74371-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="74371-143">WCF 使用 WS-ReliableMessaging 在发起方和响应方之间建立可靠会话。</span><span class="sxs-lookup"><span data-stu-id="74371-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="74371-144">WCF WS-ReliableMessaging 实现提供了可靠会话为单向、 请求-答复和完全双工消息传递模式。</span><span class="sxs-lookup"><span data-stu-id="74371-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="74371-145">`Offer` 和 `CreateSequence` 上的 WS-ReliableMessaging `CreateSequenceResponse` 机制允许您建立两个相关的相反序列，并提供适合于所有消息终结点的会话协议。</span><span class="sxs-lookup"><span data-stu-id="74371-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="74371-146">因为 WCF 提供了会话包括会话完整性的端到端保护的安全保障，是用于确保适用于同一参与方的消息到达同一目标。</span><span class="sxs-lookup"><span data-stu-id="74371-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="74371-147">这还允许应用程序消息上序列确认的“非法携带”。</span><span class="sxs-lookup"><span data-stu-id="74371-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="74371-148">因此，R1102、 R1112，以及 R1113 约束应用到 WCF。</span><span class="sxs-lookup"><span data-stu-id="74371-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>  
  
 <span data-ttu-id="74371-149">`CreateSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-149">An example of a `CreateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>  
    <wsa:ReplyTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>   
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>  
      </wsrm:AcksTo>  
      <wsrm:Offer>  
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>  
        <wsrm:Endpoint>  
          <wsa:Address>http://Business456.com/clientA</wsa:Address>  
        </wsrm:Endpoint>  
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      </wsrm:Offer>  
    </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="74371-150">`CreateSequenceResponse` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-150">An example of a `CreateSequenceResponse` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      <wsrm:Accept>  
        <wsrm:AcksTo>  
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>  
        </wsrm:AcksTo>  
      </wsrm:Accept>  
    </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="closing-a-sequence"></a><span data-ttu-id="74371-151">关闭序列</span><span class="sxs-lookup"><span data-stu-id="74371-151">Closing a Sequence</span></span>  
 <span data-ttu-id="74371-152">使用 WCF`CloseSequence`和`CloseSequenceResponse`的可靠消息源启动的关闭消息。</span><span class="sxs-lookup"><span data-stu-id="74371-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="74371-153">WCF 可靠消息目标不会启动关闭，WCF 可靠消息源不支持可靠消息目标启动的关闭。</span><span class="sxs-lookup"><span data-stu-id="74371-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="74371-154">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="74371-154">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="74371-155">B1201:WCF 可靠消息源始终发送`CloseSequence`消息以关闭序列。</span><span class="sxs-lookup"><span data-stu-id="74371-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="74371-156">B1202:可靠消息源等待确认的序列消息的全部发送之前`CloseSequence`消息。</span><span class="sxs-lookup"><span data-stu-id="74371-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="74371-157">B1203:可靠消息源始终包括可选`LastMsgNumber`元素除非序列不包含消息。</span><span class="sxs-lookup"><span data-stu-id="74371-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="74371-158">R1204:可靠消息目标不能通过发送启动关闭`CloseSequence`消息。</span><span class="sxs-lookup"><span data-stu-id="74371-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="74371-159">B1205:在接收时`CloseSequence`消息时，WCF 可靠消息源认为序列不完整并发送错误。</span><span class="sxs-lookup"><span data-stu-id="74371-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="74371-160">`CloseSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-160">An example of a `CloseSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
    </wsrm:CloseSequence>  
  </s:Body>  
</s:Envelope>  
Example CloseSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:CloseSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence-termination"></a><span data-ttu-id="74371-161">序列终止</span><span class="sxs-lookup"><span data-stu-id="74371-161">Sequence Termination</span></span>  
 <span data-ttu-id="74371-162">主要使用 WCF`TerminateSequence/TerminateSequenceResponse`握手后完成`CloseSequence/CloseSequenceResponse`握手。</span><span class="sxs-lookup"><span data-stu-id="74371-162">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="74371-163">WCF 可靠消息目标不启动终止和可靠消息源不支持可靠消息目标启动的终止。</span><span class="sxs-lookup"><span data-stu-id="74371-163">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="74371-164">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="74371-164">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="74371-165">B1301:WCF 发起方仅发送`TerminateSequence`成功完成后的消息`CloseSequence/CloseSequenceResponse`握手。</span><span class="sxs-lookup"><span data-stu-id="74371-165">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="74371-166">R1302:WCF 验证`LastMsgNumber`在所有元素都都一致`CloseSequence`和`TerminateSequence`对于给定的序列消息。</span><span class="sxs-lookup"><span data-stu-id="74371-166">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="74371-167">这意味着 `LastMsgNumber` 并不存在于所有 `CloseSequence` 和 `TerminateSequence` 消息上，或者它存在于所有 `CloseSequence` 和 `TerminateSequence` 消息上且完全相同。</span><span class="sxs-lookup"><span data-stu-id="74371-167">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="74371-168">B1303:在接收时`TerminateSequence`消息后`CloseSequence/CloseSequenceResponse`握手，可靠消息目标的响应与`TerminateSequenceResponse`消息。</span><span class="sxs-lookup"><span data-stu-id="74371-168">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="74371-169">由于可靠消息源在发送 `TerminateSequence` 消息之前具有最终确认，因此可靠消息目标可毫无疑问地知道序列将结束，并立即回收资源。</span><span class="sxs-lookup"><span data-stu-id="74371-169">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="74371-170">B1304:在接收时`TerminateSequence`消息之前`CloseSequence/CloseSequenceResponse`握手，WCF 可靠消息目标的响应与`TerminateSequenceResponse`消息。</span><span class="sxs-lookup"><span data-stu-id="74371-170">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="74371-171">如果可靠消息目标确定序列中没有不一致之处，则可靠消息目标将在回收资源之前等待应用程序目标指定的时间，以便客户端有机会接收最终确认。</span><span class="sxs-lookup"><span data-stu-id="74371-171">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="74371-172">否则，可靠消息目标立即回收资源，并通过引发 `Faulted` 事件向应用程序目标指出序列结束但存有疑问。</span><span class="sxs-lookup"><span data-stu-id="74371-172">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="74371-173">`TerminateSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-173">An example of a `TerminateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
      </wsrm:TerminateSequence>  
  </s:Body>  
</s:Envelope>  
Example TerminateSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:TerminateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequences"></a><span data-ttu-id="74371-174">序列</span><span class="sxs-lookup"><span data-stu-id="74371-174">Sequences</span></span>  
 <span data-ttu-id="74371-175">以下是适用于序列的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="74371-175">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="74371-176">B1401:WCF 生成，并访问序列号不高于`xs:long`的最大包含值 9223372036854775807。</span><span class="sxs-lookup"><span data-stu-id="74371-176">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="74371-177">`Sequence` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-177">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="74371-178">请求确认</span><span class="sxs-lookup"><span data-stu-id="74371-178">Request Acknowledgement</span></span>  
 <span data-ttu-id="74371-179">WCF 使用`AckRequested`标头，因为保持活动状态的机制。</span><span class="sxs-lookup"><span data-stu-id="74371-179">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="74371-180">`AckRequested` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-180">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="74371-181">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="74371-181">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="74371-182">WCF 将"非法携带"机制用于在 Ws-reliable Messaging 中提供的序列确认。</span><span class="sxs-lookup"><span data-stu-id="74371-182">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="74371-183">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="74371-183">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="74371-184">R1601:使用建立的两个相反序列时`Offer`机制，`SequenceAcknowledgement`可能传输到目标接收方的任何应用程序消息中包括标头。</span><span class="sxs-lookup"><span data-stu-id="74371-184">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="74371-185">远程终结点必须能够访问非法携带的 `SequenceAcknowledgement` 标头。</span><span class="sxs-lookup"><span data-stu-id="74371-185">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="74371-186">B1602:WCF 不会生成`SequenceAcknowledgement`标头包含`Nack`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-186">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="74371-187">WCF 将验证每个`Nack`元素包含一个序列号，但否则忽略`Nack`元素和值。</span><span class="sxs-lookup"><span data-stu-id="74371-187">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="74371-188">`SequenceAcknowledgement` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-188">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="74371-189">WS-ReliableMessaging 错误</span><span class="sxs-lookup"><span data-stu-id="74371-189">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="74371-190">下面是适用于 WCF 实现的 WS-ReliableMessaging 错误的约束的列表。</span><span class="sxs-lookup"><span data-stu-id="74371-190">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="74371-191">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="74371-191">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="74371-192">B1701:WCF 不会生成`MessageNumberRollover`故障。</span><span class="sxs-lookup"><span data-stu-id="74371-192">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="74371-193">B1702:通过 SOAP 1.2，当服务终结点达到其连接限制并无法处理新连接时，WCF 生成嵌套`CreateSequenceRefused`错误子代码`netrm:ConnectionLimitReached`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="74371-193">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>  
  </s:Header>  
  <s:Body>  
    <s:Fault>  
      <s:Code>  
        <s:Value>s:Receiver</s:Value>  
        <s:Subcode>  
          <s:Value>wsrm:CreateSequenceRefused</s:Value>  
          <s:Subcode>  
            <s:Value>netrm:ConnectionLimitReached</s:Value>  
          </s:Subcode>  
        </s:Subcode>  
      </s:Code>  
      <s:Reason>  
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>  
      </s:Reason>  
    </s:Fault>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="74371-194">WS-Addressing 错误</span><span class="sxs-lookup"><span data-stu-id="74371-194">WS-Addressing Faults</span></span>  
 <span data-ttu-id="74371-195">由于 WS-ReliableMessaging 使用 Ws-addressing，WCF WS-ReliableMessaging 实现可能会生成并传输 Ws-addressing 错误。</span><span class="sxs-lookup"><span data-stu-id="74371-195">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="74371-196">本部分介绍了 WCF 显式生成并传输在 WS-ReliableMessaging 层上的 Ws-addressing 错误：</span><span class="sxs-lookup"><span data-stu-id="74371-196">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="74371-197">B1801:WCF 生成并传输`Message Addressing Header Required`发生故障时以下项之一为 true:</span><span class="sxs-lookup"><span data-stu-id="74371-197">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="74371-198">`CreateSequence``CloseSequence` 或 `TerminateSequence` 消息缺少 `MessageId` 头。</span><span class="sxs-lookup"><span data-stu-id="74371-198">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="74371-199">`CreateSequence``CloseSequence` 或 `TerminateSequence` 消息缺少 `ReplyTo` 头。</span><span class="sxs-lookup"><span data-stu-id="74371-199">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="74371-200">`CreateSequenceResponse`、`CloseSequenceResponse` 或 `TerminateSequenceResponse` 消息缺少 `RelatesTo` 头。</span><span class="sxs-lookup"><span data-stu-id="74371-200">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="74371-201">B1802:WCF 生成并传输`Endpoint Unavailable`错误，以指示没有任何终结点侦听的可以处理基于对中的寻址标头的检查序列`CreateSequence`消息。</span><span class="sxs-lookup"><span data-stu-id="74371-201">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="74371-202">协议组合</span><span class="sxs-lookup"><span data-stu-id="74371-202">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="74371-203">与 WS-Addressing 组合</span><span class="sxs-lookup"><span data-stu-id="74371-203">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="74371-204">WCF 支持两个版本的 Ws-addressing:的 Ws-addressing 2004/08 [WS-ADDR] 以及 W3C Ws-addressing 1.0 建议 [WS ADDR 核] 和 [WS ADDR SOAP]。</span><span class="sxs-lookup"><span data-stu-id="74371-204">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="74371-205">尽管 WS-ReliableMessaging 规范仅提及 WS-Addressing 2004/08，但是它不限制要使用的 WS-Addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="74371-205">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="74371-206">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="74371-206">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="74371-207">R2101:可以与 Ws-reliable Messaging 使用 Ws-addressing 2004/08 和 Ws-addressing 1.0。</span><span class="sxs-lookup"><span data-stu-id="74371-207">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="74371-208">R2102:必须在整个的给定的 WS-ReliableMessaging 序列或通过使用相关的反向序列对使用单一版本的 Ws-addressing`Offer`机制。</span><span class="sxs-lookup"><span data-stu-id="74371-208">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="74371-209">与 SOAP 组合</span><span class="sxs-lookup"><span data-stu-id="74371-209">Composition with SOAP</span></span>  
 <span data-ttu-id="74371-210">WCF 支持 SOAP 1.1 和 SOAP 1.2 与 Ws-reliable Messaging 的使用。</span><span class="sxs-lookup"><span data-stu-id="74371-210">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="74371-211">与 WS-Security 和 WS-SecureConversation 组合</span><span class="sxs-lookup"><span data-stu-id="74371-211">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="74371-212">WCF 通过使用 Ws-secure Conversation 使用安全传输协议 (HTTPS)、 与 Ws-security 的组合和组合提供了对 WS-ReliableMessaging 序列的保护。</span><span class="sxs-lookup"><span data-stu-id="74371-212">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="74371-213">WS-ReliableMessaging 1.1 协议、WS-Security 1.1 和 WS-Secure Conversation 1.3 协议应该一起使用。</span><span class="sxs-lookup"><span data-stu-id="74371-213">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="74371-214">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="74371-214">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="74371-215">R2301:若要保护的各个消息的完整性 WS-ReliableMessaging 序列的完整性和保密性，WCF 需要必须使用 Ws-secure Conversation。</span><span class="sxs-lookup"><span data-stu-id="74371-215">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="74371-216">R2302:AWS-必须在建立 WS-ReliableMessaging 序列之前建立安全对话会话中。</span><span class="sxs-lookup"><span data-stu-id="74371-216">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="74371-217">R2303:如果 WS-ReliableMessaging 序列生存期超过了 Ws-secure Conversation 会话的生存期，`SecurityContextToken`建立通过使用 Ws-secure Conversation 必须续订通过使用相应的 Ws-secure Conversation 续订绑定。</span><span class="sxs-lookup"><span data-stu-id="74371-217">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="74371-218">B2304:WS-ReliableMessaging 序列或一对相关的相反序列始终绑定到单个 Ws-secureconversation 会话。</span><span class="sxs-lookup"><span data-stu-id="74371-218">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="74371-219">R2305:当使用 Ws-secure Conversation 撰写，WCF 响应方要求`CreateSequence`消息包含`wsse:SecurityTokenReference`元素和`wsrm:UsesSequenceSTR`标头。</span><span class="sxs-lookup"><span data-stu-id="74371-219">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="74371-220">`UsesSequenceSTR` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-220">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="74371-221">与 SSL/TLS 会话组合</span><span class="sxs-lookup"><span data-stu-id="74371-221">Composition with SSL/TLS sessions</span></span>  
 <span data-ttu-id="74371-222">WCF 不支持与 SSL/TLS 会话组合：</span><span class="sxs-lookup"><span data-stu-id="74371-222">WCF does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="74371-223">B2401:WCF 不会生成`wsrm:UsesSequenceSSL`标头。</span><span class="sxs-lookup"><span data-stu-id="74371-223">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="74371-224">R2402:可靠消息发起方不能发送`CreateSequence`消息`wsrm:UsesSequenceSSL`向 WCF 响应程序的标头。</span><span class="sxs-lookup"><span data-stu-id="74371-224">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="74371-225">与 WS-Policy 组合</span><span class="sxs-lookup"><span data-stu-id="74371-225">Composition with WS-Policy</span></span>  
 <span data-ttu-id="74371-226">WCF 支持 Ws-policy 的两个版本：Ws-policy 1.2 和 Ws-policy 1.5。</span><span class="sxs-lookup"><span data-stu-id="74371-226">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="74371-227">WS-ReliableMessaging WS-Policy 断言</span><span class="sxs-lookup"><span data-stu-id="74371-227">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="74371-228">WCF 使用 WS-ReliableMessaging Ws-policy 断言`wsrm:RMAssertion`来描述终结点功能。</span><span class="sxs-lookup"><span data-stu-id="74371-228">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="74371-229">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="74371-229">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="74371-230">B3001:WCF 将附加`wsrmn:RMAssertion`Ws-policy 断言到`wsdl:binding`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-230">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="74371-231">WCF 支持这两个附件`wsdl:binding`和`wsdl:port`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-231">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="74371-232">B3002:WCF 永远不会生成`wsp:Optional`标记。</span><span class="sxs-lookup"><span data-stu-id="74371-232">B3002: WCF never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="74371-233">B3003:访问时`wsrmp:RMAssertion`Ws-policy 断言，WCF 将忽略`wsp:Optional`标记并将 WS-RM 策略视为强制。</span><span class="sxs-lookup"><span data-stu-id="74371-233">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="74371-234">R3004:WCF 未构成与 SSL/TLS 会话，因为 WCF 不接受指定的策略`wsrmp:SequenceTransportSecurity`。</span><span class="sxs-lookup"><span data-stu-id="74371-234">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="74371-235">B3005:WCF 始终生成`wsrmp:DeliveryAssurance`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-235">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="74371-236">B3006:WCF 始终指定`wsrmp:ExactlyOnce`传递保证。</span><span class="sxs-lookup"><span data-stu-id="74371-236">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="74371-237">B3007:WCF 生成并读取 WS-ReliableMessaging 断言的以下属性和对它们的控制了 WCF`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="74371-237">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="74371-238">`RMAssertion` 的一个示例。</span><span class="sxs-lookup"><span data-stu-id="74371-238">An example of a `RMAssertion`.</span></span>  
  
    ```xml  
    <wsrmp:RMAssertion>  
      <wsp:Policy>  
        <wsrmp:SequenceSTR/>  
        <wsrmp:DeliveryAssurance>  
          <wsp:Policy>  
            <wsrmp:ExactlyOnce/>  
            <wsrmp:InOrder/>  
          </wsp:Policy>  
        </wsrmp:DeliveryAssurance>  
      </wsp:Policy>  
      <netrmp:InactivityTimeout Milliseconds="600000"/>  
      <netrmp:AcknowledgementInterval Milliseconds="200"/>  
    </wsrmp:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="74371-239">流控制 WS-ReliableMessaging 扩展</span><span class="sxs-lookup"><span data-stu-id="74371-239">Flow Control WS-ReliableMessaging Extension</span></span>  
 <span data-ttu-id="74371-240">WCF 使用 WS-ReliableMessaging 扩展性提供对序列消息流的可选更紧密控制。</span><span class="sxs-lookup"><span data-stu-id="74371-240">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="74371-241">设置启用流控制<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="74371-241">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="74371-242">下面是适用于 WCF 的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="74371-242">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="74371-243">B4001:当启用可靠消息流控制时，WCF 生成`netrm:BufferRemaining`元素的元素扩展性中`SequenceAcknowledgement`标头，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="74371-243">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="74371-244">B4002:即使启用可靠消息流控制时，WCF 不需要`netrm:BufferRemaining`中的元素`SequenceAcknowledgement`标头。</span><span class="sxs-lookup"><span data-stu-id="74371-244">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="74371-245">B4003:WCF 可靠消息目标使用`netrm:BufferRemaining`以指示如何许多新的消息可以缓冲。</span><span class="sxs-lookup"><span data-stu-id="74371-245">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="74371-246">启用 B4004:When 可靠消息流控制时，WCF 可靠消息源使用的值`netrm:BufferRemaining`遏制消息传输。</span><span class="sxs-lookup"><span data-stu-id="74371-246">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="74371-247">B4005:WCF 将生成`netrm:BufferRemaining`整数值介于 0 和 4096 （含)，并读取介于 0 的整数值和`xs:int`的`maxInclusive`值 214748364 （含)。</span><span class="sxs-lookup"><span data-stu-id="74371-247">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="74371-248">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="74371-248">Message Exchange Patterns</span></span>  
 <span data-ttu-id="74371-249">WS-ReliableMessaging 用于不同消息交换模式时，本部分将介绍 WCF 的行为。</span><span class="sxs-lookup"><span data-stu-id="74371-249">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="74371-250">对于每个消息交换模式，可以考虑下面的两个部署方案：</span><span class="sxs-lookup"><span data-stu-id="74371-250">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="74371-251">不可寻址的发起方：发起方位于防火墙;响应方可以将消息传递到发起方仅在 HTTP 响应上。</span><span class="sxs-lookup"><span data-stu-id="74371-251">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="74371-252">可寻址的发起方：发起方和响应方都可以发送 HTTP 请求;换而言之，可以建立两个反向 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="74371-252">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="74371-253">单向、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="74371-253">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="74371-254">绑定</span><span class="sxs-lookup"><span data-stu-id="74371-254">Binding</span></span>  
 <span data-ttu-id="74371-255">WCF 提供了通过一个 HTTP 通道使用一个序列的单向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="74371-255">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="74371-256">WCF 使用 HTTP 请求传输所有消息从发起方到响应方，并使用 HTTP 响应传输到发起方从响应方的所有消息。</span><span class="sxs-lookup"><span data-stu-id="74371-256">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="74371-257">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="74371-258">WCF 发起方传输`CreateSequence`没有消息`Offer`HTTP 请求上的元素，并期望`CreateSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-258">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="74371-259">WCF 响应方创建一个序列并传输`CreateSequenceResponse`没有消息`Accept`HTTP 响应上的元素。</span><span class="sxs-lookup"><span data-stu-id="74371-259">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="74371-260">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="74371-260">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="74371-261">WCF 发起方处理除之外的所有消息的确认答复`CreateSequence`消息和错误消息。</span><span class="sxs-lookup"><span data-stu-id="74371-261">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="74371-262">WCF 响应方始终将对所有序列的 HTTP 响应上的独立确认传输和`AckRequested`消息。</span><span class="sxs-lookup"><span data-stu-id="74371-262">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="74371-263">CloseSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-263">CloseSequence Exchange</span></span>  
 <span data-ttu-id="74371-264">WCF 发起方传输`CloseSequence`上的 HTTP 请求消息，并需要`CreateSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-264">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="74371-265">WCF 响应方传输`CloseSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-265">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="74371-266">TerminateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-266">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="74371-267">WCF 发起方传输`TerminateSequence`上的 HTTP 请求消息，并需要`TerminateSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-267">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="74371-268">WCF 响应方传输`TerminateSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-268">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="74371-269">单向、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="74371-269">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="74371-270">绑定</span><span class="sxs-lookup"><span data-stu-id="74371-270">Binding</span></span>  
 <span data-ttu-id="74371-271">WCF 提供了通过一个使用一个序列的单向消息交换模式入站和一个出站 HTTP 通道。</span><span class="sxs-lookup"><span data-stu-id="74371-271">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="74371-272">WCF 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="74371-272">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="74371-273">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="74371-273">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="74371-274">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-274">CreateSequence Exchange</span></span>  
 <span data-ttu-id="74371-275">WCF 发起方传输`CreateSequence`没有消息`Offer`HTTP 请求上的元素。</span><span class="sxs-lookup"><span data-stu-id="74371-275">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="74371-276">WCF 响应方创建一个序列并传输`CreateSequenceResponse`没有消息`Accept`HTTP 请求上的元素。</span><span class="sxs-lookup"><span data-stu-id="74371-276">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="74371-277">双工、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="74371-277">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="74371-278">绑定</span><span class="sxs-lookup"><span data-stu-id="74371-278">Binding</span></span>  
 <span data-ttu-id="74371-279">WCF 提供了完全异步的双向消息交换模式，使用两个序列通过一个入站和一个出站 HTTP 通道。</span><span class="sxs-lookup"><span data-stu-id="74371-279">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="74371-280">此消息交换模式可以与 `Request/Reply`、`Addressable` 发起方消息交换模式以有限方式混合使用。</span><span class="sxs-lookup"><span data-stu-id="74371-280">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="74371-281">WCF 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="74371-281">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="74371-282">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="74371-282">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="74371-283">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-283">CreateSequence Exchange</span></span>  
 <span data-ttu-id="74371-284">WCF 发起方传输`CreateSequence`消息`Offer`HTTP 请求上的元素。</span><span class="sxs-lookup"><span data-stu-id="74371-284">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="74371-285">WCF 响应方确保`CreateSequence`已`Offer`元素，然后创建一个序列并传输`CreateSequenceResponse`消息`Accept`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-285">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="74371-286">序列生存期</span><span class="sxs-lookup"><span data-stu-id="74371-286">Sequence Lifetime</span></span>  
 <span data-ttu-id="74371-287">WCF 将两个序列视为一个全双工会话。</span><span class="sxs-lookup"><span data-stu-id="74371-287">WCF treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="74371-288">在生成的错误，使一个序列，WCF 需要要故障这两个序列的远程终结点。</span><span class="sxs-lookup"><span data-stu-id="74371-288">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="74371-289">在读取的错误，使一个序列，WCF 会使故障这两个序列。</span><span class="sxs-lookup"><span data-stu-id="74371-289">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="74371-290">WCF 可以关闭其出站序列并继续处理其入站序列上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-290">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="74371-291">相反，WCF 可以处理入站序列的关闭和继续其出站序列上发送消息。</span><span class="sxs-lookup"><span data-stu-id="74371-291">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="74371-292">请求-答复和单向、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="74371-292">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="74371-293">绑定</span><span class="sxs-lookup"><span data-stu-id="74371-293">Binding</span></span>  
 <span data-ttu-id="74371-294">WCF 提供了单向和请求-答复消息交换模式使用两个序列通过一个 HTTP 通道。</span><span class="sxs-lookup"><span data-stu-id="74371-294">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="74371-295">WCF 使用 HTTP 请求传输所有消息从发起方到响应方，并使用 HTTP 响应传输到发起方从响应方的所有消息。</span><span class="sxs-lookup"><span data-stu-id="74371-295">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="74371-296">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-296">CreateSequence Exchange</span></span>  
 <span data-ttu-id="74371-297">WCF 发起方传输`CreateSequence`消息`Offer`HTTP 请求上的元素，并期望`CreateSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-297">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="74371-298">WCF 响应方创建一个序列并传输`CreateSequenceResponse`消息`Accept`HTTP 响应上的元素。</span><span class="sxs-lookup"><span data-stu-id="74371-298">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="74371-299">单向消息</span><span class="sxs-lookup"><span data-stu-id="74371-299">One-way Message</span></span>  
 <span data-ttu-id="74371-300">若要成功完成单向消息交换，WCF 发起方传输请求序列消息在 HTTP 请求和接收独立`SequenceAcknowledgement`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-300">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="74371-301">`SequenceAcknowledgement` 必须确认已传输的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-301">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="74371-302">确认、 错误或正文为空且 HTTP 202 状态代码的响应与请求的 WCF 响应可能会答复。</span><span class="sxs-lookup"><span data-stu-id="74371-302">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="74371-303">双向消息</span><span class="sxs-lookup"><span data-stu-id="74371-303">Two Way Messages</span></span>  
 <span data-ttu-id="74371-304">若要成功地完成双向消息交换协议，WCF 发起方传输请求序列消息在 HTTP 请求和接收答复序列消息在 HTTP 响应上。</span><span class="sxs-lookup"><span data-stu-id="74371-304">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="74371-305">响应必须包含一个确认已传输的请求序列消息的 `SequenceAcknowledgement`。</span><span class="sxs-lookup"><span data-stu-id="74371-305">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="74371-306">使用应用程序答复、 错误或正文为空且 HTTP 202 状态代码的响应请求的 WCF 响应可能会答复。</span><span class="sxs-lookup"><span data-stu-id="74371-306">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="74371-307">由于存在单向消息和应用程序答复的计时，因此请求序列消息的序列号与响应消息的序列号不相关联。</span><span class="sxs-lookup"><span data-stu-id="74371-307">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="74371-308">重试答复</span><span class="sxs-lookup"><span data-stu-id="74371-308">Retrying Replies</span></span>  
 <span data-ttu-id="74371-309">WCF 依赖于双向消息交换协议关联的 HTTP 请求-答复相关。</span><span class="sxs-lookup"><span data-stu-id="74371-309">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="74371-310">因此，WCF 发起方不会停止重试请求序列消息，确认请求序列消息时，但而不是在 HTTP 响应携带`SequenceAcknowledgement`，应用程序答复或错误。</span><span class="sxs-lookup"><span data-stu-id="74371-310">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="74371-311">WCF 响应方重试次数依赖向其答复相关联的请求的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="74371-311">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="74371-312">CloseSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-312">CloseSequence Exchange</span></span>  
 <span data-ttu-id="74371-313">收到后的所有答复序列消息和所有单向请求序列消息的确认，WCF 发起方传输`CloseSequence`HTTP 请求上请求序列消息，并需要`CloseSequenceResponse`HTTP 响应上。</span><span class="sxs-lookup"><span data-stu-id="74371-313">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="74371-314">关闭请求序列将隐式关闭答复序列。</span><span class="sxs-lookup"><span data-stu-id="74371-314">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="74371-315">这意味着 WCF 发起方包括答复序列的最终`SequenceAcknowledgement`上`CloseSequence`消息和答复序列没有`CloseSequence`exchange。</span><span class="sxs-lookup"><span data-stu-id="74371-315">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="74371-316">WCF 响应方确保所有答复确认并传输`CloseSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-316">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="74371-317">TerminateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-317">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="74371-318">收到后`CloseSequenceResponse`消息时，WCF 发起方传输`TerminateSequence`上的 HTTP 请求的请求序列消息，并需要`TerminateSequenceResponse`HTTP 响应上。</span><span class="sxs-lookup"><span data-stu-id="74371-318">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="74371-319">与 `CloseSequence` 交换一样，终止请求序列将隐式终止答复序列。</span><span class="sxs-lookup"><span data-stu-id="74371-319">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="74371-320">这意味着 WCF 发起方包括答复序列的最终`SequenceAcknowledgement`上`TerminateSequence`消息和答复序列没有`TerminateSequence`exchange。</span><span class="sxs-lookup"><span data-stu-id="74371-320">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="74371-321">WCF 响应方传输`TerminateSequenceResponse`HTTP 响应上的消息。</span><span class="sxs-lookup"><span data-stu-id="74371-321">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="74371-322">请求/答复、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="74371-322">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="74371-323">绑定</span><span class="sxs-lookup"><span data-stu-id="74371-323">Binding</span></span>  
 <span data-ttu-id="74371-324">WCF 提供了使用两个的请求-答复消息交换模式序列通过一个入站和一个出站 HTTP 通道。</span><span class="sxs-lookup"><span data-stu-id="74371-324">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="74371-325">此消息交换模式可以与 `Duplex, Addressable` 发起方消息交换模式以有限方式混合使用。</span><span class="sxs-lookup"><span data-stu-id="74371-325">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="74371-326">WCF 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="74371-326">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="74371-327">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="74371-327">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="74371-328">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="74371-328">CreateSequence Exchange</span></span>  
 <span data-ttu-id="74371-329">WCF 发起方传输`CreateSequence`消息`Offer`HTTP 请求上的元素。</span><span class="sxs-lookup"><span data-stu-id="74371-329">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="74371-330">WCF 响应方确保`CreateSequence`已`Offer`元素，然后创建一个序列并传输`CreateSequenceResponse`消息`Accept`元素。</span><span class="sxs-lookup"><span data-stu-id="74371-330">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="74371-331">请求/答复关联</span><span class="sxs-lookup"><span data-stu-id="74371-331">Request/Reply Correlation</span></span>  
 <span data-ttu-id="74371-332">以下内容适用于所有关联的请求和答复：</span><span class="sxs-lookup"><span data-stu-id="74371-332">The following applies to all correlated requests and replies:</span></span>  
  
-   <span data-ttu-id="74371-333">WCF 可确保所有应用程序请求消息都具有`ReplyTo`终结点引用和一个`MessageId`。</span><span class="sxs-lookup"><span data-stu-id="74371-333">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   <span data-ttu-id="74371-334">WCF 为每个应用程序请求消息的应用的本地终结点引用`ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="74371-334">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="74371-335">本地终结点引用是发起方的 `CreateSequence` 消息的 `ReplyTo` 和响应方的 `CreateSequence` 消息的 `To`。</span><span class="sxs-lookup"><span data-stu-id="74371-335">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   <span data-ttu-id="74371-336">WCF 可确保该传入请求消息具有`MessageId`和一个`ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="74371-336">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   <span data-ttu-id="74371-337">WCF 可确保`ReplyTo`前面定义的所有应用程序请求消息的终结点引用的 URI 匹配的本地终结点引用。</span><span class="sxs-lookup"><span data-stu-id="74371-337">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   <span data-ttu-id="74371-338">WCF 可确保所有答复都具有正确`RelatesTo`并`To`标头遵循`wsa`请求/答复关联规则。</span><span class="sxs-lookup"><span data-stu-id="74371-338">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
