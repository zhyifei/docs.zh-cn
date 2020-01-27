---
title: 서비스 및 클라이언트에 보안 설정
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: 719ab26198bd7b83310025e03e541fa11b109612
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746411"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="d6eb3-102">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="d6eb3-102">Securing Services and Clients</span></span>
<span data-ttu-id="d6eb3-103">本部分中的信息重点介绍 Windows Communication Foundation （WCF）中的编程安全性。</span><span class="sxs-lookup"><span data-stu-id="d6eb3-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d6eb3-104">일반적으로 여기에는 적절한 시스템 제공 바인딩 선택, 보안 요소의 속성 설정 및 서비스나 클라이언트에서 사용할 자격 증명을 검색하는 방법을 제어하는 서비스 동작의 속성 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6eb3-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="d6eb3-105">这些技术涵盖大多数用户在大多数情况下的安全要求，如[常见安全方案](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)中所示。</span><span class="sxs-lookup"><span data-stu-id="d6eb3-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="d6eb3-106">如果你的方案需要更多功能，请首先查看[具有自定义绑定的安全功能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md);如果解决方案不明显，请参阅[扩展安全性](../../../../docs/framework/wcf/extending/extending-security.md)。</span><span class="sxs-lookup"><span data-stu-id="d6eb3-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="d6eb3-107">如果要创建（或与）使用丰富声明的系统进行互操作，请参阅[授权](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)中的主题。</span><span class="sxs-lookup"><span data-stu-id="d6eb3-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6eb3-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d6eb3-108">In This Section</span></span>  
 [<span data-ttu-id="d6eb3-109">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d6eb3-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="d6eb3-110">메시지 보안을 설정하는 데 사용되는 프로그래밍 모델의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="d6eb3-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="d6eb3-111">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="d6eb3-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="d6eb3-112">전송 계층에서 메시지 보안을 설정하는 방법의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="d6eb3-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="d6eb3-113">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d6eb3-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="d6eb3-114">汇总在 Windows Communication Foundation （WCF）中使用消息级安全的原因。</span><span class="sxs-lookup"><span data-stu-id="d6eb3-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="d6eb3-115">보안 세션</span><span class="sxs-lookup"><span data-stu-id="d6eb3-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="d6eb3-116">讨论在保护 WCF 会话时需要注意的事项。</span><span class="sxs-lookup"><span data-stu-id="d6eb3-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="d6eb3-117">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="d6eb3-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="d6eb3-118">X.509 인증서를 사용할 때 필요한 일반 작업 중 일부에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6eb3-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d6eb3-119">참조</span><span class="sxs-lookup"><span data-stu-id="d6eb3-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="d6eb3-120">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="d6eb3-120">Related Sections</span></span>  
 [<span data-ttu-id="d6eb3-121">보안 개념</span><span class="sxs-lookup"><span data-stu-id="d6eb3-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="d6eb3-122">보안 확장</span><span class="sxs-lookup"><span data-stu-id="d6eb3-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="d6eb3-123">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="d6eb3-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="d6eb3-124">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="d6eb3-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="d6eb3-125">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="d6eb3-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="d6eb3-126">보안 확장</span><span class="sxs-lookup"><span data-stu-id="d6eb3-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="d6eb3-127">권한 부여</span><span class="sxs-lookup"><span data-stu-id="d6eb3-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="d6eb3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6eb3-128">See also</span></span>

- [<span data-ttu-id="d6eb3-129">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d6eb3-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- <span data-ttu-id="d6eb3-130">[Windows Server App Fabric 的安全模型](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d6eb3-130">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
