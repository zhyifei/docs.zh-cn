---
title: 布尔表达式 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 065df7d6217dd6f817dee1d11dd0fd4a68b6323c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965535"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="4b061-102">布尔表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b061-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="4b061-103">一个*布尔表达式*是表达式的计算结果为值[布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md):`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="4b061-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="4b061-104">`Boolean` 表达式可以采用多种形式。</span><span class="sxs-lookup"><span data-stu-id="4b061-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="4b061-105">简单的方法是直接的值的比较`Boolean`变量`Boolean`文本，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="4b061-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="4b061-106">两种含义的 = 运算符</span><span class="sxs-lookup"><span data-stu-id="4b061-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="4b061-107">请注意，在赋值语句`newCustomer = True`与在前面的示例中，表达式看起来相同，但它执行不同的功能，以不同的方式使用。</span><span class="sxs-lookup"><span data-stu-id="4b061-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="4b061-108">在前面的示例中，表达式`newCustomer = True`表示一个布尔值，和`=`符号被解释为比较运算符。</span><span class="sxs-lookup"><span data-stu-id="4b061-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="4b061-109">在独立语句中，`=`符号被解释为赋值运算符，分配给左侧变量右侧值。</span><span class="sxs-lookup"><span data-stu-id="4b061-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="4b061-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="4b061-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 <span data-ttu-id="4b061-111">有关详细信息，请参阅[值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)并[语句](../../../../visual-basic/language-reference/statements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4b061-111">For further information, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) and [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="4b061-112">比较运算符</span><span class="sxs-lookup"><span data-stu-id="4b061-112">Comparison Operators</span></span>  
 <span data-ttu-id="4b061-113">比较运算符，如`=`， `<`， `>`， `<>`， `<=`，并`>=`通过比较运算符右侧表达式的左侧和右侧表达式产生布尔表达式运算符和评估结果作为`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="4b061-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="4b061-114">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="4b061-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="4b061-115">由于 42 是小于 81，前面示例中的布尔表达式计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="4b061-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="4b061-116">此类表达式的详细信息，请参阅[值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)。</span><span class="sxs-lookup"><span data-stu-id="4b061-116">For more information on this kind of expression, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="4b061-117">与逻辑运算符结合使用的比较运算符</span><span class="sxs-lookup"><span data-stu-id="4b061-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="4b061-118">可以使用逻辑运算符以生成更复杂的布尔表达式组合比较表达式。</span><span class="sxs-lookup"><span data-stu-id="4b061-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="4b061-119">下面的示例演示如何将具有一个逻辑运算符结合使用的比较运算符。</span><span class="sxs-lookup"><span data-stu-id="4b061-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="4b061-120">在前面的示例中，整个表达式的值取决于每侧的表达式的值`And`运算符。</span><span class="sxs-lookup"><span data-stu-id="4b061-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="4b061-121">如果两个表达式均`True`，则整个表达式的计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="4b061-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="4b061-122">如果任一表达式`False`，则整个表达式的计算结果为`False`。</span><span class="sxs-lookup"><span data-stu-id="4b061-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="4b061-123">短路运算符</span><span class="sxs-lookup"><span data-stu-id="4b061-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="4b061-124">逻辑运算符`AndAlso`并`OrElse`表现出行为称为*短路*。</span><span class="sxs-lookup"><span data-stu-id="4b061-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="4b061-125">短路运算符首先计算左的操作数。</span><span class="sxs-lookup"><span data-stu-id="4b061-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="4b061-126">如果左的操作数确定整个表达式的值，然后程序执行继续进行而不计算右侧表达式。</span><span class="sxs-lookup"><span data-stu-id="4b061-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="4b061-127">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="4b061-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 <span data-ttu-id="4b061-128">在上述示例中，运算符将计算左侧的表达式`45 < 12`。</span><span class="sxs-lookup"><span data-stu-id="4b061-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="4b061-129">由于左侧的表达式的计算结果为`False`，整个逻辑表达式的计算结果必须为`False`。</span><span class="sxs-lookup"><span data-stu-id="4b061-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="4b061-130">程序执行因此将跳过执行中的代码`If`而无需计算右侧表达式块`testFunction(3)`。</span><span class="sxs-lookup"><span data-stu-id="4b061-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="4b061-131">此示例不会调用`testFunction()`因为左侧的表达式使整个表达式。</span><span class="sxs-lookup"><span data-stu-id="4b061-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="4b061-132">同样，如果左侧的表达式在逻辑表达式中使用`OrElse`计算结果为`True`，执行过程前进到下一行代码而无需计算右侧表达式，因为左侧的表达式已经证明整个表达式。</span><span class="sxs-lookup"><span data-stu-id="4b061-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="4b061-133">与非短路运算符的比较</span><span class="sxs-lookup"><span data-stu-id="4b061-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="4b061-134">与此相反，计算逻辑运算符的两端时逻辑运算符`And`和`Or`使用。</span><span class="sxs-lookup"><span data-stu-id="4b061-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="4b061-135">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="4b061-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 <span data-ttu-id="4b061-136">前面的示例调用`testFunction()`即使左侧的表达式的计算结果为`False`。</span><span class="sxs-lookup"><span data-stu-id="4b061-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="4b061-137">加括号的表达式</span><span class="sxs-lookup"><span data-stu-id="4b061-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="4b061-138">可以使用括号来控制的布尔表达式计算顺序。</span><span class="sxs-lookup"><span data-stu-id="4b061-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="4b061-139">首先计算由括号括起来的表达式。</span><span class="sxs-lookup"><span data-stu-id="4b061-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="4b061-140">多个层级的嵌套，优先将授予嵌套最深的表达式。</span><span class="sxs-lookup"><span data-stu-id="4b061-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="4b061-141">在括号内，评估会继续按照运算符优先级规则。</span><span class="sxs-lookup"><span data-stu-id="4b061-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="4b061-142">有关详细信息，请参阅[在 Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="4b061-142">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b061-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b061-143">See also</span></span>
- [<span data-ttu-id="4b061-144">在 Visual Basic 中的逻辑和位运算符</span><span class="sxs-lookup"><span data-stu-id="4b061-144">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="4b061-145">值的比较</span><span class="sxs-lookup"><span data-stu-id="4b061-145">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="4b061-146">语句</span><span class="sxs-lookup"><span data-stu-id="4b061-146">Statements</span></span>](../../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="4b061-147">比较运算符</span><span class="sxs-lookup"><span data-stu-id="4b061-147">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="4b061-148">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="4b061-148">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="4b061-149">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="4b061-149">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4b061-150">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="4b061-150">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
