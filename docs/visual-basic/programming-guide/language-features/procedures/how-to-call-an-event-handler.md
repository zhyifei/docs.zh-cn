---
title: 如何：在 Visual Basic 中调用事件处理程序
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: a9e090e83b180686ccb832aa6efb314c7e0fcc9a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216614"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="df4bb-102">如何：在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="df4bb-102">How to: Call an Event Handler in Visual Basic</span></span>

<span data-ttu-id="df4bb-103">事件是指由某些程序组件识别的操作或*事件*（例如鼠标单击或信用限制），可以为其编写代码来做出响应。</span><span class="sxs-lookup"><span data-stu-id="df4bb-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="df4bb-104">*事件处理程序*是为响应事件而编写的代码。</span><span class="sxs-lookup"><span data-stu-id="df4bb-104">An *event handler* is the code you write to respond to an event.</span></span>

 <span data-ttu-id="df4bb-105">Visual Basic 中的事件处理程序是`Sub`一个过程。</span><span class="sxs-lookup"><span data-stu-id="df4bb-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="df4bb-106">不过，通常不会像其他`Sub`过程那样调用它。</span><span class="sxs-lookup"><span data-stu-id="df4bb-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="df4bb-107">而是将该过程标识为事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="df4bb-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="df4bb-108">您可以使用[Handles](../../../language-reference/statements/handles-clause.md)子句和[WithEvents](../../../language-reference/modifiers/withevents.md)变量或使用[AddHandler 语句](../../../language-reference/statements/addhandler-statement.md)来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="df4bb-108">You can do this either with a [Handles](../../../language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="df4bb-109">`Handles`使用子句是在 Visual Basic 中声明事件处理程序的默认方式。</span><span class="sxs-lookup"><span data-stu-id="df4bb-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="df4bb-110">当你在集成开发环境（IDE）中编程时，这就是设计器编写事件处理程序的方式。</span><span class="sxs-lookup"><span data-stu-id="df4bb-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="df4bb-111">`AddHandler`语句适用于在运行时动态引发事件。</span><span class="sxs-lookup"><span data-stu-id="df4bb-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>

 <span data-ttu-id="df4bb-112">事件发生时，Visual Basic 会自动调用事件处理程序过程。</span><span class="sxs-lookup"><span data-stu-id="df4bb-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="df4bb-113">有权访问事件的任何代码都可以通过执行[RaiseEvent 语句](../../../language-reference/statements/raiseevent-statement.md)来导致事件发生。</span><span class="sxs-lookup"><span data-stu-id="df4bb-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span></span>

 <span data-ttu-id="df4bb-114">可以将多个事件处理程序与同一事件关联。</span><span class="sxs-lookup"><span data-stu-id="df4bb-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="df4bb-115">在某些情况下，您可以取消关联事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="df4bb-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="df4bb-116">有关详细信息，请参阅[事件](../events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="df4bb-116">For more information, see [Events](../events/index.md).</span></span>

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="df4bb-117">使用 Handles 和 WithEvents 调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="df4bb-117">To call an event handler using Handles and WithEvents</span></span>

1. <span data-ttu-id="df4bb-118">请确保事件是用[事件语句](../../../language-reference/statements/event-statement.md)声明的。</span><span class="sxs-lookup"><span data-stu-id="df4bb-118">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span></span>

2. <span data-ttu-id="df4bb-119">使用[WithEvents](../../../language-reference/modifiers/withevents.md)关键字在模块或类级别声明对象变量。</span><span class="sxs-lookup"><span data-stu-id="df4bb-119">Declare an object variable at module or class level, using the [WithEvents](../../../language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="df4bb-120">此`As`变量的子句必须指定引发事件的类。</span><span class="sxs-lookup"><span data-stu-id="df4bb-120">The `As` clause for this variable must specify the class that raises the event.</span></span>

3. <span data-ttu-id="df4bb-121">在事件处理`Sub`过程的声明中，添加一个指定`WithEvents`变量和事件名称的[Handles](../../../language-reference/statements/handles-clause.md)子句。</span><span class="sxs-lookup"><span data-stu-id="df4bb-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>

4. <span data-ttu-id="df4bb-122">事件发生时，Visual Basic 自动调用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="df4bb-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="df4bb-123">你的`RaiseEvent`代码可以使用语句来使事件发生。</span><span class="sxs-lookup"><span data-stu-id="df4bb-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="df4bb-124">下面的示例定义了一个事件和`WithEvents`一个引用引发事件的类的变量。</span><span class="sxs-lookup"><span data-stu-id="df4bb-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="df4bb-125">事件处理`Sub`过程`Handles`使用子句来指定它处理的类和事件。</span><span class="sxs-lookup"><span data-stu-id="df4bb-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="df4bb-126">使用 AddHandler 调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="df4bb-126">To call an event handler using AddHandler</span></span>

1. <span data-ttu-id="df4bb-127">请确保用`Event`语句声明了该事件。</span><span class="sxs-lookup"><span data-stu-id="df4bb-127">Make sure the event is declared with an `Event` statement.</span></span>

2. <span data-ttu-id="df4bb-128">执行[AddHandler 语句](../../../language-reference/statements/addhandler-statement.md)以使用事件动态连接事件处理`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="df4bb-128">Execute an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>

3. <span data-ttu-id="df4bb-129">事件发生时，Visual Basic 自动调用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="df4bb-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="df4bb-130">你的`RaiseEvent`代码可以使用语句来使事件发生。</span><span class="sxs-lookup"><span data-stu-id="df4bb-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="df4bb-131">下面的示例定义`Sub`处理窗体的<xref:System.Windows.Forms.Form.Closing>事件的过程。</span><span class="sxs-lookup"><span data-stu-id="df4bb-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="df4bb-132">然后，它使用[AddHandler 语句](../../../language-reference/statements/addhandler-statement.md)将`catchClose`过程与的事件处理程序<xref:System.Windows.Forms.Form.Closing>相关联。</span><span class="sxs-lookup"><span data-stu-id="df4bb-132">It then uses the [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     <span data-ttu-id="df4bb-133">可以通过执行[RemoveHandler 语句](../../../language-reference/statements/removehandler-statement.md)，将事件处理程序与事件取消关联。</span><span class="sxs-lookup"><span data-stu-id="df4bb-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../language-reference/statements/removehandler-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df4bb-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="df4bb-134">See also</span></span>

- [<span data-ttu-id="df4bb-135">过程</span><span class="sxs-lookup"><span data-stu-id="df4bb-135">Procedures</span></span>](index.md)
- [<span data-ttu-id="df4bb-136">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="df4bb-136">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="df4bb-137">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="df4bb-137">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="df4bb-138">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="df4bb-138">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="df4bb-139">如何：创建过程</span><span class="sxs-lookup"><span data-stu-id="df4bb-139">How to: Create a Procedure</span></span>](how-to-create-a-procedure.md)
- [<span data-ttu-id="df4bb-140">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="df4bb-140">How to: Call a Procedure that Does Not Return a Value</span></span>](how-to-call-a-procedure-that-does-not-return-a-value.md)
