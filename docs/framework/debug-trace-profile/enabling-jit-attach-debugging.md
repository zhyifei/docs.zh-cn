---
title: "Enabling JIT-Attach Debugging | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "JIT-attach debugging"
  - "debugging [.NET Framework], JIT-attach debugging"
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Enabling JIT-Attach Debugging
JIT 附加调试是用于描述如何在发生错误时将调试器附加到进程的词组，它也可以由特定的方法或函数触发。  
  
 在以下错误情况下，使用 JIT 附加调试：  
  
-   未经处理的异常（在本机代码和托管代码中）。  
  
-   <xref:System.Environment.FailFast%2A?displayProperty=fullName> 方法或 [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) 函数 \(Windows 7 系列\)。  
  
-   运行时错误。  
  
 也可以通过调用以下方法和函数来触发 JIT 附加调试：  
  
-   <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=fullName> 方法。  
  
-   <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=fullName> 方法。  
  
-   [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) 函数 \(Win32\)。  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]之前的 .NET Framework 提供单独的注册表项来控制本机调试器和托管调试器的行为。  从 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 开始，此类控制合并到了一个注册表项下：HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\Current Version\\AeDebug。  您可以为该注册表项设置值来确定是否调用调试器，如果调用，则还要确定是否使用需要用户交互的对话框来调用调试器。  有关设置此注册表项的信息，请参见 MSDN Library中的[配置自动调试](http://go.microsoft.com/fwlink/?LinkId=181767) 。  
  
## 请参阅  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)   
 [令映像更易于调试](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)   
 [Enabling Profiling](http://msdn.microsoft.com/zh-cn/3b669676-f0e0-4ebf-8674-68986dd2020d)