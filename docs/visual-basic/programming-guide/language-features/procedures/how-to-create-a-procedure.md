---
title: 如何：创建过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 06fed04a0ebe7a0b3111a94308d15d01bcf47c1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636529"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="a8938-102">如何：创建过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8938-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="a8938-103">将起始的声明语句之间的过程 (`Sub`或`Function`) 和结束的声明语句 (`End Sub`或`End Function`)。</span><span class="sxs-lookup"><span data-stu-id="a8938-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="a8938-104">该过程的所有代码均位于这些语句之间。</span><span class="sxs-lookup"><span data-stu-id="a8938-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="a8938-105">过程不能包含另一个过程，使其开始和结束语句必须位于任何其他过程之外。</span><span class="sxs-lookup"><span data-stu-id="a8938-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="a8938-106">如果你有在不同的位置执行相同的任务的代码，您可以编写一次在过程中的任务，然后调用它从不同的位置在代码中。</span><span class="sxs-lookup"><span data-stu-id="a8938-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="a8938-107">若要创建一个过程，不会返回一个值</span><span class="sxs-lookup"><span data-stu-id="a8938-107">To create a procedure that does not return a value</span></span>  
  
1.  <span data-ttu-id="a8938-108">任何其他过程之外，使用`Sub`语句后, 跟`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="a8938-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="a8938-109">在中`Sub`语句，请按照`Sub`关键字的过程，然后在括号中的参数列表的名称。</span><span class="sxs-lookup"><span data-stu-id="a8938-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="a8938-110">将过程的代码语句之间`Sub`和`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="a8938-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="a8938-111">若要创建的过程将返回一个值</span><span class="sxs-lookup"><span data-stu-id="a8938-111">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="a8938-112">任何其他过程之外，使用`Function`语句后, 跟`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="a8938-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="a8938-113">在中`Function`语句，请按照`Function`关键字的过程，然后在括号中的参数列表的名称，然后`As`子句，用于指定返回值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a8938-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3.  <span data-ttu-id="a8938-114">将过程的代码语句之间`Function`和`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="a8938-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4.  <span data-ttu-id="a8938-115">使用`Return`语句以返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="a8938-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="a8938-116">若要连接用旧的重复的块的代码的新过程</span><span class="sxs-lookup"><span data-stu-id="a8938-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1.  <span data-ttu-id="a8938-117">请确保你在旧代码有权访问其中的位置来定义新过程。</span><span class="sxs-lookup"><span data-stu-id="a8938-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2.  <span data-ttu-id="a8938-118">在旧的重复代码块中，将为执行重复任务使用的单个语句的调用的语句`Sub`或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="a8938-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3.  <span data-ttu-id="a8938-119">如果您的过程是`Function`返回一个值，请确保调用语句中执行的操作的返回值，例如将其存储在变量中，否则将丢失的值。</span><span class="sxs-lookup"><span data-stu-id="a8938-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8938-120">示例</span><span class="sxs-lookup"><span data-stu-id="a8938-120">Example</span></span>  
 <span data-ttu-id="a8938-121">以下`Function`过程计算的最长边或斜边的直角三角形而言，其他两个方面为给定的值。</span><span class="sxs-lookup"><span data-stu-id="a8938-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a8938-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8938-122">See also</span></span>

- [<span data-ttu-id="a8938-123">过程</span><span class="sxs-lookup"><span data-stu-id="a8938-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a8938-124">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="a8938-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a8938-125">Function 过程</span><span class="sxs-lookup"><span data-stu-id="a8938-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="a8938-126">属性过程</span><span class="sxs-lookup"><span data-stu-id="a8938-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a8938-127">运算符过程</span><span class="sxs-lookup"><span data-stu-id="a8938-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="a8938-128">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="a8938-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a8938-129">递归过程</span><span class="sxs-lookup"><span data-stu-id="a8938-129">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="a8938-130">过程重载</span><span class="sxs-lookup"><span data-stu-id="a8938-130">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="a8938-131">对象和类</span><span class="sxs-lookup"><span data-stu-id="a8938-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="a8938-132">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8938-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
