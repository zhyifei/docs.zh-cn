---
title: 弱事件模式
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: e0cd6837de626fa6bcd560811c6a70f7f6604daa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316162"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="e67f1-102">弱事件模式</span><span class="sxs-lookup"><span data-stu-id="e67f1-102">Weak Event Patterns</span></span>
<span data-ttu-id="e67f1-103">在应用程序，很可能附加到事件源的处理程序不会破坏与该处理程序附加到源的侦听器对象结合使用。</span><span class="sxs-lookup"><span data-stu-id="e67f1-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="e67f1-104">这种情况下可能会导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="e67f1-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="e67f1-105">引入了可用于解决此问题，请通过专用管理器类的特定事件并在该事件的侦听器上实现接口的设计模式。</span><span class="sxs-lookup"><span data-stu-id="e67f1-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="e67f1-106">这种设计模式被称为*弱事件模式*。</span><span class="sxs-lookup"><span data-stu-id="e67f1-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="e67f1-107">为什么要实现弱事件模式？</span><span class="sxs-lookup"><span data-stu-id="e67f1-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="e67f1-108">侦听事件可能会导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="e67f1-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="e67f1-109">为要侦听的事件的典型方法是使用将一个处理程序附加到源中的事件的特定于语言的语法。</span><span class="sxs-lookup"><span data-stu-id="e67f1-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="e67f1-110">例如，在C#，语法是： `source.SomeEvent += new SomeEventHandler(MyEventHandler)`。</span><span class="sxs-lookup"><span data-stu-id="e67f1-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="e67f1-111">此方法创建事件源到事件侦听器的强引用。</span><span class="sxs-lookup"><span data-stu-id="e67f1-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="e67f1-112">通常，为侦听器附加事件处理程序会导致具有受到了源的对象生存期 （除非显式删除事件处理程序） 的对象生存期的侦听器。</span><span class="sxs-lookup"><span data-stu-id="e67f1-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="e67f1-113">但在某些情况下，你可能想要由其他因素控制的侦听器的对象生存期，如是否当前属于可视化树的应用程序，而不是由源的生存期。</span><span class="sxs-lookup"><span data-stu-id="e67f1-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="e67f1-114">只要源对象生存期超出侦听器的对象生存期，正常事件模式会导致内存泄漏： 侦听器保持活动状态比预期更长时间。</span><span class="sxs-lookup"><span data-stu-id="e67f1-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="e67f1-115">弱事件模式旨在解决此内存泄漏问题。</span><span class="sxs-lookup"><span data-stu-id="e67f1-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="e67f1-116">侦听器需要注册一个事件，但侦听器并不显式了解何时取消注册时，可以使用弱事件模式。</span><span class="sxs-lookup"><span data-stu-id="e67f1-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="e67f1-117">源的对象生存期超过侦听器的有用的对象生存期时，还可以使用弱事件模式。</span><span class="sxs-lookup"><span data-stu-id="e67f1-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="e67f1-118">(在这种情况下，*有用*由您决定。)弱事件模式允许注册和接收事件，而不会影响任何方式侦听器的对象生存期特征的侦听器。</span><span class="sxs-lookup"><span data-stu-id="e67f1-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="e67f1-119">实际上，来自源的隐式的引用不确定侦听器是否处于可进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="e67f1-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="e67f1-120">引用是弱引用，因此命名弱事件模式和相关的[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e67f1-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="e67f1-121">可以对侦听器进行垃圾回收或销毁，且源可以继续而不保留对现在销毁的对象的非可收集处理程序引用。</span><span class="sxs-lookup"><span data-stu-id="e67f1-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="e67f1-122">谁应该实现弱事件模式？</span><span class="sxs-lookup"><span data-stu-id="e67f1-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="e67f1-123">主要为控件创作者有趣的是实现弱事件模式。</span><span class="sxs-lookup"><span data-stu-id="e67f1-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="e67f1-124">作为控件作者，您有很大程度上责任的行为和包容控件以及对其插入到的应用程序的影响。</span><span class="sxs-lookup"><span data-stu-id="e67f1-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="e67f1-125">这包括控制对象生存期行为，特别是描述的内存泄漏问题的处理。</span><span class="sxs-lookup"><span data-stu-id="e67f1-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="e67f1-126">某些情况下本质上是有助于使自身在弱事件模式的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e67f1-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="e67f1-127">其中一种方案是数据绑定。</span><span class="sxs-lookup"><span data-stu-id="e67f1-127">One such scenario is data binding.</span></span> <span data-ttu-id="e67f1-128">数据绑定中很常见的源对象是完全独立于侦听器对象，它是绑定的目标。</span><span class="sxs-lookup"><span data-stu-id="e67f1-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="e67f1-129">许多方面[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]数据绑定已具有弱事件模式应用于事件的实现方式。</span><span class="sxs-lookup"><span data-stu-id="e67f1-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="e67f1-130">如何实现弱事件模式</span><span class="sxs-lookup"><span data-stu-id="e67f1-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="e67f1-131">有三种方法来实现弱事件模式。</span><span class="sxs-lookup"><span data-stu-id="e67f1-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="e67f1-132">下表列出了三种方法，并提供了应何时使用每个的一些指导。</span><span class="sxs-lookup"><span data-stu-id="e67f1-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="e67f1-133">方法</span><span class="sxs-lookup"><span data-stu-id="e67f1-133">Approach</span></span>|<span data-ttu-id="e67f1-134">何时实现</span><span class="sxs-lookup"><span data-stu-id="e67f1-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="e67f1-135">使用现有的弱事件管理器类</span><span class="sxs-lookup"><span data-stu-id="e67f1-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="e67f1-136">如果你想要订阅的事件具有对应<xref:System.Windows.WeakEventManager>，使用现有的弱事件管理器。</span><span class="sxs-lookup"><span data-stu-id="e67f1-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="e67f1-137">弱事件管理器所包含的 WPF 的列表，请参阅中的继承层次结构<xref:System.Windows.WeakEventManager>类。</span><span class="sxs-lookup"><span data-stu-id="e67f1-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="e67f1-138">由于包含弱事件管理器是有限的可能需要选择其他方法之一。</span><span class="sxs-lookup"><span data-stu-id="e67f1-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="e67f1-139">使用泛型弱事件管理器类</span><span class="sxs-lookup"><span data-stu-id="e67f1-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="e67f1-140">使用通用<xref:System.Windows.WeakEventManager%602>时的现有<xref:System.Windows.WeakEventManager>不可用，您希望轻松地实现，而你并不关心的是效率。</span><span class="sxs-lookup"><span data-stu-id="e67f1-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="e67f1-141">泛型<xref:System.Windows.WeakEventManager%602>效率低于现有或自定义的弱事件管理器。</span><span class="sxs-lookup"><span data-stu-id="e67f1-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="e67f1-142">例如，泛型类执行的更多的反射来发现给定事件的名称的事件。</span><span class="sxs-lookup"><span data-stu-id="e67f1-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="e67f1-143">此外，通过使用泛型注册事件的代码<xref:System.Windows.WeakEventManager%602>是更详细比使用一个现有或自定义<xref:System.Windows.WeakEventManager>。</span><span class="sxs-lookup"><span data-stu-id="e67f1-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="e67f1-144">创建自定义弱事件管理器类</span><span class="sxs-lookup"><span data-stu-id="e67f1-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="e67f1-145">创建自定义<xref:System.Windows.WeakEventManager>时的现有<xref:System.Windows.WeakEventManager>不可用，并且希望获得最佳的效率。</span><span class="sxs-lookup"><span data-stu-id="e67f1-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="e67f1-146">使用自定义<xref:System.Windows.WeakEventManager>来订阅事件将会更高效，但确实会产生编写更多代码开头的成本。</span><span class="sxs-lookup"><span data-stu-id="e67f1-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="e67f1-147">使用第三方弱事件管理器</span><span class="sxs-lookup"><span data-stu-id="e67f1-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="e67f1-148">NuGet 已[几个弱事件管理器](https://www.nuget.org/packages?q=weak+event+manager&prerel=false)和许多 WPF 框架还支持模式 (例如，请参阅[松散耦合的事件订阅的 Prism 的文档](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events))。</span><span class="sxs-lookup"><span data-stu-id="e67f1-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="e67f1-149">以下部分介绍如何实现弱事件模式。</span><span class="sxs-lookup"><span data-stu-id="e67f1-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="e67f1-150">出于本文的讨论，以订阅该事件具有以下特征。</span><span class="sxs-lookup"><span data-stu-id="e67f1-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
-   <span data-ttu-id="e67f1-151">事件名称是`SomeEvent`。</span><span class="sxs-lookup"><span data-stu-id="e67f1-151">The event name is `SomeEvent`.</span></span>  
  
-   <span data-ttu-id="e67f1-152">引发事件`EventSource`类。</span><span class="sxs-lookup"><span data-stu-id="e67f1-152">The event is raised by the `EventSource` class.</span></span>  
  
-   <span data-ttu-id="e67f1-153">事件处理程序类型： `SomeEventEventHandler` (或`EventHandler<SomeEventEventArgs>`)。</span><span class="sxs-lookup"><span data-stu-id="e67f1-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
-   <span data-ttu-id="e67f1-154">该事件传递的类型参数`SomeEventEventArgs`到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e67f1-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="e67f1-155">使用现有的弱事件管理器类</span><span class="sxs-lookup"><span data-stu-id="e67f1-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="e67f1-156">查找现有的弱事件管理器。</span><span class="sxs-lookup"><span data-stu-id="e67f1-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="e67f1-157">弱事件管理器所包含的 WPF 的列表，请参阅中的继承层次结构<xref:System.Windows.WeakEventManager>类。</span><span class="sxs-lookup"><span data-stu-id="e67f1-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="e67f1-158">使用新的弱事件管理器，而不是普通事件挂钩。</span><span class="sxs-lookup"><span data-stu-id="e67f1-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="e67f1-159">例如，如果你的代码使用以下模式来订阅事件：</span><span class="sxs-lookup"><span data-stu-id="e67f1-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="e67f1-160">将其更改为以下模式：</span><span class="sxs-lookup"><span data-stu-id="e67f1-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="e67f1-161">同样，如果你的代码使用以下模式来取消订阅事件：</span><span class="sxs-lookup"><span data-stu-id="e67f1-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="e67f1-162">将其更改为以下模式：</span><span class="sxs-lookup"><span data-stu-id="e67f1-162">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="e67f1-163">使用泛型弱事件管理器类</span><span class="sxs-lookup"><span data-stu-id="e67f1-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="e67f1-164">使用泛型<xref:System.Windows.WeakEventManager%602>类而不是普通事件挂钩。</span><span class="sxs-lookup"><span data-stu-id="e67f1-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="e67f1-165">当你使用<xref:System.Windows.WeakEventManager%602>若要注册事件侦听器，您提供事件源和<xref:System.EventArgs>类型的类和调用的类型参数作为<xref:System.Windows.WeakEventManager%602.AddHandler%2A>如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="e67f1-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="e67f1-166">创建自定义的弱事件管理器类</span><span class="sxs-lookup"><span data-stu-id="e67f1-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="e67f1-167">将以下类模板复制到你的项目。</span><span class="sxs-lookup"><span data-stu-id="e67f1-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="e67f1-168">此类继承<xref:System.Windows.WeakEventManager>类。</span><span class="sxs-lookup"><span data-stu-id="e67f1-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="e67f1-169">替换为`SomeEventWeakEventManager`名称与你自己的名称。</span><span class="sxs-lookup"><span data-stu-id="e67f1-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="e67f1-170">替换为您的活动的相应名称的前面所述的三个名称。</span><span class="sxs-lookup"><span data-stu-id="e67f1-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="e67f1-171">(`SomeEvent`， `EventSource`，和`SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="e67f1-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="e67f1-172">设置为相同的可见性为它所管理的事件的弱事件管理器类的可见性 （公共 / 内部 / 专用）。</span><span class="sxs-lookup"><span data-stu-id="e67f1-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="e67f1-173">使用新的弱事件管理器，而不是普通事件挂钩。</span><span class="sxs-lookup"><span data-stu-id="e67f1-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="e67f1-174">例如，如果你的代码使用以下模式来订阅事件：</span><span class="sxs-lookup"><span data-stu-id="e67f1-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="e67f1-175">将其更改为以下模式：</span><span class="sxs-lookup"><span data-stu-id="e67f1-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="e67f1-176">同样，如果你的代码使用以下模式来取消订阅某个事件：</span><span class="sxs-lookup"><span data-stu-id="e67f1-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="e67f1-177">将其更改为以下模式：</span><span class="sxs-lookup"><span data-stu-id="e67f1-177">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e67f1-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="e67f1-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="e67f1-179">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="e67f1-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="e67f1-180">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="e67f1-180">Data Binding Overview</span></span>](../data/data-binding-overview.md)
