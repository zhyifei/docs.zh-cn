---
title: "如何︰ 在 Visual Basic 中调用事件处理程序 |Microsoft 文档"
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
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
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
ms.openlocfilehash: dc0174d50c7b5f5cda9d057bce39960b3e563f4e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="cffb7-102">如何：在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="cffb7-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="cffb7-103">*事件*的操作或匹配项 — 如鼠标单击或信用额度超出 —，识别，被某程序组件，并且为其编写代码进行响应。</span><span class="sxs-lookup"><span data-stu-id="cffb7-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="cffb7-104">*事件处理程序*是为响应某个事件而编写的代码。</span><span class="sxs-lookup"><span data-stu-id="cffb7-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="cffb7-105">中的事件处理程序[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]是`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="cffb7-105">An event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="cffb7-106">但是，您不能正常情况下调用此相同方式其他`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="cffb7-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="cffb7-107">相反，作为事件处理程序标识过程。</span><span class="sxs-lookup"><span data-stu-id="cffb7-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="cffb7-108">您可以执行此操作与[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句和一个[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)变量，或使用[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cffb7-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="cffb7-109">使用`Handles`子句是声明中的事件处理程序的默认方式[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cffb7-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="cffb7-110">这是您在集成的开发环境 (IDE) 中进行编程时，事件处理程序会写入设计器的方法。</span><span class="sxs-lookup"><span data-stu-id="cffb7-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="cffb7-111">`AddHandler`语句是适用于在运行时动态地引发事件。</span><span class="sxs-lookup"><span data-stu-id="cffb7-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="cffb7-112">发生事件时，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]自动调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cffb7-112">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="cffb7-113">有权访问该事件的任何代码会使它通过执行[RaiseEvent 语句](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cffb7-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="cffb7-114">可以将多个事件处理程序与同一个事件关联。</span><span class="sxs-lookup"><span data-stu-id="cffb7-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="cffb7-115">在某些情况下您可以从事件处理程序解除关联。</span><span class="sxs-lookup"><span data-stu-id="cffb7-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="cffb7-116">有关详细信息，请参阅[事件](../../../../visual-basic/programming-guide/language-features/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cffb7-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="cffb7-117">若要调用事件处理程序使用句柄和 WithEvents</span><span class="sxs-lookup"><span data-stu-id="cffb7-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="cffb7-118">请确保用声明了事件[Event 语句](../../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cffb7-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="cffb7-119">声明对象变量在模块或类级别，而使用[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="cffb7-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="cffb7-120">`As`此变量的子句必须指定引发事件的类。</span><span class="sxs-lookup"><span data-stu-id="cffb7-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="cffb7-121">在处理事件的声明中`Sub`的过程中，添加[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句，以指定`WithEvents`变量和事件名称。</span><span class="sxs-lookup"><span data-stu-id="cffb7-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="cffb7-122">发生事件时，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]自动调用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="cffb7-122">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="cffb7-123">你的代码可以使用`RaiseEvent`语句来引发事件。</span><span class="sxs-lookup"><span data-stu-id="cffb7-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="cffb7-124">下面的示例定义一个事件和一个`WithEvents`指的是引发该事件的类中的变量。</span><span class="sxs-lookup"><span data-stu-id="cffb7-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="cffb7-125">事件处理`Sub`过程使用`Handles`子句，以指定的类和它处理的事件。</span><span class="sxs-lookup"><span data-stu-id="cffb7-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     <span data-ttu-id="cffb7-126">[!code-vb[VbVbcnProcedures #&4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cffb7-126">[!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span></span>  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="cffb7-127">若要调用 AddHandler 使用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="cffb7-127">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="cffb7-128">请确保用声明了事件`Event`语句。</span><span class="sxs-lookup"><span data-stu-id="cffb7-128">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="cffb7-129">执行[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)以动态连接处理事件的`Sub`与该事件的过程。</span><span class="sxs-lookup"><span data-stu-id="cffb7-129">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="cffb7-130">发生事件时，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]自动调用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="cffb7-130">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="cffb7-131">你的代码可以使用`RaiseEvent`语句来引发事件。</span><span class="sxs-lookup"><span data-stu-id="cffb7-131">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="cffb7-132">下面的示例定义`Sub`过程来处理<xref:System.Windows.Forms.Form.Closing>窗体的事件。</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="cffb7-132">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="cffb7-133">然后，它使用[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)关联`catchClose` <xref:System.Windows.Forms.Form.Closing>。</xref:System.Windows.Forms.Form.Closing>一个事件处理程序的过程</span><span class="sxs-lookup"><span data-stu-id="cffb7-133">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     <span data-ttu-id="cffb7-134">[!code-vb[VbVbcnProcedures #&5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cffb7-134">[!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span></span>  
  
     <span data-ttu-id="cffb7-135">可以通过执行取消事件处理程序从事件[RemoveHandler 语句](../../../../visual-basic/language-reference/statements/removehandler-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cffb7-135">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffb7-136">请参见</span><span class="sxs-lookup"><span data-stu-id="cffb7-136">See Also</span></span>  
 <span data-ttu-id="cffb7-137">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="cffb7-137">[Procedures](./index.md) </span></span>  
<span data-ttu-id="cffb7-138"> [Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="cffb7-138"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="cffb7-139"> [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cffb7-139"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="cffb7-140"> [AddressOf 运算符](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="cffb7-140"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="cffb7-141"> [如何︰ 创建过程](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="cffb7-141"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="cffb7-142"> [如何：调用不返回值的过程](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="cffb7-142"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
