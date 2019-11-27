---
title: 如何：创建过程
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344914"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="c7c7d-102">如何：创建过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7c7d-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="c7c7d-103">在开始声明语句（`Sub` 或 `Function`）与结束声明语句（`End Sub` 或 `End Function`）之间包含过程。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="c7c7d-104">过程的所有代码都位于这些语句之间。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="c7c7d-105">一个过程不能包含另一个过程，所以其开始和结束语句必须在其他任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="c7c7d-106">如果你的代码在不同的位置执行相同的任务，则可以将该任务作为过程写入一次，然后从代码中的不同位置调用它。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="c7c7d-107">创建不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="c7c7d-108">在任何其他过程之外，使用 `Sub` 语句，后跟 `End Sub` 语句。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="c7c7d-109">在 `Sub` 语句中，将 `Sub` 关键字跟过程的名称一起，然后将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="c7c7d-110">将过程的代码语句置于 `Sub` 和 `End Sub` 语句之间。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="c7c7d-111">创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="c7c7d-112">在任何其他过程之外，使用 `Function` 语句，后跟 `End Function` 语句。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="c7c7d-113">在 `Function` 语句中，将 `Function` 关键字后面跟过程的名称，然后将参数列表括在括号中 `As`，然后指定返回值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="c7c7d-114">将过程的代码语句置于 `Function` 和 `End Function` 语句之间。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="c7c7d-115">使用 `Return` 语句将值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="c7c7d-116">将新过程与旧的、重复的代码块连接起来</span><span class="sxs-lookup"><span data-stu-id="c7c7d-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="c7c7d-117">请确保在旧代码有权访问的位置定义新过程。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="c7c7d-118">在旧的、重复的代码块中，将执行重复任务的语句替换为调用 `Sub` 或 `Function` 过程的单个语句。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="c7c7d-119">如果你的过程是返回值的 `Function`，请确保调用语句使用返回值执行操作（例如，将其存储在变量中），否则值将丢失。</span><span class="sxs-lookup"><span data-stu-id="c7c7d-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="c7c7d-120">示例</span><span class="sxs-lookup"><span data-stu-id="c7c7d-120">Example</span></span>

 <span data-ttu-id="c7c7d-121">以下 `Function` 过程将计算直角三角形的最长边（或斜边），并给出另一方的值：</span><span class="sxs-lookup"><span data-stu-id="c7c7d-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="c7c7d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7c7d-122">See also</span></span>

- [<span data-ttu-id="c7c7d-123">过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="c7c7d-124">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="c7c7d-125">Function 过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="c7c7d-126">属性过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="c7c7d-127">运算符过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="c7c7d-128">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="c7c7d-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c7c7d-129">递归过程</span><span class="sxs-lookup"><span data-stu-id="c7c7d-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="c7c7d-130">过程重载</span><span class="sxs-lookup"><span data-stu-id="c7c7d-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="c7c7d-131">对象和类</span><span class="sxs-lookup"><span data-stu-id="c7c7d-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="c7c7d-132">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7c7d-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
