---
title: "安全对话和安全会话"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d519640c40daf248a01a19f0450f3aea8de6cc04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="secure-conversations-and-secure-sessions"></a><span data-ttu-id="a6c42-102">安全对话和安全会话</span><span class="sxs-lookup"><span data-stu-id="a6c42-102">Secure Conversations and Secure Sessions</span></span>
<span data-ttu-id="a6c42-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 的一项功能是能够在如下两个终结点之间建立安全会话：这两个终结点互相进行身份验证，并就加密和数字签名过程达成一致。</span><span class="sxs-lookup"><span data-stu-id="a6c42-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to establish secure sessions between two endpoints that authenticate each other and agree upon an encryption and digital signature process.</span></span> <span data-ttu-id="a6c42-104">例如，服务终结点可能要求客户端终结点发送一个基于 X.509 证书的安全令牌，以便进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a6c42-104">For example, the service endpoint might require a client endpoint to send a security token based upon an X.509 certificate for authentication.</span></span> <span data-ttu-id="a6c42-105">在对客户端进行身份验证之后，服务终结点将向客户端返回一个安全上下文令牌 (SCT)，该令牌随后将用于保护该会话中的所有后续消息。</span><span class="sxs-lookup"><span data-stu-id="a6c42-105">Once the client is authenticated, the service endpoint returns a security context token (SCT) back to the client that is then used to secure all subsequent messages within the session.</span></span> <span data-ttu-id="a6c42-106">通过建立这一安全会话，可使两个终结点之间交换的一组消息更有效率，因为 SCT 具有对称密钥。</span><span class="sxs-lookup"><span data-stu-id="a6c42-106">Establishing this secure session enables the set of messages that are exchanged between the two endpoints to be more efficient, because the SCT has a symmetric key.</span></span> <span data-ttu-id="a6c42-107">在生成数字签名或加密一组数据时，与对称密钥相比，作为 X.509 证书基础的非对称密钥明显需要更多的计算能力。</span><span class="sxs-lookup"><span data-stu-id="a6c42-107">Asymmetric keys, which X.509 certificates are based upon, require significantly more computational power than symmetric keys when generating a digital signature or encrypting a set of data.</span></span>  
  
 <span data-ttu-id="a6c42-108">启动策略 (6.2.7 节中定义[Ws-securitypolicy](http://go.microsoft.com/fwlink/?LinkId=99817)标准) 包含用于通道的安全和身份验证之前 RST/SCT 和 RSTR/SCT exchange 客户端的消息安全断言。</span><span class="sxs-lookup"><span data-stu-id="a6c42-108">The bootstrap policy (defined in section 6.2.7 of the [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) contains the message security assertions used to secure the channel and authenticate the client prior to the RST/SCT and RSTR/SCT exchange.</span></span> <span data-ttu-id="a6c42-109">某些 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 标准绑定具有一个 `Security.Message.EstablishSecurityContext` 属性，该属性用于控制是否使用安全对话。</span><span class="sxs-lookup"><span data-stu-id="a6c42-109">Certain [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standard bindings have a `Security.Message.EstablishSecurityContext` property which controls whether secure conversation is used.</span></span> <span data-ttu-id="a6c42-110">当使用自定义绑定时由嵌套的安全绑定元素，不论是通过指示 bootstrap [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)在配置文件中，或通过调用<xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>在代码中。</span><span class="sxs-lookup"><span data-stu-id="a6c42-110">When using custom bindings the bootstrap is indicated by nesting security binding elements, either through [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in the configuration file, or by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> in code.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a6c42-111">会话，请参阅[使用会话](../../../../docs/framework/wcf/using-sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="a6c42-111"> sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c42-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c42-112">See Also</span></span>  
 [<span data-ttu-id="a6c42-113">会话、实例化和并发</span><span class="sxs-lookup"><span data-stu-id="a6c42-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="a6c42-114">如何：创建要求会话的服务</span><span class="sxs-lookup"><span data-stu-id="a6c42-114">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
