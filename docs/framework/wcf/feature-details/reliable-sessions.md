---
title: 可靠会话
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 396c76cbdb8eada881a5c87edfc2500dcdab3ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497160"
---
# <a name="reliable-sessions"></a><span data-ttu-id="8446d-102">可靠会话</span><span class="sxs-lookup"><span data-stu-id="8446d-102">Reliable Sessions</span></span>

<span data-ttu-id="8446d-103">此部分描述哪些 Windows Communication Foundation (WCF) 可靠会话，它的用途，如何以及何时使用它，哪些绑定配置支持它，以及有关最佳实践。</span><span class="sxs-lookup"><span data-stu-id="8446d-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="8446d-104">下表汇总了有关本节中要点和相关主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8446d-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="8446d-105">可靠会话 WCF 提供了 featrues 确保终结点之间发送的消息跨 SOAP 或传输媒介传输，而与发送这些相同的顺序传递一次和 （可选）。</span><span class="sxs-lookup"><span data-stu-id="8446d-105">The reliable session WCF provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="8446d-106">若要与 WCF 应用程序使用可靠会话，请使用 WCF 中默认情况下或作为一个选项，支持可靠会话的系统提供绑定之一，或创建自己的自定义绑定支持会话。</span><span class="sxs-lookup"><span data-stu-id="8446d-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8446d-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="8446d-107">In This Section</span></span>

<span data-ttu-id="8446d-108">[可靠会话概述](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8446d-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="8446d-109">描述可靠会话、何时使用它们、支持可靠会话的不同绑定以及它们的工作方式。</span><span class="sxs-lookup"><span data-stu-id="8446d-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="8446d-110">[如何： 在可靠会话内交换消息](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="8446d-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="8446d-111">描述如何使用在配置中指定的自定义绑定创建通过 HTTP 的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="8446d-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="8446d-112">[如何： 在可靠会话内保护消息](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="8446d-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="8446d-113">描述如何保护可靠会话。</span><span class="sxs-lookup"><span data-stu-id="8446d-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="8446d-114">[如何： 创建使用 HTTPS 的自定义可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="8446d-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="8446d-115">描述如何创建通过 HTTPS 的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="8446d-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="8446d-116">[可靠会话的最佳实践](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="8446d-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="8446d-117">描述与使用可靠会话关联的一些最佳实践。</span><span class="sxs-lookup"><span data-stu-id="8446d-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="8446d-118">参考</span><span class="sxs-lookup"><span data-stu-id="8446d-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="8446d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8446d-119">See Also</span></span>

<span data-ttu-id="8446d-120">[队列和可靠会话](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="8446d-120">[Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span></span>  
[<span data-ttu-id="8446d-121">会话、实例化和并发</span><span class="sxs-lookup"><span data-stu-id="8446d-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
