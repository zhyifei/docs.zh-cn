---
title: 事件 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- events [Visual Basic], about events
- events [Visual Basic]
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a303b0bc9a51ec5566be5cf6db40ff9b9de4c9c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="events-visual-basic"></a><span data-ttu-id="5bebf-102">事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bebf-102">Events (Visual Basic)</span></span>
<span data-ttu-id="5bebf-103">大多数程序时可能会将 Visual Studio 项目可视化为一系列实际上，在序列中，执行的过程是事件驱动的-也就是说执行流由外部发生的事情调用决定*事件*。</span><span class="sxs-lookup"><span data-stu-id="5bebf-103">While you might visualize a Visual Studio project as a series of procedures that execute in a sequence, in reality, most programs are event driven—meaning the flow of execution is determined by external occurrences called *events*.</span></span>  
  
 <span data-ttu-id="5bebf-104">事件是一种信号，可指示应用程序某重要事件已发生。</span><span class="sxs-lookup"><span data-stu-id="5bebf-104">An event is a signal that informs an application that something important has occurred.</span></span> <span data-ttu-id="5bebf-105">例如，当用户单击窗体控件时，窗体会引发 `Click` 事件，并调用可处理此事件的过程。</span><span class="sxs-lookup"><span data-stu-id="5bebf-105">For example, when a user clicks a control on a form, the form can raise a `Click` event and call a procedure that handles the event.</span></span> <span data-ttu-id="5bebf-106">借助事件，各个不同的任务还可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="5bebf-106">Events also allow separate tasks to communicate.</span></span> <span data-ttu-id="5bebf-107">例如，应用程序执行的排序任务与主应用程序是分开的。</span><span class="sxs-lookup"><span data-stu-id="5bebf-107">Say, for example, that your application performs a sort task separately from the main application.</span></span> <span data-ttu-id="5bebf-108">如果用户取消排序，应用程序便会发送 cancel 事件，指示停止排序过程。</span><span class="sxs-lookup"><span data-stu-id="5bebf-108">If a user cancels the sort, your application can send a cancel event instructing the sort process to stop.</span></span>  
  
## <a name="event-terms-and-concepts"></a><span data-ttu-id="5bebf-109">事件术语和概念</span><span class="sxs-lookup"><span data-stu-id="5bebf-109">Event Terms and Concepts</span></span>  
 <span data-ttu-id="5bebf-110">本部分介绍的术语和概念与在 Visual Basic 中的事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="5bebf-110">This section describes the terms and concepts used with events in Visual Basic.</span></span>  
  
### <a name="declaring-events"></a><span data-ttu-id="5bebf-111">声明事件</span><span class="sxs-lookup"><span data-stu-id="5bebf-111">Declaring Events</span></span>  
 <span data-ttu-id="5bebf-112">可以使用 `Event` 关键字在类、结构、模块和接口中声明事件，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5bebf-112">You declare events within classes, structures, modules, and interfaces using the `Event` keyword, as in the following example:</span></span>  
  
 [!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]  
  
### <a name="raising-events"></a><span data-ttu-id="5bebf-113">引发事件</span><span class="sxs-lookup"><span data-stu-id="5bebf-113">Raising Events</span></span>  
 <span data-ttu-id="5bebf-114">事件类似于消息，指示某重要事件已发生。</span><span class="sxs-lookup"><span data-stu-id="5bebf-114">An event is like a message announcing that something important has occurred.</span></span> <span data-ttu-id="5bebf-115">广播消息的行为称为*引发*事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-115">The act of broadcasting the message is called *raising* the event.</span></span> <span data-ttu-id="5bebf-116">在 Visual Basic 中，你可以引发事件的`RaiseEvent`语句，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5bebf-116">In Visual Basic, you raise events with the `RaiseEvent` statement, as in the following example:</span></span>  
  
 [!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]  
  
 <span data-ttu-id="5bebf-117">必须在声明事件的类、模块或结构范围内引发事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-117">Events must be raised within the scope of the class, module, or structure where they are declared.</span></span> <span data-ttu-id="5bebf-118">例如，派生类不能引发继承自基类的事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-118">For example, a derived class cannot raise events inherited from a base class.</span></span>  
  
### <a name="event-senders"></a><span data-ttu-id="5bebf-119">事件发送方</span><span class="sxs-lookup"><span data-stu-id="5bebf-119">Event Senders</span></span>  
 <span data-ttu-id="5bebf-120">所有能够引发事件的对象都是*事件发送方*，亦称为“*事件源*”。</span><span class="sxs-lookup"><span data-stu-id="5bebf-120">Any object capable of raising an event is an *event sender*, also known as an *event source*.</span></span> <span data-ttu-id="5bebf-121">例如，窗体、控件和用户定义对象都是事件发送方。</span><span class="sxs-lookup"><span data-stu-id="5bebf-121">Forms, controls, and user-defined objects are examples of event senders.</span></span>  
  
### <a name="event-handlers"></a><span data-ttu-id="5bebf-122">事件处理程序</span><span class="sxs-lookup"><span data-stu-id="5bebf-122">Event Handlers</span></span>  
 <span data-ttu-id="5bebf-123">*事件处理程序*是在相应事件发生时调用的过程。</span><span class="sxs-lookup"><span data-stu-id="5bebf-123">*Event handlers* are procedures that are called when a corresponding event occurs.</span></span> <span data-ttu-id="5bebf-124">可以将签名一致的任意有效子例程用作事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5bebf-124">You can use any valid subroutine with a matching signature as an event handler.</span></span> <span data-ttu-id="5bebf-125">不过，不能将函数用作事件处理程序，因为它不能向事件源返回值。</span><span class="sxs-lookup"><span data-stu-id="5bebf-125">You cannot use a function as an event handler, however, because it cannot return a value to the event source.</span></span>  
  
 <span data-ttu-id="5bebf-126">Visual Basic 使用标准命名约定对事件处理程序将合并的事件发送方、 下划线和事件的名称的名称。</span><span class="sxs-lookup"><span data-stu-id="5bebf-126">Visual Basic uses a standard naming convention for event handlers that combines the name of the event sender, an underscore, and the name of the event.</span></span> <span data-ttu-id="5bebf-127">例如，`button1` 按钮的 `Click` 事件将命名为 `Sub button1_Click`。</span><span class="sxs-lookup"><span data-stu-id="5bebf-127">For example, the `Click` event of a button named `button1` would be named `Sub button1_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bebf-128">我们建议在为你自己的事件定义事件处理程序时采用此命名约定，但这不是一项强制性要求；可以命名任意有效的子例程名称。</span><span class="sxs-lookup"><span data-stu-id="5bebf-128">We recommend that you use this naming convention when defining event handlers for your own events, but it is not required; you can use any valid subroutine name.</span></span>  
  
## <a name="associating-events-with-event-handlers"></a><span data-ttu-id="5bebf-129">关联事件与事件处理程序</span><span class="sxs-lookup"><span data-stu-id="5bebf-129">Associating Events with Event Handlers</span></span>  
 <span data-ttu-id="5bebf-130">必须先使用 `Handles` 或 `AddHandler` 语句关联事件处理程序与事件，然后才能使用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5bebf-130">Before an event handler becomes usable, you must first associate it with an event by using either the `Handles` or `AddHandler` statement.</span></span>  
  
### <a name="withevents-and-the-handles-clause"></a><span data-ttu-id="5bebf-131">WithEvents 和 Handles 子句</span><span class="sxs-lookup"><span data-stu-id="5bebf-131">WithEvents and the Handles Clause</span></span>  
 <span data-ttu-id="5bebf-132">使用 `WithEvents` 语句和 `Handles` 子句，可以声明性的方式指定事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5bebf-132">The `WithEvents` statement and `Handles` clause provide a declarative way of specifying event handlers.</span></span> <span data-ttu-id="5bebf-133">使用 `WithEvents` 关键字声明的对象引发的事件可以由使用 `Handles` 语句针对相应事件指定的任意过程进行处理，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5bebf-133">An event raised by an object declared with the `WithEvents` keyword can be handled by any procedure with a `Handles` statement for that event, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]  
  
 <span data-ttu-id="5bebf-134">`WithEvents` 语句和 `Handles` 子句通常是事件处理程序的最佳选择，因为它们使用的声明性语法简化了事件处理程序的编码、读取和调试。</span><span class="sxs-lookup"><span data-stu-id="5bebf-134">The `WithEvents` statement and the `Handles` clause are often the best choice for event handlers because the declarative syntax they use makes event handling easier to code, read and debug.</span></span> <span data-ttu-id="5bebf-135">不过，请注意，使用 `WithEvents` 变量还要遵循以下限制：</span><span class="sxs-lookup"><span data-stu-id="5bebf-135">However, be aware of the following limitations on the use of `WithEvents` variables:</span></span>  
  
-   <span data-ttu-id="5bebf-136">不能将 `WithEvents` 变量用作对象变量。</span><span class="sxs-lookup"><span data-stu-id="5bebf-136">You cannot use a `WithEvents` variable as an object variable.</span></span> <span data-ttu-id="5bebf-137">也就是说，不能将其声明为 `Object`，必须在声明变量时指定类名。</span><span class="sxs-lookup"><span data-stu-id="5bebf-137">That is, you cannot declare it as `Object`—you must specify the class name when you declare the variable.</span></span>  
  
-   <span data-ttu-id="5bebf-138">因为共享的事件不会与类实例关联的不能使用`WithEvents`以声明方式处理共享的事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-138">Because shared events are not tied to class instances, you cannot use `WithEvents` to declaratively handle shared events.</span></span> <span data-ttu-id="5bebf-139">同样，不能使用 `WithEvents` 或 `Handles` 处理 `Structure` 中的事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-139">Similarly, you cannot use `WithEvents` or `Handles` to handle events from a `Structure`.</span></span> <span data-ttu-id="5bebf-140">在这两种情况下，均可使用 `AddHandler` 语句处理这些事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-140">In both cases, you can use the `AddHandler` statement to handle those events.</span></span>  
  
-   <span data-ttu-id="5bebf-141">无法创建 `WithEvents` 变量的数组。</span><span class="sxs-lookup"><span data-stu-id="5bebf-141">You cannot create arrays of `WithEvents` variables.</span></span>  
  
 <span data-ttu-id="5bebf-142">`WithEvents` 变量允许一个事件处理程序处理一种或多种事件，也允许一个或多个事件处理程序处理同一种事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-142">`WithEvents` variables allow a single event handler to handle one or more kind of event, or one or more event handlers to handle the same kind of event.</span></span>  
  
 <span data-ttu-id="5bebf-143">虽然 `Handles` 子句是关联事件与事件处理程序的标准方法，但只能在编译时关联事件与事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5bebf-143">Although the `Handles` clause is the standard way of associating an event with an event handler, it is limited to associating events with event handlers at compile time.</span></span>  
  
 <span data-ttu-id="5bebf-144">在某些情况下，如使用窗体或控件，与关联的事件 Visual Basic 自动引出一个空的事件处理程序并将其与事件关联。</span><span class="sxs-lookup"><span data-stu-id="5bebf-144">In some cases, such as with events associated with forms or controls, Visual Basic automatically stubs out an empty event handler and associates it with an event.</span></span> <span data-ttu-id="5bebf-145">例如，双击在设计模式下的窗体上的命令按钮时，Visual Basic 创建一个空的事件处理程序和`WithEvents`变量的命令按钮，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="5bebf-145">For example, when you double-click a command button on a form in design mode, Visual Basic creates an empty event handler and a `WithEvents` variable for the command button, as in the following code:</span></span>  
  
 [!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]  
  
### <a name="addhandler-and-removehandler"></a><span data-ttu-id="5bebf-146">AddHandler 和 RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="5bebf-146">AddHandler and RemoveHandler</span></span>  
 <span data-ttu-id="5bebf-147">`AddHandler` 语句与 `Handles` 子句类似，两者都允许指定事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5bebf-147">The `AddHandler` statement is similar to the `Handles` clause in that both allow you to specify an event handler.</span></span> <span data-ttu-id="5bebf-148">不同之处在于，`AddHandler` 与 `RemoveHandler` 结合使用比 `Handles` 子句更具灵活性，你可以动态添加、删除和更改与事件关联的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5bebf-148">However, `AddHandler`, used with `RemoveHandler`, provides greater flexibility than the `Handles` clause, allowing you to dynamically add, remove, and change the event handler associated with an event.</span></span> <span data-ttu-id="5bebf-149">若要处理共享事件或结构中的事件，必须使用 `AddHandler`。</span><span class="sxs-lookup"><span data-stu-id="5bebf-149">If you want to handle shared events or events from a structure, you must use `AddHandler`.</span></span>  
  
 <span data-ttu-id="5bebf-150">`AddHandler` 需要使用两个自变量：事件发送方（如控件）引发的事件的名称和计算结果为委托的表达式。</span><span class="sxs-lookup"><span data-stu-id="5bebf-150">`AddHandler` takes two arguments: the name of an event from an event sender such as a control, and an expression that evaluates to a delegate.</span></span> <span data-ttu-id="5bebf-151">使用 `AddHandler` 时，无需显式指定委托类，因为 `AddressOf` 语句始终返回对委托的引用。</span><span class="sxs-lookup"><span data-stu-id="5bebf-151">You do not need to explicitly specify the delegate class when using `AddHandler`, since the `AddressOf` statement always returns a reference to the delegate.</span></span> <span data-ttu-id="5bebf-152">下面的示例将事件处理程序与对象引发的事件相关联：</span><span class="sxs-lookup"><span data-stu-id="5bebf-152">The following example associates an event handler with an event raised by an object:</span></span>  
  
 [!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]  
  
 <span data-ttu-id="5bebf-153">`RemoveHandler` 用于解除事件与事件处理程序的关联，所用语法与 `AddHandler` 一样。</span><span class="sxs-lookup"><span data-stu-id="5bebf-153">`RemoveHandler`, which disconnects an event from an event handler, uses the same syntax as `AddHandler`.</span></span> <span data-ttu-id="5bebf-154">例如：</span><span class="sxs-lookup"><span data-stu-id="5bebf-154">For example:</span></span>  
  
 [!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]  
  
 <span data-ttu-id="5bebf-155">在以下示例中，事件处理程序与事件相关联，且此事件已引发。</span><span class="sxs-lookup"><span data-stu-id="5bebf-155">In the following example, an event handler is associated with an event, and the event is raised.</span></span> <span data-ttu-id="5bebf-156">事件处理程序捕获此事件并显示消息。</span><span class="sxs-lookup"><span data-stu-id="5bebf-156">The event handler catches the event and displays a message.</span></span>  
  
 <span data-ttu-id="5bebf-157">然后删除第一个事件处理程序，并将另一个事件处理程序与此事件相关联。</span><span class="sxs-lookup"><span data-stu-id="5bebf-157">Then the first event handler is removed and a different event handler is associated with the event.</span></span> <span data-ttu-id="5bebf-158">当此事件再次引发时，显示不同的消息。</span><span class="sxs-lookup"><span data-stu-id="5bebf-158">When the event is raised again, a different message is displayed.</span></span>  
  
 <span data-ttu-id="5bebf-159">最后删除第二个事件处理程序，然后第三次引发此事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-159">Finally, the second event handler is removed and the event is raised for a third time.</span></span> <span data-ttu-id="5bebf-160">因为不再有事件处理程序与此事件相关联，所以不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5bebf-160">Because there is no longer an event handler associated with the event, no action is taken.</span></span>  
  
 [!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]  
  
## <a name="handling-events-inherited-from-a-base-class"></a><span data-ttu-id="5bebf-161">处理继承自基类的事件</span><span class="sxs-lookup"><span data-stu-id="5bebf-161">Handling Events Inherited from a Base Class</span></span>  
 <span data-ttu-id="5bebf-162">*派生类*继承了基类特征的类，可以使用 `Handles``MyBase` 语句处理基类引发的事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-162">*Derived classes*—classes that inherit characteristics from a base class—can handle events raised by their base class using the `Handles``MyBase` statement.</span></span>  
  
#### <a name="to-handle-events-from-a-base-class"></a><span data-ttu-id="5bebf-163">处理继承自基类的事件的具体操作</span><span class="sxs-lookup"><span data-stu-id="5bebf-163">To handle events from a base class</span></span>  
  
-   <span data-ttu-id="5bebf-164">向事件处理程序过程的声明行添加 `Handles MyBase.` *eventname* 语句，在派生类中声明事件处理程序，其中 *eventname* 是要处理的继承自基类的事件名称。</span><span class="sxs-lookup"><span data-stu-id="5bebf-164">Declare an event handler in the derived class by adding a `Handles MyBase.`*eventname* statement to the declaration line of your event-handler procedure, where *eventname* is the name of the event in the base class you are handling.</span></span> <span data-ttu-id="5bebf-165">例如：</span><span class="sxs-lookup"><span data-stu-id="5bebf-165">For example:</span></span>  
  
     [!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]  
  
## <a name="related-sections"></a><span data-ttu-id="5bebf-166">相关章节</span><span class="sxs-lookup"><span data-stu-id="5bebf-166">Related Sections</span></span>  
  
|<span data-ttu-id="5bebf-167">标题</span><span class="sxs-lookup"><span data-stu-id="5bebf-167">Title</span></span>|<span data-ttu-id="5bebf-168">描述</span><span class="sxs-lookup"><span data-stu-id="5bebf-168">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5bebf-169">演练：声明和引发事件</span><span class="sxs-lookup"><span data-stu-id="5bebf-169">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|<span data-ttu-id="5bebf-170">分步展示了如何声明和引发类事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-170">Provides a step-by-step description of how to declare and raise events for a class.</span></span>|  
|[<span data-ttu-id="5bebf-171">演练：处理事件</span><span class="sxs-lookup"><span data-stu-id="5bebf-171">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|<span data-ttu-id="5bebf-172">展示了如何编写事件处理程序过程。</span><span class="sxs-lookup"><span data-stu-id="5bebf-172">Demonstrates how to write an event-handler procedure.</span></span>|  
|[<span data-ttu-id="5bebf-173">如何：声明自定义事件以避免阻止</span><span class="sxs-lookup"><span data-stu-id="5bebf-173">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|<span data-ttu-id="5bebf-174">介绍了如何定义允许异步调用事件处理程序的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-174">Demonstrates how to define a custom event that allows its event handlers to be called asynchronously.</span></span>|  
|[<span data-ttu-id="5bebf-175">如何：声明自定义事件以节省内存</span><span class="sxs-lookup"><span data-stu-id="5bebf-175">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|<span data-ttu-id="5bebf-176">介绍了如何定义仅在事件处理时占用内存的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-176">Demonstrates how to define a custom event that uses memory only when the event is handled.</span></span>|  
|[<span data-ttu-id="5bebf-177">Visual Basic 中继承的事件处理程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="5bebf-177">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|<span data-ttu-id="5bebf-178">列出了在继承的组件中使用事件处理程序时遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="5bebf-178">Lists common issues that arise with event handlers in inherited components.</span></span>|  
|[<span data-ttu-id="5bebf-179">事件</span><span class="sxs-lookup"><span data-stu-id="5bebf-179">Events</span></span>](../../../../standard/events/index.md)|<span data-ttu-id="5bebf-180">概述了 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中的事件模型。</span><span class="sxs-lookup"><span data-stu-id="5bebf-180">Provides an overview of the event model in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="5bebf-181">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="5bebf-181">Creating Event Handlers in Windows Forms</span></span>](../../../../framework/winforms/creating-event-handlers-in-windows-forms.md)|<span data-ttu-id="5bebf-182">介绍了如何处理与 Windows 窗体对象关联的事件。</span><span class="sxs-lookup"><span data-stu-id="5bebf-182">Describes how to work with events associated with Windows Forms objects.</span></span>|  
|[<span data-ttu-id="5bebf-183">委托</span><span class="sxs-lookup"><span data-stu-id="5bebf-183">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)|<span data-ttu-id="5bebf-184">概述了 Visual Basic 中的委托。</span><span class="sxs-lookup"><span data-stu-id="5bebf-184">Provides an overview of delegates in Visual Basic.</span></span>|
