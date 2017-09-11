---
title: "如何︰ 创建 Lambda 表达式 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: edd475490dce81ff9cca32b5f9a5090d99f4d80d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="88609-102">如何：创建 Lambda 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88609-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="88609-103">一个*lambda 表达式*是函数或不具有名称的子例程。</span><span class="sxs-lookup"><span data-stu-id="88609-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="88609-104">委托类型有效的任何地方，则可以使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="88609-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="88609-105">若要创建的单行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="88609-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="88609-106">在任何情况下，可以使用一种委托类型的位置，键入关键字`Function`，下面的示例所示︰</span><span class="sxs-lookup"><span data-stu-id="88609-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="88609-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="88609-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="88609-108">在括号内，紧靠`Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="88609-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="88609-109">请注意不指定后的名称`Function`。</span><span class="sxs-lookup"><span data-stu-id="88609-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="88609-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="88609-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="88609-111">以下参数列表中，作为该函数的正文中键入一个表达式。</span><span class="sxs-lookup"><span data-stu-id="88609-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="88609-112">表达式计算结果的值是由函数返回的值。</span><span class="sxs-lookup"><span data-stu-id="88609-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="88609-113">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="88609-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="88609-114">[!code-vb[VbVbalrLambdas #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-114">[!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span></span>  
  
     <span data-ttu-id="88609-115">Lambda 表达式通过调用传入一个整数参数。</span><span class="sxs-lookup"><span data-stu-id="88609-115">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="88609-116">[!code-vb[VbVbalrLambdas #&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-116">[!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span></span>  
  
4.  <span data-ttu-id="88609-117">或者，相同的结果被通过下面的示例︰</span><span class="sxs-lookup"><span data-stu-id="88609-117">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     <span data-ttu-id="88609-118">[!code-vb[VbVbalrLambdas #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-118">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="88609-119">若要创建的单行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="88609-119">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="88609-120">在任何情况下，可以使用一种委托类型的位置，键入关键字`Sub`，如在下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="88609-120">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="88609-121">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="88609-121">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="88609-122">在括号内，紧靠`Sub`，键入该子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="88609-122">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="88609-123">请注意不指定后的名称`Sub`。</span><span class="sxs-lookup"><span data-stu-id="88609-123">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="88609-124">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="88609-124">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="88609-125">以下参数列表中，键入作为该子例程的正文的单个语句。</span><span class="sxs-lookup"><span data-stu-id="88609-125">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     <span data-ttu-id="88609-126">[!code-vb[VbVbalrLambdas #&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-126">[!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span></span>  
  
     <span data-ttu-id="88609-127">Lambda 表达式通过调用传入一个字符串参数。</span><span class="sxs-lookup"><span data-stu-id="88609-127">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="88609-128">[!code-vb[VbVbalrLambdas #&18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-128">[!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="88609-129">若要创建多行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="88609-129">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="88609-130">在任何情况下，可以使用一种委托类型的位置，键入关键字`Function`，如在下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="88609-130">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="88609-131">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="88609-131">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="88609-132">在括号内，紧靠`Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="88609-132">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="88609-133">请注意不指定后的名称`Function`。</span><span class="sxs-lookup"><span data-stu-id="88609-133">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="88609-134">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="88609-134">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="88609-135">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="88609-135">Press ENTER.</span></span> <span data-ttu-id="88609-136">`End Function`语句会自动添加。</span><span class="sxs-lookup"><span data-stu-id="88609-136">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="88609-137">该函数体内，添加以下代码以创建一个表达式，返回的值。</span><span class="sxs-lookup"><span data-stu-id="88609-137">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="88609-138">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="88609-138">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="88609-139">[!code-vb[VbVbalrLambdas #&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-139">[!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span></span>  
  
     <span data-ttu-id="88609-140">Lambda 表达式通过调用传入一个整数参数。</span><span class="sxs-lookup"><span data-stu-id="88609-140">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="88609-141">[!code-vb[VbVbalrLambdas #&20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-141">[!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="88609-142">若要创建多行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="88609-142">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="88609-143">在任何情况下，可以使用一种委托类型的位置，键入关键字`Sub`，如在下面的示例所示︰</span><span class="sxs-lookup"><span data-stu-id="88609-143">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="88609-144">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="88609-144">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="88609-145">在括号内，紧靠`Sub`，键入该子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="88609-145">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="88609-146">请注意不指定后的名称`Sub`。</span><span class="sxs-lookup"><span data-stu-id="88609-146">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="88609-147">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="88609-147">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="88609-148">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="88609-148">Press ENTER.</span></span> <span data-ttu-id="88609-149">`End Sub`语句会自动添加。</span><span class="sxs-lookup"><span data-stu-id="88609-149">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="88609-150">该函数体内，添加以下代码以调用该子例程时应执行。</span><span class="sxs-lookup"><span data-stu-id="88609-150">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     <span data-ttu-id="88609-151">[!code-vb[VbVbalrLambdas #&21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-151">[!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span></span>  
  
     <span data-ttu-id="88609-152">Lambda 表达式通过调用传入一个字符串参数。</span><span class="sxs-lookup"><span data-stu-id="88609-152">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="88609-153">[!code-vb[VbVbalrLambdas #&22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-153">[!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="88609-154">示例</span><span class="sxs-lookup"><span data-stu-id="88609-154">Example</span></span>  
 <span data-ttu-id="88609-155">Lambda 表达式的常见用途是定义一个函数，它可以作为参数的类型的参数中传递`Delegate`。</span><span class="sxs-lookup"><span data-stu-id="88609-155">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="88609-156">在下面的示例中，<xref:System.Diagnostics.Process.GetProcesses%2A>方法返回在本地计算机上运行的进程的数组。</xref:System.Diagnostics.Process.GetProcesses%2A></span><span class="sxs-lookup"><span data-stu-id="88609-156">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="88609-157"><xref:System.Linq.Enumerable.Where%2A>方法从<xref:System.Linq.Enumerable>类需要`Boolean`委托作为其参数。</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="88609-157">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="88609-158">该示例中的 lambda 表达式用于此目的。</span><span class="sxs-lookup"><span data-stu-id="88609-158">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="88609-159">它将返回`True`的每个进程，只有一个线程，并且初始屏幕中选择`filteredList`。</span><span class="sxs-lookup"><span data-stu-id="88609-159">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 <span data-ttu-id="88609-160">[!code-vb[VbVbalrLambdas #&10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-160">[!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span></span>  
  
 <span data-ttu-id="88609-161">上一个示例是等效于下面的代码中编写[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]语法︰</span><span class="sxs-lookup"><span data-stu-id="88609-161">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] syntax:</span></span>  
  
 <span data-ttu-id="88609-162">[!code-vb[VbVbalrLambdas #&11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="88609-162">[!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88609-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88609-163">See Also</span></span>  
 <span data-ttu-id="88609-164"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="88609-164"><xref:System.Linq.Enumerable></span></span>   
<span data-ttu-id="88609-165"> [Lambda 表达式](./lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="88609-165"> [Lambda Expressions](./lambda-expressions.md) </span></span>  
<span data-ttu-id="88609-166"> [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="88609-166"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="88609-167"> [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="88609-167"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="88609-168"> [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="88609-168"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="88609-169"> [如何︰ 将过程传递给在 Visual Basic 中的另一个过程](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="88609-169"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="88609-170"> [Delegate 语句](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="88609-170"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="88609-171"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="88609-171"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
