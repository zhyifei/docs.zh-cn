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
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="f5e58-102">如何：实现观察程序</span><span class="sxs-lookup"><span data-stu-id="f5e58-102">How to: Implement an Observer</span></span>
<span data-ttu-id="f5e58-103">观察程序设计模式要求观察程序，用于通知中注册和一个提供程序，可监视数据并将通知发送到一个或多个观察程序之间进行区分。</span><span class="sxs-lookup"><span data-stu-id="f5e58-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="f5e58-104">本主题讨论如何创建观察程序。</span><span class="sxs-lookup"><span data-stu-id="f5e58-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="f5e58-105">相关的主题，[如何： 实现提供程序](../../../docs/standard/events/how-to-implement-a-provider.md)，讨论如何创建提供程序。</span><span class="sxs-lookup"><span data-stu-id="f5e58-105">A related topic, [How to: Implement a Provider](../../../docs/standard/events/how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="f5e58-106">若要创建观察程序</span><span class="sxs-lookup"><span data-stu-id="f5e58-106">To create an observer</span></span>  
  
1.  <span data-ttu-id="f5e58-107">定义观察程序，即一个实现类型<xref:System.IObserver%601?displayProperty=nameWithType>接口。</span><span class="sxs-lookup"><span data-stu-id="f5e58-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="f5e58-108">例如，下面的代码定义名为的类型`TemperatureReporter`，它是构造<xref:System.IObserver%601?displayProperty=nameWithType>与的泛型类型参数实现`Temperature`。</span><span class="sxs-lookup"><span data-stu-id="f5e58-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  <span data-ttu-id="f5e58-109">如果观察者可以之前停止接收通知的提供程序调用其<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>实现中，定义将保存的私有变量<xref:System.IDisposable>实现提供程序的返回<xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="f5e58-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f5e58-110">你还应定义调用提供程序的订阅方法<xref:System.IObservable%601.Subscribe%2A>方法并存储返回的<xref:System.IDisposable>对象。</span><span class="sxs-lookup"><span data-stu-id="f5e58-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="f5e58-111">例如，下面的代码定义一个名为的私有变量`unsubscriber`并定义`Subscribe`方法调用提供程序的<xref:System.IObservable%601.Subscribe%2A>方法并将分配到返回的对象`unsubscriber`变量。</span><span class="sxs-lookup"><span data-stu-id="f5e58-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  <span data-ttu-id="f5e58-112">定义一个方法，使观察者来停止接收通知的提供程序调用之前其<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>实现中，如果此功能是必需的。</span><span class="sxs-lookup"><span data-stu-id="f5e58-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="f5e58-113">下面的示例定义`Unsubscribe`方法。</span><span class="sxs-lookup"><span data-stu-id="f5e58-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <span data-ttu-id="f5e58-114">提供由定义的三个方法的实现<xref:System.IObserver%601>接口： <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>， <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>，和<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f5e58-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f5e58-115">具体取决于提供程序和应用程序，需要<xref:System.IObserver%601.OnError%2A>和<xref:System.IObserver%601.OnCompleted%2A>方法可以是存根 （stub） 实现。</span><span class="sxs-lookup"><span data-stu-id="f5e58-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="f5e58-116">请注意，<xref:System.IObserver%601.OnError%2A>方法不应处理传入<xref:System.Exception>对象作为异常，和<xref:System.IObserver%601.OnCompleted%2A>方法可以随意调用提供程序的<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>实现。</span><span class="sxs-lookup"><span data-stu-id="f5e58-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="f5e58-117">下面的示例演示<xref:System.IObserver%601>实现`TemperatureReporter`类。</span><span class="sxs-lookup"><span data-stu-id="f5e58-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="f5e58-118">示例</span><span class="sxs-lookup"><span data-stu-id="f5e58-118">Example</span></span>  
 <span data-ttu-id="f5e58-119">下面的示例包含的完整源代码`TemperatureReporter`类，该类提供<xref:System.IObserver%601>温度监控应用程序的实现。</span><span class="sxs-lookup"><span data-stu-id="f5e58-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="f5e58-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5e58-120">See Also</span></span>  
 <xref:System.IObserver%601>  
 [<span data-ttu-id="f5e58-121">观察程序设计模式</span><span class="sxs-lookup"><span data-stu-id="f5e58-121">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="f5e58-122">如何：实现提供程序</span><span class="sxs-lookup"><span data-stu-id="f5e58-122">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [<span data-ttu-id="f5e58-123">监视程序设计模式最佳做法</span><span class="sxs-lookup"><span data-stu-id="f5e58-123">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
