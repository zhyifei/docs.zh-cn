---
title: 使用 ETW 进行分析跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 210418b8a8765a1fc59658e9df57c92ce087c95f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="7a787-102">使用 ETW 进行分析跟踪</span><span class="sxs-lookup"><span data-stu-id="7a787-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="7a787-103">Windows Communication Foundation (WCF) 分析跟踪提供了一个方法来捕获的 WCF 服务执行期间的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="7a787-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="7a787-104">WCF 堆栈，以便在生产环境中的 WCF 服务的故障排除中的关键点处发出的 WCF 分析跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="7a787-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="7a787-105">WCF 服务的分析跟踪最小对性能有影响的产品服务器承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]WCF 服务，因为这些事件可以非常高效地发送到 Windows 事件跟踪 (ETW) 会话。</span><span class="sxs-lookup"><span data-stu-id="7a787-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a787-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="7a787-106">In This Section</span></span>  
 [<span data-ttu-id="7a787-107">分析跟踪概述</span><span class="sxs-lookup"><span data-stu-id="7a787-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="7a787-108">讨论 WCF 分析跟踪中的工作方式[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7a787-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="7a787-109">动态启用分析跟踪</span><span class="sxs-lookup"><span data-stu-id="7a787-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="7a787-110">讨论如何使用 ETW 动态启用或禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a787-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="7a787-111">配置消息流跟踪</span><span class="sxs-lookup"><span data-stu-id="7a787-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="7a787-112">描述如何配置消息流跟踪。</span><span class="sxs-lookup"><span data-stu-id="7a787-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="7a787-113">分析跟踪事件参考</span><span class="sxs-lookup"><span data-stu-id="7a787-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="7a787-114">显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。</span><span class="sxs-lookup"><span data-stu-id="7a787-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a787-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a787-115">See Also</span></span>  
 [<span data-ttu-id="7a787-116">WCF Services and Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="7a787-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="7a787-117">在 Windows 中将事件跟踪到事件跟踪</span><span class="sxs-lookup"><span data-stu-id="7a787-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
