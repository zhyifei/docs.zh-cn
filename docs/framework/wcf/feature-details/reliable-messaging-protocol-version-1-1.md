---
title: "可靠消息传送协议版本 1.1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 98fe8ac04b7ac811802466cf63c58ea4cebd791e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="c4474-102">可靠消息传送协议版本 1.1</span><span class="sxs-lookup"><span data-stu-id="c4474-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="c4474-103">本主题介绍使用 HTTP 传输进行互操作所需的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] WS-ReliableMessaging 2007 年 2 月（版本 1.1）协议的实现细节。</span><span class="sxs-lookup"><span data-stu-id="c4474-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-104"> 遵循 WS ReliableMessaging 规范以及本主题中解释的约束和声明。</span><span class="sxs-lookup"><span data-stu-id="c4474-104"> follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="c4474-105">请注意，Ws-reliablemessaging 版本 1.1 协议实现开头[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c4474-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="c4474-106">2007 年 2 月发布的 WS-ReliableMessaging 协议是在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中由 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> 实现的。</span><span class="sxs-lookup"><span data-stu-id="c4474-106">The WS-ReliableMessaging February 2007 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="c4474-107">为方便起见，本主题使用以下角色：</span><span class="sxs-lookup"><span data-stu-id="c4474-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="c4474-108">发起方：启动 WS-Reliable Message 序列创建的客户端。</span><span class="sxs-lookup"><span data-stu-id="c4474-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="c4474-109">响应方：接收发起方请求的服务。</span><span class="sxs-lookup"><span data-stu-id="c4474-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="c4474-110">本文档使用下表中的前缀和命名空间。</span><span class="sxs-lookup"><span data-stu-id="c4474-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="c4474-111">前缀</span><span class="sxs-lookup"><span data-stu-id="c4474-111">Prefix</span></span>|<span data-ttu-id="c4474-112">命名空间</span><span class="sxs-lookup"><span data-stu-id="c4474-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="c4474-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="c4474-113">wsrm</span></span>|<span data-ttu-id="c4474-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span><span class="sxs-lookup"><span data-stu-id="c4474-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span></span>|  
|<span data-ttu-id="c4474-115">netrm</span><span class="sxs-lookup"><span data-stu-id="c4474-115">netrm</span></span>|<span data-ttu-id="c4474-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="c4474-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="c4474-117">s</span><span class="sxs-lookup"><span data-stu-id="c4474-117">s</span></span>|<span data-ttu-id="c4474-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="c4474-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="c4474-119">wsa</span><span class="sxs-lookup"><span data-stu-id="c4474-119">wsa</span></span>|<span data-ttu-id="c4474-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="c4474-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="c4474-121">wsse</span><span class="sxs-lookup"><span data-stu-id="c4474-121">wsse</span></span>|<span data-ttu-id="c4474-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="c4474-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="c4474-123">wsrmp</span><span class="sxs-lookup"><span data-stu-id="c4474-123">wsrmp</span></span>|<span data-ttu-id="c4474-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="c4474-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="c4474-125">netrmp</span><span class="sxs-lookup"><span data-stu-id="c4474-125">netrmp</span></span>|<span data-ttu-id="c4474-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="c4474-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="c4474-127">wsp</span><span class="sxs-lookup"><span data-stu-id="c4474-127">wsp</span></span>|<span data-ttu-id="c4474-128">（WS-Policy 1.2 或 WS-Policy 1.5）</span><span class="sxs-lookup"><span data-stu-id="c4474-128">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="c4474-129">消息传送</span><span class="sxs-lookup"><span data-stu-id="c4474-129">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="c4474-130">序列创建</span><span class="sxs-lookup"><span data-stu-id="c4474-130">Sequence Creation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-131"> 实现 `CreateSequence` 和 `CreateSequenceResponse` 消息以建立可靠消息序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-131"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="c4474-132">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-132">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c4474-133">B1101：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方与 `CreateSequence` 消息的 `ReplyTo`、`AcksTo` 和 `Offer/Endpoint` 使用相同的终结点引用。</span><span class="sxs-lookup"><span data-stu-id="c4474-133">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="c4474-134">R1102：`AcksTo` 消息中的 `ReplyTo`、`Offer/Endpoint` 和 `CreateSequence` 终结点引用必须具有包含相同字符串表示的地址值，以便它们与八进制形式匹配。</span><span class="sxs-lookup"><span data-stu-id="c4474-134">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="c4474-135">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方在创建序列之前验证 `AcksTo`、`ReplyTo` 和 `Endpoint` 终结点引用的 URI 部分是否相同。</span><span class="sxs-lookup"><span data-stu-id="c4474-135">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="c4474-136">R1103：`AcksTo` 消息中的 `ReplyTo`、`Offer/Endpoint` 和 `CreateSequence` 终结点引用应该具有一组相同的引用参数。</span><span class="sxs-lookup"><span data-stu-id="c4474-136">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-137"> 不强制而是假定 `AcksTo` 上的 `ReplyTo`、`Offer/Endpoint` 和 `CreateSequence` 终结点引用的引用参数是相同的，并将来自 `ReplyTo` 终结点应用的引用参数用于确认和相反序列消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-137"> does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="c4474-138">B1104：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方不在 `Expires` 消息中生成可选的 `Offer/Expires` 或 `CreateSequence` 元素。</span><span class="sxs-lookup"><span data-stu-id="c4474-138">B1104: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="c4474-139">B1105：访问 `CreateSequence` 消息时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方将 `Expires` 元素中的 `CreateSequence` 值用作 `Expires` 元素中的 `CreateSequenceResponse` 值。</span><span class="sxs-lookup"><span data-stu-id="c4474-139">B1105: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="c4474-140">否则，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方读取并忽略 `Expires` 和 `Offer/Expires` 值。</span><span class="sxs-lookup"><span data-stu-id="c4474-140">Otherwise, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="c4474-141">B1106：访问 `CreateSequenceResponse` 消息时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方读取可选的 `Expires` 值但不使用它。</span><span class="sxs-lookup"><span data-stu-id="c4474-141">B1106: When accessing the `CreateSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="c4474-142">B1107：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方和响应方始终在 `IncompleteSequenceBehavior` 和 `CreateSequence/Offer` 元素中生成可选的 `CreateSequenceResponse` 元素。</span><span class="sxs-lookup"><span data-stu-id="c4474-142">B1107: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="c4474-143">B1108：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 仅使用 `DiscardFollowingFirstGap` 元素中的 `NoDiscard` 和 `IncompleteSequenceBehavior` 值。</span><span class="sxs-lookup"><span data-stu-id="c4474-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="c4474-144">WS-ReliableMessaging 利用 `Offer` 机制建立构成会话的两个相反的相关序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-144">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="c4474-145">B1109：如果 `CreateSequence` 包含 `Offer` 元素，则单向 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方通过没有 `CreateSequenceResponse` 元素的 `Accept` 进行响应来拒绝所提供的序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-145">B1109: If `CreateSequence` contains an `Offer` element, the one way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="c4474-146">B1110：如果可靠消息响应方拒绝所提供的序列，则 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方查找新建立的序列中的错误。</span><span class="sxs-lookup"><span data-stu-id="c4474-146">B1110: If a Reliable Messaging Responder rejects the offered sequence, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="c4474-147">B1111：如果 `CreateSequence` 不包含 `Offer` 元素，则双向 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方通过 `CreateSequenceRefused` 错误进行响应来拒绝所提供的序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-147">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="c4474-148">R1112：使用 `Offer` 机制建立两个相反序列时，`[address]` 终结点引用的 `CreateSequenceResponse/Accept/AcksTo` 属性必须与 `CreateSequence` 消息的目标 URI 逐字节匹配。</span><span class="sxs-lookup"><span data-stu-id="c4474-148">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="c4474-149">R1113：使用 `Offer` 机制建立两个相反序列时，从发起方流向响应方的两个序列上的所有消息都必须发送到同一终结点引用。</span><span class="sxs-lookup"><span data-stu-id="c4474-149">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-150"> 使用 WS-ReliableMessaging 在发起方和响应方之间建立可靠的会话。</span><span class="sxs-lookup"><span data-stu-id="c4474-150"> uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="c4474-151">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging 实现为单向、请求-答复和全双工消息模式提供了可靠的会话。</span><span class="sxs-lookup"><span data-stu-id="c4474-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="c4474-152">`Offer` 和 `CreateSequence` 上的 WS-ReliableMessaging `CreateSequenceResponse` 机制允许您建立两个相关的相反序列，并提供适合于所有消息终结点的会话协议。</span><span class="sxs-lookup"><span data-stu-id="c4474-152">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="c4474-153">由于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 为这样的会话提供了安全保证（包括会话完整性的端到端保护），因此确保发往同一方的消息到达同一目标是很实用的。</span><span class="sxs-lookup"><span data-stu-id="c4474-153">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="c4474-154">这还允许应用程序消息上序列确认的“非法携带”。</span><span class="sxs-lookup"><span data-stu-id="c4474-154">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="c4474-155">因此，约束 R1102、 R1112 和 R1113 适用于[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c4474-155">Therefore, constraints R1102, R1112, and R1113 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="c4474-156">`CreateSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-156">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="c4474-157">`CreateSequenceResponse` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-157">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="c4474-158">关闭序列</span><span class="sxs-lookup"><span data-stu-id="c4474-158">Closing a Sequence</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-159"> 将 `CloseSequence` 和 `CloseSequenceResponse` 消息用于可靠消息源启动的关闭。</span><span class="sxs-lookup"><span data-stu-id="c4474-159"> uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="c4474-160">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠消息目标不会启动关闭，且 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠消息源不支持可靠消息目标启动的关闭。</span><span class="sxs-lookup"><span data-stu-id="c4474-160">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate shutdown and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="c4474-161">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-161">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c4474-162">B1201：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠消息源始终发送 `CloseSequence` 消息以关闭序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-162">B1201: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="c4474-163">B1202：可靠消息源在发送 `CloseSequence` 消息之前，等待确认全部的序列消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-163">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="c4474-164">B1203：除非序列不包含消息，否则可靠消息源始终包括可选的 `LastMsgNumber` 元素。</span><span class="sxs-lookup"><span data-stu-id="c4474-164">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="c4474-165">R1204：可靠消息目标不得通过发送 `CloseSequence` 消息启动关闭。</span><span class="sxs-lookup"><span data-stu-id="c4474-165">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="c4474-166">B1205：接收到 `CloseSequence` 消息时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠消息源认为序列不完整并发送错误。</span><span class="sxs-lookup"><span data-stu-id="c4474-166">B1205: Upon receiving a `CloseSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="c4474-167">`CloseSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-167">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="c4474-168">序列终止</span><span class="sxs-lookup"><span data-stu-id="c4474-168">Sequence Termination</span></span>  
 <span data-ttu-id="c4474-169">在完成 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 握手后 `TerminateSequence/TerminateSequenceResponse` 主要使用 `CloseSequence/CloseSequenceResponse` 握手。</span><span class="sxs-lookup"><span data-stu-id="c4474-169">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="c4474-170">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠消息目标不启动终止，且可靠消息源不支持可靠消息目标启动的终止。</span><span class="sxs-lookup"><span data-stu-id="c4474-170">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="c4474-171">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-171">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c4474-172">B1301：在成功完成 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 握手后，`TerminateSequence` 发起方仅发送 `CloseSequence/CloseSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-172">B1301: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="c4474-173">R1302：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 验证 `LastMsgNumber` 元素在给定序列的所有 `CloseSequence` 和 `TerminateSequence` 消息中是否一致。</span><span class="sxs-lookup"><span data-stu-id="c4474-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="c4474-174">这意味着 `LastMsgNumber` 并不存在于所有 `CloseSequence` 和 `TerminateSequence` 消息上，或者它存在于所有 `CloseSequence` 和 `TerminateSequence` 消息上且完全相同。</span><span class="sxs-lookup"><span data-stu-id="c4474-174">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="c4474-175">B1303：在 `TerminateSequence` 握手后收到 `CloseSequence/CloseSequenceResponse` 消息时，可靠消息目标通过 `TerminateSequenceResponse` 消息进行响应。</span><span class="sxs-lookup"><span data-stu-id="c4474-175">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c4474-176">由于可靠消息源在发送 `TerminateSequence` 消息之前具有最终确认，因此可靠消息目标可毫无疑问地知道序列将结束，并立即回收资源。</span><span class="sxs-lookup"><span data-stu-id="c4474-176">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="c4474-177">B1304：在 `TerminateSequence` 握手之前收到 `CloseSequence/CloseSequenceResponse` 消息时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠消息目标通过 `TerminateSequenceResponse` 消息进行响应。</span><span class="sxs-lookup"><span data-stu-id="c4474-177">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c4474-178">如果可靠消息目标确定序列中没有不一致之处，则可靠消息目标将在回收资源之前等待应用程序目标指定的时间，以便客户端有机会接收最终确认。</span><span class="sxs-lookup"><span data-stu-id="c4474-178">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="c4474-179">否则，可靠消息目标立即回收资源，并通过引发 `Faulted` 事件向应用程序目标指出序列结束但存有疑问。</span><span class="sxs-lookup"><span data-stu-id="c4474-179">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="c4474-180">`TerminateSequence` 消息的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-180">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="c4474-181">序列</span><span class="sxs-lookup"><span data-stu-id="c4474-181">Sequences</span></span>  
 <span data-ttu-id="c4474-182">以下是适用于序列的约束的列表：</span><span class="sxs-lookup"><span data-stu-id="c4474-182">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="c4474-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]生成，并访问序列号不高于`xs:long`的最大非独占值，9223372036854775807。</span><span class="sxs-lookup"><span data-stu-id="c4474-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="c4474-184">`Sequence` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-184">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="c4474-185">请求确认</span><span class="sxs-lookup"><span data-stu-id="c4474-185">Request Acknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-186"> 将 `AckRequested` 头用作“保持活动状态”机制。</span><span class="sxs-lookup"><span data-stu-id="c4474-186"> uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="c4474-187">`AckRequested` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-187">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="c4474-188">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c4474-188">SequenceAcknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-189"> 将“非法携带”机制用于在 WS-Reliable Messaging 中提供的序列确认。</span><span class="sxs-lookup"><span data-stu-id="c4474-189"> uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="c4474-190">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-190">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c4474-191">R1601： 两个相反序列建立时使用`Offer`机制，`SequenceAcknowledgement`标头可能包含在传输到目标接收方的任何应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-191">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="c4474-192">远程终结点必须能够访问非法携带的 `SequenceAcknowledgement` 标头。</span><span class="sxs-lookup"><span data-stu-id="c4474-192">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="c4474-193">B1602：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不生成包含 `SequenceAcknowledgement` 元素的 `Nack` 标题。</span><span class="sxs-lookup"><span data-stu-id="c4474-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-194"> 验证每个 `Nack` 元素都包含一个序列号；如果不包含序列号，则忽略 `Nack` 元素和值。</span><span class="sxs-lookup"><span data-stu-id="c4474-194"> validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="c4474-195">`SequenceAcknowledgement` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-195">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="c4474-196">WS-ReliableMessaging 错误</span><span class="sxs-lookup"><span data-stu-id="c4474-196">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="c4474-197">下面列出了适用 WS-ReliableMessaging 错误的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 实现的约束。</span><span class="sxs-lookup"><span data-stu-id="c4474-197">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="c4474-198">适用以下约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-198">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c4474-199">B1701:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]不会生成`MessageNumberRollover`错误。</span><span class="sxs-lookup"><span data-stu-id="c4474-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="c4474-200">B1702：对于 SOAP 1.2，当服务终结点达到其连接限制而无法处理新连接时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 生成嵌套的 `CreateSequenceRefused` 错误子代码 `netrm:ConnectionLimitReached`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c4474-200">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="c4474-201">WS-Addressing 错误</span><span class="sxs-lookup"><span data-stu-id="c4474-201">WS-Addressing Faults</span></span>  
 <span data-ttu-id="c4474-202">由于 WS-ReliableMessaging 使用 WS-Addressing，因此 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging 实现可能会生成并传输 WS-Addressing 错误。</span><span class="sxs-lookup"><span data-stu-id="c4474-202">Because WS-ReliableMessaging uses WS-Addressing, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="c4474-203">本节介绍 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在 WS-ReliableMessaging 层上显式生成并传输的 WS-Addressing 错误：</span><span class="sxs-lookup"><span data-stu-id="c4474-203">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="c4474-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]生成并传输`Message Addressing Header Required`错误下列情况之一时：</span><span class="sxs-lookup"><span data-stu-id="c4474-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="c4474-205">`CreateSequence``CloseSequence` 或 `TerminateSequence` 消息缺少 `MessageId` 头。</span><span class="sxs-lookup"><span data-stu-id="c4474-205">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="c4474-206">`CreateSequence``CloseSequence` 或 `TerminateSequence` 消息缺少 `ReplyTo` 头。</span><span class="sxs-lookup"><span data-stu-id="c4474-206">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="c4474-207">`CreateSequenceResponse`、`CloseSequenceResponse` 或 `TerminateSequenceResponse` 消息缺少 `RelatesTo` 头。</span><span class="sxs-lookup"><span data-stu-id="c4474-207">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="c4474-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]生成并传输`Endpoint Unavailable`故障，用于指示侦听，没有终结点可以处理基于中的寻址标头检查序列`CreateSequence`消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="c4474-209">协议组合</span><span class="sxs-lookup"><span data-stu-id="c4474-209">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="c4474-210">与 WS-Addressing 组合</span><span class="sxs-lookup"><span data-stu-id="c4474-210">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-211"> 支持 WS-Addressing 的两种版本：WS-Addressing 2004/08 [WS-ADDR] 以及 W3C WS-Addressing 1.0 建议 [WS-ADDR-CORE] 和 [WS-ADDR-SOAP]。</span><span class="sxs-lookup"><span data-stu-id="c4474-211"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="c4474-212">尽管 WS-ReliableMessaging 规范仅提及 WS-Addressing 2004/08，但是它不限制要使用的 WS-Addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="c4474-212">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="c4474-213">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-213">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="c4474-214">R2101：WS-Addressing 2004/08 和 WS-Addressing 1.0 都可以与 WS-Reliable Messaging 一起使用。</span><span class="sxs-lookup"><span data-stu-id="c4474-214">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="c4474-215">R2102：在整个的给定 WS-ReliableMessaging 序列或通过使用 `Offer` 机制关联的一对相反序列中，必须使用 WS-Addressing 的单个版本。</span><span class="sxs-lookup"><span data-stu-id="c4474-215">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="c4474-216">与 SOAP 组合</span><span class="sxs-lookup"><span data-stu-id="c4474-216">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-217"> 支持将 SOAP 1.1 和 SOAP 1.2 与 WS-Reliable Messaging 一起使用。</span><span class="sxs-lookup"><span data-stu-id="c4474-217"> supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="c4474-218">与 WS-Security 和 WS-SecureConversation 组合</span><span class="sxs-lookup"><span data-stu-id="c4474-218">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="c4474-219">通过使用安全传输 (HTTPS)、与 WS-Security 的组合以及与 WS-Secure Conversation 的组合，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供了对 WS-ReliableMessaging 序列的保护。</span><span class="sxs-lookup"><span data-stu-id="c4474-219">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="c4474-220">WS-ReliableMessaging 1.1 协议、WS-Security 1.1 和 WS-Secure Conversation 1.3 协议应该一起使用。</span><span class="sxs-lookup"><span data-stu-id="c4474-220">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="c4474-221">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-221">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="c4474-222">R2301：为了保护单个消息的完整性和机密性以及 WS-ReliableMessaging 序列的完整性，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 要求必须使用 WS-Secure Conversation。</span><span class="sxs-lookup"><span data-stu-id="c4474-222">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="c4474-223">R2302:AWS-必须建立 Ws-reliablemessaging sequence(s) 前建立安全对话会话。</span><span class="sxs-lookup"><span data-stu-id="c4474-223">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="c4474-224">R2303：如果 WS-ReliableMessaging 序列生存期超过了 WS-Secure Conversation 会话的生存期，则必须通过使用对应的 WS-Secure Conversation 续订绑定来续订通过使用 WS-Secure Conversation 建立的 `SecurityContextToken`。</span><span class="sxs-lookup"><span data-stu-id="c4474-224">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="c4474-225">B2304:WS-ReliableMessaging 序列或一对相关的反向序列始终被绑定到单个 Ws-secureconversation 会话。</span><span class="sxs-lookup"><span data-stu-id="c4474-225">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="c4474-226">R2305：与 WS-Secure Conversation 组合时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方要求 `CreateSequence` 消息包含 `wsse:SecurityTokenReference` 元素和 `wsrm:UsesSequenceSTR` 头。</span><span class="sxs-lookup"><span data-stu-id="c4474-226">R2305: When composed with WS-Secure Conversation, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="c4474-227">`UsesSequenceSTR` 标头的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-227">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="c4474-228">与 SSL/TLS 会话组合</span><span class="sxs-lookup"><span data-stu-id="c4474-228">Composition with SSL/TLS sessions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-229"> 不支持与 SSL/TLS 会话组合：</span><span class="sxs-lookup"><span data-stu-id="c4474-229"> does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="c4474-230">B2401：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不生成 `wsrm:UsesSequenceSSL` 头。</span><span class="sxs-lookup"><span data-stu-id="c4474-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="c4474-231">R2402：可靠消息发起方不得将包含 `CreateSequence` 头的 `wsrm:UsesSequenceSSL` 消息发送到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方。</span><span class="sxs-lookup"><span data-stu-id="c4474-231">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="c4474-232">与 WS-Policy 组合</span><span class="sxs-lookup"><span data-stu-id="c4474-232">Composition with WS-Policy</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-233"> 支持 WS-Policy 的两种版本：WS-Policy 1.2 和 WS-Policy 1.5。</span><span class="sxs-lookup"><span data-stu-id="c4474-233"> supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="c4474-234">WS-ReliableMessaging WS-Policy 断言</span><span class="sxs-lookup"><span data-stu-id="c4474-234">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-235"> 使用 WS-ReliableMessaging WS-Policy 断言 `wsrm:RMAssertion` 描述终结点功能。</span><span class="sxs-lookup"><span data-stu-id="c4474-235"> uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="c4474-236">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-236">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="c4474-237">B3001：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将 `wsrmn:RMAssertion` WS-Policy 断言附加到 `wsdl:binding` 元素。</span><span class="sxs-lookup"><span data-stu-id="c4474-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-238"> 同时支持附加到 `wsdl:binding` 和 `wsdl:port` 元素。</span><span class="sxs-lookup"><span data-stu-id="c4474-238"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="c4474-239">B3002：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 从不生成 `wsp:Optional` 标记。</span><span class="sxs-lookup"><span data-stu-id="c4474-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="c4474-240">B3003：访问 `wsrmp:RMAssertion` WS-Policy 断言时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 忽略 `wsp:Optional` 标记并将 WS-RM 策略视为强制。</span><span class="sxs-lookup"><span data-stu-id="c4474-240">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="c4474-241">R3004：由于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不与 SSL/TLS 会话组合，因此 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不接受指定 `wsrmp:SequenceTransportSecurity` 的策略。</span><span class="sxs-lookup"><span data-stu-id="c4474-241">R3004: Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not compose with SSL/TLS sessions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="c4474-242">B3005：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 始终生成 `wsrmp:DeliveryAssurance` 元素。</span><span class="sxs-lookup"><span data-stu-id="c4474-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="c4474-243">B3006：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 始终指定 `wsrmp:ExactlyOnce` 传递确定性。</span><span class="sxs-lookup"><span data-stu-id="c4474-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="c4474-244">B3007：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 生成并读取 WS-ReliableMessaging 断言的以下属性，以及在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement` 上提供对它们的控制：</span><span class="sxs-lookup"><span data-stu-id="c4474-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="c4474-245">`RMAssertion` 的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c4474-245">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="c4474-246">流控制 WS-ReliableMessaging 扩展</span><span class="sxs-lookup"><span data-stu-id="c4474-246">Flow Control WS-ReliableMessaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-247"> 使用 WS-ReliableMessaging 扩展性提供对序列消息流的其他可选的更紧密控制。</span><span class="sxs-lookup"><span data-stu-id="c4474-247"> uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="c4474-248">通过设置启用流控制`ReliableSessionBindingElement`的`FlowControlEnabled``boolean`属性`true`。</span><span class="sxs-lookup"><span data-stu-id="c4474-248">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="c4474-249">下面列出了适用于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的约束：</span><span class="sxs-lookup"><span data-stu-id="c4474-249">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="c4474-250">B4001：启用可靠消息流控制时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在 `netrm:BufferRemaining` 头的元素扩展性中生成 `SequenceAcknowledgement` 元素，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="c4474-250">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="c4474-251">B4002：甚至在启用可靠消息流控制时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 也不要求 `netrm:BufferRemaining` 标头中包含 `SequenceAcknowledgement` 元素。</span><span class="sxs-lookup"><span data-stu-id="c4474-251">B4002: Even when Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="c4474-252">B4003：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠消息目标使用 `netrm:BufferRemaining` 指示它可以缓冲多少条新消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-252">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="c4474-253">启用 B4004:When 可靠消息传递流控制时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]可靠消息源使用的值`netrm:BufferRemaining`限制消息传输。</span><span class="sxs-lookup"><span data-stu-id="c4474-253">B4004:When Reliable Messaging Flow Control is enabled, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="c4474-254">B4005：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 生成介于 0 和 4096（包括这两个值）之间的 `netrm:BufferRemaining` 整数值，并读取介于 0 和 `xs:int` 的 `maxInclusive` 值 214748364（包括这两个值）之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="c4474-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="c4474-255">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="c4474-255">Message Exchange Patterns</span></span>  
 <span data-ttu-id="c4474-256">本节介绍 WS-ReliableMessaging 用于不同消息交换模式时 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的行为。</span><span class="sxs-lookup"><span data-stu-id="c4474-256">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="c4474-257">对于每个消息交换模式，可以考虑下面的两个部署方案：</span><span class="sxs-lookup"><span data-stu-id="c4474-257">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="c4474-258">不可寻址的发起方：发起方位于防火墙背后；响应方只能在 HTTP 响应上将消息传递到发起方。</span><span class="sxs-lookup"><span data-stu-id="c4474-258">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="c4474-259">可寻址的发起方：发起方和响应方都可以发送 HTTP 请求；换句话说，可以建立两个相反的 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="c4474-259">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="c4474-260">单向、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="c4474-260">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c4474-261">绑定</span><span class="sxs-lookup"><span data-stu-id="c4474-261">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-262"> 通过在一个 HTTP 通道上使用一个序列的方式，提供单向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="c4474-262"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-263"> 使用 HTTP 请求将所有消息从发起方传输到响应方，并使用 HTTP 响应将所有消息从响应方传输到发起方。</span><span class="sxs-lookup"><span data-stu-id="c4474-263"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c4474-264">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-264">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c4474-265">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输没有 `CreateSequence` 元素的 `Offer` 消息，并在 HTTP 响应上期望 `CreateSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-265">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c4474-266">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方创建一个序列，并在 HTTP 响应上传输没有 `CreateSequenceResponse` 元素的 `Accept` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-266">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="c4474-267">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c4474-267">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="c4474-268">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方处理除 `CreateSequence` 消息和错误消息之外的所有消息答复的确认消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="c4474-269">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方始终将 HTTP 响应上的独立确认传输到所有序列和 `AckRequested` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-269">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="c4474-270">CloseSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-270">CloseSequence Exchange</span></span>  
 <span data-ttu-id="c4474-271">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输 `CloseSequence` 消息，并在 HTTP 响应上期望 `CreateSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-271">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c4474-272">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方在 HTTP 响应上传输 `CloseSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-272">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c4474-273">TerminateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-273">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="c4474-274">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输 `TerminateSequence` 消息，并在 HTTP 响应上期望 `TerminateSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c4474-275">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方在 HTTP 响应上传输 `TerminateSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="c4474-276">单向、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="c4474-276">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c4474-277">绑定</span><span class="sxs-lookup"><span data-stu-id="c4474-277">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-278"> 提供一种单向消息交换模式，这种模式在一个入站和一个出站 HTTP 通道上使用一个序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-278"> provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-279"> 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-279"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c4474-280">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="c4474-280">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c4474-281">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-281">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c4474-282">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输没有 `CreateSequence` 元素的 `Offer` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-282">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c4474-283">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方创建一个序列，并在 HTTP 请求上传输没有 `CreateSequenceResponse` 元素的 `Accept` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-283">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="c4474-284">双工、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="c4474-284">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c4474-285">绑定</span><span class="sxs-lookup"><span data-stu-id="c4474-285">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-286"> 提供了通过一个入站和一个出站 HTTP 通道使用两个序列的完全异步的双向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="c4474-286"> provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c4474-287">此消息交换模式可以与 `Request/Reply`、`Addressable` 发起方消息交换模式以有限方式混合使用。</span><span class="sxs-lookup"><span data-stu-id="c4474-287">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-288"> 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-288"> uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c4474-289">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="c4474-289">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c4474-290">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-290">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c4474-291">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输具有 `CreateSequence` 元素的 `Offer` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-291">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c4474-292">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保 `CreateSequence` 具有 `Offer` 元素，然后创建一个序列并传输具有 `CreateSequenceResponse` 元素的 `Accept` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="c4474-293">序列生存期</span><span class="sxs-lookup"><span data-stu-id="c4474-293">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-294"> 将两个序列视为一个全双工会话。</span><span class="sxs-lookup"><span data-stu-id="c4474-294"> treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="c4474-295">生成使一个序列出错的错误时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 期望远程终结点使这两个序列出错。</span><span class="sxs-lookup"><span data-stu-id="c4474-295">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="c4474-296">读取使一个序列出错的错误时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 会使这两个序列出错。</span><span class="sxs-lookup"><span data-stu-id="c4474-296">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-297"> 可以关闭其出站序列并继续处理其入站序列上的消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-297"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="c4474-298">相反，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可以处理入站序列的关闭，并在其出站序列上继续发送消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-298">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="c4474-299">请求-答复和单向、不可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="c4474-299">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c4474-300">绑定</span><span class="sxs-lookup"><span data-stu-id="c4474-300">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-301"> 通过在一个 HTTP 通道上使用两个序列的方式，提供了单向和请求-答复消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="c4474-301"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-302"> 使用 HTTP 请求将所有消息从发起方传输到响应方，并使用 HTTP 响应将所有消息从响应方传输到发起方。</span><span class="sxs-lookup"><span data-stu-id="c4474-302"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c4474-303">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-303">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c4474-304">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输具有 `CreateSequence` 元素的 `Offer` 消息，并在 HTTP 响应上期望 `CreateSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-304">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c4474-305">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方创建一个序列，并在 HTTP 响应上传输具有 `CreateSequenceResponse` 元素的 `Accept` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-305">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="c4474-306">单向消息</span><span class="sxs-lookup"><span data-stu-id="c4474-306">One-way Message</span></span>  
 <span data-ttu-id="c4474-307">为成功完成单向消息交换，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输请求序列消息，并在 HTTP 响应上接收独立的 `SequenceAcknowledgement` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-307">To complete a one-way message exchange successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="c4474-308">`SequenceAcknowledgement` 必须确认已传输的消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-308">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="c4474-309">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方可能通过确认、错误或正文为空且具有 HTTP 202 状态代码的响应来答复请求。</span><span class="sxs-lookup"><span data-stu-id="c4474-309">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="c4474-310">双向消息</span><span class="sxs-lookup"><span data-stu-id="c4474-310">Two Way Messages</span></span>  
 <span data-ttu-id="c4474-311">为了成功地完成双向消息交换协议，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输请求序列消息，并在 HTTP 响应上接收答复序列消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-311">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="c4474-312">响应必须包含一个确认已传输的请求序列消息的 `SequenceAcknowledgement`。</span><span class="sxs-lookup"><span data-stu-id="c4474-312">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="c4474-313">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方可以使用应用程序答复、错误或正文为空且具有 HTTP 202 状态代码的响应来答复请求。</span><span class="sxs-lookup"><span data-stu-id="c4474-313">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="c4474-314">由于存在单向消息和应用程序答复的计时，因此请求序列消息的序列号与响应消息的序列号不相关联。</span><span class="sxs-lookup"><span data-stu-id="c4474-314">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="c4474-315">重试答复</span><span class="sxs-lookup"><span data-stu-id="c4474-315">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-316"> 依赖于 HTTP 请求-答复关联来进行双向消息交换协议关联。</span><span class="sxs-lookup"><span data-stu-id="c4474-316"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="c4474-317">由于这一原因，在已确认请求序列消息时而不是在 HTTP 响应包含 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]、应用程序答复或错误时，`SequenceAcknowledgement` 发起方不停止重试请求序列消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-317">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="c4474-318">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方在答复与其相关的请求的 HTTP 响应上重试答复。</span><span class="sxs-lookup"><span data-stu-id="c4474-318">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="c4474-319">CloseSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-319">CloseSequence Exchange</span></span>  
 <span data-ttu-id="c4474-320">收到所有单向请求序列消息的所有答复序列消息和确认后，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输请求序列的 `CloseSequence` 消息，并在 HTTP 响应上期望 `CloseSequenceResponse`。</span><span class="sxs-lookup"><span data-stu-id="c4474-320">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="c4474-321">关闭请求序列将隐式关闭答复序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-321">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="c4474-322">这意味着 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 `SequenceAcknowledgement` 消息上包括答复序列的最终 `CloseSequence`，且答复序列没有 `CloseSequence` 交换。</span><span class="sxs-lookup"><span data-stu-id="c4474-322">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="c4474-323">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保已确认所有答复并在 HTTP 响应上传输 `CloseSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-323">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c4474-324">TerminateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-324">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="c4474-325">收到 `CloseSequenceResponse` 消息后，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输请求序列的 `TerminateSequence` 消息，并在 HTTP 响应上期望 `TerminateSequenceResponse`。</span><span class="sxs-lookup"><span data-stu-id="c4474-325">After receiving the `CloseSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="c4474-326">与 `CloseSequence` 交换一样，终止请求序列将隐式终止答复序列。</span><span class="sxs-lookup"><span data-stu-id="c4474-326">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="c4474-327">这意味着 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 `SequenceAcknowledgement` 消息上包括答复序列的最终 `TerminateSequence`，且答复序列没有 `TerminateSequence` 交换。</span><span class="sxs-lookup"><span data-stu-id="c4474-327">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="c4474-328">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方在 HTTP 响应上传输 `TerminateSequenceResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-328">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="c4474-329">请求/答复、可寻址的发起方</span><span class="sxs-lookup"><span data-stu-id="c4474-329">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c4474-330">绑定</span><span class="sxs-lookup"><span data-stu-id="c4474-330">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-331"> 提供了通过一个入站和一个出站 HTTP 通道使用两个序列的请求-答复消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="c4474-331"> provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c4474-332">此消息交换模式可以与 `Duplex, Addressable` 发起方消息交换模式以有限方式混合使用。</span><span class="sxs-lookup"><span data-stu-id="c4474-332">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-333"> 使用 HTTP 请求传输所有消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-333"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c4474-334">所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。</span><span class="sxs-lookup"><span data-stu-id="c4474-334">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c4474-335">CreateSequence 交换</span><span class="sxs-lookup"><span data-stu-id="c4474-335">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c4474-336">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发起方在 HTTP 请求上传输具有 `CreateSequence` 元素的 `Offer` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-336">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c4474-337">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 响应方确保 `CreateSequence` 具有 `Offer` 元素，然后创建一个序列并传输具有 `CreateSequenceResponse` 元素的 `Accept` 消息。</span><span class="sxs-lookup"><span data-stu-id="c4474-337">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="c4474-338">请求/答复关联</span><span class="sxs-lookup"><span data-stu-id="c4474-338">Request/Reply Correlation</span></span>  
 <span data-ttu-id="c4474-339">以下内容适用于所有关联的请求和答复：</span><span class="sxs-lookup"><span data-stu-id="c4474-339">The following applies to all correlated requests and replies:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-340"> 确保所有应用程序请求消息都具有 `ReplyTo` 终结点引用和 `MessageId`。</span><span class="sxs-lookup"><span data-stu-id="c4474-340"> ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-341"> 将本地终结点引用作为每个应用程序请求消息的 `ReplyTo` 应用。</span><span class="sxs-lookup"><span data-stu-id="c4474-341"> applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="c4474-342">本地终结点引用是发起方的 `CreateSequence` 消息的 `ReplyTo` 和响应方的 `CreateSequence` 消息的 `To`。</span><span class="sxs-lookup"><span data-stu-id="c4474-342">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-343"> 确保传入请求消息具有 `MessageId` 和 `ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="c4474-343"> ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-344"> 确保所有应用程序请求消息的 `ReplyTo` 终结点引用的 URI 都与前面定义的本地终结点引用匹配。</span><span class="sxs-lookup"><span data-stu-id="c4474-344"> ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c4474-345"> 确保所有答复都具有遵循 `RelatesTo` 请求/答复关联规则的正确 `To` 和 `wsa` 头。</span><span class="sxs-lookup"><span data-stu-id="c4474-345"> ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
