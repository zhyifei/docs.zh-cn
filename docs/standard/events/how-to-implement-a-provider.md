---
title: "如何：实现提供程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9d8f96de8cb3d13568e755f1d5e885e0474d891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-provider"></a>如何：实现提供程序
观察程序设计模式需要一个提供程序，可监视数据和发送通知，并从提供程序接收通知 （回调） 一个或多个观察程序之间进行区分。 本主题讨论如何创建提供程序。 相关的主题，[如何： 实现观察程序](../../../docs/standard/events/how-to-implement-an-observer.md)，讨论如何创建观察程序。  
  
### <a name="to-create-a-provider"></a>创建提供程序  
  
1.  定义提供程序负责将发送给观察者的数据。 尽管的提供程序和发送给观察者的数据可能是一种类型，它们通常表示由不同的类型。 例如，在温度监控应用程序，`Temperature`结构定义的数据，提供程序 (这由`TemperatureMonitor`在下一步中定义的类) 监视和观察者订阅。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  定义数据提供程序，后者是一种实现<xref:System.IObservable%601?displayProperty=nameWithType>接口。 提供程序的泛型类型参数是提供程序发送给观察者的类型。 下面的示例定义`TemperatureMonitor`类，它是构造<xref:System.IObservable%601?displayProperty=nameWithType>与的泛型类型参数实现`Temperature`。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  确定如何提供程序将存储对观察者的引用，以便在适当的时候，可以通知每个观察程序。 通常情况下，一个集合对象，如泛型<xref:System.Collections.Generic.List%601>对象用于此目的。 下面的示例定义了一个专用<xref:System.Collections.Generic.List%601>中实例化的对象`TemperatureMonitor`类构造函数。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  定义<xref:System.IDisposable>提供程序可以返回到订阅服务器，以便它们可以停止在任何时接收通知的实现。 下面的示例定义了一个嵌套`Unsubscriber`类实例化类时传递到订阅者集合和订阅服务器的引用。 此代码允许订阅服务器调用对象的<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>实现，以将其自身从订阅者集合中移除。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  实现 <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> 方法。 该方法传递的引用<xref:System.IObserver%601?displayProperty=nameWithType>接口，并应存储在第 3 步中为该目的而设计的对象。 该方法应然后返回<xref:System.IDisposable>开发在步骤 4 中的实现。 下面的示例演示的实现<xref:System.IObservable%601.Subscribe%2A>中的方法`TemperatureMonitor`类。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  通过调用通知观察者根据其<xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>， <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>，和<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>实现。 在某些情况下，提供程序可能不调用<xref:System.IObserver%601.OnError%2A>方法时发生错误。 例如，以下`GetTemperature`方法模拟读取每五秒的温度数据，如果温度自从按至少.1 角度以前读取通知观察者的监视器。 如果设备不会报告温度 （即，如果其值为 null），提供程序通知观察者传输已完成。 请注意，除了调用每个观察程序<xref:System.IObserver%601.OnCompleted%2A>方法，`GetTemperature`方法清除<xref:System.Collections.Generic.List%601>集合。 在这种情况下，提供程序不调用<xref:System.IObserver%601.OnError%2A>其观察者的方法。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>示例  
 下面的示例包含用于定义的完整源代码<xref:System.IObservable%601>温度监控应用程序的实现。 它包括`Temperature`结构，这是发送给观察者的数据，与`TemperatureMonitor`类，该类是<xref:System.IObservable%601>实现。  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IObservable%601>  
 [观察程序设计模式](../../../docs/standard/events/observer-design-pattern.md)  
 [如何：实现监视程序](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [监视程序设计模式最佳做法](../../../docs/standard/events/observer-design-pattern-best-practices.md)
