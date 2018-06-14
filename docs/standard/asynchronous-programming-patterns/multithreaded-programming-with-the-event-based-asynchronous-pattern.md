---
title: 使用基于事件的异步模式进行多线程编程
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
ms.openlocfilehash: 26e555a158ced352c297952b56f7557cbd825cd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567297"
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a>使用基于事件的异步模式进行多线程编程
有多种方式可向客户端代码公开异步功能。 基于事件的异步模式为类规定了用于显示异步行为的建议方式。  
  
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
  
## <a name="see-also"></a>请参阅  
 [托管线程处理的最佳做法](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [事件](../../../docs/standard/events/index.md)  
 [组件中的多线程处理](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
