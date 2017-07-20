---
title: "堆栈 ETW 事件 | Microsoft Docs"
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
  - "ETW, 堆栈事件 (CLR)"
  - "堆栈事件 [.NET Framework]"
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# 堆栈 ETW 事件
堆栈事件应与其他事件结合使用，以便在引发事件后生成堆栈跟踪。  当启用运行时提供程序时会记录此事件。  这是一个发生频率极高的事件，因为只要有另一个运行时事件被引发此事件就会引发。  为此，我们建议您谨慎使用此事件。  
  
 下表显示关键字和级别。（有关详细信息，请参阅 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）  
  
|用于引发事件的关键字|级别|  
|----------------|--------|  
|`StackKeyword` \(0x40000000\)|LogAlways\(0\)|  
  
 下表显示事件信息。  
  
|Event|事件 ID|在以下情况下引发|  
|-----------|-----------|--------------|  
|`CLRStackWalk`|82|在与其他事件结合使用以生成用于跟踪事件的堆栈跟踪时。|  
  
 下表显示事件数据。  
  
|字段名|数据类型|说明|  
|---------|----------|--------|  
|ClrInstanceID|win:Uint16|唯一的运行时标识符。|  
|Reserved1|win:UInt8|保留。|  
|Reserved2|win:UInt8|保留。|  
|FrameCount|win:UInt32|堆栈跟踪中的帧数。|  
|堆栈|win:Pointer|指令指针列。|  
  
## 请参阅  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)