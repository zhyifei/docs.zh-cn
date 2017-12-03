---
title: "动态启用分析跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4984cb7fd89b69f0006c5294c24184bd8d1f1d09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="dynamically-enabling-analytic-tracing"></a><span data-ttu-id="6379c-102">动态启用分析跟踪</span><span class="sxs-lookup"><span data-stu-id="6379c-102">Dynamically Enabling Analytic Tracing</span></span>
<span data-ttu-id="6379c-103">通过 Windows 操作系统附带的工具，可以使用 Windows 事件跟踪 (ETW) 动态启用或禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="6379c-103">Using tools that ship with the Windows operating system, you can enable or disable tracing dynamically using Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="6379c-104">对于所有 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务，可以动态启用和禁用分析跟踪，而无需修改应用程序的 Web.config 文件或重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="6379c-104">For all [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, analytic tracing can be enabled and disabled dynamically without modifying the application’s Web.config file or restarting the service.</span></span> <span data-ttu-id="6379c-105">这样，发出跟踪事件的应用程序就可以保持原样。</span><span class="sxs-lookup"><span data-stu-id="6379c-105">This allows the application that emits the trace events to remain undisturbed.</span></span>  
  
 <span data-ttu-id="6379c-106">可以采用类似方式配置[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="6379c-106">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] tracing options can be configured in a similar way.</span></span> <span data-ttu-id="6379c-107">例如，可以将严重性级别从 **Error** 更改为 **Information** 而不影响应用程序。</span><span class="sxs-lookup"><span data-stu-id="6379c-107">For example, you can change the severity level from **Error** to **Information** without disturbing the application.</span></span> <span data-ttu-id="6379c-108">可以使用以下工具来实现此功能：</span><span class="sxs-lookup"><span data-stu-id="6379c-108">This can be done using the following tools:</span></span>  
  
-   <span data-ttu-id="6379c-109">**Logman** – 一个命令行工具，用于配置、控制和查询跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="6379c-109">**Logman** – A command line tool for configuring, controlling, and querying tracing data.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="6379c-110">[Logman 创建跟踪](http://go.microsoft.com/fwlink/?LinkId=165426)和[Logman 更新跟踪](http://go.microsoft.com/fwlink/?LinkId=165427)。</span><span class="sxs-lookup"><span data-stu-id="6379c-110"> [Logman Create Trace](http://go.microsoft.com/fwlink/?LinkId=165426) and [Logman Update Trace](http://go.microsoft.com/fwlink/?LinkId=165427).</span></span>  
  
-   <span data-ttu-id="6379c-111">**EventViewer** - Windows 图形管理工具，用于查看跟踪的结果。</span><span class="sxs-lookup"><span data-stu-id="6379c-111">**EventViewer** - Windows graphical management tool for viewing the results of tracing.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="6379c-112">[WCF 服务和 Windows 事件跟踪](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)和[事件查看器](http://go.microsoft.com/fwlink/?LinkId=165428)。</span><span class="sxs-lookup"><span data-stu-id="6379c-112"> [WCF Services and Event Tracing for Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md) and [Event Viewer](http://go.microsoft.com/fwlink/?LinkId=165428).</span></span>  
  
-   <span data-ttu-id="6379c-113">**Perfmon** – Windows 图形管理工具，它使用计数器监视跟踪计数器以及跟踪对性能的影响。</span><span class="sxs-lookup"><span data-stu-id="6379c-113">**Perfmon** – Windows graphical management tool that uses counters to monitor tracing counters and the effects of tracing on performance.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="6379c-114">[手动创建数据收集器集](http://go.microsoft.com/fwlink/?LinkId=165429)。</span><span class="sxs-lookup"><span data-stu-id="6379c-114"> [Create a Data Collector Set Manually](http://go.microsoft.com/fwlink/?LinkId=165429).</span></span>  
  
### <a name="keywords"></a><span data-ttu-id="6379c-115">关键字</span><span class="sxs-lookup"><span data-stu-id="6379c-115">Keywords</span></span>  
 <span data-ttu-id="6379c-116">使用 <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> 类时，通常按严重性级别（如 Error、Warning 和 Information）筛选 .NET Framework 跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="6379c-116">When using the <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> class, .NET Framework trace messages are generally filtered by the severity level (for example, Error, Warning, and Information).</span></span> <span data-ttu-id="6379c-117">ETW 支持严重性级别概念，但引入了使用关键字的新型灵活筛选器机制。</span><span class="sxs-lookup"><span data-stu-id="6379c-117">ETW supports the severity level concept, but introduces a new, flexible filter mechanism using keywords.</span></span> <span data-ttu-id="6379c-118">关键字为任意文本值，用于使跟踪事件提供有关事件含义的附加上下文。</span><span class="sxs-lookup"><span data-stu-id="6379c-118">Keywords are arbitrary textual values that let tracing events provide additional context about what that event means.</span></span>  
  
 <span data-ttu-id="6379c-119">对于 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 分析跟踪，每个跟踪事件都有两种关键字。</span><span class="sxs-lookup"><span data-stu-id="6379c-119">For [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing, each trace event has two types of keywords.</span></span> <span data-ttu-id="6379c-120">首先，每个事件包含一个或多个方案关键字。</span><span class="sxs-lookup"><span data-stu-id="6379c-120">First, each event has one or more scenario keywords.</span></span> <span data-ttu-id="6379c-121">这类关键字表示此事件将支持的各方案。</span><span class="sxs-lookup"><span data-stu-id="6379c-121">These keywords denote the scenarios that this event is intended to support.</span></span> <span data-ttu-id="6379c-122">有三个方案关键字，每一个方案关键字均设计用于特定用途，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="6379c-122">There are three scenario keywords, each designed for a specific purpose as shown in the following table.</span></span> <span data-ttu-id="6379c-123">可以动态更改使用关键字进行的筛选而不会干扰 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="6379c-123">Filtering using keywords can be changed dynamically without disturbing the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="6379c-124">这意味着您可以动态更改当前跟踪方案以及所收集的跟踪信息量。</span><span class="sxs-lookup"><span data-stu-id="6379c-124">That means that you can dynamically change your current tracing scenario and the amount of tracing information you gather.</span></span> <span data-ttu-id="6379c-125">例如，您可以将 `HealthMonitoring` 更改为 `Troubleshooting` ，并增加跟踪事件粒度。</span><span class="sxs-lookup"><span data-stu-id="6379c-125">For example, you can change `HealthMonitoring` to `Troubleshooting` and increase Tracing Event granularity.</span></span>  
  
|<span data-ttu-id="6379c-126">关键字</span><span class="sxs-lookup"><span data-stu-id="6379c-126">Keyword</span></span>|<span data-ttu-id="6379c-127">描述</span><span class="sxs-lookup"><span data-stu-id="6379c-127">Description</span></span>|  
|-------------|-----------------|  
|`HealthMonitoring`|<span data-ttu-id="6379c-128">非常轻量、程度最低的跟踪，用于监视服务活动。</span><span class="sxs-lookup"><span data-stu-id="6379c-128">Very lightweight, minimal tracing that lets you monitor your service’s activity.</span></span>|  
|`EndToEndMonitoring`|<span data-ttu-id="6379c-129">用于支持消息流跟踪的事件。</span><span class="sxs-lookup"><span data-stu-id="6379c-129">Events used to support message flow tracing.</span></span>|  
|`Troubleshooting`|<span data-ttu-id="6379c-130">围绕 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]扩展点的粒度更细的事件。</span><span class="sxs-lookup"><span data-stu-id="6379c-130">More granular events around the extensibility points of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>|  
  
 <span data-ttu-id="6379c-131">第二组关键字定义 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 的哪个组件发出了事件。</span><span class="sxs-lookup"><span data-stu-id="6379c-131">The second group of keywords define which component of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] emitted the event.</span></span>  
  
|<span data-ttu-id="6379c-132">关键字</span><span class="sxs-lookup"><span data-stu-id="6379c-132">Keyword</span></span>|<span data-ttu-id="6379c-133">描述</span><span class="sxs-lookup"><span data-stu-id="6379c-133">Description</span></span>|  
|-------------|-----------------|  
|`UserEvents`|<span data-ttu-id="6379c-134">由用户代码而非 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]发出的事件。</span><span class="sxs-lookup"><span data-stu-id="6379c-134">Events emitted by the user code and not the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span>|  
|`ServiceModel`|<span data-ttu-id="6379c-135">由 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 运行时发出的事件。</span><span class="sxs-lookup"><span data-stu-id="6379c-135">Events emitted by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] runtime.</span></span>|  
|`ServiceHost`|<span data-ttu-id="6379c-136">由服务主机发出的事件。</span><span class="sxs-lookup"><span data-stu-id="6379c-136">Events emitted by the service host.</span></span>|  
|`WCFMessageLogging`|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="6379c-137"> 消息日志记录事件。</span><span class="sxs-lookup"><span data-stu-id="6379c-137"> message logging events.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6379c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6379c-138">See Also</span></span>  
 [<span data-ttu-id="6379c-139">WCF Services and Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="6379c-139">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
