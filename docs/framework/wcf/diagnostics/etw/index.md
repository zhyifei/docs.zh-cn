---
title: 使用 ETW 进行分析跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798086"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="238e3-102">使用 ETW 进行分析跟踪</span><span class="sxs-lookup"><span data-stu-id="238e3-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="238e3-103">Windows Communication Foundation （WCF）分析跟踪提供一种在执行 WCF 服务的过程中捕获诊断信息的方法。</span><span class="sxs-lookup"><span data-stu-id="238e3-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="238e3-104">在 WCF 堆栈中的关键点处发出 WCF 分析跟踪事件，以允许在生产环境中对 WCF 服务进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="238e3-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="238e3-105">Wcf 服务的分析跟踪对承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] wcf 服务的产品服务器的性能的影响最小，因为这些事件非常有效地发送到 Windows 事件跟踪（ETW）会话。</span><span class="sxs-lookup"><span data-stu-id="238e3-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="238e3-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="238e3-106">In This Section</span></span>  
 [<span data-ttu-id="238e3-107">分析跟踪概述</span><span class="sxs-lookup"><span data-stu-id="238e3-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="238e3-108">讨论 WCF 分析跟踪在中的[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]工作方式。</span><span class="sxs-lookup"><span data-stu-id="238e3-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="238e3-109">动态启用分析跟踪</span><span class="sxs-lookup"><span data-stu-id="238e3-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="238e3-110">讨论如何使用 ETW 动态启用或禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="238e3-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="238e3-111">配置消息流跟踪</span><span class="sxs-lookup"><span data-stu-id="238e3-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="238e3-112">描述如何配置消息流跟踪。</span><span class="sxs-lookup"><span data-stu-id="238e3-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="238e3-113">分析跟踪事件参考</span><span class="sxs-lookup"><span data-stu-id="238e3-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="238e3-114">显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。</span><span class="sxs-lookup"><span data-stu-id="238e3-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238e3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="238e3-115">See also</span></span>

- [<span data-ttu-id="238e3-116">WCF Services and Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="238e3-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="238e3-117">在 Windows 中将事件跟踪到事件跟踪</span><span class="sxs-lookup"><span data-stu-id="238e3-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
