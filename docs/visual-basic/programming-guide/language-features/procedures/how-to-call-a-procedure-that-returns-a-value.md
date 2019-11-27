---
title: 如何：调用返回值的过程
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 7f5d46babf31ea3c6babb29c0f1c08a23e51d598
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340732"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="89fad-102">如何：调用返回值的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89fad-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="89fad-103">`Function` 过程将值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="89fad-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="89fad-104">通过在赋值语句或表达式的右侧包含其名称和参数来调用它。</span><span class="sxs-lookup"><span data-stu-id="89fad-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="89fad-105">在表达式中调用函数过程</span><span class="sxs-lookup"><span data-stu-id="89fad-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="89fad-106">按照使用变量的相同方式使用 `Function` 过程名称。</span><span class="sxs-lookup"><span data-stu-id="89fad-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="89fad-107">可以在表达式中使用变量或常量的任何位置使用 `Function` 过程调用。</span><span class="sxs-lookup"><span data-stu-id="89fad-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="89fad-108">在过程名称后面加上括号，以将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="89fad-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="89fad-109">如果没有参数，则可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="89fad-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="89fad-110">不过，使用括号可使代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="89fad-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="89fad-111">将参数置于括号中的参数列表内，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="89fad-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="89fad-112">请确保以 `Function` 过程定义相应参数的相同顺序提供参数。</span><span class="sxs-lookup"><span data-stu-id="89fad-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="89fad-113">或者，您可以按名称传递一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="89fad-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="89fad-114">有关详细信息，请参阅[按位置和按名称传递参数](./passing-arguments-by-position-and-by-name.md)。</span><span class="sxs-lookup"><span data-stu-id="89fad-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="89fad-115">从过程返回的值将参与表达式，就像变量或常量的值一样。</span><span class="sxs-lookup"><span data-stu-id="89fad-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="89fad-116">在赋值语句中调用函数过程</span><span class="sxs-lookup"><span data-stu-id="89fad-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="89fad-117">在赋值语句中使用等号（`=`）后，使用 `Function` 过程名称。</span><span class="sxs-lookup"><span data-stu-id="89fad-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="89fad-118">在过程名称后面加上括号，以将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="89fad-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="89fad-119">如果没有参数，则可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="89fad-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="89fad-120">不过，使用括号可使代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="89fad-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="89fad-121">将参数置于括号中的参数列表内，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="89fad-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="89fad-122">请确保以 `Function` 过程定义相应参数的相同顺序提供参数，除非你按名称传递它们。</span><span class="sxs-lookup"><span data-stu-id="89fad-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="89fad-123">从过程返回的值存储在赋值语句左侧的变量或属性中。</span><span class="sxs-lookup"><span data-stu-id="89fad-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89fad-124">示例</span><span class="sxs-lookup"><span data-stu-id="89fad-124">Example</span></span>  
 <span data-ttu-id="89fad-125">下面的示例调用 Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> 来检索操作系统环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="89fad-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="89fad-126">第一行在表达式中调用 `Environ`，第二行在赋值语句中调用它。</span><span class="sxs-lookup"><span data-stu-id="89fad-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="89fad-127">`Environ` 采用变量名称作为其唯一参数。</span><span class="sxs-lookup"><span data-stu-id="89fad-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="89fad-128">它将变量的值返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="89fad-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="89fad-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89fad-129">See also</span></span>

- [<span data-ttu-id="89fad-130">Function 过程</span><span class="sxs-lookup"><span data-stu-id="89fad-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="89fad-131">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="89fad-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="89fad-132">Function 语句</span><span class="sxs-lookup"><span data-stu-id="89fad-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="89fad-133">如何：创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="89fad-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="89fad-134">如何：从过程返回值</span><span class="sxs-lookup"><span data-stu-id="89fad-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="89fad-135">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="89fad-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
