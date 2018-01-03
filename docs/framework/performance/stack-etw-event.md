---
title: "堆栈 ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1107c6608fe5136eb6159b1d4f0a438e95c4dabb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="stack-etw-event"></a>堆栈 ETW 事件
堆栈事件应与其他事件结合使用，在引发事件后生成堆栈跟踪。 启用运行时提供程序时，记录该事件。 这是一个发生频率非常高的事件，因为每当引发另一个运行时事件时，都将引发此事件。 因此，我们建议谨慎使用此事件。  
  
 下表显示了关键字和级别。 （有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）  
  
|引发事件的关键字|级别|  
|-----------------------------------|-----------|  
|`StackKeyword` (0x40000000)|LogAlways(0)|  
  
 下表显示了事件信息。  
  
|Event|事件 ID|在发生以下情况时引发|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|82|与其他事件结合使用，在事件发生后生成堆栈跟踪。|  
  
 下表显示了事件数据。  
  
|字段名|数据类型|描述|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:Uint16|唯一运行时标识符。|  
|Reserved1|win:UInt8|保留。|  
|Reserved2|win:UInt8|保留。|  
|FrameCount|win:UInt32|堆栈跟踪中的帧数。|  
|堆栈|win:Pointer|指令指针的列|  
  
## <a name="see-also"></a>请参阅  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)
