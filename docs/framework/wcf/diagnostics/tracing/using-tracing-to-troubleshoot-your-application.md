---
title: "使用跟踪来排除应用程序故障"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7676b9bb-cbd1-41fd-9a93-cc615af6e2d0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c04817d5a13c85f739f17fe25dd3c48ec9941a79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-tracing-to-troubleshoot-your-application"></a><span data-ttu-id="2dbf3-102">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="2dbf3-102">Using Tracing to Troubleshoot Your Application</span></span>
<span data-ttu-id="2dbf3-103">本节包含描述如何使用跟踪来排除应用程序故障的各种主题。</span><span class="sxs-lookup"><span data-stu-id="2dbf3-103">This section contains various topics that describe how you can use tracing to troubleshoot your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2dbf3-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="2dbf3-104">In This Section</span></span>  
 [<span data-ttu-id="2dbf3-105">建议用于跟踪和消息日志记录设置</span><span class="sxs-lookup"><span data-stu-id="2dbf3-105">Recommended Settings for Tracing and Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)  
 <span data-ttu-id="2dbf3-106">描述生产和调试环境的建议设置。</span><span class="sxs-lookup"><span data-stu-id="2dbf3-106">Describes suggested settings for production and debugging environments.</span></span>  
  
 [<span data-ttu-id="2dbf3-107">使用服务跟踪查看器查看相关跟踪和进行故障排除</span><span class="sxs-lookup"><span data-stu-id="2dbf3-107">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 <span data-ttu-id="2dbf3-108">描述如何使用服务跟踪查看器工具来查看、关联和分析跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="2dbf3-108">Describes how you can use the Service Trace Viewer tool to view, correlate and analyze trace data.</span></span>  
  
 [<span data-ttu-id="2dbf3-109">重要跟踪</span><span class="sxs-lookup"><span data-stu-id="2dbf3-109">Significant Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/significant-traces.md)  
 <span data-ttu-id="2dbf3-110">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 发出的一些主要跟踪的列表。</span><span class="sxs-lookup"><span data-stu-id="2dbf3-110">A list of major traces emitted by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="2dbf3-111">在客户端上进行调试</span><span class="sxs-lookup"><span data-stu-id="2dbf3-111">Debugging on the Client</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/debugging-on-the-client.md)  
 <span data-ttu-id="2dbf3-112">使客户端可以调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="2dbf3-112">Enables clients to debug your application.</span></span>  
  
 [<span data-ttu-id="2dbf3-113">端到端跟踪方案</span><span class="sxs-lookup"><span data-stu-id="2dbf3-113">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 <span data-ttu-id="2dbf3-114">描述用于 E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 方案的跟踪，例如，同步的 wsHttp 请求-答复和异步的 TCP 单向请求。</span><span class="sxs-lookup"><span data-stu-id="2dbf3-114">Describes traces used for E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scenarios, for example, synchronous wsHttp request-replies, and asynchronous TCP one-way requests.</span></span>  
  
 [<span data-ttu-id="2dbf3-115">发出用户代码跟踪</span><span class="sxs-lookup"><span data-stu-id="2dbf3-115">Emitting User-Code Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)  
 <span data-ttu-id="2dbf3-116">描述如何在用户代码中以编程方式发出跟踪，以便可以主动创建检测数据，供以后在进行诊断和与 WCF 跟踪相关联时使用。</span><span class="sxs-lookup"><span data-stu-id="2dbf3-116">Describes how to emit traces programmatically in user code, so that you can proactively create instrumentation data to be used later for diagnostic purpose, and in correlation with WCF traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbf3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2dbf3-117">See Also</span></span>  
 [<span data-ttu-id="2dbf3-118">服务跟踪查看器工具 (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="2dbf3-118">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="2dbf3-119">跟踪</span><span class="sxs-lookup"><span data-stu-id="2dbf3-119">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2dbf3-120">端到端跟踪</span><span class="sxs-lookup"><span data-stu-id="2dbf3-120">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
