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
# <a name="how-to-implement-a-provider"></a><span data-ttu-id="ed4ac-102">如何：实现提供程序</span><span class="sxs-lookup"><span data-stu-id="ed4ac-102">How to: Implement a Provider</span></span>
<span data-ttu-id="ed4ac-103">观察程序设计模式需要一个提供程序，可监视数据和发送通知，并从提供程序接收通知 （回调） 一个或多个观察程序之间进行区分。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-103">The observer design pattern requires a division between a provider, which monitors data and sends notifications, and one or more observers, which receive notifications (callbacks) from the provider.</span></span> <span data-ttu-id="ed4ac-104">本主题讨论如何创建提供程序。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-104">This topic discusses how to create a provider.</span></span> <span data-ttu-id="ed4ac-105">相关的主题，[如何： 实现观察程序](../../../docs/standard/events/how-to-implement-an-observer.md)，讨论如何创建观察程序。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-105">A related topic, [How to: Implement an Observer](../../../docs/standard/events/how-to-implement-an-observer.md), discusses how to create an observer.</span></span>  
  
### <a name="to-create-a-provider"></a><span data-ttu-id="ed4ac-106">创建提供程序</span><span class="sxs-lookup"><span data-stu-id="ed4ac-106">To create a provider</span></span>  
  
1.  <span data-ttu-id="ed4ac-107">定义提供程序负责将发送给观察者的数据。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-107">Define the data that the provider is responsible for sending to observers.</span></span> <span data-ttu-id="ed4ac-108">尽管的提供程序和发送给观察者的数据可能是一种类型，它们通常表示由不同的类型。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-108">Although the provider and the data that it sends to observers can be a single type, they are generally represented by different types.</span></span> <span data-ttu-id="ed4ac-109">例如，在温度监控应用程序，`Temperature`结构定义的数据，提供程序 (这由`TemperatureMonitor`在下一步中定义的类) 监视和观察者订阅。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-109">For example, in a temperature monitoring application, the `Temperature` structure defines the data that the provider (which is represented by the `TemperatureMonitor` class defined in the next step) monitors and to which observers subscribe.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  <span data-ttu-id="ed4ac-110">定义数据提供程序，后者是一种实现<xref:System.IObservable%601?displayProperty=nameWithType>接口。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-110">Define the data provider, which is a type that implements the <xref:System.IObservable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="ed4ac-111">提供程序的泛型类型参数是提供程序发送给观察者的类型。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-111">The provider's generic type argument is the type that the provider sends to observers.</span></span> <span data-ttu-id="ed4ac-112">下面的示例定义`TemperatureMonitor`类，它是构造<xref:System.IObservable%601?displayProperty=nameWithType>与的泛型类型参数实现`Temperature`。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-112">The following example defines a `TemperatureMonitor` class, which is a constructed <xref:System.IObservable%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  <span data-ttu-id="ed4ac-113">确定如何提供程序将存储对观察者的引用，以便在适当的时候，可以通知每个观察程序。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-113">Determine how the provider will store references to observers so that each observer can be notified when appropriate.</span></span> <span data-ttu-id="ed4ac-114">通常情况下，一个集合对象，如泛型<xref:System.Collections.Generic.List%601>对象用于此目的。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-114">Most commonly, a collection object such as a generic <xref:System.Collections.Generic.List%601> object is used for this purpose.</span></span> <span data-ttu-id="ed4ac-115">下面的示例定义了一个专用<xref:System.Collections.Generic.List%601>中实例化的对象`TemperatureMonitor`类构造函数。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-115">The following example defines a private <xref:System.Collections.Generic.List%601> object that is instantiated in the `TemperatureMonitor` class constructor.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  <span data-ttu-id="ed4ac-116">定义<xref:System.IDisposable>提供程序可以返回到订阅服务器，以便它们可以停止在任何时接收通知的实现。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-116">Define an <xref:System.IDisposable> implementation that the provider can return to subscribers so that they can stop receiving notifications at any time.</span></span> <span data-ttu-id="ed4ac-117">下面的示例定义了一个嵌套`Unsubscriber`类实例化类时传递到订阅者集合和订阅服务器的引用。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-117">The following example defines a nested `Unsubscriber` class that is passed a reference to the subscribers collection and to the subscriber when the class is instantiated.</span></span> <span data-ttu-id="ed4ac-118">此代码允许订阅服务器调用对象的<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>实现，以将其自身从订阅者集合中移除。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-118">This code enables the subscriber to call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation to remove itself from the subscribers collection.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  <span data-ttu-id="ed4ac-119">实现 <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-119">Implement the <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ed4ac-120">该方法传递的引用<xref:System.IObserver%601?displayProperty=nameWithType>接口，并应存储在第 3 步中为该目的而设计的对象。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-120">The method is passed a reference to the <xref:System.IObserver%601?displayProperty=nameWithType> interface and should be stored in the object designed for that purpose in step 3.</span></span> <span data-ttu-id="ed4ac-121">该方法应然后返回<xref:System.IDisposable>开发在步骤 4 中的实现。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-121">The method should then return the <xref:System.IDisposable> implementation developed in step 4.</span></span> <span data-ttu-id="ed4ac-122">下面的示例演示的实现<xref:System.IObservable%601.Subscribe%2A>中的方法`TemperatureMonitor`类。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-122">The following example shows the implementation of the <xref:System.IObservable%601.Subscribe%2A> method in the `TemperatureMonitor` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  <span data-ttu-id="ed4ac-123">通过调用通知观察者根据其<xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>， <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>，和<xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>实现。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-123">Notify observers as appropriate by calling their <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementations.</span></span> <span data-ttu-id="ed4ac-124">在某些情况下，提供程序可能不调用<xref:System.IObserver%601.OnError%2A>方法时发生错误。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-124">In some cases, a provider may not call the <xref:System.IObserver%601.OnError%2A> method when an error occurs.</span></span> <span data-ttu-id="ed4ac-125">例如，以下`GetTemperature`方法模拟读取每五秒的温度数据，如果温度自从按至少.1 角度以前读取通知观察者的监视器。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-125">For example, the following `GetTemperature` method simulates a monitor that reads temperature data every five seconds and notifies observers if the temperature has changed by at least .1 degree since the previous reading.</span></span> <span data-ttu-id="ed4ac-126">如果设备不会报告温度 （即，如果其值为 null），提供程序通知观察者传输已完成。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-126">If the device does not report a temperature (that is, if its value is null), the provider notifies observers that the transmission is complete.</span></span> <span data-ttu-id="ed4ac-127">请注意，除了调用每个观察程序<xref:System.IObserver%601.OnCompleted%2A>方法，`GetTemperature`方法清除<xref:System.Collections.Generic.List%601>集合。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-127">Note that, in addition to calling each observer's <xref:System.IObserver%601.OnCompleted%2A> method, the `GetTemperature` method clears the <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="ed4ac-128">在这种情况下，提供程序不调用<xref:System.IObserver%601.OnError%2A>其观察者的方法。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-128">In this case, the provider makes no calls to the <xref:System.IObserver%601.OnError%2A> method of its observers.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="ed4ac-129">示例</span><span class="sxs-lookup"><span data-stu-id="ed4ac-129">Example</span></span>  
 <span data-ttu-id="ed4ac-130">下面的示例包含用于定义的完整源代码<xref:System.IObservable%601>温度监控应用程序的实现。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-130">The following example contains the complete source code for defining an <xref:System.IObservable%601> implementation for a temperature monitoring application.</span></span> <span data-ttu-id="ed4ac-131">它包括`Temperature`结构，这是发送给观察者的数据，与`TemperatureMonitor`类，该类是<xref:System.IObservable%601>实现。</span><span class="sxs-lookup"><span data-stu-id="ed4ac-131">It includes the `Temperature` structure, which is the data sent to observers, and the `TemperatureMonitor` class, which is the <xref:System.IObservable%601> implementation.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="ed4ac-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed4ac-132">See Also</span></span>  
 <xref:System.IObservable%601>  
 [<span data-ttu-id="ed4ac-133">观察程序设计模式</span><span class="sxs-lookup"><span data-stu-id="ed4ac-133">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="ed4ac-134">如何：实现监视程序</span><span class="sxs-lookup"><span data-stu-id="ed4ac-134">How to: Implement an Observer</span></span>](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [<span data-ttu-id="ed4ac-135">监视程序设计模式最佳做法</span><span class="sxs-lookup"><span data-stu-id="ed4ac-135">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
