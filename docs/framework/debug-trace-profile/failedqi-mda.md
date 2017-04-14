---
title: "failedQI MDA | Microsoft Docs"
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
  - "failed QueryInterface"
  - "FailedQI MDA"
  - "QueryInterface call failures"
  - "MDAs (managed debugging assistants), failed QueryInterface"
  - "managed debugging assistants (MDAs), failed QueryInterface"
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# failedQI MDA
当运行时代表运行时可调用包装器 \(RCW\) 在 COM 接口指针上调用 `QueryInterface` 且 `QueryInterface` 调用失败时，将激活 `failedQI` 托管调试助手 \(MDA\)。  
  
## 症状  
 对 RCW 的强制转换失败，或从 RCW 调用 COM 意外失败。  
  
## 原因  
  
-   从错误的上下文进行调用。  
  
-   注册的代理将无法进行 `QueryInterface` 调用，因为尝试在错误的上下文中进行调用。  
  
-   OLE 拥有的代理返回失败 HRESULT。  
  
## 解决方法  
 请参阅 MSDN 文档的 COM 规则部分。  
  
## 对运行时的影响  
 如果 `QueryInterface` 调用失败，将切换上下文并再次尝试调用`QueryInterface`，以确定是否因上下文错误而引起。  
  
## 输出  
 接口的托管名称、接口的 GUID 和失败的 HRESULT。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)