---
title: 如何：调用返回值的过程 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbaaa5ed17845a7ac8847786fb10111c724015ba
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="1fe29-102">如何：调用返回值的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fe29-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="1fe29-103">A`Function`过程返回到调用代码的一个值。</span><span class="sxs-lookup"><span data-stu-id="1fe29-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="1fe29-104">它通过调用包括其名称和自变量放在右边的赋值语句或表达式中。</span><span class="sxs-lookup"><span data-stu-id="1fe29-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="1fe29-105">调用函数过程在表达式中</span><span class="sxs-lookup"><span data-stu-id="1fe29-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="1fe29-106">使用`Function`过程名称相同的方式将使用变量。</span><span class="sxs-lookup"><span data-stu-id="1fe29-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="1fe29-107">你可以使用`Function`过程调用可以在表达式中使用变量或常量的任何位置。</span><span class="sxs-lookup"><span data-stu-id="1fe29-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="1fe29-108">过程名后面加上括号将自变量列表括起来。</span><span class="sxs-lookup"><span data-stu-id="1fe29-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1fe29-109">如果不有任何自变量，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="1fe29-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="1fe29-110">但是，使用括号使得你的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="1fe29-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="1fe29-111">将自变量放在括号里，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="1fe29-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1fe29-112">请确保你提供的相同顺序的自变量，`Function`过程所定义的相应参数。</span><span class="sxs-lookup"><span data-stu-id="1fe29-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="1fe29-113">或者，你可以按名称传递一个或多个自变量。</span><span class="sxs-lookup"><span data-stu-id="1fe29-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="1fe29-114">有关详细信息，请参阅[按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)。</span><span class="sxs-lookup"><span data-stu-id="1fe29-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="1fe29-115">从过程返回的值参与值一样的表达式的变量或常数那样。</span><span class="sxs-lookup"><span data-stu-id="1fe29-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="1fe29-116">在赋值语句中调用函数过程</span><span class="sxs-lookup"><span data-stu-id="1fe29-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="1fe29-117">使用`Function`过程名称之后相等 (`=`) 在赋值语句登录。</span><span class="sxs-lookup"><span data-stu-id="1fe29-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="1fe29-118">过程名后面加上括号将自变量列表括起来。</span><span class="sxs-lookup"><span data-stu-id="1fe29-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1fe29-119">如果不有任何自变量，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="1fe29-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="1fe29-120">但是，使用括号使得你的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="1fe29-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="1fe29-121">将自变量放在括号里，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="1fe29-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1fe29-122">请确保你提供的相同顺序的自变量，`Function`过程所定义的相应参数，除非您要按名称传递它们。</span><span class="sxs-lookup"><span data-stu-id="1fe29-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="1fe29-123">从过程返回的值存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="1fe29-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fe29-124">示例</span><span class="sxs-lookup"><span data-stu-id="1fe29-124">Example</span></span>  
 <span data-ttu-id="1fe29-125">下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.Environ%2A>检索操作系统环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="1fe29-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="1fe29-126">第一个行调用`Environ`内一个表达式和第二个行调用它在赋值语句中。</span><span class="sxs-lookup"><span data-stu-id="1fe29-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="1fe29-127">`Environ` 将变量名称作为其唯一的自变量。</span><span class="sxs-lookup"><span data-stu-id="1fe29-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="1fe29-128">它返回到调用代码的变量的值。</span><span class="sxs-lookup"><span data-stu-id="1fe29-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1fe29-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fe29-129">See Also</span></span>  
 [<span data-ttu-id="1fe29-130">Function 过程</span><span class="sxs-lookup"><span data-stu-id="1fe29-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="1fe29-131">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="1fe29-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="1fe29-132">Function 语句</span><span class="sxs-lookup"><span data-stu-id="1fe29-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="1fe29-133">如何：创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="1fe29-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="1fe29-134">如何：从过程返回值</span><span class="sxs-lookup"><span data-stu-id="1fe29-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="1fe29-135">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="1fe29-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
