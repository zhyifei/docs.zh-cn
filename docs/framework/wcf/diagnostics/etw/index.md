---
title: 使用 ETW 进行分析跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4651c515a938ed8f8736597808156080cfb0bbed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609078"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="cf5e6-102">使用 ETW 进行分析跟踪</span><span class="sxs-lookup"><span data-stu-id="cf5e6-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="cf5e6-103">Windows Communication Foundation (WCF) 分析跟踪提供了一种方法来执行 WCF 服务期间捕获诊断信息。</span><span class="sxs-lookup"><span data-stu-id="cf5e6-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="cf5e6-104">WCF 分析跟踪事件发出的 WCF 堆栈，以允许在生产环境中的 WCF 服务的故障排除中的关键点。</span><span class="sxs-lookup"><span data-stu-id="cf5e6-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="cf5e6-105">分析跟踪 WCF 服务的最小对性能产生影响的产品服务器承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]WCF 服务，因为这些事件非常高效地发送到 Windows 事件跟踪 (ETW) 会话。</span><span class="sxs-lookup"><span data-stu-id="cf5e6-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf5e6-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf5e6-106">In This Section</span></span>  
 [<span data-ttu-id="cf5e6-107">分析跟踪概述</span><span class="sxs-lookup"><span data-stu-id="cf5e6-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="cf5e6-108">讨论 WCF 分析跟踪中的工作方式[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf5e6-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="cf5e6-109">动态启用分析跟踪</span><span class="sxs-lookup"><span data-stu-id="cf5e6-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="cf5e6-110">讨论如何使用 ETW 动态启用或禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="cf5e6-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="cf5e6-111">配置消息流跟踪</span><span class="sxs-lookup"><span data-stu-id="cf5e6-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="cf5e6-112">描述如何配置消息流跟踪。</span><span class="sxs-lookup"><span data-stu-id="cf5e6-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="cf5e6-113">分析跟踪事件参考</span><span class="sxs-lookup"><span data-stu-id="cf5e6-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="cf5e6-114">显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5e6-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf5e6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf5e6-115">See also</span></span>
- [<span data-ttu-id="cf5e6-116">WCF Services and Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="cf5e6-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="cf5e6-117">在 Windows 中将事件跟踪到事件跟踪</span><span class="sxs-lookup"><span data-stu-id="cf5e6-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
