---
title: "缓解：EventSource.WriteEvent 方法调用 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cde809989d89c10caeb97ec853c8649a108cd72d
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a>缓解：EventSource.WriteEvent 方法调用
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 在派生自 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 的类中的 ETW 事件方法和基类的 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> 方法之间强制实施协定。 ETW 事件方法必须向 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> 方法传递事件 ID，后跟传递给事件方法的相同自变量。  
  
## <a name="impact"></a>影响  
 按以下方式定义的 ETW 事件方法会使协定中断：  
  
```  
  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
  
```  
  
 如果违反此协定，在 <xref:System.Diagnostics.Tracing.EventListener> 对象读取进程中的 <xref:System.Diagnostics.Tracing.EventSource> 数据时，<xref:System.IndexOutOfRangeException> 异常会在运行时抛出。  
  
 此 ETW 事件方法的定义应遵循以下模式：  
  
```  
  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
  
```  
  
## <a name="mitigation"></a>缓解操作  
 必须修改现有代码以符合所需模式。  
  
 可以定义两个方法来调用 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> 方法，从而最大限度地减少需要更改的代码量，如下所示：  
  
```  
  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)
