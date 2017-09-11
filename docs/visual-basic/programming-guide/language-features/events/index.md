---
title: "事件 (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- events [Visual Basic], about events
- events [Visual Basic]
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 84f8385e1b2f16c4bcfa53ef2c77e1f0cf61e5e3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="events-visual-basic"></a><span data-ttu-id="99664-102">事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99664-102">Events (Visual Basic)</span></span>
<span data-ttu-id="99664-103">虽然可以将 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 项目可视化为按序列执行的一系列过程，但实际上大多数程序都是事件驱动型。也就是说，外部发生的*事件*决定了执行流。</span><span class="sxs-lookup"><span data-stu-id="99664-103">While you might visualize a [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] project as a series of procedures that execute in a sequence, in reality, most programs are event driven—meaning the flow of execution is determined by external occurrences called *events*.</span></span>  
  
 <span data-ttu-id="99664-104">事件是一种信号，可指示应用程序某重要事件已发生。</span><span class="sxs-lookup"><span data-stu-id="99664-104">An event is a signal that informs an application that something important has occurred.</span></span> <span data-ttu-id="99664-105">例如，当用户单击窗体控件时，窗体会引发 `Click` 事件，并调用可处理此事件的过程。</span><span class="sxs-lookup"><span data-stu-id="99664-105">For example, when a user clicks a control on a form, the form can raise a `Click` event and call a procedure that handles the event.</span></span> <span data-ttu-id="99664-106">借助事件，各个不同的任务还可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="99664-106">Events also allow separate tasks to communicate.</span></span> <span data-ttu-id="99664-107">例如，应用程序执行的排序任务与主应用程序是分开的。</span><span class="sxs-lookup"><span data-stu-id="99664-107">Say, for example, that your application performs a sort task separately from the main application.</span></span> <span data-ttu-id="99664-108">如果用户取消排序，应用程序便会发送 cancel 事件，指示停止排序过程。</span><span class="sxs-lookup"><span data-stu-id="99664-108">If a user cancels the sort, your application can send a cancel event instructing the sort process to stop.</span></span>  
  
## <a name="event-terms-and-concepts"></a><span data-ttu-id="99664-109">事件术语和概念</span><span class="sxs-lookup"><span data-stu-id="99664-109">Event Terms and Concepts</span></span>  
 <span data-ttu-id="99664-110">此部分介绍了 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 中的事件术语和概念。</span><span class="sxs-lookup"><span data-stu-id="99664-110">This section describes the terms and concepts used with events in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="declaring-events"></a><span data-ttu-id="99664-111">声明事件</span><span class="sxs-lookup"><span data-stu-id="99664-111">Declaring Events</span></span>  
 <span data-ttu-id="99664-112">可以使用 `Event` 关键字在类、结构、模块和接口中声明事件，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="99664-112">You declare events within classes, structures, modules, and interfaces using the `Event` keyword, as in the following example:</span></span>  
  
 <span data-ttu-id="99664-113">[!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-113">[!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]</span></span>  
  
### <a name="raising-events"></a><span data-ttu-id="99664-114">引发事件</span><span class="sxs-lookup"><span data-stu-id="99664-114">Raising Events</span></span>  
 <span data-ttu-id="99664-115">事件类似于消息，指示某重要事件已发生。</span><span class="sxs-lookup"><span data-stu-id="99664-115">An event is like a message announcing that something important has occurred.</span></span> <span data-ttu-id="99664-116">广播消息的行为称为*引发*事件。</span><span class="sxs-lookup"><span data-stu-id="99664-116">The act of broadcasting the message is called *raising* the event.</span></span> <span data-ttu-id="99664-117">在 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 中，使用 `RaiseEvent` 语句引发事件，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="99664-117">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], you raise events with the `RaiseEvent` statement, as in the following example:</span></span>  
  
 <span data-ttu-id="99664-118">[!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-118">[!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]</span></span>  
  
 <span data-ttu-id="99664-119">必须在声明事件的类、模块或结构范围内引发事件。</span><span class="sxs-lookup"><span data-stu-id="99664-119">Events must be raised within the scope of the class, module, or structure where they are declared.</span></span> <span data-ttu-id="99664-120">例如，派生类不能引发继承自基类的事件。</span><span class="sxs-lookup"><span data-stu-id="99664-120">For example, a derived class cannot raise events inherited from a base class.</span></span>  
  
### <a name="event-senders"></a><span data-ttu-id="99664-121">事件发送方</span><span class="sxs-lookup"><span data-stu-id="99664-121">Event Senders</span></span>  
 <span data-ttu-id="99664-122">所有能够引发事件的对象都是*事件发送方*，亦称为“*事件源*”。</span><span class="sxs-lookup"><span data-stu-id="99664-122">Any object capable of raising an event is an *event sender*, also known as an *event source*.</span></span> <span data-ttu-id="99664-123">例如，窗体、控件和用户定义对象都是事件发送方。</span><span class="sxs-lookup"><span data-stu-id="99664-123">Forms, controls, and user-defined objects are examples of event senders.</span></span>  
  
### <a name="event-handlers"></a><span data-ttu-id="99664-124">事件处理程序</span><span class="sxs-lookup"><span data-stu-id="99664-124">Event Handlers</span></span>  
 <span data-ttu-id="99664-125">*事件处理程序*是在相应事件发生时调用的过程。</span><span class="sxs-lookup"><span data-stu-id="99664-125">*Event handlers* are procedures that are called when a corresponding event occurs.</span></span> <span data-ttu-id="99664-126">可以将签名一致的任意有效子例程用作事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="99664-126">You can use any valid subroutine with a matching signature as an event handler.</span></span> <span data-ttu-id="99664-127">不过，不能将函数用作事件处理程序，因为它不能向事件源返回值。</span><span class="sxs-lookup"><span data-stu-id="99664-127">You cannot use a function as an event handler, however, because it cannot return a value to the event source.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="99664-128"> 对事件处理程序采用标准命名约定，即名称中包含事件发送方的名称、下划线和事件名称。</span><span class="sxs-lookup"><span data-stu-id="99664-128"> uses a standard naming convention for event handlers that combines the name of the event sender, an underscore, and the name of the event.</span></span> <span data-ttu-id="99664-129">例如，`button1` 按钮的 `Click` 事件将命名为 `Sub button1_Click`。</span><span class="sxs-lookup"><span data-stu-id="99664-129">For example, the `Click` event of a button named `button1` would be named `Sub button1_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99664-130">我们建议在为你自己的事件定义事件处理程序时采用此命名约定，但这不是一项强制性要求；可以命名任意有效的子例程名称。</span><span class="sxs-lookup"><span data-stu-id="99664-130">We recommend that you use this naming convention when defining event handlers for your own events, but it is not required; you can use any valid subroutine name.</span></span>  
  
## <a name="associating-events-with-event-handlers"></a><span data-ttu-id="99664-131">关联事件与事件处理程序</span><span class="sxs-lookup"><span data-stu-id="99664-131">Associating Events with Event Handlers</span></span>  
 <span data-ttu-id="99664-132">必须先使用 `Handles` 或 `AddHandler` 语句关联事件处理程序与事件，然后才能使用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="99664-132">Before an event handler becomes usable, you must first associate it with an event by using either the `Handles` or `AddHandler` statement.</span></span>  
  
### <a name="withevents-and-the-handles-clause"></a><span data-ttu-id="99664-133">WithEvents 和 Handles 子句</span><span class="sxs-lookup"><span data-stu-id="99664-133">WithEvents and the Handles Clause</span></span>  
 <span data-ttu-id="99664-134">使用 `WithEvents` 语句和 `Handles` 子句，可以声明性的方式指定事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="99664-134">The `WithEvents` statement and `Handles` clause provide a declarative way of specifying event handlers.</span></span> <span data-ttu-id="99664-135">使用 `WithEvents` 关键字声明的对象引发的事件可以由使用 `Handles` 语句针对相应事件指定的任意过程进行处理，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="99664-135">An event raised by an object declared with the `WithEvents` keyword can be handled by any procedure with a `Handles` statement for that event, as shown in the following example:</span></span>  
  
 <span data-ttu-id="99664-136">[!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-136">[!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]</span></span>  
  
 <span data-ttu-id="99664-137">`WithEvents` 语句和 `Handles` 子句通常是事件处理程序的最佳选择，因为它们使用的声明性语法简化了事件处理程序的编码、读取和调试。</span><span class="sxs-lookup"><span data-stu-id="99664-137">The `WithEvents` statement and the `Handles` clause are often the best choice for event handlers because the declarative syntax they use makes event handling easier to code, read and debug.</span></span> <span data-ttu-id="99664-138">不过，请注意，使用 `WithEvents` 变量还要遵循以下限制：</span><span class="sxs-lookup"><span data-stu-id="99664-138">However, be aware of the following limitations on the use of `WithEvents` variables:</span></span>  
  
-   <span data-ttu-id="99664-139">不能将 `WithEvents` 变量用作对象变量。</span><span class="sxs-lookup"><span data-stu-id="99664-139">You cannot use a `WithEvents` variable as an object variable.</span></span> <span data-ttu-id="99664-140">也就是说，不能将其声明为 `Object`，必须在声明变量时指定类名。</span><span class="sxs-lookup"><span data-stu-id="99664-140">That is, you cannot declare it as `Object`—you must specify the class name when you declare the variable.</span></span>  
  
-   <span data-ttu-id="99664-141">由于共享事件未与类实例绑定，因此不能使用 `WithEvents` 以声明性方式处理共享事件。</span><span class="sxs-lookup"><span data-stu-id="99664-141">Because shared eventsare not tied to class instances, you cannot use `WithEvents` to declaratively handle shared events.</span></span> <span data-ttu-id="99664-142">同样，不能使用 `WithEvents` 或 `Handles` 处理 `Structure` 中的事件。</span><span class="sxs-lookup"><span data-stu-id="99664-142">Similarly, you cannot use `WithEvents` or `Handles` to handle events from a `Structure`.</span></span> <span data-ttu-id="99664-143">在这两种情况下，均可使用 `AddHandler` 语句处理这些事件。</span><span class="sxs-lookup"><span data-stu-id="99664-143">In both cases, you can use the `AddHandler` statement to handle those events.</span></span>  
  
-   <span data-ttu-id="99664-144">无法创建 `WithEvents` 变量的数组。</span><span class="sxs-lookup"><span data-stu-id="99664-144">You cannot create arrays of `WithEvents` variables.</span></span>  
  
 <span data-ttu-id="99664-145">`WithEvents` 变量允许一个事件处理程序处理一种或多种事件，也允许一个或多个事件处理程序处理同一种事件。</span><span class="sxs-lookup"><span data-stu-id="99664-145">`WithEvents` variables allow a single event handler to handle one or more kind of event, or one or more event handlers to handle the same kind of event.</span></span>  
  
 <span data-ttu-id="99664-146">虽然 `Handles` 子句是关联事件与事件处理程序的标准方法，但只能在编译时关联事件与事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="99664-146">Although the `Handles` clause is the standard way of associating an event with an event handler, it is limited to associating events with event handlers at compile time.</span></span>  
  
 <span data-ttu-id="99664-147">在某些情况下（如事件与窗体或控件相关联），[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 会自动存根空事件处理程序，并将其与事件相关联。</span><span class="sxs-lookup"><span data-stu-id="99664-147">In some cases, such as with events associated with forms or controls, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically stubs out an empty event handler and associates it with an event.</span></span> <span data-ttu-id="99664-148">例如，在设计模式下双击窗体上的命令按钮时，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 会为命令按钮创建空事件处理程序和 `WithEvents` 变量，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="99664-148">For example, when you double-click a command button on a form in design mode, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] creates an empty event handler and a `WithEvents` variable for the command button, as in the following code:</span></span>  
  
 <span data-ttu-id="99664-149">[!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-149">[!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]</span></span>  
  
### <a name="addhandler-and-removehandler"></a><span data-ttu-id="99664-150">AddHandler 和 RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="99664-150">AddHandler and RemoveHandler</span></span>  
 <span data-ttu-id="99664-151">`AddHandler` 语句与 `Handles` 子句类似，两者都允许指定事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="99664-151">The `AddHandler` statement is similar to the `Handles` clause in that both allow you to specify an event handler.</span></span> <span data-ttu-id="99664-152">不同之处在于，`AddHandler` 与 `RemoveHandler` 结合使用比 `Handles` 子句更具灵活性，你可以动态添加、删除和更改与事件关联的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="99664-152">However, `AddHandler`, used with `RemoveHandler`, provides greater flexibility than the `Handles` clause, allowing you to dynamically add, remove, and change the event handler associated with an event.</span></span> <span data-ttu-id="99664-153">若要处理共享事件或结构中的事件，必须使用 `AddHandler`。</span><span class="sxs-lookup"><span data-stu-id="99664-153">If you want to handle shared events or events from a structure, you must use `AddHandler`.</span></span>  
  
 <span data-ttu-id="99664-154">`AddHandler` 需要使用两个自变量：事件发送方（如控件）引发的事件的名称和计算结果为委托的表达式。</span><span class="sxs-lookup"><span data-stu-id="99664-154">`AddHandler` takes two arguments: the name of an event from an event sender such as a control, and an expression that evaluates to a delegate.</span></span> <span data-ttu-id="99664-155">使用 `AddHandler` 时，无需显式指定委托类，因为 `AddressOf` 语句始终返回对委托的引用。</span><span class="sxs-lookup"><span data-stu-id="99664-155">You do not need to explicitly specify the delegate class when using `AddHandler`, since the `AddressOf` statement always returns a reference to the delegate.</span></span> <span data-ttu-id="99664-156">下面的示例将事件处理程序与对象引发的事件相关联：</span><span class="sxs-lookup"><span data-stu-id="99664-156">The following example associates an event handler with an event raised by an object:</span></span>  
  
 <span data-ttu-id="99664-157">[!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-157">[!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]</span></span>  
  
 <span data-ttu-id="99664-158">`RemoveHandler` 用于解除事件与事件处理程序的关联，所用语法与 `AddHandler` 一样。</span><span class="sxs-lookup"><span data-stu-id="99664-158">`RemoveHandler`, which disconnects an event from an event handler, uses the same syntax as `AddHandler`.</span></span> <span data-ttu-id="99664-159">例如: </span><span class="sxs-lookup"><span data-stu-id="99664-159">For example:</span></span>  
  
 <span data-ttu-id="99664-160">[!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-160">[!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]</span></span>  
  
 <span data-ttu-id="99664-161">在以下示例中，事件处理程序与事件相关联，且此事件已引发。</span><span class="sxs-lookup"><span data-stu-id="99664-161">In the following example, an event handler is associated with an event, and the event is raised.</span></span> <span data-ttu-id="99664-162">事件处理程序捕获此事件并显示消息。</span><span class="sxs-lookup"><span data-stu-id="99664-162">The event handler catches the event and displays a message.</span></span>  
  
 <span data-ttu-id="99664-163">然后删除第一个事件处理程序，并将另一个事件处理程序与此事件相关联。</span><span class="sxs-lookup"><span data-stu-id="99664-163">Then the first event handler is removed and a different event handler is associated with the event.</span></span> <span data-ttu-id="99664-164">当此事件再次引发时，显示不同的消息。</span><span class="sxs-lookup"><span data-stu-id="99664-164">When the event is raised again, a different message is displayed.</span></span>  
  
 <span data-ttu-id="99664-165">最后删除第二个事件处理程序，然后第三次引发此事件。</span><span class="sxs-lookup"><span data-stu-id="99664-165">Finally, the second event handler is removed and the event is raised for a third time.</span></span> <span data-ttu-id="99664-166">因为不再有事件处理程序与此事件相关联，所以不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="99664-166">Because there is no longer an event handler associated with the event, no action is taken.</span></span>  
  
 <span data-ttu-id="99664-167">[!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-167">[!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]</span></span>  
  
## <a name="handling-events-inherited-from-a-base-class"></a><span data-ttu-id="99664-168">处理继承自基类的事件</span><span class="sxs-lookup"><span data-stu-id="99664-168">Handling Events Inherited from a Base Class</span></span>  
 <span data-ttu-id="99664-169">*派生类*继承了基类特征的类，可以使用 `Handles``MyBase` 语句处理基类引发的事件。</span><span class="sxs-lookup"><span data-stu-id="99664-169">*Derived classes*—classes that inherit characteristics from a base class—can handle events raised by their base class using the `Handles``MyBase` statement.</span></span>  
  
#### <a name="to-handle-events-from-a-base-class"></a><span data-ttu-id="99664-170">处理继承自基类的事件的具体操作</span><span class="sxs-lookup"><span data-stu-id="99664-170">To handle events from a base class</span></span>  
  
-   <span data-ttu-id="99664-171">向事件处理程序过程的声明行添加 `Handles MyBase.` *eventname* 语句，在派生类中声明事件处理程序，其中 *eventname* 是要处理的继承自基类的事件名称。</span><span class="sxs-lookup"><span data-stu-id="99664-171">Declare an event handler in the derived class by adding a `Handles MyBase.`*eventname* statement to the declaration line of your event-handler procedure, where *eventname* is the name of the event in the base class you are handling.</span></span> <span data-ttu-id="99664-172">例如: </span><span class="sxs-lookup"><span data-stu-id="99664-172">For example:</span></span>  
  
     <span data-ttu-id="99664-173">[!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="99664-173">[!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="99664-174">相关章节</span><span class="sxs-lookup"><span data-stu-id="99664-174">Related Sections</span></span>  
  
|<span data-ttu-id="99664-175">标题</span><span class="sxs-lookup"><span data-stu-id="99664-175">Title</span></span>|<span data-ttu-id="99664-176">说明</span><span class="sxs-lookup"><span data-stu-id="99664-176">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="99664-177">演练：声明和引发事件</span><span class="sxs-lookup"><span data-stu-id="99664-177">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|<span data-ttu-id="99664-178">分步展示了如何声明和引发类事件。</span><span class="sxs-lookup"><span data-stu-id="99664-178">Provides a step-by-step description of how to declare and raise events for a class.</span></span>|  
|[<span data-ttu-id="99664-179">演练：处理事件</span><span class="sxs-lookup"><span data-stu-id="99664-179">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|<span data-ttu-id="99664-180">展示了如何编写事件处理程序过程。</span><span class="sxs-lookup"><span data-stu-id="99664-180">Demonstrates how to write an event-handler procedure.</span></span>|  
|[<span data-ttu-id="99664-181">如何：声明自定义事件以避免阻止</span><span class="sxs-lookup"><span data-stu-id="99664-181">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|<span data-ttu-id="99664-182">介绍了如何定义允许异步调用事件处理程序的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="99664-182">Demonstrates how to define a custom event that allows its event handlers to be called asynchronously.</span></span>|  
|[<span data-ttu-id="99664-183">如何：声明自定义事件以节省内存</span><span class="sxs-lookup"><span data-stu-id="99664-183">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|<span data-ttu-id="99664-184">介绍了如何定义仅在事件处理时占用内存的自定义事件。</span><span class="sxs-lookup"><span data-stu-id="99664-184">Demonstrates how to define a custom event that uses memory only when the event is handled.</span></span>|  
|[<span data-ttu-id="99664-185">Visual Basic 中继承的事件处理程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="99664-185">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|<span data-ttu-id="99664-186">列出了在继承的组件中使用事件处理程序时遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="99664-186">Lists common issues that arise with event handlers in inherited components.</span></span>|  
|[<span data-ttu-id="99664-187">事件</span><span class="sxs-lookup"><span data-stu-id="99664-187">Events</span></span>](../../../../standard/events/index.md)|<span data-ttu-id="99664-188">概述了 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中的事件模型。</span><span class="sxs-lookup"><span data-stu-id="99664-188">Provides an overview of the event model in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="99664-189">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="99664-189">Creating Event Handlers in Windows Forms</span></span>](https://msdn.microsoft.com/library/dacysss4.aspx)|<span data-ttu-id="99664-190">介绍了如何处理与 Windows 窗体对象关联的事件。</span><span class="sxs-lookup"><span data-stu-id="99664-190">Describes how to work with events associated with Windows Forms objects.</span></span>|  
|[<span data-ttu-id="99664-191">委托</span><span class="sxs-lookup"><span data-stu-id="99664-191">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)|<span data-ttu-id="99664-192">概述了 Visual Basic 中的委托。</span><span class="sxs-lookup"><span data-stu-id="99664-192">Provides an overview of delegates in Visual Basic.</span></span>|

