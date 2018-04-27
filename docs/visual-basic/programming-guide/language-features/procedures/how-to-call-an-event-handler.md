---
title: 如何：在 Visual Basic 中调用事件处理程序
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b8a35459fdeb7cce0b494a9b3024a79bd4173cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="7fa1e-102">如何：在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="7fa1e-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="7fa1e-103">*事件*是匹配项或操作-例如鼠标单击或信用额度超出-，识别被某程序组件，并为其编写代码以响应。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="7fa1e-104">*事件处理程序*是为响应事件而编写的代码。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="7fa1e-105">在 Visual Basic 中的一个事件处理程序`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="7fa1e-106">但是，你不能正常情况下调用此相同方式其他`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="7fa1e-107">相反，为事件处理程序标识过程。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="7fa1e-108">你可以使用执行此操作[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句和[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)变量，或与[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="7fa1e-109">使用`Handles`子句是声明一个事件处理程序在 Visual Basic 中的默认方法。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="7fa1e-110">这是事件处理程序编写的设计器时在集成的开发环境 (IDE) 中编程的方式。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="7fa1e-111">`AddHandler`语句是适用于在运行时动态引发事件。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="7fa1e-112">发生事件时，Visual Basic 会自动调用事件处理程序过程中。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="7fa1e-113">有权访问该事件的任何代码可能会导致它通过执行发生[RaiseEvent 语句](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="7fa1e-114">你可以与同一事件关联多个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="7fa1e-115">在某些情况下可以取消关联从事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="7fa1e-116">有关详细信息，请参阅[事件](../../../../visual-basic/programming-guide/language-features/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="7fa1e-117">若要调用事件处理程序使用句柄和 WithEvents</span><span class="sxs-lookup"><span data-stu-id="7fa1e-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="7fa1e-118">请确保该事件声明与[Event 语句](../../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="7fa1e-119">声明对象变量在模块或类级别，请使用[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="7fa1e-120">`As`此变量的子句必须指定引发事件的类。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="7fa1e-121">事件处理的声明中`Sub`过程中，添加[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句，以指定`WithEvents`变量和事件名称。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="7fa1e-122">发生事件时，Visual Basic 将自动调用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="7fa1e-123">你的代码可以使用`RaiseEvent`语句使发生的事件。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="7fa1e-124">下面的示例定义一个事件和一个`WithEvents`引用引发事件的类中的变量。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="7fa1e-125">事件处理`Sub`过程使用`Handles`子句指定的类和它所处理的事件。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="7fa1e-126">若要调用事件处理程序使用 AddHandler</span><span class="sxs-lookup"><span data-stu-id="7fa1e-126">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="7fa1e-127">请确保该事件声明与`Event`语句。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="7fa1e-128">执行[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)动态连接事件处理`Sub`与事件的过程。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="7fa1e-129">发生事件时，Visual Basic 将自动调用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="7fa1e-130">你的代码可以使用`RaiseEvent`语句使发生的事件。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="7fa1e-131">下面的示例定义`Sub`过程来处理<xref:System.Windows.Forms.Form.Closing>窗体的事件。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="7fa1e-132">然后，它使用[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)关联`catchClose`的事件处理程序的过程<xref:System.Windows.Forms.Form.Closing>。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     <span data-ttu-id="7fa1e-133">你可以通过执行取消事件处理程序从事件[RemoveHandler 语句](../../../../visual-basic/language-reference/statements/removehandler-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa1e-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa1e-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fa1e-134">See Also</span></span>  
 [<span data-ttu-id="7fa1e-135">过程</span><span class="sxs-lookup"><span data-stu-id="7fa1e-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="7fa1e-136">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="7fa1e-136">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="7fa1e-137">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="7fa1e-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="7fa1e-138">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="7fa1e-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="7fa1e-139">如何：创建过程</span><span class="sxs-lookup"><span data-stu-id="7fa1e-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="7fa1e-140">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="7fa1e-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
