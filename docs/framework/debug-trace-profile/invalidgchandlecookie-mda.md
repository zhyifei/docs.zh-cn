---
title: "invalidGCHandleCookie MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid cookies"
  - "cookies, invalid"
  - "managed debugging assistants (MDAs), invalid cookies"
  - "InvalidGCHandleCookie MDA"
  - "invalid cookies"
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# invalidGCHandleCookie MDA
尝试从无效的 <xref:System.IntPtr> cookie 转换为 <xref:System.Runtime.InteropServices.GCHandle> 时，将激活 `invalidGCHandleCookie` 托管调试助手 \(MDA\)。  
  
## 症状  
 尝试使用 <xref:System.Runtime.InteropServices.GCHandle> 或从 <xref:System.IntPtr> 中检索它时发生未定义的行为，如访问冲突和内存损坏。  
  
## 原因  
 该 cookie 可能因为它最初不是从 <xref:System.Runtime.InteropServices.GCHandle> 创建的而无效，可能表示一个已释放的 <xref:System.Runtime.InteropServices.GCHandle>，可能是另一个应用程序域中的 <xref:System.Runtime.InteropServices.GCHandle> 的一个 cookie，也可能是作为一个 <xref:System.Runtime.InteropServices.GCHandle> 被封送到本机代码但却作为一个 <xref:System.IntPtr> 传回了 CLR 中（此时发生了强制转换）。  
  
## 解决方法  
 为 <xref:System.Runtime.InteropServices.GCHandle> 指定一个有效的 <xref:System.IntPtr> cookie。  
  
## 对运行时的影响  
 启用此 MDA 时，调试器再也无法跟踪返回其对象的根，因为传递回的 cookie 值与未启用此 MDA 时返回的值不同。  
  
## Output  
 会报告无效的 <xref:System.IntPtr> cookie 值。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>   
 <xref:System.Runtime.InteropServices.GCHandle>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)