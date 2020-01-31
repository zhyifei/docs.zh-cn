---
title: Windows Communication Foundation 보안
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 0f79ac28af45e8c05922373955c5317095d2c682
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744632"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="2f2a5-102">Windows Communication Foundation 보안</span><span class="sxs-lookup"><span data-stu-id="2f2a5-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="2f2a5-103">本节中的主题介绍 Windows Communication Foundation （WCF）安全功能以及如何使用它们来帮助保护消息。</span><span class="sxs-lookup"><span data-stu-id="2f2a5-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="2f2a5-104">有关 Windows Server AppFabric 和 security 的详细信息，请参阅[Windows Server Appfabric 安全模型](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2f2a5-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f2a5-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2f2a5-105">In This Section</span></span>  
 [<span data-ttu-id="2f2a5-106">보안 개요</span><span class="sxs-lookup"><span data-stu-id="2f2a5-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="2f2a5-107">描述 WCF 中的安全功能。</span><span class="sxs-lookup"><span data-stu-id="2f2a5-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="2f2a5-108">보안 개념</span><span class="sxs-lookup"><span data-stu-id="2f2a5-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="2f2a5-109">描述 WCF 安全性中使用的基本术语和概念。</span><span class="sxs-lookup"><span data-stu-id="2f2a5-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="2f2a5-110">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="2f2a5-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="2f2a5-111">介绍可以配置 WCF 的方案和拓扑。</span><span class="sxs-lookup"><span data-stu-id="2f2a5-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="2f2a5-112">보안 동작</span><span class="sxs-lookup"><span data-stu-id="2f2a5-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="2f2a5-113">보안에 영향을 주는 WCF 동작에 대한 개요를 제공합니다(예: 자격 증명 설정).</span><span class="sxs-lookup"><span data-stu-id="2f2a5-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="2f2a5-114">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="2f2a5-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="2f2a5-115">사용자 지정 보안 바인딩을 만드는 방법을 보여 주는 항목을 비롯한 바인딩의 보안 지향적인 뷰입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2a5-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="2f2a5-116">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="2f2a5-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="2f2a5-117">介绍如何使用 WCF 安全功能保护消息。</span><span class="sxs-lookup"><span data-stu-id="2f2a5-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="2f2a5-118">인증</span><span class="sxs-lookup"><span data-stu-id="2f2a5-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="2f2a5-119">일반적인 인증 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f2a5-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="2f2a5-120">권한 부여</span><span class="sxs-lookup"><span data-stu-id="2f2a5-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="2f2a5-121">보안 구현을 사용하여 일반적인 인증 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2a5-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="2f2a5-122">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="2f2a5-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="2f2a5-123">페더레이션 기본 사항 및 페더레이션 서버와 통신하는 클라이언트를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2a5-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="2f2a5-124">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="2f2a5-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="2f2a5-125">介绍如何运行部分受信任的方案和 WCF 限制（在部分受信任的情况下运行）。</span><span class="sxs-lookup"><span data-stu-id="2f2a5-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="2f2a5-126">감사</span><span class="sxs-lookup"><span data-stu-id="2f2a5-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="2f2a5-127">보안 이벤트를 감사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2a5-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="2f2a5-128">보안 지침 및 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="2f2a5-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="2f2a5-129">用于创建安全 WCF 应用程序的准则。</span><span class="sxs-lookup"><span data-stu-id="2f2a5-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2f2a5-130">참조</span><span class="sxs-lookup"><span data-stu-id="2f2a5-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="2f2a5-131">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="2f2a5-131">Related Sections</span></span>  
 [<span data-ttu-id="2f2a5-132">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="2f2a5-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="2f2a5-133">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2f2a5-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="2f2a5-134">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="2f2a5-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="2f2a5-135">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="2f2a5-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f2a5-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f2a5-136">See also</span></span>

- [<span data-ttu-id="2f2a5-137">애플리케이션 구성</span><span class="sxs-lookup"><span data-stu-id="2f2a5-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
