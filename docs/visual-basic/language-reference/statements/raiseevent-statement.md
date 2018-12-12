---
title: RaiseEvent 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: ba4c05b3ef69d180f43ac3b90aa8fd6dee9c80fb
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143293"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="cb277-102">RaiseEvent 语句</span><span class="sxs-lookup"><span data-stu-id="cb277-102">RaiseEvent Statement</span></span>
<span data-ttu-id="cb277-103">触发器在类、 窗体或文档中的模块级声明的事件。</span><span class="sxs-lookup"><span data-stu-id="cb277-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb277-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb277-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="cb277-105">部件</span><span class="sxs-lookup"><span data-stu-id="cb277-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="cb277-106">必需。</span><span class="sxs-lookup"><span data-stu-id="cb277-106">Required.</span></span> <span data-ttu-id="cb277-107">要触发的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="cb277-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="cb277-108">可选。</span><span class="sxs-lookup"><span data-stu-id="cb277-108">Optional.</span></span> <span data-ttu-id="cb277-109">变量、 数组或表达式的以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="cb277-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="cb277-110">`argumentlist`参数必须括在圆括号。</span><span class="sxs-lookup"><span data-stu-id="cb277-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="cb277-111">如果没有任何自变量，必须省略括号。</span><span class="sxs-lookup"><span data-stu-id="cb277-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb277-112">备注</span><span class="sxs-lookup"><span data-stu-id="cb277-112">Remarks</span></span>  
 <span data-ttu-id="cb277-113">所需`eventname`模块中声明的事件名称。</span><span class="sxs-lookup"><span data-stu-id="cb277-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="cb277-114">它遵循 Visual Basic 变量命名约定。</span><span class="sxs-lookup"><span data-stu-id="cb277-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="cb277-115">如果尚未在其中引发的模块中声明事件，就会出错。</span><span class="sxs-lookup"><span data-stu-id="cb277-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="cb277-116">下面的代码段演示了一个事件声明和引发该事件的过程。</span><span class="sxs-lookup"><span data-stu-id="cb277-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 <span data-ttu-id="cb277-117">不能使用`RaiseEvent`引发未在模块中显式声明的事件。</span><span class="sxs-lookup"><span data-stu-id="cb277-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="cb277-118">例如，所有窗体继承<xref:System.Windows.Forms.Control.Click>从事件<xref:System.Windows.Forms.Form?displayProperty=nameWithType>，不能提升使用`RaiseEvent`派生窗体中。</span><span class="sxs-lookup"><span data-stu-id="cb277-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="cb277-119">如果声明`Click`事件在窗体模块中，它会隐藏窗体的自己<xref:System.Windows.Forms.Control.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="cb277-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="cb277-120">还可调用窗体的<xref:System.Windows.Forms.Control.Click>通过调用事件<xref:System.Windows.Forms.Control.OnClick%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="cb277-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="cb277-121">默认情况下，在 Visual Basic 中定义的事件引发其事件处理程序建立连接的顺序。</span><span class="sxs-lookup"><span data-stu-id="cb277-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="cb277-122">因为事件可以具有`ByRef`参数，晚期连接的进程可能会收到已被较早的事件处理程序更改的参数。</span><span class="sxs-lookup"><span data-stu-id="cb277-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="cb277-123">事件处理程序执行后，控制权就会归还引发该事件的子例程。</span><span class="sxs-lookup"><span data-stu-id="cb277-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb277-124">不应在声明它们的类的构造函数中引发非共享事件。</span><span class="sxs-lookup"><span data-stu-id="cb277-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="cb277-125">尽管此类事件不会导致运行时错误，但它们可能无法由关联的事件处理程序捕获。</span><span class="sxs-lookup"><span data-stu-id="cb277-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="cb277-126">使用`Shared`修饰符来创建共享的事件，如果您需要从一个构造函数中引发事件。</span><span class="sxs-lookup"><span data-stu-id="cb277-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb277-127">你可以通过定义自定义事件的事件的默认行为。</span><span class="sxs-lookup"><span data-stu-id="cb277-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="cb277-128">用于自定义事件`RaiseEvent`语句调用事件的`RaiseEvent`访问器。</span><span class="sxs-lookup"><span data-stu-id="cb277-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="cb277-129">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cb277-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb277-130">示例</span><span class="sxs-lookup"><span data-stu-id="cb277-130">Example</span></span>  
 <span data-ttu-id="cb277-131">下面的示例使用事件从 10 秒到 0 秒进行倒计时。</span><span class="sxs-lookup"><span data-stu-id="cb277-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="cb277-132">该代码演示了几个与事件相关的方法、 属性和语句，其中包括`RaiseEvent`语句。</span><span class="sxs-lookup"><span data-stu-id="cb277-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="cb277-133">引发事件的类是事件源，处理事件的方法是事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cb277-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="cb277-134">事件源对于它生成的事件可以具有多个处理程序。</span><span class="sxs-lookup"><span data-stu-id="cb277-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="cb277-135">类引发事件时，会在选择用于为对象的该实例处理事件的每个类上引发该事件。</span><span class="sxs-lookup"><span data-stu-id="cb277-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="cb277-136">该示例还使用一个窗体 (`Form1`)，其中包含一个按钮 (`Button1`) 和一个文本框 (`TextBox1`)。</span><span class="sxs-lookup"><span data-stu-id="cb277-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="cb277-137">单击该按钮时，第一个文本框显示从 10 秒到 0 秒的倒计时。</span><span class="sxs-lookup"><span data-stu-id="cb277-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="cb277-138">经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。</span><span class="sxs-lookup"><span data-stu-id="cb277-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="cb277-139">`Form1` 的代码指定窗体的初始和最终状态。</span><span class="sxs-lookup"><span data-stu-id="cb277-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="cb277-140">它还包含引发事件时执行的代码。</span><span class="sxs-lookup"><span data-stu-id="cb277-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="cb277-141">若要使用此示例中，打开一个新的 Windows 应用程序项目中，添加名为的按钮`Button1`和一个名为文本框`TextBox1`到主窗体，名为`Form1`。</span><span class="sxs-lookup"><span data-stu-id="cb277-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="cb277-142">右键单击窗体，然后单击**查看代码**以打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="cb277-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="cb277-143">添加`WithEvents`变量的声明部分`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="cb277-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="cb277-144">示例</span><span class="sxs-lookup"><span data-stu-id="cb277-144">Example</span></span>  
 <span data-ttu-id="cb277-145">将下面的代码添加到 `Form1` 的代码：</span><span class="sxs-lookup"><span data-stu-id="cb277-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="cb277-146">替换可能存在，例如任何重复过程`Form_Load`，或`Button_Click`。</span><span class="sxs-lookup"><span data-stu-id="cb277-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 <span data-ttu-id="cb277-147">按 F5 以运行上述示例中，并单击标记的按钮**启动**。</span><span class="sxs-lookup"><span data-stu-id="cb277-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="cb277-148">第一个文本框中开始倒计时秒数。</span><span class="sxs-lookup"><span data-stu-id="cb277-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="cb277-149">经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。</span><span class="sxs-lookup"><span data-stu-id="cb277-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb277-150">`My.Application.DoEvents`窗体一样方法不会完全相同的方式处理事件。</span><span class="sxs-lookup"><span data-stu-id="cb277-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="cb277-151">若要使表单能够直接处理事件，可以使用多线程处理。</span><span class="sxs-lookup"><span data-stu-id="cb277-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="cb277-152">有关详细信息，请参阅[托管线程处理](../../../standard/threading/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cb277-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb277-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb277-153">See Also</span></span>  
 [<span data-ttu-id="cb277-154">事件</span><span class="sxs-lookup"><span data-stu-id="cb277-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="cb277-155">Event 语句</span><span class="sxs-lookup"><span data-stu-id="cb277-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="cb277-156">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="cb277-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="cb277-157">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="cb277-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="cb277-158">Handles</span><span class="sxs-lookup"><span data-stu-id="cb277-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
