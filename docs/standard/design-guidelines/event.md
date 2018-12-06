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
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261363"
---
# <a name="event-design"></a><span data-ttu-id="1308f-102">事件设计</span><span class="sxs-lookup"><span data-stu-id="1308f-102">Event Design</span></span>
<span data-ttu-id="1308f-103">事件是最常用的回叫（允许框架调用用户代码的结构）。</span><span class="sxs-lookup"><span data-stu-id="1308f-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="1308f-104">其他回叫机制包括接受委托的成员、虚拟成员和基于接口的插件。来自可用性研究的数据表明，相比使用其他回叫机制，大多数开发人员更习惯使用事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="1308f-105">事件能与 Visual Studio 和许多语言很好地集成。</span><span class="sxs-lookup"><span data-stu-id="1308f-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="1308f-106">值得注意的是，有两组事件：在系统状态发生变化之前引发的事件，称为事前事件，以及状态更改后引发的事件，称为事后事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="1308f-107">事前事件的一个例子是 `Form.Closing`，它是在窗体关闭之前引发的。</span><span class="sxs-lookup"><span data-stu-id="1308f-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="1308f-108">事后事件的一个例子是 `Form.Closed`，它是在窗体关闭后引发的。</span><span class="sxs-lookup"><span data-stu-id="1308f-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="1308f-109">**✓ 务必** 对事件使用术语 “raise” 而不是 “fire” 或 “trigger”。</span><span class="sxs-lookup"><span data-stu-id="1308f-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="1308f-110">**✓ 务必** 使用<xref:System.EventHandler%601?displayProperty=nameWithType>而不是手动创建新的委托以用作事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1308f-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="1308f-111">**✓ 考虑** 使用 <xref:System.EventArgs> 的子类作为事件参数，除非您完全确定事件永远不需要将任何数据传递给事件处理方法，在这种情况下您可以直接使用 `EventArgs` 类型。</span><span class="sxs-lookup"><span data-stu-id="1308f-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="1308f-112">如果直接使用 `EventArgs` 发布API，您将永远无法在不破坏兼容性的情况下添加任何要随事件携带的数据。</span><span class="sxs-lookup"><span data-stu-id="1308f-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="1308f-113">如果使用子类，即使最初完全为空，也可以在需要时向子类添加属性。</span><span class="sxs-lookup"><span data-stu-id="1308f-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="1308f-114">**✓ 务必** 使用受保护的虚拟方法来引发每个事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="1308f-115">这仅适用于非密封类的非静态事件，而不适用于结构、密封类或静态事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="1308f-116">该方法的目的是为派生类提供一种使用重写来处理事件的方法。</span><span class="sxs-lookup"><span data-stu-id="1308f-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="1308f-117">重写是一种更灵活、更快、更自然的方式来处理派生类中的基类事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="1308f-118">按照惯例，方法的名称应以 “On” 开头，并跟随事件的名称。</span><span class="sxs-lookup"><span data-stu-id="1308f-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="1308f-119">派生类可以选择在其重写中不调用方法的基本实现。</span><span class="sxs-lookup"><span data-stu-id="1308f-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="1308f-120">要做到这点，需要在方法中不包括使基类正常工作所需的任何处理过程。</span><span class="sxs-lookup"><span data-stu-id="1308f-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="1308f-121">**✓ 务必** 为引发事件的受保护方法采用一个参数。</span><span class="sxs-lookup"><span data-stu-id="1308f-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="1308f-122">该参数应命名为 `e`，其类型应为事件参数类。</span><span class="sxs-lookup"><span data-stu-id="1308f-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="1308f-123">**X 切忌** 在引发非静态事件时传递 null 值作为 sender。</span><span class="sxs-lookup"><span data-stu-id="1308f-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="1308f-124">**✓ 务必** 在引发静态事件时传递 null 值作为 sender。</span><span class="sxs-lookup"><span data-stu-id="1308f-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="1308f-125">**X 切忌** 在引发事件时传递 null 值作为事件数据参数。</span><span class="sxs-lookup"><span data-stu-id="1308f-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="1308f-126">如果不想将任何数据传递给事件处理方法，则应传递 `EventArgs.Empty`。</span><span class="sxs-lookup"><span data-stu-id="1308f-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="1308f-127">开发人员希望此参数不为 null。</span><span class="sxs-lookup"><span data-stu-id="1308f-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="1308f-128">**✓ 考虑** 引发最终用户可以取消的事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="1308f-129">这仅适用于事前事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="1308f-130">使用 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> 或其子类作为事件参数，以允许最终用户取消事件。</span><span class="sxs-lookup"><span data-stu-id="1308f-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="1308f-131">自定义事件处理程序设计</span><span class="sxs-lookup"><span data-stu-id="1308f-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="1308f-132">某些情况下不能使用 `EventHandler<T>`，例如当框架需要使用早期版本的 CLR（不支持泛型）时。</span><span class="sxs-lookup"><span data-stu-id="1308f-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="1308f-133">在这种情况下，可能需要设计和开发自定义事件处理程序委托。</span><span class="sxs-lookup"><span data-stu-id="1308f-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="1308f-134">**✓ DO** 对于事件处理程序使用返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="1308f-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="1308f-135">事件处理程序可以调用多个事件处理方法，可能在多个对象上。</span><span class="sxs-lookup"><span data-stu-id="1308f-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="1308f-136">如果允许事件处理方法返回一个值，则会为每个事件调用多个返回值。</span><span class="sxs-lookup"><span data-stu-id="1308f-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="1308f-137">**✓ DO** 使用`object`作为事件处理程序的第一个参数的类型和调用它`sender`。</span><span class="sxs-lookup"><span data-stu-id="1308f-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="1308f-138">**✓ 务必** 使用 <xref:System.EventArgs?displayProperty=nameWithType> 作为事件处理程序的第一个参数的类型，并将其命名为`e`。</span><span class="sxs-lookup"><span data-stu-id="1308f-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="1308f-139">**X DO NOT** 对事件处理程序的两个以上参数。</span><span class="sxs-lookup"><span data-stu-id="1308f-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="1308f-140">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="1308f-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1308f-141">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="1308f-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1308f-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1308f-142">See also</span></span>

- [<span data-ttu-id="1308f-143">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="1308f-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="1308f-144">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="1308f-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
