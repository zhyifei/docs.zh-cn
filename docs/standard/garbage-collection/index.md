---
title: "Garbage Collection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "memory, garbage collection"
  - "garbage collection, automatic memory management"
  - "GC [.NET Framework]"
  - "memory, allocating"
  - "common language runtime, garbage collection"
  - "garbage collector"
  - "cleanup operations"
  - "garbage collection"
  - "memory, releasing"
  - "common language runtime, automatic memory management"
  - "automatic memory management"
  - "runtime, automatic memory management"
  - "runtime, garbage collection"
  - "garbage collection, about"
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
caps.latest.revision: 36
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 36
---
# Garbage Collection
.NET Framework 的垃圾回收器管理应用程序的内存分配和释放。  每当您创建新对象时，公共语言运行时都会从托管堆为该对象分配内存。  只要托管堆中有地址空间可用，运行时就会继续为新对象分配空间。  但是，内存不是无限大的。  最终，垃圾回收器必须执行回收以释放一些内存。  垃圾回收器优化引擎根据正在进行的分配情况确定执行回收的最佳时间。  当垃圾回收器执行回收时，它检查托管堆中不再被应用程序使用的对象并执行必要的操作来回收它们占用的内存。  
  
<a name="related_topics"></a>   
## 相关主题  
  
|标题|描述|  
|--------|--------|  
|[Fundamentals of Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md)|描述了垃圾回收的工作原理，如何在托管堆中分配对象以及其他核心概念。|  
|[Garbage Collection and Performance](../../../docs/standard/garbage-collection/performance.md)|介绍可用于诊断垃圾回收和性能问题的性能检查。|  
|[被动回收](../../../docs/standard/garbage-collection/induced.md)|描述如何启动垃圾回收。|  
|[Latency Modes](../../../docs/standard/garbage-collection/latency.md)|介绍可确定垃圾回收侵入性的模式。|  
|[Optimization for Shared Web Hosting](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|介绍在由若干个小型网站共享的服务器上如何优化垃圾回收。|  
|[Garbage Collection Notifications](../../../docs/standard/garbage-collection/notifications.md)|介绍如何确定完整垃圾回收何时即将发生以及何时完成。|  
|[Application Domain Resource Monitoring](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|描述如何监控应用程序域对 CPU 和内存的使用情况。|  
|[Weak References](../../../docs/standard/garbage-collection/weak-references.md)|介绍允许应用程序访问对象，同时也允许垃圾回收器收集该对象的功能。|  
  
## 引用  
 <xref:System.GC?displayProperty=fullName>  
  
 <xref:System.GCCollectionMode?displayProperty=fullName>  
  
 <xref:System.GCNotificationStatus?displayProperty=fullName>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName>  
  
 <xref:System.Object.Finalize%2A?displayProperty=fullName>  
  
 <xref:System.IDisposable?displayProperty=fullName>  
  
## 请参阅  
 [Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)