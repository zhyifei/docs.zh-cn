---
title: WCF 中的安全注意事项
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 6cc19f7719b9cdbcd3852c99f450c1d728dc833b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745953"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="cf49a-102">WCF 中的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="cf49a-102">Security Considerations in WCF</span></span>
<span data-ttu-id="cf49a-103">在本部分中的主题列出了各种与安全相关项设计的 Windows Communication Foundation (WCF) 应用程序时要考虑。</span><span class="sxs-lookup"><span data-stu-id="cf49a-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf49a-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf49a-104">In This Section</span></span>  
 [<span data-ttu-id="cf49a-105">信息泄漏</span><span class="sxs-lookup"><span data-stu-id="cf49a-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="cf49a-106">讨论信息可能泄露或受到攻击的各种方式，以及如何缓解这些问题。</span><span class="sxs-lookup"><span data-stu-id="cf49a-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="cf49a-107">特权提升</span><span class="sxs-lookup"><span data-stu-id="cf49a-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="cf49a-108">讨论给予攻击者的权限超出最初授予的权限范围的后果，以及如何减轻这种后果。</span><span class="sxs-lookup"><span data-stu-id="cf49a-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="cf49a-109">拒绝服务</span><span class="sxs-lookup"><span data-stu-id="cf49a-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="cf49a-110">讨论当系统无法正确处理消息时所发生的情况，以及如何缓解这一问题。</span><span class="sxs-lookup"><span data-stu-id="cf49a-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="cf49a-111">篡改</span><span class="sxs-lookup"><span data-stu-id="cf49a-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="cf49a-112">讨论消息或消息传递的篡改以及如何缓解这种问题。</span><span class="sxs-lookup"><span data-stu-id="cf49a-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="cf49a-113">重放攻击</span><span class="sxs-lookup"><span data-stu-id="cf49a-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="cf49a-114">讨论当攻击者复制通信双方之间的消息流并将该消息流向一方或多方重播时将发生的情况，以及如何缓解这一问题。</span><span class="sxs-lookup"><span data-stu-id="cf49a-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="cf49a-115">安全会话的安全性注意事项</span><span class="sxs-lookup"><span data-stu-id="cf49a-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="cf49a-116">讨论在实现安全会话时影响安全的下列事项。</span><span class="sxs-lookup"><span data-stu-id="cf49a-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="cf49a-117">不支持的方案</span><span class="sxs-lookup"><span data-stu-id="cf49a-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="cf49a-118">列出不支持某个特定安全方面的各种方案，应当避免或谨慎考虑这些方案。</span><span class="sxs-lookup"><span data-stu-id="cf49a-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cf49a-119">参考</span><span class="sxs-lookup"><span data-stu-id="cf49a-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="cf49a-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="cf49a-120">Related Sections</span></span>  
 [<span data-ttu-id="cf49a-121">安全指导和最佳做法</span><span class="sxs-lookup"><span data-stu-id="cf49a-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf49a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf49a-122">See also</span></span>
- [<span data-ttu-id="cf49a-123">安全性</span><span class="sxs-lookup"><span data-stu-id="cf49a-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
