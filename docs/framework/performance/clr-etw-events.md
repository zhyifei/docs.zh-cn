---
title: "CLR ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: "45"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17701ee1ddbb1056c9b06b2467c4ce10b91271ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="clr-etw-events"></a><span data-ttu-id="1c220-102">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="1c220-102">CLR ETW Events</span></span>
<span data-ttu-id="1c220-103">本部分的主题介绍 Windows (ETW) 事件的事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="1c220-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="1c220-104">每个事件都有关联的关键字和级别，详见 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)主题。</span><span class="sxs-lookup"><span data-stu-id="1c220-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="1c220-105">CLR 有两个事件提供程序：</span><span class="sxs-lookup"><span data-stu-id="1c220-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="1c220-106">运行时提供程序，根据启用的关键字（事件类别）引发事件。</span><span class="sxs-lookup"><span data-stu-id="1c220-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="1c220-107">CLR 运行时提供程序 GUID 是 e13c0d23-ccbc-4e12-931b-d9cc2eee27e4。</span><span class="sxs-lookup"><span data-stu-id="1c220-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="1c220-108">断开提供程序，此提供程序具有特殊用途。</span><span class="sxs-lookup"><span data-stu-id="1c220-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="1c220-109">CLR 断开提供程序 GUID 是 a669021c-c450-4609-a035-5af59af4df18。</span><span class="sxs-lookup"><span data-stu-id="1c220-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="1c220-110">有关提供程序的详细信息，请参阅 [CLR ETW 提供程序](../../../docs/framework/performance/clr-etw-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="1c220-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c220-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="1c220-111">In This Section</span></span>  
 [<span data-ttu-id="1c220-112">运行时信息事件</span><span class="sxs-lookup"><span data-stu-id="1c220-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="1c220-113">捕获有关运行时的信息，包括 SKU、版本号、激活运行时的方式、启动运行时所使用的命令行参数、GUID（如果适用），以及其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="1c220-114">异常 Thrown_V1 事件</span><span class="sxs-lookup"><span data-stu-id="1c220-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="1c220-115">捕获有关引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="1c220-116">争用事件</span><span class="sxs-lookup"><span data-stu-id="1c220-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="1c220-117">捕获有关对运行时使用的监控视器锁或本机锁的争用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="1c220-118">线程池事件</span><span class="sxs-lookup"><span data-stu-id="1c220-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="1c220-119">捕获有关工作线程池和 I/O 线程池的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="1c220-120">加载程序事件</span><span class="sxs-lookup"><span data-stu-id="1c220-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="1c220-121">捕获有关加载和卸载应用程序域、程序集和模块的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="1c220-122">方法事件</span><span class="sxs-lookup"><span data-stu-id="1c220-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="1c220-123">捕获有关用于符号解析的 CLR 方法的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="1c220-124">垃圾回收事件</span><span class="sxs-lookup"><span data-stu-id="1c220-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="1c220-125">捕获与诊断和调试中的垃圾回收和帮助有关的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="1c220-126">JIT 跟踪事件</span><span class="sxs-lookup"><span data-stu-id="1c220-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="1c220-127">捕获有关实时 (JIT) 内联和尾调用的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="1c220-128">互操作事件</span><span class="sxs-lookup"><span data-stu-id="1c220-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="1c220-129">捕获有关 Microsoft 中间语言 (MSIL) 存根生成和缓存的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="1c220-130">ARM 事件</span><span class="sxs-lookup"><span data-stu-id="1c220-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="1c220-131">捕获有关应用程序域的状态的详细诊断信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="1c220-132">安全事件</span><span class="sxs-lookup"><span data-stu-id="1c220-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="1c220-133">捕获有关强名称和验证码验证的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="1c220-134">堆栈事件</span><span class="sxs-lookup"><span data-stu-id="1c220-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="1c220-135">捕获可用于其他事件以在引发事件后生成堆栈跟踪的信息。</span><span class="sxs-lookup"><span data-stu-id="1c220-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c220-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c220-136">See Also</span></span>  
 [<span data-ttu-id="1c220-137">改善调试和性能优化与 ETW</span><span class="sxs-lookup"><span data-stu-id="1c220-137">Improve Debugging And Performance Tuning With ETW</span></span>](http://go.microsoft.com/fwlink/?LinkId=179696)  
 [<span data-ttu-id="1c220-138">Windows 性能博客</span><span class="sxs-lookup"><span data-stu-id="1c220-138">Windows Performance Blog</span></span>](http://go.microsoft.com/fwlink/?LinkId=179509)  
 [<span data-ttu-id="1c220-139">控制 .NET Framework 日志记录</span><span class="sxs-lookup"><span data-stu-id="1c220-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 [<span data-ttu-id="1c220-140">CLR ETW 提供程序</span><span class="sxs-lookup"><span data-stu-id="1c220-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 [<span data-ttu-id="1c220-141">CLR ETW 关键字和级别</span><span class="sxs-lookup"><span data-stu-id="1c220-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 [<span data-ttu-id="1c220-142">公共语言运行时中的 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="1c220-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
