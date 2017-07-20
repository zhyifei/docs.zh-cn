---
title: "gcUnmanagedToManaged MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), garbage collection"
  - "GC unmanaged to managed"
  - "transitioning threads unmanaged to managed code"
  - "GcUnmanagedToManaged MDA"
  - "threading [.NET Framework], garbage collection"
  - "managed debugging assistants (MDAs), garbage collection"
  - "threading [.NET Framework], managed debugging assistants"
  - "garbage collection, run-time errors"
  - "unmanaged to managed garbage collection"
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# gcUnmanagedToManaged MDA
每当一个线程从托管代码转换到非托管代码，`gcUnmanagedToManaged` 托管调试助手 \(MDA\) 就会导致垃圾回收。  
  
## 症状  
 使用 COM 和平台调用来运行非托管用户组件的应用程序在 CLR 中导致了一个非确定性的访问冲突。  
  
## 原因  
 如果一个应用程序运行非托管用户组件，则这些组件可能损坏了已垃圾回收的堆。  在垃圾回收器尝试审核对象图时，这会在 CLR 中导致访问冲突。  
  
## 解决方法  
 通过在每次托管转换之前强制垃圾回收来启用此助手，可以减少从非托管组件损坏已垃圾回收的堆到发生访问冲突之间的时间。  
  
## 对运行时的影响  
 导致每当发生从非托管代码到托管代码的线程转换时都进行垃圾回收。  
  
## 输出  
 此 MDA 不会产生任何输出。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)   
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)