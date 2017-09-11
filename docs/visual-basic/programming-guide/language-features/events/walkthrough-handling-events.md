---
title: "处理事件 (Visual Basic 中) |Microsoft 文档"
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
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword, walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b4ad77b3b0236e762fc17b8aba9d34108c8d75b5
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="5a67b-102">演练：处理事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a67b-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="5a67b-103">这是演示如何处理事件的两个主题的第二个。</span><span class="sxs-lookup"><span data-stu-id="5a67b-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="5a67b-104">第一个主题，[演练︰ 声明和引发事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)，演示如何声明和引发事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="5a67b-105">本部分使用窗体和该演练中的类来说明如何处理时其发生的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="5a67b-106">`Widget`类的示例使用传统的事件处理语句。</span><span class="sxs-lookup"><span data-stu-id="5a67b-106">The `Widget` class example uses traditional event-handling statements.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="5a67b-107">提供用于处理事件的其他技术。</span><span class="sxs-lookup"><span data-stu-id="5a67b-107"> provides other techniques for working with events.</span></span> <span data-ttu-id="5a67b-108">作为一个练习，您可以修改该示例以使用`AddHandler`和`Handles`语句。</span><span class="sxs-lookup"><span data-stu-id="5a67b-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="5a67b-109">若要处理的小组件类 PercentDone 事件</span><span class="sxs-lookup"><span data-stu-id="5a67b-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="5a67b-110">将以下代码中的放置`Form1`:</span><span class="sxs-lookup"><span data-stu-id="5a67b-110">Place the following code in `Form1`:</span></span>  
  
     <span data-ttu-id="5a67b-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a67b-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span></span>  
  
     <span data-ttu-id="5a67b-112">`WithEvents`关键字指定变量`mWidget`用于处理对象的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-112">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="5a67b-113">通过提供从其创建对象的类的名称指定对象的类型。</span><span class="sxs-lookup"><span data-stu-id="5a67b-113">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="5a67b-114">该变量`mWidget`中声明`Form1`因为`WithEvents`变量必须是类级别。</span><span class="sxs-lookup"><span data-stu-id="5a67b-114">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="5a67b-115">这是类的您将它们放入的类型无关，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="5a67b-115">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="5a67b-116">该变量`mblnCancel`用于取消`LongTask`方法。</span><span class="sxs-lookup"><span data-stu-id="5a67b-116">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="5a67b-117">编写代码来处理事件</span><span class="sxs-lookup"><span data-stu-id="5a67b-117">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="5a67b-118">一旦您声明变量的使用`WithEvents`，变量名都会显示在左侧的下拉列表的类**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="5a67b-118">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="5a67b-119">当您选择`mWidget`、`Widget`右侧下拉列表中不显示类的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-119">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="5a67b-120">选择一个事件将显示对应的事件过程以前缀`mWidget`和一条下划线。</span><span class="sxs-lookup"><span data-stu-id="5a67b-120">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="5a67b-121">与相关联的所有事件过程`WithEvents`变量指定的变量名称作为前缀。</span><span class="sxs-lookup"><span data-stu-id="5a67b-121">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="5a67b-122">若要处理的事件</span><span class="sxs-lookup"><span data-stu-id="5a67b-122">To handle an event</span></span>  
  
1.  <span data-ttu-id="5a67b-123">选择`mWidget`从左侧的下拉列表中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="5a67b-123">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="5a67b-124">选择`PercentDone`右侧下拉列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-124">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="5a67b-125">**代码编辑器**打开`mWidget_PercentDone`事件过程。</span><span class="sxs-lookup"><span data-stu-id="5a67b-125">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a67b-126">**代码编辑器**很有用，但并不是必需的插入新的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5a67b-126">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="5a67b-127">在本演练中，就更直接，只是事件处理程序将直接复制到您的代码。</span><span class="sxs-lookup"><span data-stu-id="5a67b-127">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="5a67b-128">将以下代码添加到 `mWidget_PercentDone` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="5a67b-128">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     <span data-ttu-id="5a67b-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a67b-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span></span>  
  
     <span data-ttu-id="5a67b-130">每当`PercentDone`引发事件、 事件过程中显示在完成百分比`Label`控件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-130">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="5a67b-131">`DoEvents`方法允许标签来重绘，并且还为用户提供机会单击**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="5a67b-131">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="5a67b-132">添加以下代码为`Button2_Click`事件处理程序︰</span><span class="sxs-lookup"><span data-stu-id="5a67b-132">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     <span data-ttu-id="5a67b-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&6;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a67b-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span></span>  
  
 <span data-ttu-id="5a67b-134">如果用户单击**取消**按钮`LongTask`运行的，`Button2_Click`执行事件就立即`DoEvents`语句允许发生的事件处理。</span><span class="sxs-lookup"><span data-stu-id="5a67b-134">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="5a67b-135">类级变量`mblnCancel`设置为`True`，和`mWidget_PercentDone`事件然后测试它，并将`ByRef Cancel`参数`True`。</span><span class="sxs-lookup"><span data-stu-id="5a67b-135">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="5a67b-136">连接到一个对象的 WithEvents 变量</span><span class="sxs-lookup"><span data-stu-id="5a67b-136">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="5a67b-137">`Form1`现在已设置好处理`Widget`对象的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-137">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="5a67b-138">剩下的就是要查找`Widget`某个位置。</span><span class="sxs-lookup"><span data-stu-id="5a67b-138">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="5a67b-139">当您声明一个变量`WithEvents`在设计时，没有对象，则与之相关联。</span><span class="sxs-lookup"><span data-stu-id="5a67b-139">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="5a67b-140">一个`WithEvents`变量是就像任何其他对象变量一样。</span><span class="sxs-lookup"><span data-stu-id="5a67b-140">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="5a67b-141">您必须创建一个对象，并为其分配一个引用`WithEvents`变量。</span><span class="sxs-lookup"><span data-stu-id="5a67b-141">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="5a67b-142">若要创建一个对象，并为其分配一个引用</span><span class="sxs-lookup"><span data-stu-id="5a67b-142">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="5a67b-143">选择**（form1 事件）**从左侧的下拉列表中**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="5a67b-143">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="5a67b-144">选择`Load`右侧下拉列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-144">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="5a67b-145">**代码编辑器**打开`Form1_Load`事件过程。</span><span class="sxs-lookup"><span data-stu-id="5a67b-145">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="5a67b-146">添加以下代码为`Form1_Load`事件过程中以创建`Widget`:</span><span class="sxs-lookup"><span data-stu-id="5a67b-146">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     <span data-ttu-id="5a67b-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a67b-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span></span>  
  
 <span data-ttu-id="5a67b-148">此代码执行时，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]创建`Widget`对象，并将其事件连接到与关联的事件过程`mWidget`。</span><span class="sxs-lookup"><span data-stu-id="5a67b-148">When this code executes, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="5a67b-149">自此以后，每当`Widget`引发其`PercentDone`事件，`mWidget_PercentDone`事件过程中执行。</span><span class="sxs-lookup"><span data-stu-id="5a67b-149">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="5a67b-150">若要调用 LongTask 方法</span><span class="sxs-lookup"><span data-stu-id="5a67b-150">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="5a67b-151">将以下代码添加到 `Button1_Click` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="5a67b-151">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     <span data-ttu-id="5a67b-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a67b-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span></span>  
  
 <span data-ttu-id="5a67b-153">之前`LongTask`标签，显示完成百分比必须进行初始化，并且类级别调用方法`Boolean`标志取消该方法必须设置为`False`。</span><span class="sxs-lookup"><span data-stu-id="5a67b-153">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="5a67b-154">`LongTask`被调用，任务持续时间为 12.2 秒。</span><span class="sxs-lookup"><span data-stu-id="5a67b-154">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="5a67b-155">`PercentDone`事件引发一次每&1; /&3; 的第二个。</span><span class="sxs-lookup"><span data-stu-id="5a67b-155">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="5a67b-156">引发事件时，每次`mWidget_PercentDone`事件过程中执行。</span><span class="sxs-lookup"><span data-stu-id="5a67b-156">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="5a67b-157">当`LongTask`操作后，`mblnCancel`测试以查看是否`LongTask`正常结束，或者如果它已停止，因为`mblnCancel`已设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="5a67b-157">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="5a67b-158">仅在前一种情况中将更新的完成百分比。</span><span class="sxs-lookup"><span data-stu-id="5a67b-158">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="5a67b-159">运行程序</span><span class="sxs-lookup"><span data-stu-id="5a67b-159">To run the program</span></span>  
  
1.  <span data-ttu-id="5a67b-160">按 f5 键以将项目放在运行模式下。</span><span class="sxs-lookup"><span data-stu-id="5a67b-160">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="5a67b-161">单击**启动任务**按钮。</span><span class="sxs-lookup"><span data-stu-id="5a67b-161">Click the **Start Task** button.</span></span> <span data-ttu-id="5a67b-162">每次`PercentDone`引发事件，标签已更新为包含任务已完成的百分比。</span><span class="sxs-lookup"><span data-stu-id="5a67b-162">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="5a67b-163">单击**取消**按钮以停止该任务。</span><span class="sxs-lookup"><span data-stu-id="5a67b-163">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="5a67b-164">请注意，外观的**取消**按钮并不立即单击时更改。</span><span class="sxs-lookup"><span data-stu-id="5a67b-164">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="5a67b-165">`Click`才会发生直到`My.Application.DoEvents`语句允许事件处理。</span><span class="sxs-lookup"><span data-stu-id="5a67b-165">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a67b-166">`My.Application.DoEvents`窗体一样方法不完全相同的方式处理事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-166">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="5a67b-167">例如，在本演练中，您必须单击**取消**按钮两次。</span><span class="sxs-lookup"><span data-stu-id="5a67b-167">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="5a67b-168">若要使表单能够直接处理事件，可以使用多线程处理。</span><span class="sxs-lookup"><span data-stu-id="5a67b-168">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="5a67b-169">有关详细信息，请参阅[线程处理](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)。</span><span class="sxs-lookup"><span data-stu-id="5a67b-169">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="5a67b-170">您可能会发现有意义，按 f11 键运行该程序，并单步执行代码行一次。</span><span class="sxs-lookup"><span data-stu-id="5a67b-170">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="5a67b-171">您可以清楚地看到如何执行进入`LongTask`，，然后简要重新进入`Form1`每次`PercentDone`引发事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-171">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="5a67b-172">会发生什么情况如果，在执行过程中的代码返回`Form1`、`LongTask`方法再次被调用？</span><span class="sxs-lookup"><span data-stu-id="5a67b-172">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="5a67b-173">如果堆栈溢出可能会出现最坏的情形，`LongTask`每次引发事件时调用。</span><span class="sxs-lookup"><span data-stu-id="5a67b-173">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="5a67b-174">您可能会导致该变量`mWidget`来处理另一个事件`Widget`对象的引用赋给新`Widget`到`mWidget`。</span><span class="sxs-lookup"><span data-stu-id="5a67b-174">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="5a67b-175">事实上，您可以在代码`Button1_Click`每次单击按钮时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5a67b-175">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="5a67b-176">若要处理不同的小组件的事件</span><span class="sxs-lookup"><span data-stu-id="5a67b-176">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="5a67b-177">添加下面的代码行`Button1_Click`过程中，紧靠前读取的行`mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="5a67b-177">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     <span data-ttu-id="5a67b-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&9;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a67b-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span></span>  
  
 <span data-ttu-id="5a67b-179">上面的代码创建一个新`Widget`每次单击按钮。</span><span class="sxs-lookup"><span data-stu-id="5a67b-179">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="5a67b-180">只要`LongTask`方法完成后，对引用`Widget`发布后，与`Widget`被销毁。</span><span class="sxs-lookup"><span data-stu-id="5a67b-180">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="5a67b-181">一个`WithEvents`变量可以包含只有一个对象引用，一次，因此，如果您分配一个不同`Widget`对象传递给`mWidget`上, 一个`Widget`将不再处理对象的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-181">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="5a67b-182">如果`mWidget`是唯一包含对旧的引用的对象变量`Widget`，该对象被销毁。</span><span class="sxs-lookup"><span data-stu-id="5a67b-182">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="5a67b-183">如果你想要处理来自多个事件`Widget`对象，请使用`AddHandler`语句，以分别处理每个对象的事件。</span><span class="sxs-lookup"><span data-stu-id="5a67b-183">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a67b-184">您可以声明任意多个`WithEvents`需要作为您的变量，但数组`WithEvents`不支持变量。</span><span class="sxs-lookup"><span data-stu-id="5a67b-184">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a67b-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a67b-185">See Also</span></span>  
 <span data-ttu-id="5a67b-186">[演练︰ 声明和引发事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span><span class="sxs-lookup"><span data-stu-id="5a67b-186">[Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span></span>  
<span data-ttu-id="5a67b-187"> [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="5a67b-187"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
