---
title: 声明和引发事件
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345092"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="0836a-102">演练：声明和引发事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0836a-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="0836a-103">本演练演示如何为名为 `Widget`的类声明和引发事件。</span><span class="sxs-lookup"><span data-stu-id="0836a-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="0836a-104">完成这些步骤后，你可能需要阅读相关主题[演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)，其中显示了如何使用 `Widget` 对象中的事件来提供应用程序中的状态信息。</span><span class="sxs-lookup"><span data-stu-id="0836a-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="0836a-105">小组件类</span><span class="sxs-lookup"><span data-stu-id="0836a-105">The Widget Class</span></span>  
 <span data-ttu-id="0836a-106">假设你有一个 `Widget` 类。</span><span class="sxs-lookup"><span data-stu-id="0836a-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="0836a-107">您的 `Widget` 类有一个可能需要很长时间才能执行的方法，并且您希望您的应用程序能够提供某种类型的完成指示器。</span><span class="sxs-lookup"><span data-stu-id="0836a-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="0836a-108">当然，您可以使 `Widget` 对象显示一个百分比完成对话框，但随后在您使用 `Widget` 类的每个项目中都将出现该对话框。</span><span class="sxs-lookup"><span data-stu-id="0836a-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="0836a-109">对象设计的一个很好的原则是让使用对象的应用程序处理用户界面，除非对象的全部用途是管理窗体或对话框。</span><span class="sxs-lookup"><span data-stu-id="0836a-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="0836a-110">`Widget` 的目的是执行其他任务，因此最好添加 `PercentDone` 事件，并让调用 `Widget`的方法的过程处理该事件并显示状态更新。</span><span class="sxs-lookup"><span data-stu-id="0836a-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="0836a-111">`PercentDone` 事件还可以提供取消任务的机制。</span><span class="sxs-lookup"><span data-stu-id="0836a-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="0836a-112">生成本主题的代码示例</span><span class="sxs-lookup"><span data-stu-id="0836a-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="0836a-113">打开一个新的 Visual Basic Windows 应用程序项目，并创建一个名为 `Form1`的窗体。</span><span class="sxs-lookup"><span data-stu-id="0836a-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="0836a-114">将两个按钮和一个标签添加到 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="0836a-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="0836a-115">按下表所示命名对象。</span><span class="sxs-lookup"><span data-stu-id="0836a-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="0836a-116">Object</span><span class="sxs-lookup"><span data-stu-id="0836a-116">Object</span></span>|<span data-ttu-id="0836a-117">属性</span><span class="sxs-lookup"><span data-stu-id="0836a-117">Property</span></span>|<span data-ttu-id="0836a-118">设置</span><span class="sxs-lookup"><span data-stu-id="0836a-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="0836a-119">启动任务</span><span class="sxs-lookup"><span data-stu-id="0836a-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="0836a-120">取消</span><span class="sxs-lookup"><span data-stu-id="0836a-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="0836a-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="0836a-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="0836a-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="0836a-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="0836a-123">在 "**项目**" 菜单上，选择 "**添加类**"，将名为 `Widget.vb` 的类添加到项目。</span><span class="sxs-lookup"><span data-stu-id="0836a-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="0836a-124">为小组件类声明事件</span><span class="sxs-lookup"><span data-stu-id="0836a-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="0836a-125">使用 `Event` 关键字在 `Widget` 类中声明事件。</span><span class="sxs-lookup"><span data-stu-id="0836a-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="0836a-126">请注意，事件可以有 `ByVal` 和 `ByRef` 参数，如 `Widget``PercentDone` 事件所示：</span><span class="sxs-lookup"><span data-stu-id="0836a-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="0836a-127">当调用对象收到 `PercentDone` 事件时，`Percent` 参数包含完成的任务的百分比。</span><span class="sxs-lookup"><span data-stu-id="0836a-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="0836a-128">`Cancel` 参数可以设置为 `True` 以取消引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="0836a-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0836a-129">可以声明事件自变量，就像处理过程的参数一样，但有以下例外：事件不能具有 `Optional` 或 `ParamArray` 参数，并且事件没有返回值。</span><span class="sxs-lookup"><span data-stu-id="0836a-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="0836a-130">`PercentDone` 事件由 `Widget` 类的 `LongTask` 方法引发。</span><span class="sxs-lookup"><span data-stu-id="0836a-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="0836a-131">`LongTask` 采用以下两个参数：方法在经过一段时间后进行工作，并在 `LongTask` 暂停以引发 `PercentDone` 事件之前的最小时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0836a-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="0836a-132">引发 PercentDone 事件</span><span class="sxs-lookup"><span data-stu-id="0836a-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="0836a-133">若要简化对此类使用的 `Timer` 属性的访问，请将 `Imports` 语句添加到类模块的 "声明" 部分的顶部，并在 `Class Widget` 语句的上方。</span><span class="sxs-lookup"><span data-stu-id="0836a-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="0836a-134">将下面的代码添加到 `Widget` 类中:</span><span class="sxs-lookup"><span data-stu-id="0836a-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="0836a-135">当应用程序调用 `LongTask` 方法时，`Widget` 类每 `MinimumInterval` 秒引发 `PercentDone` 事件。</span><span class="sxs-lookup"><span data-stu-id="0836a-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="0836a-136">当事件返回时，`LongTask` 会检查 `Cancel` 参数是否设置为 `True`。</span><span class="sxs-lookup"><span data-stu-id="0836a-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="0836a-137">此处有一些免责声明是必需的。</span><span class="sxs-lookup"><span data-stu-id="0836a-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="0836a-138">为简单起见，`LongTask` 过程假设您事先知道任务将花费多长时间。</span><span class="sxs-lookup"><span data-stu-id="0836a-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="0836a-139">几乎不会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="0836a-139">This is almost never the case.</span></span> <span data-ttu-id="0836a-140">将任务划分为偶大的块可能比较困难，通常，用户最重要的是，用户只需经过一段时间，就能看出发生了什么情况。</span><span class="sxs-lookup"><span data-stu-id="0836a-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="0836a-141">在此示例中，可能已发现另一个缺陷。</span><span class="sxs-lookup"><span data-stu-id="0836a-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="0836a-142">`Timer` 属性返回从午夜开始经过的秒数;因此，如果应用程序在午夜之前启动，则该应用程序会停滞。</span><span class="sxs-lookup"><span data-stu-id="0836a-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="0836a-143">更仔细地测量时间的方法会将这种情况（例如这种情况）考虑在内，或者使用 `Now`等属性来完全避免这类情况。</span><span class="sxs-lookup"><span data-stu-id="0836a-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="0836a-144">现在 `Widget` 类可以引发事件，您可以转到下一个演练。</span><span class="sxs-lookup"><span data-stu-id="0836a-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="0836a-145">[演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)演示如何使用 `WithEvents` 将事件处理程序与 `PercentDone` 事件关联。</span><span class="sxs-lookup"><span data-stu-id="0836a-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0836a-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0836a-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="0836a-147">演练：处理事件</span><span class="sxs-lookup"><span data-stu-id="0836a-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="0836a-148">事件</span><span class="sxs-lookup"><span data-stu-id="0836a-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
