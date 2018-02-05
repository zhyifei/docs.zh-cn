---
title: "基于事件的异步模式 (EAP)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2a83d638255d27317ba5d566ab46b83526659365
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="event-based-asynchronous-pattern-eap"></a>基于事件的异步模式 (EAP)
有多种方式可向客户端代码公开异步功能。 基于事件的异步模式规定了类呈现异步行为的一种方式。  
  
> [!NOTE]
>  从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 开始，任务并行库为异步和并行编程提供了一种新模型。 有关详细信息，请参阅[并行编程](../../../docs/standard/parallel-programming/index.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 描述基于事件的异步模式如何在隐藏多线程设计中固有的许多复杂问题的同时，提供多线程应用程序的优点。  
  
 [实现基于事件的异步模式](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 描述打包具有异步功能的类的标准方式。  
  
 [实现基于事件的异步模式的最佳做法](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 描述根据基于事件的异步模式公开异步功能的需求。  
  
 [确定何时实现基于事件的异步模式](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 描述如何确定何时应选择实现基于事件的异步模式而不是 <xref:System.IAsyncResult> 模式。  
  
 [演练：实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 演示如何创建实现基于事件的异步模式的组件。 它是使用 <xref:System.ComponentModel?displayProperty=nameWithType> 命名空间的帮助器类实现的，这可确保该组件在任何应用程序模型下均可正常工作。  
  
 [如何：使用支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 描述如何使用支持基于事件的异步模式的组件。  
  
## <a name="reference"></a>参考  
 <xref:System.ComponentModel.AsyncOperation>  
 描述 <xref:System.ComponentModel.AsyncOperation> 类并提供指向其所有成员的链接。  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 描述 <xref:System.ComponentModel.AsyncOperationManager> 类并提供指向其所有成员的链接。  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 描述 <xref:System.ComponentModel.BackgroundWorker> 组件并提供指向其所有成员的链接。  
  
## <a name="related-sections"></a>相关章节  
 [任务并行库 (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 描述用于异步和并行操作的编程模型。  
  
 [线程处理](../../../docs/standard/threading/index.md)  
 描述 .NET Framework 中的多线程处理功能。  
  
 [线程处理](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 描述 C# 和 Visual Basic 语言中的多线程处理功能。  
  
## <a name="see-also"></a>请参阅  
 [托管线程处理的最佳做法](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [事件](../../../docs/standard/events/index.md)  
 [组件中的多线程处理](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [异步编程设计模式](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
