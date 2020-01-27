---
title: 이벤트 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: b44ee5933f8629b4dddbf3be1b79b2e77b0254f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741686"
---
# <a name="event-design"></a><span data-ttu-id="b68ef-102">이벤트 디자인</span><span class="sxs-lookup"><span data-stu-id="b68ef-102">Event Design</span></span>
<span data-ttu-id="b68ef-103">事件是最常用的回叫（允许框架调用用户代码的结构）。</span><span class="sxs-lookup"><span data-stu-id="b68ef-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="b68ef-104">其他回调机制包括采用委托、虚拟成员和基于接口的插件的成员。可用性研究的数据表明，大多数开发人员比使用其他回调机制更喜欢使用事件.</span><span class="sxs-lookup"><span data-stu-id="b68ef-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="b68ef-105">事件能与 Visual Studio 和许多语言很好地集成。</span><span class="sxs-lookup"><span data-stu-id="b68ef-105">Events are nicely integrated with Visual Studio and many languages.</span></span>

 <span data-ttu-id="b68ef-106">值得注意的是，有两组事件：在系统状态发生变化之前引发的事件，称为事前事件，以及状态更改后引发的事件，称为事后事件。</span><span class="sxs-lookup"><span data-stu-id="b68ef-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="b68ef-107">事前事件的一个例子是 `Form.Closing`，它是在窗体关闭之前引发的。</span><span class="sxs-lookup"><span data-stu-id="b68ef-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="b68ef-108">事后事件的一个例子是 `Form.Closed`，它是在窗体关闭后引发的。</span><span class="sxs-lookup"><span data-stu-id="b68ef-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>

 <span data-ttu-id="b68ef-109">✔️对事件（而不是 "火灾" 或 "trigger"）使用术语 "引发"。</span><span class="sxs-lookup"><span data-stu-id="b68ef-109">✔️ DO use the term "raise" for events rather than "fire" or "trigger."</span></span>

 <span data-ttu-id="b68ef-110">✔️使用 <xref:System.EventHandler%601?displayProperty=nameWithType> 而不是手动创建要用作事件处理程序的新委托。</span><span class="sxs-lookup"><span data-stu-id="b68ef-110">✔️ DO use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>

 <span data-ttu-id="b68ef-111">✔️考虑使用 <xref:System.EventArgs> 的子类作为事件参数，除非你完全确信该事件从不需要将任何数据传递到事件处理方法，在这种情况下，你可以直接使用 `EventArgs` 类型。</span><span class="sxs-lookup"><span data-stu-id="b68ef-111">✔️ CONSIDER using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>

 <span data-ttu-id="b68ef-112">如果直接使用 `EventArgs` 发布API，您将永远无法在不破坏兼容性的情况下添加任何要随事件携带的数据。</span><span class="sxs-lookup"><span data-stu-id="b68ef-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="b68ef-113">如果使用子类，即使最初完全为空，也可以在需要时向子类添加属性。</span><span class="sxs-lookup"><span data-stu-id="b68ef-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>

 <span data-ttu-id="b68ef-114">✔️使用受保护的虚拟方法引发每个事件。</span><span class="sxs-lookup"><span data-stu-id="b68ef-114">✔️ DO use a protected virtual method to raise each event.</span></span> <span data-ttu-id="b68ef-115">这仅适用于非密封类的非静态事件，而不适用于结构、密封类或静态事件。</span><span class="sxs-lookup"><span data-stu-id="b68ef-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>

 <span data-ttu-id="b68ef-116">该方法的目的是为派生类提供一种使用重写来处理事件的方法。</span><span class="sxs-lookup"><span data-stu-id="b68ef-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="b68ef-117">重写是一种更灵活、更快、更自然的方式来处理派生类中的基类事件。</span><span class="sxs-lookup"><span data-stu-id="b68ef-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="b68ef-118">按照惯例，方法的名称应以 “On” 开头，并跟随事件的名称。</span><span class="sxs-lookup"><span data-stu-id="b68ef-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>

 <span data-ttu-id="b68ef-119">派生类可以选择在其重写中不调用方法的基本实现。</span><span class="sxs-lookup"><span data-stu-id="b68ef-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="b68ef-120">要做到这点，需要在方法中不包括使基类正常工作所需的任何处理过程。</span><span class="sxs-lookup"><span data-stu-id="b68ef-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>

 <span data-ttu-id="b68ef-121">✔️会对引发事件的受保护方法执行一个参数。</span><span class="sxs-lookup"><span data-stu-id="b68ef-121">✔️ DO take one parameter to the protected method that raises an event.</span></span>

 <span data-ttu-id="b68ef-122">该参数应命名为 `e`，其类型应为事件参数类。</span><span class="sxs-lookup"><span data-stu-id="b68ef-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>

 <span data-ttu-id="b68ef-123">引发非静态事件时，❌ 不会将 null 传递为发送方。</span><span class="sxs-lookup"><span data-stu-id="b68ef-123">❌ DO NOT pass null as the sender when raising a nonstatic event.</span></span>

 <span data-ttu-id="b68ef-124">✔️在引发静态事件时将 null 作为发件人传递。</span><span class="sxs-lookup"><span data-stu-id="b68ef-124">✔️ DO pass null as the sender when raising a static event.</span></span>

 <span data-ttu-id="b68ef-125">引发事件时，❌ 不会传递 null 作为事件数据参数。</span><span class="sxs-lookup"><span data-stu-id="b68ef-125">❌ DO NOT pass null as the event data parameter when raising an event.</span></span>

 <span data-ttu-id="b68ef-126">如果不想将任何数据传递给事件处理方法，则应传递 `EventArgs.Empty`。</span><span class="sxs-lookup"><span data-stu-id="b68ef-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="b68ef-127">开发人员希望此参数不为 null。</span><span class="sxs-lookup"><span data-stu-id="b68ef-127">Developers expect this parameter not to be null.</span></span>

 <span data-ttu-id="b68ef-128">✔️考虑引发最终用户可以取消的事件。</span><span class="sxs-lookup"><span data-stu-id="b68ef-128">✔️ CONSIDER raising events that the end user can cancel.</span></span> <span data-ttu-id="b68ef-129">这仅适用于事前事件。</span><span class="sxs-lookup"><span data-stu-id="b68ef-129">This only applies to pre-events.</span></span>

 <span data-ttu-id="b68ef-130">使用 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> 或其子类作为事件参数，以允许最终用户取消事件。</span><span class="sxs-lookup"><span data-stu-id="b68ef-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>

### <a name="custom-event-handler-design"></a><span data-ttu-id="b68ef-131">自定义事件处理程序设计</span><span class="sxs-lookup"><span data-stu-id="b68ef-131">Custom Event Handler Design</span></span>
 <span data-ttu-id="b68ef-132">某些情况下不能使用 `EventHandler<T>`，例如当框架需要使用早期版本的 CLR（不支持泛型）时。</span><span class="sxs-lookup"><span data-stu-id="b68ef-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="b68ef-133">在这种情况下，可能需要设计和开发自定义事件处理程序委托。</span><span class="sxs-lookup"><span data-stu-id="b68ef-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>

 <span data-ttu-id="b68ef-134">✔️使用 void 的返回类型作为事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b68ef-134">✔️ DO use a return type of void for event handlers.</span></span>

 <span data-ttu-id="b68ef-135">事件处理程序可以调用多个事件处理方法（可能在多个对象上）。</span><span class="sxs-lookup"><span data-stu-id="b68ef-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="b68ef-136">如果允许事件处理方法返回值，则每个事件调用都有多个返回值。</span><span class="sxs-lookup"><span data-stu-id="b68ef-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>

 <span data-ttu-id="b68ef-137">✔️使用 `object` 作为事件处理程序的第一个参数的类型，并 `sender`调用它。</span><span class="sxs-lookup"><span data-stu-id="b68ef-137">✔️ DO use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>

 <span data-ttu-id="b68ef-138">✔️使用 <xref:System.EventArgs?displayProperty=nameWithType> 或其子类作为事件处理程序的第二个参数的类型，并将其调用 `e`。</span><span class="sxs-lookup"><span data-stu-id="b68ef-138">✔️ DO use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>

 <span data-ttu-id="b68ef-139">❌ 在事件处理程序上没有两个以上的参数。</span><span class="sxs-lookup"><span data-stu-id="b68ef-139">❌ DO NOT have more than two parameters on event handlers.</span></span>

 <span data-ttu-id="b68ef-140">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b68ef-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b68ef-141">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b68ef-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b68ef-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b68ef-142">See also</span></span>

- [<span data-ttu-id="b68ef-143">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b68ef-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="b68ef-144">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b68ef-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
