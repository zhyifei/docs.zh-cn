---
title: 如何：创建一个 Lambda 表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665931"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="38931-102">如何：创建一个 Lambda 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38931-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="38931-103">一个*lambda 表达式*是函数或不具有名称的子例程。</span><span class="sxs-lookup"><span data-stu-id="38931-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="38931-104">委托类型有效的任何地方，可以使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="38931-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="38931-105">若要创建的单行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="38931-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="38931-106">在其中可以使用的委托类型的任何情况下，键入关键字`Function`，如下面的示例：</span><span class="sxs-lookup"><span data-stu-id="38931-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="38931-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="38931-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="38931-108">在括号内，紧`Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="38931-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="38931-109">请注意，未指定的名称后`Function`。</span><span class="sxs-lookup"><span data-stu-id="38931-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="38931-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="38931-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="38931-111">以下参数列表中，作为函数的正文中键入一个表达式。</span><span class="sxs-lookup"><span data-stu-id="38931-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="38931-112">表达式的计算结果的值是由函数返回的值。</span><span class="sxs-lookup"><span data-stu-id="38931-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="38931-113">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="38931-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="38931-114">调用 lambda 表达式将传递一个整数自变量中。</span><span class="sxs-lookup"><span data-stu-id="38931-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="38931-115">或者，使用下面的示例完成相同的结果：</span><span class="sxs-lookup"><span data-stu-id="38931-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="38931-116">若要创建的单行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="38931-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="38931-117">在其中可以使用的委托类型的任何情况下，键入关键字`Sub`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="38931-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="38931-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="38931-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="38931-119">在括号内，紧`Sub`，键入该子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="38931-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="38931-120">请注意，未指定的名称后`Sub`。</span><span class="sxs-lookup"><span data-stu-id="38931-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="38931-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="38931-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="38931-122">以下参数列表中，作为该子例程的正文中键入一条语句。</span><span class="sxs-lookup"><span data-stu-id="38931-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="38931-123">调用 lambda 表达式将传递一个字符串参数中。</span><span class="sxs-lookup"><span data-stu-id="38931-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="38931-124">若要创建多行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="38931-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="38931-125">在其中可以使用的委托类型的任何情况下，键入关键字`Function`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="38931-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="38931-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="38931-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="38931-127">在括号内，紧`Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="38931-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="38931-128">请注意，未指定的名称后`Function`。</span><span class="sxs-lookup"><span data-stu-id="38931-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="38931-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="38931-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="38931-130">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="38931-130">Press ENTER.</span></span> <span data-ttu-id="38931-131">`End Function`语句会自动添加。</span><span class="sxs-lookup"><span data-stu-id="38931-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="38931-132">该函数体内，添加以下代码以创建一个表达式，返回的值。</span><span class="sxs-lookup"><span data-stu-id="38931-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="38931-133">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="38931-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="38931-134">调用 lambda 表达式将传递一个整数自变量中。</span><span class="sxs-lookup"><span data-stu-id="38931-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="38931-135">若要创建多行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="38931-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="38931-136">在其中可以使用的委托类型的任何情况下，键入关键字`Sub`，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="38931-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="38931-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="38931-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="38931-138">在括号内，紧`Sub`，键入该子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="38931-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="38931-139">请注意，未指定的名称后`Sub`。</span><span class="sxs-lookup"><span data-stu-id="38931-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="38931-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="38931-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="38931-141">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="38931-141">Press ENTER.</span></span> <span data-ttu-id="38931-142">`End Sub`语句会自动添加。</span><span class="sxs-lookup"><span data-stu-id="38931-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="38931-143">该函数体内，添加以下代码调用该子例程时要执行。</span><span class="sxs-lookup"><span data-stu-id="38931-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="38931-144">调用 lambda 表达式将传递一个字符串参数中。</span><span class="sxs-lookup"><span data-stu-id="38931-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="38931-145">示例</span><span class="sxs-lookup"><span data-stu-id="38931-145">Example</span></span>  
 <span data-ttu-id="38931-146">Lambda 表达式的一个常见用途是定义函数可以作为其类型的参数的参数中传递`Delegate`。</span><span class="sxs-lookup"><span data-stu-id="38931-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="38931-147">在以下示例中，<xref:System.Diagnostics.Process.GetProcesses%2A>方法返回在本地计算机上运行的进程的一个数组。</span><span class="sxs-lookup"><span data-stu-id="38931-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="38931-148"><xref:System.Linq.Enumerable.Where%2A>方法从<xref:System.Linq.Enumerable>类需要`Boolean`委托作为其参数。</span><span class="sxs-lookup"><span data-stu-id="38931-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="38931-149">在示例中的 lambda 表达式用于此目的。</span><span class="sxs-lookup"><span data-stu-id="38931-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="38931-150">它将返回`True`每个进程具有只有一个线程，并且已选择这些`filteredList`。</span><span class="sxs-lookup"><span data-stu-id="38931-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="38931-151">上一示例等效于以下代码，以编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]语法：</span><span class="sxs-lookup"><span data-stu-id="38931-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="38931-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="38931-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="38931-153">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="38931-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="38931-154">Function 语句</span><span class="sxs-lookup"><span data-stu-id="38931-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="38931-155">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="38931-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="38931-156">委托</span><span class="sxs-lookup"><span data-stu-id="38931-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="38931-157">如何：将过程传递给 Visual Basic 中的另一个过程</span><span class="sxs-lookup"><span data-stu-id="38931-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="38931-158">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="38931-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="38931-159">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="38931-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
