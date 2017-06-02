---
title: "争用 ETW 事件 | Microsoft Docs"
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
  - "争用事件 [.NET Framework]"
  - "ETW, 争用事件 (CLR)"
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 争用 ETW 事件
只要运行时使用的 <xref:System.Threading.Monitor?displayProperty=fullName> 锁或本机锁出现争用情况，就会引发争用事件。  当一个线程正在等待另一个线程拥有的锁时将发生争用。  
  
 下表显示用于引发争用事件的关键字和事件的级别。（有关详细信息，请参阅 [CLR ETW 关键字和级别](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）  
  
|用于引发事件的关键字|级别|  
|----------------|--------|  
|`ContentionKeyword` \(0x4000\)|信息性 \(4\)|  
  
 下表显示事件信息。  
  
|Event|事件 ID|在以下情况下引发|  
|-----------|-----------|--------------|  
|`ContentionStart_V1`|81|争用开始。  此事件不包括线程等待获取锁之前的旋转时间；此事件只有在线程等待获取锁时才会引发。|  
|`ContentionStop`|81|争用结束。|  
  
 下表显示事件数据。  
  
|字段名|数据类型|说明|  
|---------|----------|--------|  
|Flags|win:UInt8|0 表示托管；1 表示本机。|  
|ClrInstanceID|win:UInt16|CLR 实例的唯一 ID。|  
  
## 请参阅  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)