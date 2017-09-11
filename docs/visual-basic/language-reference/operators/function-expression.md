---
title: "函数表达式 (Visual Basic 中) |Microsoft 文档"
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
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: c379ed1694f72243ccb8367d5b820803b4fcf190
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="64f39-102">函数表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64f39-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="64f39-103">声明的参数和函数的 lambda 表达式定义的代码。</span><span class="sxs-lookup"><span data-stu-id="64f39-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f39-104">语法</span><span class="sxs-lookup"><span data-stu-id="64f39-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="64f39-105">部件</span><span class="sxs-lookup"><span data-stu-id="64f39-105">Parts</span></span>  
  
|<span data-ttu-id="64f39-106">术语</span><span class="sxs-lookup"><span data-stu-id="64f39-106">Term</span></span>|<span data-ttu-id="64f39-107">定义</span><span class="sxs-lookup"><span data-stu-id="64f39-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="64f39-108">可选。</span><span class="sxs-lookup"><span data-stu-id="64f39-108">Optional.</span></span> <span data-ttu-id="64f39-109">本地变量的名称，表示此过程的参数的列表。</span><span class="sxs-lookup"><span data-stu-id="64f39-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="64f39-110">括号必须存在，即使该列表为空。</span><span class="sxs-lookup"><span data-stu-id="64f39-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="64f39-111">请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="64f39-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="64f39-112">必需。</span><span class="sxs-lookup"><span data-stu-id="64f39-112">Required.</span></span> <span data-ttu-id="64f39-113">单个表达式。</span><span class="sxs-lookup"><span data-stu-id="64f39-113">A single expression.</span></span> <span data-ttu-id="64f39-114">表达式的类型是该函数的返回类型。</span><span class="sxs-lookup"><span data-stu-id="64f39-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="64f39-115">必需。</span><span class="sxs-lookup"><span data-stu-id="64f39-115">Required.</span></span> <span data-ttu-id="64f39-116">返回一个值，通过使用语句的列表`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="64f39-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="64f39-117">(请参阅[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。)返回的值的类型为该函数的返回类型。</span><span class="sxs-lookup"><span data-stu-id="64f39-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64f39-118">备注</span><span class="sxs-lookup"><span data-stu-id="64f39-118">Remarks</span></span>  
 <span data-ttu-id="64f39-119">一个*lambda 表达式*是没有名称，用于计算并返回一个值的函数。</span><span class="sxs-lookup"><span data-stu-id="64f39-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="64f39-120">您可以使用 lambda 表达式任意位置可用作委托类型，除参数`RemoveHandler`。</span><span class="sxs-lookup"><span data-stu-id="64f39-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="64f39-121">有关委托和使用委托的 lambda 表达式的用法的详细信息，请参阅[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)和[宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。</span><span class="sxs-lookup"><span data-stu-id="64f39-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="64f39-122">Lambda 表达式语法</span><span class="sxs-lookup"><span data-stu-id="64f39-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="64f39-123">Lambda 表达式的语法类似于标准函数。</span><span class="sxs-lookup"><span data-stu-id="64f39-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="64f39-124">区别，如下所示如下︰</span><span class="sxs-lookup"><span data-stu-id="64f39-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="64f39-125">Lambda 表达式不具有一个名称。</span><span class="sxs-lookup"><span data-stu-id="64f39-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="64f39-126">Lambda 表达式不能具有修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="64f39-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="64f39-127">不使用 lambda 表达式`As`子句来指定该函数的返回类型。</span><span class="sxs-lookup"><span data-stu-id="64f39-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="64f39-128">相反，该类型被推断从单行 lambda 表达式的主体，计算得出的值或多行 lambda 表达式的返回值。</span><span class="sxs-lookup"><span data-stu-id="64f39-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="64f39-129">例如，如果单行 lambda 表达式的主体是`Where cust.City = "London"`，其返回类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="64f39-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="64f39-130">单行 lambda 表达式的主体必须是一个表达式，而不是语句。</span><span class="sxs-lookup"><span data-stu-id="64f39-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="64f39-131">主体可以包含的调用函数的过程，但未对一个 sub 过程的调用。</span><span class="sxs-lookup"><span data-stu-id="64f39-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="64f39-132">必须必须推断数据类型或所有已经指定所有参数。</span><span class="sxs-lookup"><span data-stu-id="64f39-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="64f39-133">不允许使用可选和 Paramarray 参数。</span><span class="sxs-lookup"><span data-stu-id="64f39-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="64f39-134">不允许泛型参数。</span><span class="sxs-lookup"><span data-stu-id="64f39-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f39-135">示例</span><span class="sxs-lookup"><span data-stu-id="64f39-135">Example</span></span>  
 <span data-ttu-id="64f39-136">下面的示例演示两种方法可以创建简单的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="64f39-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="64f39-137">第一个使用`Dim`提供该函数的名称。</span><span class="sxs-lookup"><span data-stu-id="64f39-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="64f39-138">若要调用函数时，您传递参数的值。</span><span class="sxs-lookup"><span data-stu-id="64f39-138">To call the function, you send in a value for the parameter.</span></span>  
  
 <span data-ttu-id="64f39-139">[!code-vb[VbVbalrLambdas #&1;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="64f39-139">[!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span></span>  
  
 <span data-ttu-id="64f39-140">[!code-vb[VbVbalrLambdas #&2;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="64f39-140">[!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f39-141">示例</span><span class="sxs-lookup"><span data-stu-id="64f39-141">Example</span></span>  
 <span data-ttu-id="64f39-142">或者，可以声明并在同一时间运行该函数。</span><span class="sxs-lookup"><span data-stu-id="64f39-142">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 <span data-ttu-id="64f39-143">[!code-vb[VbVbalrLambdas #&3;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="64f39-143">[!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f39-144">示例</span><span class="sxs-lookup"><span data-stu-id="64f39-144">Example</span></span>  
 <span data-ttu-id="64f39-145">下面是递增其参数并返回的值的 lambda 表达式的示例。</span><span class="sxs-lookup"><span data-stu-id="64f39-145">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="64f39-146">该示例同时显示的单行和多行 lambda 表达式语法的函数。</span><span class="sxs-lookup"><span data-stu-id="64f39-146">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="64f39-147">有关更多示例，请参阅[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="64f39-147">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="64f39-148">[!code-vb[VbVbalrLambdas #&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="64f39-148">[!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="64f39-149">示例</span><span class="sxs-lookup"><span data-stu-id="64f39-149">Example</span></span>  
 <span data-ttu-id="64f39-150">Lambda 表达式是基础中的查询运算符的许多[!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)]，并可以在基于方法的查询中显式使用。</span><span class="sxs-lookup"><span data-stu-id="64f39-150">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="64f39-151">下面的示例显示了典型[!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)]查询，然后再查询的平移到方法格式。</span><span class="sxs-lookup"><span data-stu-id="64f39-151">The following example shows a typical [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="64f39-152">有关查询方法的详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/queries.md)。</span><span class="sxs-lookup"><span data-stu-id="64f39-152">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="64f39-153">有关标准查询运算符的详细信息，请参阅[标准查询运算符概述](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)。</span><span class="sxs-lookup"><span data-stu-id="64f39-153">For more information about standard query operators, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f39-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64f39-154">See Also</span></span>  
 <span data-ttu-id="64f39-155">[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="64f39-155">[Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="64f39-156"> [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="64f39-156"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="64f39-157"> [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="64f39-157"> [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="64f39-158"> [语句](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="64f39-158"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="64f39-159"> [值的比较](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="64f39-159"> [Value Comparisons](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="64f39-160"> [布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="64f39-160"> [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span></span>  
<span data-ttu-id="64f39-161"> [如果运算符](../../../visual-basic/language-reference/operators/if-operator.md) </span><span class="sxs-lookup"><span data-stu-id="64f39-161"> [If Operator](../../../visual-basic/language-reference/operators/if-operator.md) </span></span>  
<span data-ttu-id="64f39-162"> [宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="64f39-162"> [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

