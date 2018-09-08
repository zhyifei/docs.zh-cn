---
title: 事件设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b257da73d33fae54ef464e9dd69906316b87fd88
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44127915"
---
# <a name="event-design"></a><span data-ttu-id="35a3d-102">事件设计</span><span class="sxs-lookup"><span data-stu-id="35a3d-102">Event Design</span></span>
<span data-ttu-id="35a3d-103">事件是最常使用的窗体的回叫 （允许框架在调用用户代码调用的构造）。</span><span class="sxs-lookup"><span data-stu-id="35a3d-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="35a3d-104">其他回调机制包括成员撰写委托、 虚拟成员，以及使用基于接口的插件。可用性研究中的数据表示大多数开发人员更熟练使用事件，它们使用与其他回调机制。</span><span class="sxs-lookup"><span data-stu-id="35a3d-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="35a3d-105">使用 Visual Studio 和许多语言可以很好地集成事件。</span><span class="sxs-lookup"><span data-stu-id="35a3d-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="35a3d-106">务必要注意，有两个组的事件： 事件的系统更改，名为事前事件和事件引发后状态发生变化，状态之前，将引发调用后的事件。</span><span class="sxs-lookup"><span data-stu-id="35a3d-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="35a3d-107">事件前的示例将`Form.Closing`，引发之前关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="35a3d-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="35a3d-108">事件后的示例将`Form.Closed`，这引发后关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="35a3d-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="35a3d-109">**✓ DO** 使用术语"引发"事件而不是"激发"或"触发"。</span><span class="sxs-lookup"><span data-stu-id="35a3d-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="35a3d-110">**✓ DO** 使用<xref:System.EventHandler%601?displayProperty=nameWithType>而不是手动创建要用作事件处理程序的新委托。</span><span class="sxs-lookup"><span data-stu-id="35a3d-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="35a3d-111">**✓ CONSIDER** 使用的一个子类<xref:System.EventArgs>作为事件自变量，除非您完全确定事件永远都不需要执行任何数据到的事件处理方法，在这种情况下你可以使用`EventArgs`直接键入。</span><span class="sxs-lookup"><span data-stu-id="35a3d-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="35a3d-112">如果 API 使用寄送`EventArgs`直接，您将永远无法添加任何数据，以执行与该事件，而不会破坏兼容性。</span><span class="sxs-lookup"><span data-stu-id="35a3d-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="35a3d-113">如果使用的子类，即使是如果最初完全为空，可以将属性添加到需要时的子类。</span><span class="sxs-lookup"><span data-stu-id="35a3d-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="35a3d-114">**✓ DO** 使用受保护的虚拟方法引发每个事件。</span><span class="sxs-lookup"><span data-stu-id="35a3d-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="35a3d-115">这是仅适用于未密封类，不适用于结构、 密封的类或静态事件上的非静态事件。</span><span class="sxs-lookup"><span data-stu-id="35a3d-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="35a3d-116">此方法的用途是提供派生类来处理使用替代的事件的方法。</span><span class="sxs-lookup"><span data-stu-id="35a3d-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="35a3d-117">重写是一种更灵活、 更快，且更自然的方式来处理在派生类中的基类事件。</span><span class="sxs-lookup"><span data-stu-id="35a3d-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="35a3d-118">按照约定，方法的名称应以"On"开头，并按照向事件的名称。</span><span class="sxs-lookup"><span data-stu-id="35a3d-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="35a3d-119">在派生的类可以选择不在其重写中调用该方法的基实现。</span><span class="sxs-lookup"><span data-stu-id="35a3d-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="35a3d-120">准备此基类才能正常工作所需的方法中不包括任何处理。</span><span class="sxs-lookup"><span data-stu-id="35a3d-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="35a3d-121">**✓ DO** 引发事件的受保护方法采用一个参数。</span><span class="sxs-lookup"><span data-stu-id="35a3d-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="35a3d-122">该参数应命名为`e`和的类型应为事件参数类。</span><span class="sxs-lookup"><span data-stu-id="35a3d-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="35a3d-123">**X DO NOT** 时引发的非静态事件传递 null 值作为发件人。</span><span class="sxs-lookup"><span data-stu-id="35a3d-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="35a3d-124">**✓ DO** 时引发的静态事件传递 null 值作为发件人。</span><span class="sxs-lookup"><span data-stu-id="35a3d-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="35a3d-125">**X DO NOT** 时引发事件传递 null 值作为事件数据参数。</span><span class="sxs-lookup"><span data-stu-id="35a3d-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="35a3d-126">应传递`EventArgs.Empty`如果不想将任何数据传递给事件处理方法。</span><span class="sxs-lookup"><span data-stu-id="35a3d-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="35a3d-127">开发人员看到此参数不为 null。</span><span class="sxs-lookup"><span data-stu-id="35a3d-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="35a3d-128">**✓ CONSIDER** 引发最终用户可以取消的事件。</span><span class="sxs-lookup"><span data-stu-id="35a3d-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="35a3d-129">这仅适用于预事件。</span><span class="sxs-lookup"><span data-stu-id="35a3d-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="35a3d-130">使用<xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>或要允许最终用户可取消事件的事件参数作为其子类。</span><span class="sxs-lookup"><span data-stu-id="35a3d-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="35a3d-131">自定义事件处理程序设计</span><span class="sxs-lookup"><span data-stu-id="35a3d-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="35a3d-132">某些情况下，在其中`EventHandler<T>`不能使用，如框架需要与早期版本的 CLR 不支持泛型。</span><span class="sxs-lookup"><span data-stu-id="35a3d-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="35a3d-133">在这种情况下，可能需要设计和开发自定义事件处理程序委托。</span><span class="sxs-lookup"><span data-stu-id="35a3d-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="35a3d-134">**✓ DO** 对于事件处理程序使用返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="35a3d-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="35a3d-135">事件处理程序可以调用多个事件处理方法，可能在多个对象上。</span><span class="sxs-lookup"><span data-stu-id="35a3d-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="35a3d-136">如果允许事件处理方法返回一个值，则会为每个事件调用多个返回值。</span><span class="sxs-lookup"><span data-stu-id="35a3d-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="35a3d-137">**✓ DO** 使用`object`作为事件处理程序的第一个参数的类型和调用它`sender`。</span><span class="sxs-lookup"><span data-stu-id="35a3d-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="35a3d-138">**✓ DO** 使用<xref:System.EventArgs?displayProperty=nameWithType>或其子类作为事件处理程序中，第二个参数的类型和调用它`e`。</span><span class="sxs-lookup"><span data-stu-id="35a3d-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="35a3d-139">**X DO NOT** 对事件处理程序的两个以上参数。</span><span class="sxs-lookup"><span data-stu-id="35a3d-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="35a3d-140">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="35a3d-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="35a3d-141">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="35a3d-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a3d-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="35a3d-142">See also</span></span>

- [<span data-ttu-id="35a3d-143">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="35a3d-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="35a3d-144">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="35a3d-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
