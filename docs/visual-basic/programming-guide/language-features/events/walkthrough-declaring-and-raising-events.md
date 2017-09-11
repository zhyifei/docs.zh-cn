---
title: "声明和引发事件 (Visual Basic 中) |Microsoft 文档"
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
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
ms.openlocfilehash: eca112aca39bd998697d379a1705845e8f607367
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="14307-102">演练：声明和引发事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14307-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="14307-103">本演练演示如何声明和引发事件的一个名为类`Widget`。</span><span class="sxs-lookup"><span data-stu-id="14307-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="14307-104">完成步骤后，您可能需要阅读的配套主题，[演练︰ 处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)，它演示如何使用来自事件`Widget`对象提供应用程序中的状态信息。</span><span class="sxs-lookup"><span data-stu-id="14307-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="14307-105">小组件类</span><span class="sxs-lookup"><span data-stu-id="14307-105">The Widget Class</span></span>  
 <span data-ttu-id="14307-106">假定您有目前`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="14307-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="14307-107">您`Widget`类具有方法会很长时间才能执行，并且您希望您的应用程序能够提供某种进度指示器。</span><span class="sxs-lookup"><span data-stu-id="14307-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="14307-108">当然，你可以制作`Widget`对象会显示完成百分比的对话框中，但这样您将会使用在其中每个项目在该对话框`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="14307-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="14307-109">一个好的对象的设计原则是让使用对象句柄的用户界面的应用程序，除非该对象的总体目的就是管理表单或对话框。</span><span class="sxs-lookup"><span data-stu-id="14307-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="14307-110">用途`Widget`是执行其他任务，所以最好添加`PercentDone`事件并让调用的过程`Widget`方法的处理事件和显示状态更新。</span><span class="sxs-lookup"><span data-stu-id="14307-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="14307-111">`PercentDone`事件还可以提供用于取消该任务的机制。</span><span class="sxs-lookup"><span data-stu-id="14307-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="14307-112">若要生成本主题的代码示例</span><span class="sxs-lookup"><span data-stu-id="14307-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="14307-113">打开一个新[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Windows 应用程序项目，然后创建名为窗体`Form1`。</span><span class="sxs-lookup"><span data-stu-id="14307-113">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="14307-114">添加两个按钮和标签与`Form1`。</span><span class="sxs-lookup"><span data-stu-id="14307-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="14307-115">下表中所示命名对象。</span><span class="sxs-lookup"><span data-stu-id="14307-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="14307-116">对象</span><span class="sxs-lookup"><span data-stu-id="14307-116">Object</span></span>|<span data-ttu-id="14307-117">属性</span><span class="sxs-lookup"><span data-stu-id="14307-117">Property</span></span>|<span data-ttu-id="14307-118">设置</span><span class="sxs-lookup"><span data-stu-id="14307-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="14307-119">启动任务</span><span class="sxs-lookup"><span data-stu-id="14307-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="14307-120">取消</span><span class="sxs-lookup"><span data-stu-id="14307-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="14307-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="14307-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="14307-122">lblPercentDone 0</span><span class="sxs-lookup"><span data-stu-id="14307-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="14307-123">在**项目**菜单上，选择**添加类**添加一个名为类`Widget.vb`到项目。</span><span class="sxs-lookup"><span data-stu-id="14307-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="14307-124">若要声明构件类的事件</span><span class="sxs-lookup"><span data-stu-id="14307-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="14307-125">使用`Event`关键字来声明中的事件`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="14307-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="14307-126">请注意，一个事件可以有`ByVal`和`ByRef`参数，为`Widget`的`PercentDone`事件所示︰</span><span class="sxs-lookup"><span data-stu-id="14307-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     <span data-ttu-id="14307-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&1;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="14307-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span></span>  
  
 <span data-ttu-id="14307-128">当调用对象收到`PercentDone`事件，`Percent`参数中包含的任务已完成的百分比。</span><span class="sxs-lookup"><span data-stu-id="14307-128">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="14307-129">`Cancel`参数可以设置为`True`取消引发该事件的方法。</span><span class="sxs-lookup"><span data-stu-id="14307-129">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14307-130">您可以声明事件参数，就像参数的过程，但存在以下例外︰ 事件不能有`Optional`或`ParamArray`参数，且事件不具有返回值。</span><span class="sxs-lookup"><span data-stu-id="14307-130">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="14307-131">`PercentDone`事件由引发`LongTask`方法`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="14307-131">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="14307-132">`LongTask`采用两个参数︰ 该方法自称要工作和之前的最小时间间隔的时间长度`LongTask`暂停以引发`PercentDone`事件。</span><span class="sxs-lookup"><span data-stu-id="14307-132">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="14307-133">若要引发 PercentDone 事件</span><span class="sxs-lookup"><span data-stu-id="14307-133">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="14307-134">若要简化对访问`Timer`此类使用的属性添加`Imports`到您的类模块的声明部分顶部的语句上方`Class Widget`语句。</span><span class="sxs-lookup"><span data-stu-id="14307-134">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     <span data-ttu-id="14307-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="14307-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span></span>  
  
2.  <span data-ttu-id="14307-136">将下面的代码添加到 `Widget` 类中:</span><span class="sxs-lookup"><span data-stu-id="14307-136">Add the following code to the `Widget` class:</span></span>  
  
     <span data-ttu-id="14307-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="14307-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span></span>  
  
 <span data-ttu-id="14307-138">当您的应用程序调用`LongTask`方法，`Widget`类引发`PercentDone`事件每个`MinimumInterval`秒为单位。</span><span class="sxs-lookup"><span data-stu-id="14307-138">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="14307-139">该事件返回时，`LongTask`检查以查看是否`Cancel`参数设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="14307-139">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="14307-140">此处有必要的几个免责声明。</span><span class="sxs-lookup"><span data-stu-id="14307-140">A few disclaimers are necessary here.</span></span> <span data-ttu-id="14307-141">为简单起见，`LongTask`过程假定您事先知道任务将花费多长时间。</span><span class="sxs-lookup"><span data-stu-id="14307-141">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="14307-142">这几乎不会是这种情况。</span><span class="sxs-lookup"><span data-stu-id="14307-142">This is almost never the case.</span></span> <span data-ttu-id="14307-143">将任务划分为大小相等的块区可能很困难，且通常最重要的事情向用户只需在获得的内容不会进行的指示之前经过的时间量。</span><span class="sxs-lookup"><span data-stu-id="14307-143">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="14307-144">您可能已经发现了另一个缺陷在此示例中。</span><span class="sxs-lookup"><span data-stu-id="14307-144">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="14307-145">`Timer`属性返回的自午夜以来经过的秒数; 因此，应用程序何故停止响应如果只是在午夜之前启动。</span><span class="sxs-lookup"><span data-stu-id="14307-145">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="14307-146">更仔细的测量时间的方法将执行如下考虑在内，边界条件或根本不用它们，如使用属性`Now`。</span><span class="sxs-lookup"><span data-stu-id="14307-146">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="14307-147">现在，`Widget`类可引发事件，您可以将移动到下一个演练。</span><span class="sxs-lookup"><span data-stu-id="14307-147">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="14307-148">[演练︰ 处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)演示如何使用`WithEvents`将与一个事件处理程序相关联`PercentDone`事件。</span><span class="sxs-lookup"><span data-stu-id="14307-148">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14307-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14307-149">See Also</span></span>  
 <span data-ttu-id="14307-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span><span class="sxs-lookup"><span data-stu-id="14307-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span></span>   
 <span data-ttu-id="14307-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="14307-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span></span>   
<span data-ttu-id="14307-152"> [演练︰ 处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span><span class="sxs-lookup"><span data-stu-id="14307-152"> [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span></span>  
<span data-ttu-id="14307-153"> [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="14307-153"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
