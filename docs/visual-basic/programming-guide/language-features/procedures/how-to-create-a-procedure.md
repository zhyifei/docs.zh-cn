---
title: 如何：创建过程 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e23358e26dbc993b0f9290a8491a3c66717b4c6
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="b6f76-102">如何：创建过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6f76-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="b6f76-103">你将包含起始的声明语句之间的过程 (`Sub`或`Function`) 和结束的声明语句 (`End Sub`或`End Function`)。</span><span class="sxs-lookup"><span data-stu-id="b6f76-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="b6f76-104">过程的所有代码均位于这些语句之间。</span><span class="sxs-lookup"><span data-stu-id="b6f76-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="b6f76-105">过程不能包含另一个过程，因此其起始和结束语句必须位于任何其他过程之外。</span><span class="sxs-lookup"><span data-stu-id="b6f76-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="b6f76-106">如果你有在不同的位置执行相同的任务的代码，你可以编写将任务作为过程一次，然后调用它从不同的位置在代码中。</span><span class="sxs-lookup"><span data-stu-id="b6f76-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="b6f76-107">若要创建过程，它不返回值</span><span class="sxs-lookup"><span data-stu-id="b6f76-107">To create a procedure that does not return a value</span></span>  
  
1.  <span data-ttu-id="b6f76-108">在任何其他过程之外使用`Sub`语句后, 跟`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="b6f76-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="b6f76-109">在`Sub`语句，请按照`Sub`关键字的过程中，然后在括号中的参数列表的名称。</span><span class="sxs-lookup"><span data-stu-id="b6f76-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="b6f76-110">放置过程的代码语句之间`Sub`和`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="b6f76-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="b6f76-111">创建过程中返回一个值</span><span class="sxs-lookup"><span data-stu-id="b6f76-111">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="b6f76-112">在任何其他过程之外使用`Function`语句后, 跟`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="b6f76-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="b6f76-113">在`Function`语句，请按照`Function`关键字的过程中，然后在括号中的参数列表的名称，然后`As`子句，用于指定返回值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b6f76-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3.  <span data-ttu-id="b6f76-114">放置过程的代码语句之间`Function`和`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="b6f76-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4.  <span data-ttu-id="b6f76-115">使用`Return`语句返回值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="b6f76-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="b6f76-116">若要将新的过程与旧的重复代码块连接起来</span><span class="sxs-lookup"><span data-stu-id="b6f76-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1.  <span data-ttu-id="b6f76-117">请确保你在其中的旧代码有权访问它的位置来定义新的过程。</span><span class="sxs-lookup"><span data-stu-id="b6f76-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2.  <span data-ttu-id="b6f76-118">在旧的重复代码块，将执行该重复任务的调用的单个语句的语句`Sub`或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="b6f76-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3.  <span data-ttu-id="b6f76-119">如果过程是`Function`返回一个值，请确保调用语句中执行了操作与返回的值，如将其存储在变量中，否则将丢失的值。</span><span class="sxs-lookup"><span data-stu-id="b6f76-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6f76-120">示例</span><span class="sxs-lookup"><span data-stu-id="b6f76-120">Example</span></span>  
 <span data-ttu-id="b6f76-121">以下`Function`过程计算的最长端或斜边直角三角形，其他两条边为给定的值。</span><span class="sxs-lookup"><span data-stu-id="b6f76-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b6f76-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6f76-122">See also</span></span>

 [<span data-ttu-id="b6f76-123">过程</span><span class="sxs-lookup"><span data-stu-id="b6f76-123">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="b6f76-124">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="b6f76-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="b6f76-125">Function 过程</span><span class="sxs-lookup"><span data-stu-id="b6f76-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="b6f76-126">属性过程</span><span class="sxs-lookup"><span data-stu-id="b6f76-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="b6f76-127">运算符过程</span><span class="sxs-lookup"><span data-stu-id="b6f76-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="b6f76-128">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="b6f76-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="b6f76-129">递归过程</span><span class="sxs-lookup"><span data-stu-id="b6f76-129">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="b6f76-130">过程重载</span><span class="sxs-lookup"><span data-stu-id="b6f76-130">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="b6f76-131">对象和类</span><span class="sxs-lookup"><span data-stu-id="b6f76-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="b6f76-132">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6f76-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
