---
title: "布尔表达式 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 48071c6833f9841fa42311dda59d6959c0645ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="e498a-102">布尔表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e498a-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="e498a-103">A*布尔表达式*是计算结果为的值的表达式[布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md):`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="e498a-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="e498a-104">`Boolean`表达式可以采用多种形式。</span><span class="sxs-lookup"><span data-stu-id="e498a-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="e498a-105">最简单的是直接比较的值的`Boolean`变量`Boolean`文本，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e498a-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="e498a-106">两种含义 = 运算符</span><span class="sxs-lookup"><span data-stu-id="e498a-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="e498a-107">请注意，赋值语句`newCustomer = True`与在前面的示例中，该表达式看上去相同但它执行不同的功能，并以不同的使用。</span><span class="sxs-lookup"><span data-stu-id="e498a-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="e498a-108">在前面的示例中，表达式`newCustomer = True`表示布尔值，与`=`号解释为一个比较运算符。</span><span class="sxs-lookup"><span data-stu-id="e498a-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="e498a-109">在独立的语句中，`=`登录解释为赋值运算符，并将分配给左侧变量右侧的值。</span><span class="sxs-lookup"><span data-stu-id="e498a-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="e498a-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="e498a-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 <span data-ttu-id="e498a-111">有关详细信息，请参阅[值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)和[语句](../../../../visual-basic/language-reference/statements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e498a-111">For further information, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) and [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="e498a-112">比较运算符</span><span class="sxs-lookup"><span data-stu-id="e498a-112">Comparison Operators</span></span>  
 <span data-ttu-id="e498a-113">比较运算符，如`=`， `<`， `>`， `<>`， `<=`，和`>=`通过比较运算符的表达式左侧的右侧表达式产生的 Boolean 表达式运算符和评估结果作为`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="e498a-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="e498a-114">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="e498a-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="e498a-115">由于 42 是小于 81，前面示例中的布尔表达式计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="e498a-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="e498a-116">这种类型的表达式的详细信息，请参阅[值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)。</span><span class="sxs-lookup"><span data-stu-id="e498a-116">For more information on this kind of expression, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="e498a-117">与逻辑运算符结合使用的比较运算符</span><span class="sxs-lookup"><span data-stu-id="e498a-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="e498a-118">可以使用逻辑运算符来生成更复杂的布尔表达式组合比较表达式。</span><span class="sxs-lookup"><span data-stu-id="e498a-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="e498a-119">下面的示例演示如何结合使用逻辑运算符的比较运算符的使用。</span><span class="sxs-lookup"><span data-stu-id="e498a-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="e498a-120">在前面的示例中，整个表达式的值取决于每一侧的表达式的值`And`运算符。</span><span class="sxs-lookup"><span data-stu-id="e498a-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="e498a-121">如果两个表达式均`True`，则整个表达式的计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="e498a-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="e498a-122">如果其中任何一个表达式是`False`，则整个表达式的计算结果为`False`。</span><span class="sxs-lookup"><span data-stu-id="e498a-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="e498a-123">短路运算符</span><span class="sxs-lookup"><span data-stu-id="e498a-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="e498a-124">逻辑运算符`AndAlso`和`OrElse`行为称为*短路*。</span><span class="sxs-lookup"><span data-stu-id="e498a-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="e498a-125">短路运算符首先计算左的操作数。</span><span class="sxs-lookup"><span data-stu-id="e498a-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="e498a-126">如果左的操作数确定整个表达式的值，程序执行过程而不计算右侧表达式。</span><span class="sxs-lookup"><span data-stu-id="e498a-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="e498a-127">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="e498a-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 <span data-ttu-id="e498a-128">在前面的示例中，在操作数的计算左侧的表达式， `45 < 12`。</span><span class="sxs-lookup"><span data-stu-id="e498a-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="e498a-129">因为左侧的表达式的计算结果为`False`，整个逻辑表达式的计算结果必须为`False`。</span><span class="sxs-lookup"><span data-stu-id="e498a-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="e498a-130">程序执行过程因此跳过执行中的代码`If`块而不计算右侧表达式， `testFunction(3)`。</span><span class="sxs-lookup"><span data-stu-id="e498a-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="e498a-131">此示例不会调用`testFunction()`因为左侧的表达式使整个表达式。</span><span class="sxs-lookup"><span data-stu-id="e498a-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="e498a-132">同样，如果左侧的表达式在逻辑表达式中使用`OrElse`计算结果为`True`，因为左侧的表达式已经证明整个，则执行将而不计算右侧表达式中，转到下一行代码表达式。</span><span class="sxs-lookup"><span data-stu-id="e498a-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="e498a-133">与非短路运算符比较</span><span class="sxs-lookup"><span data-stu-id="e498a-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="e498a-134">与此相反，计算逻辑运算符的两端时逻辑运算符`And`和`Or`使用。</span><span class="sxs-lookup"><span data-stu-id="e498a-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="e498a-135">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="e498a-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 <span data-ttu-id="e498a-136">前面的示例调用`testFunction()`即使左侧的表达式的计算结果为`False`。</span><span class="sxs-lookup"><span data-stu-id="e498a-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="e498a-137">带括号的表达式</span><span class="sxs-lookup"><span data-stu-id="e498a-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="e498a-138">可以使用括号来控制布尔表达式的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="e498a-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="e498a-139">首先计算用括号括起来的表达式。</span><span class="sxs-lookup"><span data-stu-id="e498a-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="e498a-140">针对多个级别的嵌套，优先授予嵌套最深的表达式。</span><span class="sxs-lookup"><span data-stu-id="e498a-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="e498a-141">在括号内，计算将继续按照运算符优先级规则。</span><span class="sxs-lookup"><span data-stu-id="e498a-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="e498a-142">有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="e498a-142">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e498a-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e498a-143">See Also</span></span>  
 [<span data-ttu-id="e498a-144">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="e498a-144">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="e498a-145">值的比较</span><span class="sxs-lookup"><span data-stu-id="e498a-145">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="e498a-146">语句</span><span class="sxs-lookup"><span data-stu-id="e498a-146">Statements</span></span>](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="e498a-147">比较运算符</span><span class="sxs-lookup"><span data-stu-id="e498a-147">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="e498a-148">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="e498a-148">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [<span data-ttu-id="e498a-149">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="e498a-149">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="e498a-150">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="e498a-150">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
