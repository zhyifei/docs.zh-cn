---
title: 安全会话
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: d511a45d990e441c5dcfd8405794ec937c0278d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966076"
---
# <a name="secure-sessions"></a><span data-ttu-id="fac02-102">安全会话</span><span class="sxs-lookup"><span data-stu-id="fac02-102">Secure Sessions</span></span>
<span data-ttu-id="fac02-103">Windows Communication Foundation (WCF) 的一项功能是可靠会话, 可保证按消息发送顺序接收消息。</span><span class="sxs-lookup"><span data-stu-id="fac02-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="fac02-104">本节中的主题讨论在创建可靠会话时要考虑的安全性问题。</span><span class="sxs-lookup"><span data-stu-id="fac02-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="fac02-105">有关可靠会话的详细信息, 请参阅[使用会话](../../../../docs/framework/wcf/using-sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="fac02-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fac02-106">当需要在 Windows XP 上进行模拟时，请不要在安全会话中使用有状态安全令牌上下文 (SCT)。</span><span class="sxs-lookup"><span data-stu-id="fac02-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="fac02-107">如果在模拟时使用有状态 SCT，则会引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="fac02-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="fac02-108">有关详细信息, 请参阅[不支持的方案](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="fac02-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fac02-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="fac02-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="fac02-110">安全对话和安全会话</span><span class="sxs-lookup"><span data-stu-id="fac02-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="fac02-111">安全对话和安全会话是同义词。</span><span class="sxs-lookup"><span data-stu-id="fac02-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="fac02-112">本主题解释安全对话的工作方式以及使用该模式的时机和原因。</span><span class="sxs-lookup"><span data-stu-id="fac02-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="fac02-113">如何：创建安全会话</span><span class="sxs-lookup"><span data-stu-id="fac02-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="fac02-114">演练创建安全会话的基本操作。</span><span class="sxs-lookup"><span data-stu-id="fac02-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="fac02-115">如何：创建安全会话的安全上下文令牌</span><span class="sxs-lookup"><span data-stu-id="fac02-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="fac02-116">演练创建能够保持状态以及与客户端之间会话的网络场的步骤。</span><span class="sxs-lookup"><span data-stu-id="fac02-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="fac02-117">安全会话的安全性注意事项</span><span class="sxs-lookup"><span data-stu-id="fac02-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="fac02-118">描述安全会话的特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="fac02-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="fac02-119">参考</span><span class="sxs-lookup"><span data-stu-id="fac02-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="fac02-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="fac02-120">Related Sections</span></span>  
 [<span data-ttu-id="fac02-121">会话、实例化和并发</span><span class="sxs-lookup"><span data-stu-id="fac02-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="fac02-122">设计和实现服务</span><span class="sxs-lookup"><span data-stu-id="fac02-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="fac02-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="fac02-123">See also</span></span>

- [<span data-ttu-id="fac02-124">如何：启用消息重播检测</span><span class="sxs-lookup"><span data-stu-id="fac02-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="fac02-125">重放攻击</span><span class="sxs-lookup"><span data-stu-id="fac02-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [<span data-ttu-id="fac02-126">如何：创建需要会话的服务</span><span class="sxs-lookup"><span data-stu-id="fac02-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
