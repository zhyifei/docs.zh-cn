---
title: 端到端跟踪
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fd2964b39c758e41620fb453ddd8f61a1aa550aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092105"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="b571a-102">端到端跟踪</span><span class="sxs-lookup"><span data-stu-id="b571a-102">End-to-End Tracing</span></span>
<span data-ttu-id="b571a-103">端到端 (e2e) 跟踪可使开发人员跟踪中的 Windows Communication Foundation (WCF) 基础结构，从而调查代码路径失败的原因，或者提供详细的容量规划和性能分析的跟踪代码的执行。</span><span class="sxs-lookup"><span data-stu-id="b571a-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="b571a-104">Windows Communication Foundation (WCF) 提供了三种关联机制帮助诊断发生错误的原因： 活动、 传输和传播。</span><span class="sxs-lookup"><span data-stu-id="b571a-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="b571a-105">请参阅[端到端跟踪方案](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)有关端到端跟踪方案及其各自的活动和跟踪设计的列表。</span><span class="sxs-lookup"><span data-stu-id="b571a-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b571a-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="b571a-106">In This Section</span></span>  
 <span data-ttu-id="b571a-107">[活动](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):介绍 Windows Communication Foundation (WCF) 跟踪模型中的活动跟踪。</span><span class="sxs-lookup"><span data-stu-id="b571a-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="b571a-108">[传输](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):介绍在 Windows Communication Foundation (WCF) 跟踪模型中，传输，并使用传输关联终结点内的活动。</span><span class="sxs-lookup"><span data-stu-id="b571a-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="b571a-109">[传播](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):介绍在 Windows Communication Foundation (WCF) 跟踪模型中，以及使用传播关联终结点之间的活动的活动传播。</span><span class="sxs-lookup"><span data-stu-id="b571a-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="b571a-110">跟踪类型摘要</span><span class="sxs-lookup"><span data-stu-id="b571a-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="b571a-111">提供所有活动跟踪类型的摘要</span><span class="sxs-lookup"><span data-stu-id="b571a-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b571a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b571a-112">See also</span></span>

- [<span data-ttu-id="b571a-113">配置跟踪</span><span class="sxs-lookup"><span data-stu-id="b571a-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="b571a-114">使用服务跟踪查看器查看相关跟踪和进行故障诊断</span><span class="sxs-lookup"><span data-stu-id="b571a-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="b571a-115">端到端跟踪方案</span><span class="sxs-lookup"><span data-stu-id="b571a-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="b571a-116">服务跟踪查看器工具 (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="b571a-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
