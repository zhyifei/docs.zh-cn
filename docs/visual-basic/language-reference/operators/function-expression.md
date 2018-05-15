---
title: 函数表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 29bf95a336b6f6ed5c9c310c9ea7575a91089361
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="96c24-102">函数表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96c24-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="96c24-103">声明的参数和定义函数 lambda 表达式的代码。</span><span class="sxs-lookup"><span data-stu-id="96c24-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c24-104">语法</span><span class="sxs-lookup"><span data-stu-id="96c24-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="96c24-105">部件</span><span class="sxs-lookup"><span data-stu-id="96c24-105">Parts</span></span>  
  
|<span data-ttu-id="96c24-106">术语</span><span class="sxs-lookup"><span data-stu-id="96c24-106">Term</span></span>|<span data-ttu-id="96c24-107">定义</span><span class="sxs-lookup"><span data-stu-id="96c24-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="96c24-108">可选。</span><span class="sxs-lookup"><span data-stu-id="96c24-108">Optional.</span></span> <span data-ttu-id="96c24-109">表示在此过程中的参数的本地变量名称的列表。</span><span class="sxs-lookup"><span data-stu-id="96c24-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="96c24-110">括号必须存在，即使列表为空。</span><span class="sxs-lookup"><span data-stu-id="96c24-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="96c24-111">请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="96c24-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="96c24-112">必须的。</span><span class="sxs-lookup"><span data-stu-id="96c24-112">Required.</span></span> <span data-ttu-id="96c24-113">单个表达式。</span><span class="sxs-lookup"><span data-stu-id="96c24-113">A single expression.</span></span> <span data-ttu-id="96c24-114">表达式的类型是函数的返回类型。</span><span class="sxs-lookup"><span data-stu-id="96c24-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="96c24-115">必须的。</span><span class="sxs-lookup"><span data-stu-id="96c24-115">Required.</span></span> <span data-ttu-id="96c24-116">返回一个值，通过使用的语句列表`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="96c24-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="96c24-117">(请参阅[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。)返回的类型是值的函数的返回类型。</span><span class="sxs-lookup"><span data-stu-id="96c24-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96c24-118">备注</span><span class="sxs-lookup"><span data-stu-id="96c24-118">Remarks</span></span>  
 <span data-ttu-id="96c24-119">A *lambda 表达式*是没有名称，用于计算并返回一个值的函数。</span><span class="sxs-lookup"><span data-stu-id="96c24-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="96c24-120">你可以使用 lambda 表达式任意位置可用作委托类型，除外的自变量`RemoveHandler`。</span><span class="sxs-lookup"><span data-stu-id="96c24-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="96c24-121">有关委托，而使用与委托的 lambda 表达式的详细信息，请参阅[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)和[宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。</span><span class="sxs-lookup"><span data-stu-id="96c24-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="96c24-122">Lambda 表达式语法</span><span class="sxs-lookup"><span data-stu-id="96c24-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="96c24-123">Lambda 表达式的语法类似于标准函数。</span><span class="sxs-lookup"><span data-stu-id="96c24-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="96c24-124">差异如下所示：</span><span class="sxs-lookup"><span data-stu-id="96c24-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="96c24-125">Lambda 表达式不具有名称。</span><span class="sxs-lookup"><span data-stu-id="96c24-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="96c24-126">Lambda 表达式不能具有修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="96c24-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="96c24-127">不使用 lambda 表达式`As`子句来指定函数的返回类型。</span><span class="sxs-lookup"><span data-stu-id="96c24-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="96c24-128">相反，从单行 lambda 表达式的主体，计算得出的值或多行 lambda 表达式的返回值推断的类型。</span><span class="sxs-lookup"><span data-stu-id="96c24-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="96c24-129">例如，如果单行 lambda 表达式的主体是`Where cust.City = "London"`，其返回类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="96c24-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="96c24-130">单行 lambda 表达式的主体必须是一个表达式，而不是语句。</span><span class="sxs-lookup"><span data-stu-id="96c24-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="96c24-131">主体可以包含的调用函数的过程，但未对 sub 过程的调用。</span><span class="sxs-lookup"><span data-stu-id="96c24-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="96c24-132">必须必须推断数据类型或所有具有指定任一所有参数。</span><span class="sxs-lookup"><span data-stu-id="96c24-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="96c24-133">不允许使用可选和 Paramarray 参数。</span><span class="sxs-lookup"><span data-stu-id="96c24-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="96c24-134">不允许泛型参数。</span><span class="sxs-lookup"><span data-stu-id="96c24-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96c24-135">示例</span><span class="sxs-lookup"><span data-stu-id="96c24-135">Example</span></span>  
 <span data-ttu-id="96c24-136">下面的示例演示两种方法创建的简单 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="96c24-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="96c24-137">第一个示例使用`Dim`提供函数的名称。</span><span class="sxs-lookup"><span data-stu-id="96c24-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="96c24-138">若要调用函数，您传递参数的值。</span><span class="sxs-lookup"><span data-stu-id="96c24-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="96c24-139">示例</span><span class="sxs-lookup"><span data-stu-id="96c24-139">Example</span></span>  
 <span data-ttu-id="96c24-140">或者，你可以声明并在同一时间运行此函数。</span><span class="sxs-lookup"><span data-stu-id="96c24-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="96c24-141">示例</span><span class="sxs-lookup"><span data-stu-id="96c24-141">Example</span></span>  
 <span data-ttu-id="96c24-142">下面是递增其参数并返回的值的 lambda 表达式的示例。</span><span class="sxs-lookup"><span data-stu-id="96c24-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="96c24-143">该示例演示这两个单行和多行 lambda 表达式语法的函数。</span><span class="sxs-lookup"><span data-stu-id="96c24-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="96c24-144">有关更多示例，请参阅[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="96c24-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="96c24-145">示例</span><span class="sxs-lookup"><span data-stu-id="96c24-145">Example</span></span>  
 <span data-ttu-id="96c24-146">Lambda 表达式生成的查询运算符中的许多[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]，并可以在基于方法的查询中显式使用。</span><span class="sxs-lookup"><span data-stu-id="96c24-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="96c24-147">以下示例演示一个典型[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询，为方法格式跟查询的转换。</span><span class="sxs-lookup"><span data-stu-id="96c24-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="96c24-148">有关查询方法的详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/queries.md)。</span><span class="sxs-lookup"><span data-stu-id="96c24-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="96c24-149">有关标准查询运算符的详细信息，请参阅[标准查询运算符概述](../../programming-guide/concepts/linq/standard-query-operators-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="96c24-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c24-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="96c24-150">See Also</span></span>  
 [<span data-ttu-id="96c24-151">Function 语句</span><span class="sxs-lookup"><span data-stu-id="96c24-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="96c24-152">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="96c24-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="96c24-153">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="96c24-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="96c24-154">语句</span><span class="sxs-lookup"><span data-stu-id="96c24-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="96c24-155">值的比较</span><span class="sxs-lookup"><span data-stu-id="96c24-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="96c24-156">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="96c24-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="96c24-157">If 运算符</span><span class="sxs-lookup"><span data-stu-id="96c24-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="96c24-158">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="96c24-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
