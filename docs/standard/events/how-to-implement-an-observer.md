---
title: "如何：实现观察程序"
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
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a>如何：实现观察程序
观察程序设计模式要求观察程序，用于通知中注册和一个提供程序，可监视数据并将通知发送到一个或多个观察程序之间进行区分。 本主题讨论如何创建观察程序。 相关的主题，[如何： 实现提供程序](../../../docs/standard/events/how-to-implement-a-provider.md)，讨论如何创建提供程序。  
  
### <a name="to-create-an-observer"></a>若要创建观察程序  
  
1.  定义观察程序，即一个实现类型<xref:System.IObserver%601?displayProperty=nameWithType>接口。 例如，下面的代码定义名为的类型`TemperatureReporter`，它是构造<xref:System.IObserver%601?displayProperty=nameWithType>与的泛型类型参数实现`Temperature`。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  如果观察者可以之前停止接收通知的提供程序调用其<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>实现中，定义将保存的私有变量<xref:System.IDisposable>实现提供程序的返回<xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>方法。 你还应定义调用提供程序的订阅方法<xref:System.IObservable%601.Subscribe%2A>方法并存储返回的<xref:System.IDisposable>对象。 例如，下面的代码定义一个名为的私有变量`unsubscriber`并定义`Subscribe`方法调用提供程序的<xref:System.IObservable%601.Subscribe%2A>方法并将分配到返回的对象`unsubscriber`变量。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  定义一个方法，使观察者来停止接收通知的提供程序调用之前其<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>实现中，如果此功能是必需的。 下面的示例定义`Unsubscribe`方法。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  提供由定义的三个方法的实现<xref:System.IObserver%601>接口： <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>， <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>，和<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>。 具体取决于提供程序和应用程序，需要<xref:System.IObserver%601.OnError%2A>和<xref:System.IObserver%601.OnCompleted%2A>方法可以是存根 （stub） 实现。 请注意，<xref:System.IObserver%601.OnError%2A>方法不应处理传入<xref:System.Exception>对象作为异常，和<xref:System.IObserver%601.OnCompleted%2A>方法可以随意调用提供程序的<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>实现。 下面的示例演示<xref:System.IObserver%601>实现`TemperatureReporter`类。  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>示例  
 下面的示例包含的完整源代码`TemperatureReporter`类，该类提供<xref:System.IObserver%601>温度监控应用程序的实现。  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IObserver%601>  
 [观察程序设计模式](../../../docs/standard/events/observer-design-pattern.md)  
 [如何：实现提供程序](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [监视程序设计模式最佳做法](../../../docs/standard/events/observer-design-pattern-best-practices.md)
