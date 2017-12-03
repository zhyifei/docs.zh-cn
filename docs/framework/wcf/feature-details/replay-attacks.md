---
title: "重播攻击"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd96404adea7fb8e7d59dcea322b2d3832f2bfe4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="replay-attacks"></a><span data-ttu-id="38549-102">重播攻击</span><span class="sxs-lookup"><span data-stu-id="38549-102">Replay Attacks</span></span>
<span data-ttu-id="38549-103">A*重播攻击*攻击者复制双方之间的消息流并将该到一个或多个方时发生。</span><span class="sxs-lookup"><span data-stu-id="38549-103">A *replay attack* occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="38549-104">除非攻击得到缓解，否则，受到攻击的计算机会将该消息流作为合法消息进行处理，从而导致一系列不良后果，例如重复订购某种产品。</span><span class="sxs-lookup"><span data-stu-id="38549-104">Unless mitigated, the computers subject to the attack process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a><span data-ttu-id="38549-105">绑定可能会遭受反射攻击</span><span class="sxs-lookup"><span data-stu-id="38549-105">Bindings May Be Subject to Reflection Attacks</span></span>  
 <span data-ttu-id="38549-106">*反射攻击*是重播回发送方的消息，就像它们来自接收方的答复一样。</span><span class="sxs-lookup"><span data-stu-id="38549-106">*Reflection attacks* are replays of messages back to a sender as if they came from the receiver as the reply.</span></span> <span data-ttu-id="38549-107">标准*重放检测*中[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]机制并不自动处理这。</span><span class="sxs-lookup"><span data-stu-id="38549-107">The standard *replay detection* in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mechanism does not automatically handle this.</span></span>  
  
 <span data-ttu-id="38549-108">默认情况下，反射攻击会得到缓解，因为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务模型会将一个已签名的消息 ID 添加到请求消息中，并要求响应消息中具有一个已签名的 `relates-to` 标头。</span><span class="sxs-lookup"><span data-stu-id="38549-108">Reflection attacks are mitigated by default because the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service model adds a signed message ID to request messages and expects a signed `relates-to` header on response messages.</span></span> <span data-ttu-id="38549-109">因此，请求消息无法作为响应进行重播。</span><span class="sxs-lookup"><span data-stu-id="38549-109">Consequently, the request message cannot be replayed as a response.</span></span> <span data-ttu-id="38549-110">在安全的可靠消息 (RM) 方案中，反射攻击会由于以下原因而得到缓解：</span><span class="sxs-lookup"><span data-stu-id="38549-110">In secure reliable message (RM) scenarios, reflection attacks are mitigated because:</span></span>  
  
-   <span data-ttu-id="38549-111">创建序列架构和创建序列响应消息架构是不同的。</span><span class="sxs-lookup"><span data-stu-id="38549-111">The create sequence and create sequence response message schemas are different.</span></span>  
  
-   <span data-ttu-id="38549-112">对于单工序列，无法将客户端发送的序列消息重播回客户端，因为客户端无法理解这样的消息。</span><span class="sxs-lookup"><span data-stu-id="38549-112">For simplex sequences, sequence messages the client sends cannot be replayed back to it because the client cannot understand such messages.</span></span>  
  
-   <span data-ttu-id="38549-113">对于双工序列，这两个序列 ID 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="38549-113">For duplex sequences, the two sequence IDs must be unique.</span></span> <span data-ttu-id="38549-114">因此，无法将传出序列消息作为传入序列消息重播回发送方（所有序列标头和正文也都进行了签名）。</span><span class="sxs-lookup"><span data-stu-id="38549-114">Thus, an outgoing sequence message cannot be replayed back as an incoming sequence message (all sequence headers and bodies are signed, too).</span></span>  
  
 <span data-ttu-id="38549-115">唯一容易遭受反射攻击的绑定是那些不使用 WS-Addressing 的绑定，即那些禁用了 WS-Addressing 的自定义绑定以及那些使用基于对称密钥的安全的绑定。</span><span class="sxs-lookup"><span data-stu-id="38549-115">The only bindings that are susceptible to reflection attacks are those without WS-Addressing: custom bindings that have WS-Addressing disabled and use the symmetric key-based security.</span></span> <span data-ttu-id="38549-116">默认情况下，<xref:System.ServiceModel.BasicHttpBinding> 不使用 WS-Addressing，但是它不会以使其容易遭受反射攻击的方式使用基于对称密钥的安全。</span><span class="sxs-lookup"><span data-stu-id="38549-116">The <xref:System.ServiceModel.BasicHttpBinding> does not use WS-Addressing by default, but it does not use symmetric key-based security in a way that allows it to be vulnerable to this attack.</span></span>  
  
 <span data-ttu-id="38549-117">自定义绑定的缓解措施是不建立安全上下文或要求使用 WS-Addressing 标头。</span><span class="sxs-lookup"><span data-stu-id="38549-117">The mitigation for custom bindings is to not establish security context or to require WS-Addressing headers.</span></span>  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a><span data-ttu-id="38549-118">网络场：攻击者向多个节点重播请求</span><span class="sxs-lookup"><span data-stu-id="38549-118">Web Farm: Attacker Replays Request to Multiple Nodes</span></span>  
 <span data-ttu-id="38549-119">客户端使用在网络场中实现的服务。</span><span class="sxs-lookup"><span data-stu-id="38549-119">A client uses a service that is implemented on a Web farm.</span></span> <span data-ttu-id="38549-120">攻击者将发送到网络场中某个节点的请求重播到该网络场中的其他节点。</span><span class="sxs-lookup"><span data-stu-id="38549-120">An attacker replays a request that was sent to one node in the farm to another node in the farm.</span></span> <span data-ttu-id="38549-121">另外，如果重新启动服务，则会刷新重播缓存，从而使攻击者可以重播请求。</span><span class="sxs-lookup"><span data-stu-id="38549-121">In addition, if a service is restarted, the replay cache is flushed, allowing an attacker to replay the request.</span></span> <span data-ttu-id="38549-122">（该缓存包含已使用过的、先前已见到的消息签名值并可以防止重播，因此这些签名只能使用一次。</span><span class="sxs-lookup"><span data-stu-id="38549-122">(The cache contains used, previously seen message signature values and prevents replays so those signatures can be used only once.</span></span> <span data-ttu-id="38549-123">重播缓存不在整个网络场中共享。）</span><span class="sxs-lookup"><span data-stu-id="38549-123">Replay caches are not shared across a Web farm.)</span></span>  
  
 <span data-ttu-id="38549-124">缓解措施包括：</span><span class="sxs-lookup"><span data-stu-id="38549-124">Mitigations include:</span></span>  
  
-   <span data-ttu-id="38549-125">将消息模式安全与有状态安全上下文令牌结合使用（启用或不启用安全对话）。</span><span class="sxs-lookup"><span data-stu-id="38549-125">Use message mode security with stateful security context tokens (with or without secure conversation enabled).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="38549-126">[如何： 创建安全上下文令牌的安全会话](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)。</span><span class="sxs-lookup"><span data-stu-id="38549-126"> [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
-   <span data-ttu-id="38549-127">将服务配置为使用传输级安全。</span><span class="sxs-lookup"><span data-stu-id="38549-127">Configure the service to use transport-level security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38549-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38549-128">See Also</span></span>  
 [<span data-ttu-id="38549-129">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="38549-129">Security Considerations</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [<span data-ttu-id="38549-130">信息泄露</span><span class="sxs-lookup"><span data-stu-id="38549-130">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [<span data-ttu-id="38549-131">提升权限</span><span class="sxs-lookup"><span data-stu-id="38549-131">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [<span data-ttu-id="38549-132">拒绝服务</span><span class="sxs-lookup"><span data-stu-id="38549-132">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [<span data-ttu-id="38549-133">被篡改</span><span class="sxs-lookup"><span data-stu-id="38549-133">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [<span data-ttu-id="38549-134">不支持的方案</span><span class="sxs-lookup"><span data-stu-id="38549-134">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
