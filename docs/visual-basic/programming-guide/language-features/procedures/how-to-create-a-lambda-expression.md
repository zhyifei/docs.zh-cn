---
title: 如何：创建一个 Lambda 表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344541"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="370f4-102">如何：创建一个 Lambda 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="370f4-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="370f4-103">一个*lambda 表达式*是函数或不具有名称的子例程。</span><span class="sxs-lookup"><span data-stu-id="370f4-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="370f4-104">委托类型有效的任何地方，可以使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="370f4-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="370f4-105">若要创建的单行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="370f4-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="370f4-106">在其中可以使用的委托类型的任何情况下，键入关键字`Function`，如下面的示例：</span><span class="sxs-lookup"><span data-stu-id="370f4-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="370f4-107">在括号内，紧`Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="370f4-107">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="370f4-108">请注意，未指定的名称后`Function`。</span><span class="sxs-lookup"><span data-stu-id="370f4-108">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. <span data-ttu-id="370f4-109">以下参数列表中，作为函数的正文中键入一个表达式。</span><span class="sxs-lookup"><span data-stu-id="370f4-109">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="370f4-110">表达式的计算结果的值是由函数返回的值。</span><span class="sxs-lookup"><span data-stu-id="370f4-110">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="370f4-111">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="370f4-111">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="370f4-112">调用 lambda 表达式将传递一个整数自变量中。</span><span class="sxs-lookup"><span data-stu-id="370f4-112">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="370f4-113">或者，使用下面的示例完成相同的结果：</span><span class="sxs-lookup"><span data-stu-id="370f4-113">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="370f4-114">若要创建的单行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="370f4-114">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="370f4-115">在其中可以使用的委托类型的任何情况下，键入关键字`Sub`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="370f4-115">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="370f4-116">在括号内，紧`Sub`，键入该子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="370f4-116">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="370f4-117">请注意，未指定的名称后`Sub`。</span><span class="sxs-lookup"><span data-stu-id="370f4-117">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. <span data-ttu-id="370f4-118">以下参数列表中，作为该子例程的正文中键入一条语句。</span><span class="sxs-lookup"><span data-stu-id="370f4-118">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="370f4-119">调用 lambda 表达式将传递一个字符串参数中。</span><span class="sxs-lookup"><span data-stu-id="370f4-119">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="370f4-120">若要创建多行 lambda 表达式函数</span><span class="sxs-lookup"><span data-stu-id="370f4-120">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="370f4-121">在其中可以使用的委托类型的任何情况下，键入关键字`Function`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="370f4-121">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="370f4-122">在括号内，紧`Function`，键入函数的参数。</span><span class="sxs-lookup"><span data-stu-id="370f4-122">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="370f4-123">请注意，未指定的名称后`Function`。</span><span class="sxs-lookup"><span data-stu-id="370f4-123">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. <span data-ttu-id="370f4-124">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="370f4-124">Press ENTER.</span></span> <span data-ttu-id="370f4-125">`End Function`语句会自动添加。</span><span class="sxs-lookup"><span data-stu-id="370f4-125">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="370f4-126">该函数体内，添加以下代码以创建一个表达式，返回的值。</span><span class="sxs-lookup"><span data-stu-id="370f4-126">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="370f4-127">不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="370f4-127">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="370f4-128">调用 lambda 表达式将传递一个整数自变量中。</span><span class="sxs-lookup"><span data-stu-id="370f4-128">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="370f4-129">若要创建多行 lambda 表达式子例程</span><span class="sxs-lookup"><span data-stu-id="370f4-129">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="370f4-130">在其中可以使用的委托类型的任何情况下，键入关键字`Sub`，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="370f4-130">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="370f4-131">在括号内，紧`Sub`，键入该子例程的参数。</span><span class="sxs-lookup"><span data-stu-id="370f4-131">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="370f4-132">请注意，未指定的名称后`Sub`。</span><span class="sxs-lookup"><span data-stu-id="370f4-132">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. <span data-ttu-id="370f4-133">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="370f4-133">Press ENTER.</span></span> <span data-ttu-id="370f4-134">`End Sub`语句会自动添加。</span><span class="sxs-lookup"><span data-stu-id="370f4-134">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="370f4-135">该函数体内，添加以下代码调用该子例程时要执行。</span><span class="sxs-lookup"><span data-stu-id="370f4-135">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="370f4-136">调用 lambda 表达式将传递一个字符串参数中。</span><span class="sxs-lookup"><span data-stu-id="370f4-136">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="370f4-137">示例</span><span class="sxs-lookup"><span data-stu-id="370f4-137">Example</span></span>  
 <span data-ttu-id="370f4-138">Lambda 表达式的一个常见用途是定义函数可以作为其类型的参数的参数中传递`Delegate`。</span><span class="sxs-lookup"><span data-stu-id="370f4-138">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="370f4-139">在以下示例中，<xref:System.Diagnostics.Process.GetProcesses%2A>方法返回在本地计算机上运行的进程的一个数组。</span><span class="sxs-lookup"><span data-stu-id="370f4-139">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="370f4-140"><xref:System.Linq.Enumerable.Where%2A>方法从<xref:System.Linq.Enumerable>类需要`Boolean`委托作为其参数。</span><span class="sxs-lookup"><span data-stu-id="370f4-140">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="370f4-141">在示例中的 lambda 表达式用于此目的。</span><span class="sxs-lookup"><span data-stu-id="370f4-141">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="370f4-142">它将返回`True`每个进程具有只有一个线程，并且已选择这些`filteredList`。</span><span class="sxs-lookup"><span data-stu-id="370f4-142">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="370f4-143">上一示例等效于以下代码，以编写[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]语法：</span><span class="sxs-lookup"><span data-stu-id="370f4-143">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="370f4-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="370f4-144">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="370f4-145">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="370f4-145">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="370f4-146">Function 语句</span><span class="sxs-lookup"><span data-stu-id="370f4-146">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="370f4-147">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="370f4-147">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="370f4-148">委托</span><span class="sxs-lookup"><span data-stu-id="370f4-148">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="370f4-149">如何：将过程传递给 Visual Basic 中的另一个过程</span><span class="sxs-lookup"><span data-stu-id="370f4-149">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="370f4-150">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="370f4-150">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="370f4-151">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="370f4-151">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
