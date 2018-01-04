---
title: "使用 ETW 进行分析跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a16f66ed8443749764e66d2616ae566ad788d571
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="8db69-102">使用 ETW 进行分析跟踪</span><span class="sxs-lookup"><span data-stu-id="8db69-102">Analytic Tracing with ETW</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="8db69-103"> 分析跟踪提供了一种方式来捕获 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务执行过程中的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="8db69-103"> analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="8db69-104"> 分析跟踪事件是在 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 堆栈中的关键点处发出的，用于在生产环境中排除 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务的故障。</span><span class="sxs-lookup"><span data-stu-id="8db69-104"> analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="8db69-105">分析跟踪对[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务最小对性能有影响的产品服务器承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)][!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务因为这些事件可以非常高效地发送到 Windows 事件跟踪 (ETW) 会话。</span><span class="sxs-lookup"><span data-stu-id="8db69-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8db69-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="8db69-106">In This Section</span></span>  
 [<span data-ttu-id="8db69-107">分析跟踪概述</span><span class="sxs-lookup"><span data-stu-id="8db69-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="8db69-108">讨论 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 分析跟踪如何处理 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8db69-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="8db69-109">动态启用分析跟踪</span><span class="sxs-lookup"><span data-stu-id="8db69-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="8db69-110">讨论如何使用 ETW 动态启用或禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="8db69-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="8db69-111">配置消息流跟踪</span><span class="sxs-lookup"><span data-stu-id="8db69-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="8db69-112">描述如何配置消息流跟踪。</span><span class="sxs-lookup"><span data-stu-id="8db69-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="8db69-113">分析跟踪事件参考</span><span class="sxs-lookup"><span data-stu-id="8db69-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="8db69-114">显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。</span><span class="sxs-lookup"><span data-stu-id="8db69-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db69-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8db69-115">See Also</span></span>  
 [<span data-ttu-id="8db69-116">WCF Services and Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="8db69-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="8db69-117">在 Windows 中将事件跟踪到事件跟踪</span><span class="sxs-lookup"><span data-stu-id="8db69-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
