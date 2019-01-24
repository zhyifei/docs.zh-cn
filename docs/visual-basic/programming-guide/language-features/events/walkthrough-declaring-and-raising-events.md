---
title: 声明和引发事件 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: f792109f1d1117b5b112e06da1510938e4b8a5ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580484"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="23c74-102">演练：声明和引发事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23c74-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="23c74-103">本演练演示如何声明和引发事件的类名为`Widget`。</span><span class="sxs-lookup"><span data-stu-id="23c74-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="23c74-104">完成步骤后，你可能想要读取的配套主题，[演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)，其中说明了如何使用从事件`Widget`对象提供的应用程序中的状态信息。</span><span class="sxs-lookup"><span data-stu-id="23c74-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="23c74-105">小组件类</span><span class="sxs-lookup"><span data-stu-id="23c74-105">The Widget Class</span></span>  
 <span data-ttu-id="23c74-106">假定您有目前`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="23c74-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="23c74-107">你`Widget`类有一个方法，可能需要很长时间才能执行，并且希望你的应用程序要能够提供某种进度指示器。</span><span class="sxs-lookup"><span data-stu-id="23c74-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="23c74-108">当然，您可以制作`Widget`对象显示完成百分比的对话框中，但这样您将会使用该对话框中，在您使用的每个项目`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="23c74-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="23c74-109">好的对象设计原则是让使用对象句柄的用户界面的应用程序，除非该对象的总体目的就是管理窗体或对话框。</span><span class="sxs-lookup"><span data-stu-id="23c74-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="23c74-110">目的`Widget`是执行其他任务，所以最好添加`PercentDone`事件并让调用该过程`Widget`的方法处理事件和显示状态更新。</span><span class="sxs-lookup"><span data-stu-id="23c74-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="23c74-111">`PercentDone`事件还可以提供用于取消该任务的机制。</span><span class="sxs-lookup"><span data-stu-id="23c74-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="23c74-112">若要生成本主题的代码示例</span><span class="sxs-lookup"><span data-stu-id="23c74-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="23c74-113">打开一个新的 Visual Basic Windows 应用程序项目，并创建名为的`Form1`。</span><span class="sxs-lookup"><span data-stu-id="23c74-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="23c74-114">添加两个按钮和标签与`Form1`。</span><span class="sxs-lookup"><span data-stu-id="23c74-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="23c74-115">按下表所示命名对象。</span><span class="sxs-lookup"><span data-stu-id="23c74-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="23c74-116">对象</span><span class="sxs-lookup"><span data-stu-id="23c74-116">Object</span></span>|<span data-ttu-id="23c74-117">属性</span><span class="sxs-lookup"><span data-stu-id="23c74-117">Property</span></span>|<span data-ttu-id="23c74-118">设置</span><span class="sxs-lookup"><span data-stu-id="23c74-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="23c74-119">启动任务</span><span class="sxs-lookup"><span data-stu-id="23c74-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="23c74-120">取消</span><span class="sxs-lookup"><span data-stu-id="23c74-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="23c74-121">`(Name)`， `Text`</span><span class="sxs-lookup"><span data-stu-id="23c74-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="23c74-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="23c74-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="23c74-123">上**项目**菜单中，选择**添加类**若要添加一个名为类`Widget.vb`到项目。</span><span class="sxs-lookup"><span data-stu-id="23c74-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="23c74-124">若要声明的小组件类的事件</span><span class="sxs-lookup"><span data-stu-id="23c74-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="23c74-125">使用`Event`关键字来声明中的事件`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="23c74-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="23c74-126">请注意，事件可以具有`ByVal`并`ByRef`自变量，作为`Widget`的`PercentDone`事件所示：</span><span class="sxs-lookup"><span data-stu-id="23c74-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 <span data-ttu-id="23c74-127">当调用的对象收到`PercentDone`事件，`Percent`参数中包含的任务已完成的百分比。</span><span class="sxs-lookup"><span data-stu-id="23c74-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="23c74-128">`Cancel`参数可以设置为`True`取消引发该事件的方法。</span><span class="sxs-lookup"><span data-stu-id="23c74-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23c74-129">您可以声明事件自变量，就像您处理过程，但存在以下例外的：事件不能有`Optional`或`ParamArray`参数，且事件不具有返回值。</span><span class="sxs-lookup"><span data-stu-id="23c74-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="23c74-130">`PercentDone`引发事件`LongTask`方法的`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="23c74-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="23c74-131">`LongTask` 采用两个参数： 要执行的工作和之前的最小时间间隔的时间长度方法伪装`LongTask`暂停以引发`PercentDone`事件。</span><span class="sxs-lookup"><span data-stu-id="23c74-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="23c74-132">若要引发 PercentDone 事件</span><span class="sxs-lookup"><span data-stu-id="23c74-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="23c74-133">以简化对访问`Timer`使用此类的属性添加`Imports`的类模块中，声明部分顶部的语句上方`Class Widget`语句。</span><span class="sxs-lookup"><span data-stu-id="23c74-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  <span data-ttu-id="23c74-134">将下面的代码添加到 `Widget` 类中:</span><span class="sxs-lookup"><span data-stu-id="23c74-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 <span data-ttu-id="23c74-135">当应用程序调用`LongTask`方法，`Widget`类所引发`PercentDone`事件每个`MinimumInterval`秒。</span><span class="sxs-lookup"><span data-stu-id="23c74-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="23c74-136">该事件在返回时，`LongTask`检查以查看是否`Cancel`参数设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="23c74-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="23c74-137">一些免责声明此处是必需的。</span><span class="sxs-lookup"><span data-stu-id="23c74-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="23c74-138">为简单起见，`LongTask`过程假定您事先知道该任务将花费多长时间。</span><span class="sxs-lookup"><span data-stu-id="23c74-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="23c74-139">这几乎不会是这种情况。</span><span class="sxs-lookup"><span data-stu-id="23c74-139">This is almost never the case.</span></span> <span data-ttu-id="23c74-140">将任务分割成大小相等的区块可能很困难，并且通常最重要的内容的用户只需在获得发生了某些内容的指示之前经过的时间量。</span><span class="sxs-lookup"><span data-stu-id="23c74-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="23c74-141">您可能已经发现了另一个缺陷在此示例中。</span><span class="sxs-lookup"><span data-stu-id="23c74-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="23c74-142">`Timer`属性返回的自午夜以来经过的秒数; 因此，应用程序时遇到困难如果只是在午夜之前启动。</span><span class="sxs-lookup"><span data-stu-id="23c74-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="23c74-143">更仔细的测量时间方法会采用边界条件，例如此纳入考虑范围，或根本不用它们，如使用属性`Now`。</span><span class="sxs-lookup"><span data-stu-id="23c74-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="23c74-144">现在，`Widget`类可以引发事件，您可以将移动到下一个演练。</span><span class="sxs-lookup"><span data-stu-id="23c74-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="23c74-145">[演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)演示了如何使用`WithEvents`关联的事件处理程序`PercentDone`事件。</span><span class="sxs-lookup"><span data-stu-id="23c74-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c74-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="23c74-146">See also</span></span>
- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="23c74-147">演练：处理事件</span><span class="sxs-lookup"><span data-stu-id="23c74-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="23c74-148">事件</span><span class="sxs-lookup"><span data-stu-id="23c74-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
