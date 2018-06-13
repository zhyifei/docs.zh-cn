---
title: 如何：创建 Lambda 表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: f437166bc5206b4145d6508aa2131ec94d6eca95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653541"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="e6c18-102">如何：创建 Lambda 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6c18-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="e6c18-103">A *lambda 表达式*是函数或子例程的不具有名称。</span><span class="sxs-lookup"><span data-stu-id="e6c18-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="e6c18-104">一个委托类型有效的任何地方，可以使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="e6c18-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="e6c18-105">若要创建的单行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="e6c18-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="e6c18-106">在委托类型可以使用其中任何情况下，键入关键字`Function`，下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="e6c18-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="e6c18-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="e6c18-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="e6c18-108">在括号内后直接, `Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="e6c18-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="e6c18-109">请注意，未指定的名称后`Function`。</span><span class="sxs-lookup"><span data-stu-id="e6c18-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="e6c18-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="e6c18-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="e6c18-111">以下参数列表中，作为函数的正文中键入一个表达式。</span><span class="sxs-lookup"><span data-stu-id="e6c18-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="e6c18-112">表达式计算结果为的值是由该函数返回的值。</span><span class="sxs-lookup"><span data-stu-id="e6c18-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="e6c18-113">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="e6c18-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     <span data-ttu-id="e6c18-114">调用 lambda 表达式传入一个整数自变量。</span><span class="sxs-lookup"><span data-stu-id="e6c18-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  <span data-ttu-id="e6c18-115">或者，按下面的示例被实现的相同的结果：</span><span class="sxs-lookup"><span data-stu-id="e6c18-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="e6c18-116">若要创建的单行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="e6c18-116">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="e6c18-117">在委托类型可以使用其中任何情况下，键入关键字`Sub`，下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e6c18-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="e6c18-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="e6c18-118">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="e6c18-119">在括号内后直接, `Sub`，键入子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="e6c18-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="e6c18-120">请注意，未指定的名称后`Sub`。</span><span class="sxs-lookup"><span data-stu-id="e6c18-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="e6c18-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="e6c18-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="e6c18-122">以下参数列表中，键入作为子例程的正文的单个语句。</span><span class="sxs-lookup"><span data-stu-id="e6c18-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     <span data-ttu-id="e6c18-123">Lambda 表达式通过调用传递一个字符串自变量中。</span><span class="sxs-lookup"><span data-stu-id="e6c18-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="e6c18-124">若要创建一个多行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="e6c18-124">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="e6c18-125">在委托类型可以使用其中任何情况下，键入关键字`Function`，下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e6c18-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="e6c18-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="e6c18-126">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="e6c18-127">在括号内后直接, `Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="e6c18-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="e6c18-128">请注意，未指定的名称后`Function`。</span><span class="sxs-lookup"><span data-stu-id="e6c18-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="e6c18-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="e6c18-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="e6c18-130">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="e6c18-130">Press ENTER.</span></span> <span data-ttu-id="e6c18-131">`End Function`自动添加语句。</span><span class="sxs-lookup"><span data-stu-id="e6c18-131">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="e6c18-132">该函数体内，添加以下代码以创建一个表达式并返回值。</span><span class="sxs-lookup"><span data-stu-id="e6c18-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="e6c18-133">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="e6c18-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     <span data-ttu-id="e6c18-134">调用 lambda 表达式传入一个整数自变量。</span><span class="sxs-lookup"><span data-stu-id="e6c18-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="e6c18-135">若要创建多行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="e6c18-135">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="e6c18-136">在委托类型可以使用其中任何情况下，键入关键字`Sub`，下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="e6c18-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="e6c18-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="e6c18-137">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="e6c18-138">在括号内后直接, `Sub`，键入子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="e6c18-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="e6c18-139">请注意，未指定的名称后`Sub`。</span><span class="sxs-lookup"><span data-stu-id="e6c18-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="e6c18-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="e6c18-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="e6c18-141">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="e6c18-141">Press ENTER.</span></span> <span data-ttu-id="e6c18-142">`End Sub`自动添加语句。</span><span class="sxs-lookup"><span data-stu-id="e6c18-142">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="e6c18-143">该函数体内，添加以下代码以调用子例程时应执行。</span><span class="sxs-lookup"><span data-stu-id="e6c18-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     <span data-ttu-id="e6c18-144">Lambda 表达式通过调用传递一个字符串自变量中。</span><span class="sxs-lookup"><span data-stu-id="e6c18-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a><span data-ttu-id="e6c18-145">示例</span><span class="sxs-lookup"><span data-stu-id="e6c18-145">Example</span></span>  
 <span data-ttu-id="e6c18-146">Lambda 表达式的一个常见用途是定义的函数，可以在作为其类型参数的自变量传递`Delegate`。</span><span class="sxs-lookup"><span data-stu-id="e6c18-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="e6c18-147">在下面的示例中，<xref:System.Diagnostics.Process.GetProcesses%2A>方法返回在本地计算机上运行的进程的数组。</span><span class="sxs-lookup"><span data-stu-id="e6c18-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="e6c18-148"><xref:System.Linq.Enumerable.Where%2A>方法从<xref:System.Linq.Enumerable>类要求`Boolean`委托作为其自变量。</span><span class="sxs-lookup"><span data-stu-id="e6c18-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="e6c18-149">示例中的 lambda 表达式用于此目的。</span><span class="sxs-lookup"><span data-stu-id="e6c18-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="e6c18-150">它将返回`True`每个进程，只有一个线程，并且初始屏幕中选择`filteredList`。</span><span class="sxs-lookup"><span data-stu-id="e6c18-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 <span data-ttu-id="e6c18-151">前面的示例是等效于下面的代码，以编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]语法：</span><span class="sxs-lookup"><span data-stu-id="e6c18-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e6c18-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6c18-152">See Also</span></span>  
 <xref:System.Linq.Enumerable>  
 [<span data-ttu-id="e6c18-153">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="e6c18-153">Lambda Expressions</span></span>](./lambda-expressions.md)  
 [<span data-ttu-id="e6c18-154">Function 语句</span><span class="sxs-lookup"><span data-stu-id="e6c18-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="e6c18-155">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="e6c18-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="e6c18-156">委托</span><span class="sxs-lookup"><span data-stu-id="e6c18-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="e6c18-157">如何：在 Visual Basic 中将过程传递给另一过程</span><span class="sxs-lookup"><span data-stu-id="e6c18-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [<span data-ttu-id="e6c18-158">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="e6c18-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="e6c18-159">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="e6c18-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
