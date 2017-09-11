---
title: "RaiseEvent 语句 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.openlocfilehash: 6a0cf1c5635335f22fddd57c7dd2baaeca6ddd23
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="raiseevent-statement"></a><span data-ttu-id="0c167-102">RaiseEvent 语句</span><span class="sxs-lookup"><span data-stu-id="0c167-102">RaiseEvent Statement</span></span>
<span data-ttu-id="0c167-103">触发器在类、 表单或文档中的模块级别声明的事件。</span><span class="sxs-lookup"><span data-stu-id="0c167-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c167-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c167-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="0c167-105">部件</span><span class="sxs-lookup"><span data-stu-id="0c167-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="0c167-106">必需。</span><span class="sxs-lookup"><span data-stu-id="0c167-106">Required.</span></span> <span data-ttu-id="0c167-107">要触发的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="0c167-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="0c167-108">可选。</span><span class="sxs-lookup"><span data-stu-id="0c167-108">Optional.</span></span> <span data-ttu-id="0c167-109">以逗号分隔的变量、 数组或表达式列表。</span><span class="sxs-lookup"><span data-stu-id="0c167-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="0c167-110">`argumentlist`参数必须用括号括起来。</span><span class="sxs-lookup"><span data-stu-id="0c167-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="0c167-111">如果不有任何参数，则必须省略括号。</span><span class="sxs-lookup"><span data-stu-id="0c167-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c167-112">备注</span><span class="sxs-lookup"><span data-stu-id="0c167-112">Remarks</span></span>  
 <span data-ttu-id="0c167-113">所需`eventname`模块中声明的事件名称。</span><span class="sxs-lookup"><span data-stu-id="0c167-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="0c167-114">它遵循 Visual Basic 变量命名规则。</span><span class="sxs-lookup"><span data-stu-id="0c167-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="0c167-115">如果尚未在其中将引发此事件的模块内声明该事件，就会出错。</span><span class="sxs-lookup"><span data-stu-id="0c167-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="0c167-116">下面的代码段演示了一个事件声明和引发该事件的过程。</span><span class="sxs-lookup"><span data-stu-id="0c167-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 <span data-ttu-id="0c167-117">[!code-vb[VbVbalrEvents #&37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c167-117">[!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="0c167-118">不能使用`RaiseEvent`引发未在模块中显式声明的事件。</span><span class="sxs-lookup"><span data-stu-id="0c167-118">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="0c167-119">例如，所有窗体继承<xref:System.Windows.Forms.Control.Click>来自事件<xref:System.Windows.Forms.Form?displayProperty=fullName>，不能提升使用`RaiseEvent`派生窗体中。</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="0c167-119">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=fullName>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="0c167-120">如果您声明`Click`事件在窗体模块中，它将隐藏窗体自身的<xref:System.Windows.Forms.Control.Click>事件。</xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="0c167-120">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="0c167-121">还可调用窗体的<xref:System.Windows.Forms.Control.Click>事件通过调用<xref:System.Windows.Forms.Control.OnClick%2A>方法。</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="0c167-121">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="0c167-122">默认情况下，在 Visual Basic 中定义的事件引发其事件处理程序建立的连接顺序。</span><span class="sxs-lookup"><span data-stu-id="0c167-122">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="0c167-123">由于事件可以具有`ByRef`参数，晚期连接的进程可能会收到较早的事件处理程序已更改的参数。</span><span class="sxs-lookup"><span data-stu-id="0c167-123">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="0c167-124">事件处理程序执行后，控制权就会归还引发事件的子例程。</span><span class="sxs-lookup"><span data-stu-id="0c167-124">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c167-125">非共享事件应该不会出现声明它们的类的构造函数内。</span><span class="sxs-lookup"><span data-stu-id="0c167-125">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="0c167-126">尽管此类事件不会导致运行时错误，但它们可能无法由关联的事件处理程序捕获。</span><span class="sxs-lookup"><span data-stu-id="0c167-126">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="0c167-127">使用`Shared`修饰符来创建共享的事件，如果您需要从一个构造函数中引发事件。</span><span class="sxs-lookup"><span data-stu-id="0c167-127">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c167-128">通过定义自定义事件，可以更改事件的默认行为。</span><span class="sxs-lookup"><span data-stu-id="0c167-128">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="0c167-129">对于自定义事件`RaiseEvent`语句调用的事件`RaiseEvent`取值函数。</span><span class="sxs-lookup"><span data-stu-id="0c167-129">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="0c167-130">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0c167-130">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c167-131">示例</span><span class="sxs-lookup"><span data-stu-id="0c167-131">Example</span></span>  
 <span data-ttu-id="0c167-132">下面的示例使用事件从 10 秒到 0 秒进行倒计时。</span><span class="sxs-lookup"><span data-stu-id="0c167-132">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="0c167-133">代码阐释了几个与事件相关的方法、 属性和语句，其中包括`RaiseEvent`语句。</span><span class="sxs-lookup"><span data-stu-id="0c167-133">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="0c167-134">引发事件的类是事件源，处理事件的方法是事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0c167-134">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="0c167-135">事件源对于它生成的事件可以具有多个处理程序。</span><span class="sxs-lookup"><span data-stu-id="0c167-135">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="0c167-136">类引发事件时，会在选择用于为对象的该实例处理事件的每个类上引发该事件。</span><span class="sxs-lookup"><span data-stu-id="0c167-136">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="0c167-137">该示例还使用一个窗体 (`Form1`)，其中包含一个按钮 (`Button1`) 和一个文本框 (`TextBox1`)。</span><span class="sxs-lookup"><span data-stu-id="0c167-137">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="0c167-138">单击该按钮时，第一个文本框显示从 10 秒到 0 秒的倒计时。</span><span class="sxs-lookup"><span data-stu-id="0c167-138">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="0c167-139">经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。</span><span class="sxs-lookup"><span data-stu-id="0c167-139">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="0c167-140">`Form1` 的代码指定窗体的初始和最终状态。</span><span class="sxs-lookup"><span data-stu-id="0c167-140">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="0c167-141">它还包含引发事件时执行的代码。</span><span class="sxs-lookup"><span data-stu-id="0c167-141">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="0c167-142">若要使用此示例中，打开一个新的 Windows 应用程序项目，添加名为的按钮`Button1`和一个名为文本框`TextBox1`到主窗体中，名为`Form1`。</span><span class="sxs-lookup"><span data-stu-id="0c167-142">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="0c167-143">右键单击该表单，然后单击**查看代码**以打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="0c167-143">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="0c167-144">添加`WithEvents`变量的声明部分`Form1`类。</span><span class="sxs-lookup"><span data-stu-id="0c167-144">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 <span data-ttu-id="0c167-145">[!code-vb[VbVbalrEvents #&14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c167-145">[!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c167-146">示例</span><span class="sxs-lookup"><span data-stu-id="0c167-146">Example</span></span>  
 <span data-ttu-id="0c167-147">将下面的代码添加到 `Form1` 的代码：</span><span class="sxs-lookup"><span data-stu-id="0c167-147">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="0c167-148">替换任何重复的过程，可能存在，如`Form_Load`，或`Button_Click`。</span><span class="sxs-lookup"><span data-stu-id="0c167-148">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 <span data-ttu-id="0c167-149">[!code-vb[VbVbalrEvents #&15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c167-149">[!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="0c167-150">按 f5 键以运行前面的示例中，然后单击标记为按钮**启动**。</span><span class="sxs-lookup"><span data-stu-id="0c167-150">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="0c167-151">第一个文本框中开始倒计时秒数。</span><span class="sxs-lookup"><span data-stu-id="0c167-151">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="0c167-152">经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。</span><span class="sxs-lookup"><span data-stu-id="0c167-152">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c167-153">`My.Application.DoEvents`窗体一样方法不完全相同的方式处理事件。</span><span class="sxs-lookup"><span data-stu-id="0c167-153">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="0c167-154">若要使表单能够直接处理事件，可以使用多线程处理。</span><span class="sxs-lookup"><span data-stu-id="0c167-154">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="0c167-155">有关详细信息，请参阅[线程处理](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)。</span><span class="sxs-lookup"><span data-stu-id="0c167-155">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c167-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c167-156">See Also</span></span>  
 <span data-ttu-id="0c167-157">[事件](../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="0c167-157">[Events](../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="0c167-158"> [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0c167-158"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="0c167-159"> [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0c167-159"> [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="0c167-160"> [RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0c167-160"> [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="0c167-161"> [句柄](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0c167-161"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
