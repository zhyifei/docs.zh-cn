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
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679120"
---
# <a name="reliable-sessions"></a><span data-ttu-id="516b9-102">可靠会话</span><span class="sxs-lookup"><span data-stu-id="516b9-102">Reliable Sessions</span></span>

<span data-ttu-id="516b9-103">本部分介绍哪些 Windows Communication Foundation (WCF) 是可靠会话、 它的用途是什么，如何和何时使用它，哪些绑定配置支持它，以及有关最佳实践。</span><span class="sxs-lookup"><span data-stu-id="516b9-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="516b9-104">下表汇总了有关本节中要点和相关主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="516b9-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="516b9-105">可靠会话 WCF 提供了确保终结点之间发送的消息通过 SOAP 或传输媒介传输，并在其中发送的顺序传递一次和 （可选） 的功能。</span><span class="sxs-lookup"><span data-stu-id="516b9-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="516b9-106">若要 WCF 应用程序中使用可靠会话，请使用 WCF 中默认情况下或作为一个选项，支持可靠会话的系统提供绑定之一，或创建您自己的自定义绑定的支持会话。</span><span class="sxs-lookup"><span data-stu-id="516b9-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="516b9-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="516b9-107">In This Section</span></span>

<span data-ttu-id="516b9-108">[可靠会话概述](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)描述可靠会话、 何时使用这些不同的绑定支持可靠会话，以及它们如何工作。</span><span class="sxs-lookup"><span data-stu-id="516b9-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="516b9-109">[如何：Exchange 消息内可靠会话](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)介绍如何创建通过 HTTP 使用在配置中指定的自定义绑定可靠会话。</span><span class="sxs-lookup"><span data-stu-id="516b9-109">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="516b9-110">[如何：保护可靠会话内的消息](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)介绍如何保护可靠会话。</span><span class="sxs-lookup"><span data-stu-id="516b9-110">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="516b9-111">[如何：使用 HTTPS 创建自定义可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)介绍如何创建通过 HTTPS 的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="516b9-111">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="516b9-112">[可靠会话的最佳实践](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)介绍了一些与使用可靠会话相关联的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="516b9-112">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="516b9-113">参考</span><span class="sxs-lookup"><span data-stu-id="516b9-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="516b9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="516b9-114">See also</span></span>

- [<span data-ttu-id="516b9-115">队列和可靠会话</span><span class="sxs-lookup"><span data-stu-id="516b9-115">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="516b9-116">会话、实例化和并发</span><span class="sxs-lookup"><span data-stu-id="516b9-116">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
