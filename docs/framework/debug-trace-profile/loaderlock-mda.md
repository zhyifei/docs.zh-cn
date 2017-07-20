---
title: "loaderLock MDA | Microsoft Docs"
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
  - "deadlocks [.NET Framework]"
  - "LoaderLock MDA"
  - "MDAs (managed debugging assistants), loader locks"
  - "managed debugging assistants (MDAs), loader locks"
  - "operating system loader locks"
  - "loader locks"
  - "locks, threads"
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# loaderLock MDA
`loaderLock` 托管调试助手 \(MDA\) 检测在持有 Microsoft Windows 操作系统加载程序锁的线程上执行托管代码的尝试。任何此类执行都是非法的，因为这样可能导致死锁，以及在操作系统的加载程序初始化 DLL 之前使用 DLL。  
  
## 症状  
 在操作系统的加载程序锁中执行代码的最常见故障在于，线程将在尝试调用其他也需要加载程序锁的 Win32 函数时死锁。`LoadLibrary`、`GetProcAddress`、`FreeLibrary` 和 `GetModuleHandle` 即属于此类函数。应用程序可能不直接调用这些函数；公共语言运行时 \(CLR\) 可能作为较高级别的调用（例如 <xref:System.Reflection.Assembly.Load%2A>）结果或对平台调用方法的第一次调用的结果而调用这些函数。  
  
 如果线程正在等待另一个线程开始或完成，也会发生死锁。当线程开始或完成执行时，它必须获取操作系统的加载程序锁，以便向受影响的 DLL 发送事件。  
  
 最后，还存在在操作系统的加载程序正确初始化 DLL 之前调入那些 DLL 的情况。死锁故障可通过检查死锁中涉及的所有线程的堆栈来诊断。与死锁故障不同，在不使用此 MDA 的情况下很难诊断未初始化的 DLL 的使用。  
  
## 原因  
 针对 .NET Framework 1.0 或 1.1 版生成的混合托管\/非托管 C\+\+ 程序集一般尝试在加载程序锁中执行托管代码，除非采用了特殊措施，例如使用 **\/NOENTRY** 进行链接。有关这些问题的详细说明，请参见 MSDN Library 中的“Mixed DLL Loading Problem”（混合 DLL 加载问题）。  
  
 针对 .NET Framework 2.0 版生成的混合托管\/非托管 C\+\+ 程序集不容易出现这些问题，从而降低了风险，其风险程度与使用违背操作系统规则的非托管 DLL 的应用程序相同。例如，如果非托管 DLL 的 `DllMain` 入口点调用 `CoCreateInstance` 以获得已向 COM 公开的托管对象，结果就是尝试在加载程序锁中执行托管代码。  有关 .NET Framework 2.0 和更高版本中加载程序锁问题的更多信息，请参见[混合程序集的初始化](../Topic/Initialization%20of%20Mixed%20Assemblies.md)。  
  
## 解决方法  
 在 Visual C\+\+ .NET 2002 和 Visual C\+\+ .NET 2003 中，用 `/clr` 编译器选项编译的 DLL 在加载时可能会发生不确定的死锁；此问题被称为混合 DLL 加载或加载程序锁问题。  在 Visual C\+\+ 2005 和更高版本中，已经从混合 DLL 加载进程中消除了几乎所有的不确定性。  但是，还有一些其他情况会导致加载程序锁发生（肯定会发生这种情况）。  有关其余加载程序锁问题的原因和解决方法的详细介绍，请参见[混合程序集的初始化](../Topic/Initialization%20of%20Mixed%20Assemblies.md)。  如果该主题没有涉及您的加载程序锁问题，您必须检查线程的堆栈，以确定出现加载程序锁的原因以及如何更正问题。  查看堆栈跟踪以确定激活此 MDA 的线程。该线程在持有操作系统的加载程序锁的同时，尝试非法调入托管代码。您或许会在堆栈上看到 DLL 的 `DllMain` 或等效的入口点。操作系统关于可从这样的入口点合法执行的操作的规则具有很多限制。这些规则排除任何托管执行。  
  
## 对运行时的影响  
 通常，进程中的若干线程将死锁。其中的某个线程可能是负责执行垃圾回收的线程，因此这种死锁对整个进程具有重大影响。此外，它将阻止任何需要操作系统的加载程序锁的其他操作，例如加载和卸载程序集或 DLL 以及启动或停止线程。  
  
 在某些特殊情况下，可能还会在未初始化就被调用的 DLL 中触发访问冲突或类似问题。  
  
## Output  
 此 MDA 报告正在尝试进行非法托管执行。需要检查线程的堆栈，以确定出现加载程序锁的原因以及如何更正问题。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)