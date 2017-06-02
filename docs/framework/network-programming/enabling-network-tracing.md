---
title: "启用网络跟踪 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "跟踪目标"
  - "将跟踪发送到日志文件"
  - "跟踪侦听器，网络跟踪"
  - "网络跟踪，启用"
  - "CLR 调试器"
  - "默认侦听器"
  - "日志，跟踪"
  - "跟踪输出的目标"
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 启用网络跟踪
网络跟踪提供这些信息的访问有关方法调用和托管应用程序生成的网络通信。  您必须完成以下任务启用跟踪应用程序的网络:  
  
-   生成时启用跟踪代码。  请参见 [How to: Compile Conditionally with Trace and Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) 有关所需的编译器开关的更多信息启用跟踪。  
  
-   用于跟踪输出指定目标。  
  
-   配置网络跟踪行为。  有关详细信息 [如何:配置网络跟踪](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) 参见。  
  
 最常见的跟踪目标，也称为跟踪侦听器，这是默认侦听器和日志文件。  
  
 ，如果不指定跟踪侦听器，使用默认跟踪侦听器。  可以使用.NET Framework SDK查看发送到默认侦听器通过执行您在一台托管代码启用调试器的代码\(如中提供的CLR调试器或DBwin32.exe随Windows SDK。  使用CLR调试器，跟踪消息出现在 **输出** 窗口。  
  
 如果您希望使用文件接收跟踪，通过使用配置设置，如以下示例所示，可以指定日志文件，。  \(有关配置文件的一般讨论，请参见 [配置文件](../../../docs/framework/configure-apps/index.md)。\)  
  
 若要发送跟踪到日志文件中，添加以下节点到适当的配置文件的 `<system.diagnostics>` 节点\(应用程序或设备\)。  可以更改文件\(trace.log\)的名称以满足您的要求。  
  
```  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## 请参阅  
 [解释网络跟踪](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [.NET Framework 中的网络跟踪](../../../docs/framework/network-programming/network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/zh-cn/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)