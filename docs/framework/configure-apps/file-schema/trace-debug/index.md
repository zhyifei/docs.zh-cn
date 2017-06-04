---
title: "跟踪和调试设置架构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "配置架构 [.NET Framework], 跟踪和调试设置"
  - "配置节 [.NET Framework]"
  - "配置设置 [.NET Framework], 调试"
  - "配置设置 [.NET Framework], 跟踪"
  - "元素 [.NET Framework], 跟踪和调试设置"
  - "架构配置设置"
  - "跟踪侦听器, 跟踪和调试设置架构"
  - "跟踪 [.NET Framework], 跟踪和调试设置架构"
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# 跟踪和调试设置架构
跟踪和调试设置指定对消息进行收集、存储和路由的跟踪侦听器，并且还指定设置跟踪开关的级别。  
  
 下表描述每个跟踪和调试设置元素的功能。  
  
|元素|说明|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|将侦听器添加到跟踪源的 `Listeners` 集合。|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|将侦听器添加到 `Listeners` 集合中。|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|将侦听器添加到 `sharedListeners` 集合中。|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|指定设置跟踪开关的级别。|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|指定在调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 方法时是否显示消息框；还指定要将消息写入的文件的名称。|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|清除跟踪源的 `Listeners` 集合。|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|清除跟踪的 `Listeners` 集合。|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|向跟踪源的 `Listeners` 集合中的侦听器添加筛选器。|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|向跟踪的 `Listeners` 集合中的侦听器添加筛选器。|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|向 `sharedListeners` 集合中的侦听器添加筛选器。|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|为跟踪源的 `Listeners` 集合指定侦听器。|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|为跟踪的 `Listeners` 集合指定侦听器。|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|指定由性能计数器共享的全局内存的大小。|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|从跟踪的 `Listeners` 集合中移除侦听器。|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|从跟踪源的 `Listeners` 集合中移除侦听器。|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|包含任何源或跟踪元素都能引用的侦听器。|  
|[\<sources\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|包含启动跟踪消息的跟踪源。|  
|[\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|指定启动跟踪消息的跟踪源。|  
|[\<switches\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|包含跟踪开关以及设置跟踪开关的级别。|  
|[\<system.diagnostics\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|指定对消息进行收集、存储和路由的跟踪侦听器以及设置跟踪开关的级别。|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|包含对跟踪消息进行收集、存储和路由的侦听器。|  
  
## 请参阅  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.Debug>   
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)