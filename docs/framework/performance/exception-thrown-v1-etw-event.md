---
title: "异常 Thrown_V1 ETW 事件 | Microsoft Docs"
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
  - "ETW, ExceptionThrown_V1 事件 (CLR)"
  - "ExceptionThrown_V1 事件 [.NET Framework]"
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# 异常 Thrown_V1 ETW 事件
此事件可捕获有关所引发的异常的信息。  
  
 下表显示用于引发事件的关键字和事件的级别。（有关详细信息，请参阅 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）  
  
|用于引发事件的关键字|级别|  
|----------------|--------|  
|`ExceptionKeyword` \(0x8000\)|警告 \(2\)|  
  
 下表显示事件信息。  
  
|Event|事件 ID|在以下情况下引发|  
|-----------|-----------|--------------|  
|`ExceptionThrown_V1`|80|引发托管异常。|  
  
 下表显示事件数据。  
  
|字段名|数据类型|说明|  
|---------|----------|--------|  
|异常类型|win:UnicodeString|异常的类型；例如 `System.NullReferenceException`。|  
|Exception Message|win:UnicodeString|实际的异常消息。|  
|EIPCodeThrow|win:Pointer|指向异常发生位置的指令指针。|  
|ExceptionHR|win:UInt32|异常 [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679)。|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException（参见 Visual Basic 文档中的[CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)）。<br /><br /> 0x02: IsNestedException。<br /><br /> 0x04: IsRethrownException。<br /><br /> 0x08: IsCorruptedStateException（指示进程状态已损坏；请参见 MSDN 上的[Handling Corrupted State Exceptions](http://go.microsoft.com/fwlink/?LinkId=179681) on MSDN\)）。<br /><br /> 0x10: IsCLSCompliant（从 <xref:System.Exception> 派生的异常符合 CLS，除此之外的异常将不符合 CLS）。|  
|ClrInstanceID|win:UInt16|CLR 或 CoreCLR 的实例的唯一 ID。|  
  
## 请参阅  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)