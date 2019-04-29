---
title: Windows Communication Foundation 安全性
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 58bec40f197dd1f2b104607a65c3ad456b95f69d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748456"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="69833-102">Windows Communication Foundation 安全性</span><span class="sxs-lookup"><span data-stu-id="69833-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="69833-103">在本部分中的主题介绍 Windows Communication Foundation (WCF) 安全功能以及如何使用它们来保护消息。</span><span class="sxs-lookup"><span data-stu-id="69833-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="69833-104">有关 Windows Server AppFabric 和安全性的详细信息，请参阅[Windows Server AppFabric 的安全模型](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="69833-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69833-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="69833-105">In This Section</span></span>  
 [<span data-ttu-id="69833-106">安全性概述</span><span class="sxs-lookup"><span data-stu-id="69833-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="69833-107">介绍 WCF 中的安全功能。</span><span class="sxs-lookup"><span data-stu-id="69833-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="69833-108">安全性概念</span><span class="sxs-lookup"><span data-stu-id="69833-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="69833-109">介绍基本术语和 WCF 安全中使用的概念。</span><span class="sxs-lookup"><span data-stu-id="69833-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="69833-110">常用安全方案</span><span class="sxs-lookup"><span data-stu-id="69833-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="69833-111">介绍方案和拓扑可以使用 WCF 配置。</span><span class="sxs-lookup"><span data-stu-id="69833-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="69833-112">安全行为</span><span class="sxs-lookup"><span data-stu-id="69833-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="69833-113">概要介绍会影响安全的 WCF 行为，例如设置凭据。</span><span class="sxs-lookup"><span data-stu-id="69833-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="69833-114">绑定与安全</span><span class="sxs-lookup"><span data-stu-id="69833-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="69833-115">面向安全的绑定视图，包括演示如何创建自定义安全绑定的主题。</span><span class="sxs-lookup"><span data-stu-id="69833-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="69833-116">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="69833-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="69833-117">介绍如何保护消息使用 WCF 安全功能。</span><span class="sxs-lookup"><span data-stu-id="69833-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="69833-118">身份验证</span><span class="sxs-lookup"><span data-stu-id="69833-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="69833-119">演示常见的身份验证任务。</span><span class="sxs-lookup"><span data-stu-id="69833-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="69833-120">授权</span><span class="sxs-lookup"><span data-stu-id="69833-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="69833-121">描述带有安全实现的常见授权方案。</span><span class="sxs-lookup"><span data-stu-id="69833-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="69833-122">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="69833-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="69833-123">描述联合身份验证的基本知识以及如何创建与联合服务器进行通信的客户端。</span><span class="sxs-lookup"><span data-stu-id="69833-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="69833-124">部分信任</span><span class="sxs-lookup"><span data-stu-id="69833-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="69833-125">介绍如何运行部分受信任时运行部分受信任的方案和 WCF 限制。</span><span class="sxs-lookup"><span data-stu-id="69833-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="69833-126">审核</span><span class="sxs-lookup"><span data-stu-id="69833-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="69833-127">描述如何审核安全事件。</span><span class="sxs-lookup"><span data-stu-id="69833-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="69833-128">安全指导和最佳做法</span><span class="sxs-lookup"><span data-stu-id="69833-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="69833-129">有关创建安全的 WCF 应用程序的指导。</span><span class="sxs-lookup"><span data-stu-id="69833-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="69833-130">参考</span><span class="sxs-lookup"><span data-stu-id="69833-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="69833-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="69833-131">Related Sections</span></span>  
 [<span data-ttu-id="69833-132">WCF 功能详细信息</span><span class="sxs-lookup"><span data-stu-id="69833-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="69833-133">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="69833-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="69833-134">入门教程</span><span class="sxs-lookup"><span data-stu-id="69833-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="69833-135">概念性概述</span><span class="sxs-lookup"><span data-stu-id="69833-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="69833-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="69833-136">See also</span></span>

- [<span data-ttu-id="69833-137">配置应用程序</span><span class="sxs-lookup"><span data-stu-id="69833-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
