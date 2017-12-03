---
title: "可靠会话"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53bb63fbbcf92650085514118a5e9464ab2dea30
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-sessions"></a><span data-ttu-id="41fc4-102">可靠会话</span><span class="sxs-lookup"><span data-stu-id="41fc4-102">Reliable Sessions</span></span>

<span data-ttu-id="41fc4-103">本节介绍什么[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]可靠会话是，它有何，如何及何时使用它，哪些绑定配置支持它，以及有关最佳实践。</span><span class="sxs-lookup"><span data-stu-id="41fc4-103">This section describes what a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="41fc4-104">下表汇总了有关本节中要点和相关主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="41fc4-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="41fc4-105">可靠会话[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]提供 featrues 确保终结点之间发送的消息跨 SOAP 或传输媒介传输，而与发送这些相同的顺序传递一次和 （可选）。</span><span class="sxs-lookup"><span data-stu-id="41fc4-105">The reliable session [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="41fc4-106">若要将可靠会话与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序一起使用，请使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中默认情况下支持可靠会话或作为一个选项的系统提供绑定之一，或者创建自己的支持会话的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="41fc4-106">To use a reliable session with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, either use one of the system-provided bindings in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="41fc4-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="41fc4-107">In This Section</span></span>

<span data-ttu-id="41fc4-108">[可靠会话概述](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="41fc4-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="41fc4-109">描述可靠会话、何时使用它们、支持可靠会话的不同绑定以及它们的工作方式。</span><span class="sxs-lookup"><span data-stu-id="41fc4-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="41fc4-110">[如何： 在可靠会话内交换消息](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="41fc4-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="41fc4-111">描述如何使用在配置中指定的自定义绑定创建通过 HTTP 的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="41fc4-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="41fc4-112">[如何： 在可靠会话内保护消息](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="41fc4-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="41fc4-113">描述如何保护可靠会话。</span><span class="sxs-lookup"><span data-stu-id="41fc4-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="41fc4-114">[如何： 创建使用 HTTPS 的自定义可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="41fc4-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="41fc4-115">描述如何创建通过 HTTPS 的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="41fc4-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="41fc4-116">[可靠会话的最佳实践](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="41fc4-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="41fc4-117">描述与使用可靠会话关联的一些最佳实践。</span><span class="sxs-lookup"><span data-stu-id="41fc4-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="41fc4-118">参考</span><span class="sxs-lookup"><span data-stu-id="41fc4-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="41fc4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41fc4-119">See Also</span></span>

<span data-ttu-id="41fc4-120">[队列和可靠会话](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="41fc4-120">[Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span></span>  
[<span data-ttu-id="41fc4-121">会话，实例化和并发</span><span class="sxs-lookup"><span data-stu-id="41fc4-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
