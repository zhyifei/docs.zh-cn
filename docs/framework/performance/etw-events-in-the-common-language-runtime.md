---
title: "公共语言运行时中的 ETW 事件 | Microsoft Docs"
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
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 公共语言运行时中的 ETW 事件
公共语言运行时 \(CLR\) 通过大量的调试和分析事件，提供有用的 Windows 事件跟踪 \(ETW\) 诊断信息。  CLR ETW 事件利用 Windows ETW 跟踪系统来扩充公共语言运行时所提供的现有分析和调试支持。  
  
 MSDN 上的 [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkID=161142)一文中提供了有关 ETW 的更多信息。  有关 Xperf 的信息可在 NTDebugging 博客的输入 [Windows 性能工具包 \- Xperf](http://go.microsoft.com/fwlink/?LinkID=161144) 提供。  
  
 其他CLR ETW 工具在它们变得可用之后将在 [CodePlex 网站](http://go.microsoft.com/fwlink/?LinkID=111138)提供，。  
  
 在事件主题中介绍的所有事件要求 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 或更新版本。  Windows Vista 操作系统是支持的最低客户端，而 Windows Server 2008 是支持的最低服务器。  
  
## 本节内容  
 [控制 .NET Framework 日志记录](../../../docs/framework/performance/controlling-logging.md)  
 描述用于捕获和查看 ETW 事件的工具和命令。  
  
 [CLR ETW 提供程序](../../../docs/framework/performance/clr-etw-providers.md)  
 提供有关运行时提供程序和断开提供程序以及如何使用它们进行 ETW 数据收集的信息。  
  
 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 描述运行时提供程序和断开提供程序的关键字，可利用这些关键字按类别筛选事件。  
  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)  
 提供有关 CLR ETW 事件以及这些事件的关键字、级别和事件数据的详细信息。  
  
## 请参阅  
 [.NET Framework 中的 ETW 事件](../../../docs/framework/performance/etw-events.md)