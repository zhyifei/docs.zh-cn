---
title: 安全会话的安全注意事项
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 4d1e5082ace452eabddd91a45a20c6d6363e118b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="security-considerations-for-secure-sessions"></a><span data-ttu-id="6b625-102">安全会话的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="6b625-102">Security Considerations for Secure Sessions</span></span>
<span data-ttu-id="6b625-103">您应考虑实现安全会话时影响安全的下列事项。</span><span class="sxs-lookup"><span data-stu-id="6b625-103">You should consider the following items that affect security when implementing secure sessions.</span></span> <span data-ttu-id="6b625-104">有关安全注意事项的详细信息，请参阅[安全注意事项](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)和[安全性的最佳做法](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="6b625-104">For more information about security considerations, see [Security Considerations](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) and [Best Practices for Security](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).</span></span>  
  
## <a name="secure-sessions-and-metadata"></a><span data-ttu-id="6b625-105">安全会话和元数据</span><span class="sxs-lookup"><span data-stu-id="6b625-105">Secure Sessions and Metadata</span></span>  
 <span data-ttu-id="6b625-106">当建立安全会话并且 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> 属性设置为 `false` 时，作为服务终结点的 Web Services 描述语言 (WSDL) 文档中元数据的一部分，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 发送 `mssp:MustNotSendCancel` 断言。</span><span class="sxs-lookup"><span data-stu-id="6b625-106">When a secure session is established and the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> property is set to `false`, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sends an `mssp:MustNotSendCancel` assertion as part of the metadata in the Web Services Description Language (WSDL) document for the service endpoint.</span></span> <span data-ttu-id="6b625-107">`mssp:MustNotSendCancel` 断言通知客户端此服务不响应取消安全会话的请求。</span><span class="sxs-lookup"><span data-stu-id="6b625-107">The `mssp:MustNotSendCancel` assertion informs clients that the service does not respond to requests to cancel the secure session.</span></span> <span data-ttu-id="6b625-108">当 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> 属性设置为 `true` 时，在 WSDL 文档中，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不发出 `mssp:MustNotSendCancel` 断言。</span><span class="sxs-lookup"><span data-stu-id="6b625-108">When the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> property is set to `true`, then [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not emit an `mssp:MustNotSendCancel` assertion in the WSDL document.</span></span> <span data-ttu-id="6b625-109">当客户端不再需要安全会话时，客户端应向服务发送一个取消请求。</span><span class="sxs-lookup"><span data-stu-id="6b625-109">Clients are expected to send a cancel request to the service when they no longer require the secure session.</span></span> <span data-ttu-id="6b625-110">使用生成客户端时[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)，客户端代码是否存在对相应地做出反应`mssp:MustNotSendCancel`断言。</span><span class="sxs-lookup"><span data-stu-id="6b625-110">When a client is generated using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), the client code reacts appropriately to the presence or absence of the `mssp:MustNotSendCancel` assertion.</span></span>  
  
## <a name="secure-conversations-and-custom-tokens"></a><span data-ttu-id="6b625-111">安全对话和自定义令牌</span><span class="sxs-lookup"><span data-stu-id="6b625-111">Secure Conversations and Custom Tokens</span></span>  
 <span data-ttu-id="6b625-112">将自定义令牌和派生密钥混合使用会产生一些问题，这是它在 WS-SecureConversation 规范中的定义方式所导致的。</span><span class="sxs-lookup"><span data-stu-id="6b625-112">There are some issues with mixing custom tokens and derived keys due to the way it is defined in the WS-SecureConversation specification.</span></span> <span data-ttu-id="6b625-113">该规范指出`wsse:SecurityTokenReference`是引用派生的令牌的可选元素:"`/wsc:DerivedKeyToken/wsse:SecurityTokenReference`这一可选元素用于指定安全上下文令牌、 安全令牌或用于派生的共享的密钥/机密。</span><span class="sxs-lookup"><span data-stu-id="6b625-113">The specification says that `wsse:SecurityTokenReference` is an optional element that references the derived token: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` This optional element is used to specify security context token, security token, or shared key/secret used for the derivation.</span></span> <span data-ttu-id="6b625-114">如果未指定，则假定收件人可以从消息上下文确定共享密钥。</span><span class="sxs-lookup"><span data-stu-id="6b625-114">If not specified, it is assumed that the recipient can determine the shared key from the message context.</span></span> <span data-ttu-id="6b625-115">如果无法确定上下文，然后如错误`wsc:UnknownDerivationSource`应引发。"</span><span class="sxs-lookup"><span data-stu-id="6b625-115">If the context cannot be determined, then a fault such as `wsc:UnknownDerivationSource` should be raised."</span></span>  
  
 <span data-ttu-id="6b625-116">这意味着，如果希望派生自定义令牌，应该将其子句类型包装在 `SecurityTokenReference` 元素中。</span><span class="sxs-lookup"><span data-stu-id="6b625-116">This means that if you want a custom token to be derived, you should wrap its clause type in a `SecurityTokenReference` element.</span></span> <span data-ttu-id="6b625-117">有一个选项可关闭派生，但是默认为派生密钥。</span><span class="sxs-lookup"><span data-stu-id="6b625-117">There is an option to turn off derivation but the default is to derive keys.</span></span> <span data-ttu-id="6b625-118">如果无法封装密钥，则对派生密钥令牌进行序列化将成功，但是尝试对其进行反序列化将引发异常。</span><span class="sxs-lookup"><span data-stu-id="6b625-118">If you fail to wrap the key, serializing the derived key token succeeds, but attempting to deserialize it throws an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b625-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b625-119">See Also</span></span>  
 [<span data-ttu-id="6b625-120">如何：在 WSFederationHttpBinding 上禁用安全会话</span><span class="sxs-lookup"><span data-stu-id="6b625-120">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="6b625-121">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="6b625-121">Security Considerations</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [<span data-ttu-id="6b625-122">安全性的最佳做法</span><span class="sxs-lookup"><span data-stu-id="6b625-122">Best Practices for Security</span></span>](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
