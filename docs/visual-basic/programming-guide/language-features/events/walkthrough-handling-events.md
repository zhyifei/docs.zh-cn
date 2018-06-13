---
title: 处理事件 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 0ac3514505ca42870d77317feec30a27e4384e6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655109"
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="e77ab-102">演练：处理事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e77ab-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="e77ab-103">这是演示如何使用事件的两个主题的第二个。</span><span class="sxs-lookup"><span data-stu-id="e77ab-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="e77ab-104">第一个主题，[演练： 声明和引发事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)，演示如何声明和引发事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="e77ab-105">本部分使用的窗体和该演练中的类以显示如何处理事件发生时。</span><span class="sxs-lookup"><span data-stu-id="e77ab-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="e77ab-106">`Widget`类的示例使用传统的事件处理语句。</span><span class="sxs-lookup"><span data-stu-id="e77ab-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="e77ab-107">Visual Basic 提供用于处理事件的其他技术。</span><span class="sxs-lookup"><span data-stu-id="e77ab-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="e77ab-108">作为练习，您可以修改此示例以使用`AddHandler`和`Handles`语句。</span><span class="sxs-lookup"><span data-stu-id="e77ab-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="e77ab-109">若要处理的 PercentDone 事件的小组件类</span><span class="sxs-lookup"><span data-stu-id="e77ab-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="e77ab-110">将以下代码中的`Form1`:</span><span class="sxs-lookup"><span data-stu-id="e77ab-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     <span data-ttu-id="e77ab-111">`WithEvents`关键字指定变量`mWidget`用于处理对象的事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="e77ab-112">提供将从其创建对象的类名称指定的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="e77ab-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="e77ab-113">变量`mWidget`中声明`Form1`因为`WithEvents`变量必须是类级。</span><span class="sxs-lookup"><span data-stu-id="e77ab-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="e77ab-114">这是 true 而不考虑你将其放置在类的类型。</span><span class="sxs-lookup"><span data-stu-id="e77ab-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="e77ab-115">变量`mblnCancel`用于取消`LongTask`方法。</span><span class="sxs-lookup"><span data-stu-id="e77ab-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="e77ab-116">编写代码来处理事件</span><span class="sxs-lookup"><span data-stu-id="e77ab-116">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="e77ab-117">声明变量的使用时，就会立即`WithEvents`，变量的名称将显示在左侧的下拉列表的类的**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e77ab-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="e77ab-118">当选择`mWidget`、`Widget`类的事件将出现在右侧下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e77ab-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="e77ab-119">选择一个事件将显示相应的事件过程，以前缀`mWidget`和一条下划线。</span><span class="sxs-lookup"><span data-stu-id="e77ab-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="e77ab-120">与关联的所有事件过程`WithEvents`变量提供变量的名称，作为前缀。</span><span class="sxs-lookup"><span data-stu-id="e77ab-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="e77ab-121">若要处理的事件</span><span class="sxs-lookup"><span data-stu-id="e77ab-121">To handle an event</span></span>  
  
1.  <span data-ttu-id="e77ab-122">选择`mWidget`从左侧的下拉列表中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e77ab-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="e77ab-123">选择`PercentDone`从右侧下拉列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="e77ab-124">**代码编辑器**打开`mWidget_PercentDone`事件过程。</span><span class="sxs-lookup"><span data-stu-id="e77ab-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e77ab-125">**代码编辑器**很有用，但不是必需，用于插入新的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e77ab-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="e77ab-126">在本演练中，很多直接，只需的事件处理程序将直接复制到你的代码。</span><span class="sxs-lookup"><span data-stu-id="e77ab-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="e77ab-127">将以下代码添加到 `mWidget_PercentDone` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="e77ab-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     <span data-ttu-id="e77ab-128">每当`PercentDone`引发事件，事件过程会显示在完成百分比`Label`控件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="e77ab-129">`DoEvents`方法允许重新绘制标签，并且还为用户提供机会单击**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="e77ab-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="e77ab-130">添加以下代码`Button2_Click`事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="e77ab-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 <span data-ttu-id="e77ab-131">如果用户单击**取消**时的按钮`LongTask`正在运行，`Button2_Click`执行事件就会立即`DoEvents`语句允许发生的事件处理。</span><span class="sxs-lookup"><span data-stu-id="e77ab-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="e77ab-132">类级变量`mblnCancel`设置为`True`，和`mWidget_PercentDone`事件然后测试它，并设置`ByRef Cancel`参数`True`。</span><span class="sxs-lookup"><span data-stu-id="e77ab-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="e77ab-133">连接到一个对象的 WithEvents 变量</span><span class="sxs-lookup"><span data-stu-id="e77ab-133">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="e77ab-134">`Form1` 现在已设置好处理`Widget`对象的事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="e77ab-135">剩下的就是查找`Widget`某个位置。</span><span class="sxs-lookup"><span data-stu-id="e77ab-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="e77ab-136">当你声明一个变量`WithEvents`在设计时，没有对象，则与之关联。</span><span class="sxs-lookup"><span data-stu-id="e77ab-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="e77ab-137">A`WithEvents`变量是就像任何其他对象变量一样。</span><span class="sxs-lookup"><span data-stu-id="e77ab-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="e77ab-138">你必须创建一个对象，并为其分配引用与`WithEvents`变量。</span><span class="sxs-lookup"><span data-stu-id="e77ab-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="e77ab-139">若要创建一个对象，并分配对它的引用</span><span class="sxs-lookup"><span data-stu-id="e77ab-139">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="e77ab-140">选择 **（Form1 事件）** 从左侧的下拉列表中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="e77ab-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="e77ab-141">选择`Load`从右侧下拉列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="e77ab-142">**代码编辑器**打开`Form1_Load`事件过程。</span><span class="sxs-lookup"><span data-stu-id="e77ab-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="e77ab-143">添加以下代码`Form1_Load`事件过程中以创建`Widget`:</span><span class="sxs-lookup"><span data-stu-id="e77ab-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 <span data-ttu-id="e77ab-144">在此代码的执行，Visual Basic 创建`Widget`对象，并将其事件连接到与关联的事件过程`mWidget`。</span><span class="sxs-lookup"><span data-stu-id="e77ab-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="e77ab-145">自此以后，每当`Widget`引发其`PercentDone`事件，`mWidget_PercentDone`执行事件过程。</span><span class="sxs-lookup"><span data-stu-id="e77ab-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="e77ab-146">若要调用 LongTask 方法</span><span class="sxs-lookup"><span data-stu-id="e77ab-146">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="e77ab-147">将以下代码添加到 `Button1_Click` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="e77ab-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 <span data-ttu-id="e77ab-148">之前`LongTask`调用方法时，标签，必须初始化的显示完成百分比和类级别`Boolean`标志取消方法必须设置为`False`。</span><span class="sxs-lookup"><span data-stu-id="e77ab-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="e77ab-149">`LongTask` 已调用 12.2 秒任务持续时间。</span><span class="sxs-lookup"><span data-stu-id="e77ab-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="e77ab-150">`PercentDone`引发事件一次每 1 / 3 的第二个。</span><span class="sxs-lookup"><span data-stu-id="e77ab-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="e77ab-151">引发事件时，每次`mWidget_PercentDone`执行事件过程。</span><span class="sxs-lookup"><span data-stu-id="e77ab-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="e77ab-152">当`LongTask`完成操作后，`mblnCancel`测试以查看是否`LongTask`正常结束，或如果它停止，因为`mblnCancel`已设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="e77ab-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="e77ab-153">仅在前一种情况中，会更新完成百分比。</span><span class="sxs-lookup"><span data-stu-id="e77ab-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="e77ab-154">运行程序</span><span class="sxs-lookup"><span data-stu-id="e77ab-154">To run the program</span></span>  
  
1.  <span data-ttu-id="e77ab-155">按 F5，将在运行模式下的项目。</span><span class="sxs-lookup"><span data-stu-id="e77ab-155">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="e77ab-156">单击**启动任务**按钮。</span><span class="sxs-lookup"><span data-stu-id="e77ab-156">Click the **Start Task** button.</span></span> <span data-ttu-id="e77ab-157">每次`PercentDone`引发事件，标签更新与任务已完成的百分比。</span><span class="sxs-lookup"><span data-stu-id="e77ab-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="e77ab-158">单击**取消**按钮以停止该任务。</span><span class="sxs-lookup"><span data-stu-id="e77ab-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="e77ab-159">请注意的外观**取消**按钮不会更改立即当您单击的位置。</span><span class="sxs-lookup"><span data-stu-id="e77ab-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="e77ab-160">`Click`事件不会发生直到`My.Application.DoEvents`语句允许事件处理。</span><span class="sxs-lookup"><span data-stu-id="e77ab-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e77ab-161">`My.Application.DoEvents`窗体一样方法不完全相同的方式中处理事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="e77ab-162">例如，在本演练中，你必须单击**取消**按钮两次。</span><span class="sxs-lookup"><span data-stu-id="e77ab-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="e77ab-163">若要使表单能够直接处理事件，可以使用多线程处理。</span><span class="sxs-lookup"><span data-stu-id="e77ab-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="e77ab-164">有关详细信息，请参阅[线程处理](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)。</span><span class="sxs-lookup"><span data-stu-id="e77ab-164">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="e77ab-165">您可能发现很有益按 f11 键运行程序并单步执行代码行一次。</span><span class="sxs-lookup"><span data-stu-id="e77ab-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="e77ab-166">你可以清楚地了解如何执行进入`LongTask`，，然后简要重新进入`Form1`每次`PercentDone`引发事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="e77ab-167">会发生什么情况如果是，在执行过程中的代码返回`Form1`、`LongTask`再次调用方法？</span><span class="sxs-lookup"><span data-stu-id="e77ab-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="e77ab-168">如果在坏的情况下，可能发生堆栈溢出`LongTask`每次引发事件时调用。</span><span class="sxs-lookup"><span data-stu-id="e77ab-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="e77ab-169">你可能会导致变量`mWidget`来处理另一个事件`Widget`对象的引用赋给新`Widget`到`mWidget`。</span><span class="sxs-lookup"><span data-stu-id="e77ab-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="e77ab-170">事实上，你可以在代码`Button1_Click`每次单击按钮时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e77ab-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="e77ab-171">若要处理不同的小组件的事件</span><span class="sxs-lookup"><span data-stu-id="e77ab-171">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="e77ab-172">添加以下代码的行`Button1_Click`过程中，读取的行的上一页`mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="e77ab-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 <span data-ttu-id="e77ab-173">上面的代码创建一个新`Widget`每次单击按钮。</span><span class="sxs-lookup"><span data-stu-id="e77ab-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="e77ab-174">只要`LongTask`方法完成时，对引用`Widget`发布后，与`Widget`被销毁。</span><span class="sxs-lookup"><span data-stu-id="e77ab-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="e77ab-175">A`WithEvents`变量可以包含一个对象引用，一次，因此，如果您分配一个不同`Widget`对象传递给`mWidget`上, 一个`Widget`对象的事件将无法再进行处理。</span><span class="sxs-lookup"><span data-stu-id="e77ab-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="e77ab-176">如果`mWidget`是唯一的对象变量包含对旧的引用`Widget`，对象被销毁。</span><span class="sxs-lookup"><span data-stu-id="e77ab-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="e77ab-177">如果你想要处理来自多个事件`Widget`对象，请使用`AddHandler`语句来单独处理从每个对象的事件。</span><span class="sxs-lookup"><span data-stu-id="e77ab-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e77ab-178">你可以声明任意多个`WithEvents`需要为你的变量，但数组`WithEvents`不支持变量。</span><span class="sxs-lookup"><span data-stu-id="e77ab-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77ab-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="e77ab-179">See Also</span></span>  
 [<span data-ttu-id="e77ab-180">演练：声明和引发事件</span><span class="sxs-lookup"><span data-stu-id="e77ab-180">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [<span data-ttu-id="e77ab-181">事件</span><span class="sxs-lookup"><span data-stu-id="e77ab-181">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
