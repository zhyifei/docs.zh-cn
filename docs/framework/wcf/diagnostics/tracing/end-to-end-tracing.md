---
title: "端到端跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a2127c8dda26c376d7d722a24d72d2330174027
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="292bb-102">端到端跟踪</span><span class="sxs-lookup"><span data-stu-id="292bb-102">End-to-End Tracing</span></span>
<span data-ttu-id="292bb-103">端到端 (e2e) 跟踪可使开发人员跟踪 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 基础结构中的代码执行，从而调查代码路径失败的原因，或者提供详细的跟踪以进行容量规划和性能分析。</span><span class="sxs-lookup"><span data-stu-id="292bb-103">End to End (e2e) Tracing allows developers to follow the execution of code in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="292bb-104"> 提供三种关联机制帮助诊断发生错误的原因：活动、传输和传播。</span><span class="sxs-lookup"><span data-stu-id="292bb-104"> provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="292bb-105">请参阅[端到端跟踪方案](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)有关的端到端跟踪方案和其相应的活动和跟踪设计的列表。</span><span class="sxs-lookup"><span data-stu-id="292bb-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="292bb-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="292bb-106">In This Section</span></span>  
 <span data-ttu-id="292bb-107">[活动](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md)： 描述中的活动跟踪[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]跟踪模型。</span><span class="sxs-lookup"><span data-stu-id="292bb-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
 <span data-ttu-id="292bb-108">[传输](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md)： 描述中的传输[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]跟踪模型中，以及使用传输关联终结点内的活动。</span><span class="sxs-lookup"><span data-stu-id="292bb-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="292bb-109">[传播](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md)： 描述中的活动传播[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]跟踪模型中，以及使用传播关联终结点之间的活动。</span><span class="sxs-lookup"><span data-stu-id="292bb-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="292bb-110">跟踪类型摘要</span><span class="sxs-lookup"><span data-stu-id="292bb-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="292bb-111">提供所有活动跟踪类型的摘要</span><span class="sxs-lookup"><span data-stu-id="292bb-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292bb-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="292bb-112">See Also</span></span>  
 [<span data-ttu-id="292bb-113">配置跟踪</span><span class="sxs-lookup"><span data-stu-id="292bb-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="292bb-114">使用服务跟踪查看器查看相关跟踪和进行故障排除</span><span class="sxs-lookup"><span data-stu-id="292bb-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="292bb-115">端到端跟踪方案</span><span class="sxs-lookup"><span data-stu-id="292bb-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="292bb-116">服务跟踪查看器工具 (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="292bb-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
