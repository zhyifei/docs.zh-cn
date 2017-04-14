---
title: "CLR ETW 事件 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR ETW 事件"
  - "ETW, CLR 事件"
  - "ETW, 公共语言运行时"
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: 45
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 45
---
# CLR ETW 事件
本节中的各主题描述 Windows 事件跟踪 \(ETW\) 事件。  每个事件都具有一个关联的关键字和级别，[CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)主题中对它们进行了描述。  CLR 具有针对这些事件的两个提供程序：  
  
-   运行时提供程序，此提供程序根据启用的关键字（事件的类别）引发相应事件。  CLR 运行时提供程序 GUID 为 e13c0d23\-ccbc\-4e12\-931b\-d9cc2eee27e4。  
  
-   断开提供程序，此提供程序具有特殊用途。  CLR 断开提供程序 GUID 为 a669021c\-c450\-4609\-a035\-5af59af4df18。  
  
 有关提供程序的的更多信息，请参见 [CLR ETW 提供程序](../../../docs/framework/performance/clr-etw-providers.md)。  
  
## 本节内容  
 [运行时信息事件](../../../docs/framework/performance/runtime-information-etw-events.md)  
 捕获有关运行时的信息，其中包括 SKU、版本号、运行时的激活方式、用于启动运行时的命令行参数、GUID（如果适用）以及其他相关的信息。  
  
 [异常 Thrown\_V1 事件](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 捕获有关引发的异常的信息。  
  
 [争用事件](../../../docs/framework/performance/contention-etw-events.md)  
 捕获有关运行时使用的监视器锁或本机锁的争用情况的信息。  
  
 [线程池事件](../../../docs/framework/performance/thread-pool-etw-events.md)  
 捕获有关辅助线程池和 I\/O 线程池的信息。  
  
 [加载程序事件](../../../docs/framework/performance/loader-etw-events.md)  
 捕获有关加载和卸载应用程序域、程序集和模块的信息。  
  
 [方法事件](../../../docs/framework/performance/method-etw-events.md)  
 捕获有关符号解析的 CLR 方法的信息。  
  
 [垃圾回收事件](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 捕获有关垃圾回收的信息以帮助进行诊断和调试。  
  
 [JIT 跟踪事件](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 捕获有关实时 \(JIT\) 内联和尾调用的信息。  
  
 [互操作事件](../../../docs/framework/performance/interop-etw-events.md)  
 捕获有关 Microsoft 中间语言 \(MSIL\) 存根生成和缓存的信息。  
  
 [ARM 事件](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 捕获有关应用程序域的状态的详细诊断信息。  
  
 [安全事件](../../../docs/framework/performance/security-etw-events.md)  
 捕获有关强名称和 Authenticode 验证的信息。  
  
 [堆栈事件](../../../docs/framework/performance/stack-etw-event.md)  
 捕获与其他事件结合使用以便在引发事件后生成堆栈跟踪的信息。  
  
## 请参阅  
 [提高调整使用 ETW 的调试和性能](http://go.microsoft.com/fwlink/?LinkId=179696)   
 [Windows 性能博客](http://go.microsoft.com/fwlink/?LinkId=179509)   
 [控制 .NET Framework 日志记录](../../../docs/framework/performance/controlling-logging.md)   
 [CLR ETW 提供程序](../../../docs/framework/performance/clr-etw-providers.md)   
 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)   
 [公共语言运行时中的 ETW 事件](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)