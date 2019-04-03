---
title: 如何：调用过程返回值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: ee80ae48a9b9bfae0afe8f0a2c6e7ebf047d9d36
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820381"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="e32ec-102">如何：调用过程返回值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e32ec-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="e32ec-103">一个`Function`过程返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="e32ec-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="e32ec-104">它通过调用包括其名称和参数放在右边的赋值语句或表达式中。</span><span class="sxs-lookup"><span data-stu-id="e32ec-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="e32ec-105">若要调用的表达式内 Function 过程</span><span class="sxs-lookup"><span data-stu-id="e32ec-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="e32ec-106">使用`Function`过程名称将使用变量的方法相同。</span><span class="sxs-lookup"><span data-stu-id="e32ec-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="e32ec-107">可以使用`Function`过程调用任何位置可以在表达式中使用的变量或常数。</span><span class="sxs-lookup"><span data-stu-id="e32ec-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="e32ec-108">过程名后面加上括号将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="e32ec-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e32ec-109">如果没有任何自变量，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="e32ec-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="e32ec-110">但是，使用括号使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="e32ec-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="e32ec-111">将参数放在括号中，由逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="e32ec-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e32ec-112">请确保提供的相同顺序中的自变量的`Function`过程定义的相应参数。</span><span class="sxs-lookup"><span data-stu-id="e32ec-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="e32ec-113">或者，您可以按名称传递一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="e32ec-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="e32ec-114">有关详细信息，请参阅[按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)。</span><span class="sxs-lookup"><span data-stu-id="e32ec-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="e32ec-115">从过程返回的值出现在中，只需作为值的表达式的变量或常数那样。</span><span class="sxs-lookup"><span data-stu-id="e32ec-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="e32ec-116">若要在赋值语句中调用的函数过程</span><span class="sxs-lookup"><span data-stu-id="e32ec-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="e32ec-117">使用`Function`过程名称之后等号 (`=`) 在赋值语句登录。</span><span class="sxs-lookup"><span data-stu-id="e32ec-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="e32ec-118">过程名后面加上括号将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="e32ec-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e32ec-119">如果没有任何自变量，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="e32ec-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="e32ec-120">但是，使用括号使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="e32ec-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="e32ec-121">将参数放在括号中，由逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="e32ec-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e32ec-122">请确保提供的相同顺序中的自变量的`Function`过程定义相应的参数，除非您按名称传递它们。</span><span class="sxs-lookup"><span data-stu-id="e32ec-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="e32ec-123">从过程返回的值存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="e32ec-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e32ec-124">示例</span><span class="sxs-lookup"><span data-stu-id="e32ec-124">Example</span></span>  
 <span data-ttu-id="e32ec-125">下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.Environ%2A>检索操作系统环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="e32ec-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="e32ec-126">第一个行调用`Environ`在表达式中，第二个行调用它在赋值语句中。</span><span class="sxs-lookup"><span data-stu-id="e32ec-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="e32ec-127">`Environ` 将变量名称作为其唯一的参数。</span><span class="sxs-lookup"><span data-stu-id="e32ec-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="e32ec-128">它返回到调用代码的变量的值。</span><span class="sxs-lookup"><span data-stu-id="e32ec-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="e32ec-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="e32ec-129">See also</span></span>

- [<span data-ttu-id="e32ec-130">Function 过程</span><span class="sxs-lookup"><span data-stu-id="e32ec-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="e32ec-131">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="e32ec-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e32ec-132">Function 语句</span><span class="sxs-lookup"><span data-stu-id="e32ec-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e32ec-133">如何：创建一个过程，返回一个值</span><span class="sxs-lookup"><span data-stu-id="e32ec-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="e32ec-134">如何：从过程返回值</span><span class="sxs-lookup"><span data-stu-id="e32ec-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="e32ec-135">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="e32ec-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
