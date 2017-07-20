---
title: "marshalCleanupError MDA | Microsoft Docs"
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
  - "cleanup operations"
  - "marshaling, run-time errors"
  - "managed debugging assistants (MDAs), marshaling"
  - "MDAs (managed debugging assistants), marshaling"
  - "marshaling cleanup error"
  - "MarshalCleanupError MDA"
  - "memory, cleanup errors"
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# marshalCleanupError MDA
如果公共语言运行时 \(CLR\) 在尝试清理那些用于封送本机代码和托管代码边界之间的数据类型的临时结构和内存时遇到错误，则将激活 `marshalCleanupError` 托管调试助手 \(MDA\)。  
  
## 症状  
 进行本机代码和托管代码转换时发生内存泄漏，线程区域性等运行时状态无法还原，或 <xref:System.Runtime.InteropServices.SafeHandle> 清理中发生错误。  
  
## 原因  
 清理临时结构时发生意外错误。  
  
## 解决方法  
 检查所有 <xref:System.Runtime.InteropServices.SafeHandle> 析构函数、终结器和自定义封送拆收器实现中是否存在错误。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## 输出  
 报告在清理期间失败的操作的消息。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)