---
title: 如何：创建过程（Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216720"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="02071-102">如何：创建过程（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="02071-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="02071-103">在开始声明语句`Sub` （或`Function`）和结束声明语句（`End Sub`或`End Function`）之间包含过程。</span><span class="sxs-lookup"><span data-stu-id="02071-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="02071-104">过程的所有代码都位于这些语句之间。</span><span class="sxs-lookup"><span data-stu-id="02071-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="02071-105">一个过程不能包含另一个过程，所以其开始和结束语句必须在其他任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="02071-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="02071-106">如果你的代码在不同的位置执行相同的任务，则可以将该任务作为过程写入一次，然后从代码中的不同位置调用它。</span><span class="sxs-lookup"><span data-stu-id="02071-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="02071-107">创建不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="02071-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="02071-108">在`Sub`任何其他过程之外，使用语句，然后`End Sub`使用语句。</span><span class="sxs-lookup"><span data-stu-id="02071-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="02071-109">在语句中，在`Sub`关键字后面跟过程的名称，然后是括号中的参数列表。 `Sub`</span><span class="sxs-lookup"><span data-stu-id="02071-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="02071-110">将过程的代码语句放置在`Sub`和`End Sub`语句之间。</span><span class="sxs-lookup"><span data-stu-id="02071-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="02071-111">创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="02071-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="02071-112">在`Function`任何其他过程之外，使用语句，然后`End Function`使用语句。</span><span class="sxs-lookup"><span data-stu-id="02071-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="02071-113">在语句中，在`Function`关键字后面跟过程的名称，然后是括号中的参数列表，然后是`As`指定返回值的数据类型的子句。 `Function`</span><span class="sxs-lookup"><span data-stu-id="02071-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="02071-114">将过程的代码语句放置在`Function`和`End Function`语句之间。</span><span class="sxs-lookup"><span data-stu-id="02071-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="02071-115">`Return`使用语句将值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="02071-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="02071-116">将新过程与旧的、重复的代码块连接起来</span><span class="sxs-lookup"><span data-stu-id="02071-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="02071-117">请确保在旧代码有权访问的位置定义新过程。</span><span class="sxs-lookup"><span data-stu-id="02071-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="02071-118">在旧的、重复的代码块中，使用调用`Sub`或`Function`过程的单个语句替换执行重复任务的语句。</span><span class="sxs-lookup"><span data-stu-id="02071-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="02071-119">如果你`Function`的过程是返回值的，请确保调用语句使用返回值执行操作（例如，将其存储在变量中），否则值将丢失。</span><span class="sxs-lookup"><span data-stu-id="02071-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="02071-120">示例</span><span class="sxs-lookup"><span data-stu-id="02071-120">Example</span></span>

 <span data-ttu-id="02071-121">以下`Function`过程将计算直角三角形的最长边（或斜边），并给出另两个边的值：</span><span class="sxs-lookup"><span data-stu-id="02071-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="02071-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="02071-122">See also</span></span>

- [<span data-ttu-id="02071-123">过程</span><span class="sxs-lookup"><span data-stu-id="02071-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="02071-124">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="02071-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="02071-125">Function 过程</span><span class="sxs-lookup"><span data-stu-id="02071-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="02071-126">属性过程</span><span class="sxs-lookup"><span data-stu-id="02071-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="02071-127">运算符过程</span><span class="sxs-lookup"><span data-stu-id="02071-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="02071-128">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="02071-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="02071-129">递归过程</span><span class="sxs-lookup"><span data-stu-id="02071-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="02071-130">过程重载</span><span class="sxs-lookup"><span data-stu-id="02071-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="02071-131">对象和类</span><span class="sxs-lookup"><span data-stu-id="02071-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="02071-132">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02071-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
