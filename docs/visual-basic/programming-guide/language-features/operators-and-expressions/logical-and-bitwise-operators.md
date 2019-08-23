---
title: Visual Basic 中的逻辑运算符和位运算符
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 40076b2ad6606b4c565bcd39dbeea9e55da47211
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963316"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="76efe-102">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="76efe-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="76efe-103">逻辑运算符比较`Boolean`表达式并`Boolean`返回结果。</span><span class="sxs-lookup"><span data-stu-id="76efe-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="76efe-104">`And` 、`Or`、 `Not` 、和`OrElse`运算符都是二进制, 因为运算符采用两个操作数, 而运算符是*一元*, 因为它采用单个操作数。 `AndAlso` `Xor`</span><span class="sxs-lookup"><span data-stu-id="76efe-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="76efe-105">其中一些运算符还可以对整数值执行按位逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="76efe-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="76efe-106">一元逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="76efe-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="76efe-107">[Not 运算符](../../../../visual-basic/language-reference/operators/not-operator.md)对`Boolean`表达式执行逻辑非*运算*。</span><span class="sxs-lookup"><span data-stu-id="76efe-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="76efe-108">它生成其操作数的逻辑相反。</span><span class="sxs-lookup"><span data-stu-id="76efe-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="76efe-109">如果表达式的计算结果`True`为, `Not`则`False`返回`False` `Not` ;`True`如果表达式的计算结果为, 则返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="76efe-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="76efe-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="76efe-111">二元逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="76efe-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="76efe-112">[And 运算符](../../../../visual-basic/language-reference/operators/and-operator.md)对两个 `Boolean`表达式执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="76efe-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="76efe-113">如果两个表达式的`True`计算结果`And`都`True`为, 则返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="76efe-114">如果至少有一个表达式的计算结果为`False`, 则`And`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="76efe-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="76efe-115">[Or 运算符](../../../../visual-basic/language-reference/operators/or-operator.md)对两个 `Boolean`表达式执行逻辑或*运算*。</span><span class="sxs-lookup"><span data-stu-id="76efe-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="76efe-116">如果两个表达式的`True`计算结果为, 或`True`均为`Or`计算`True`结果, 则返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="76efe-117">如果两个表达式的`True`计算`Or`结果`False`均为, 则返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="76efe-118">[Xor 运算符](../../../../visual-basic/language-reference/operators/xor-operator.md)对两个 `Boolean`表达式执行逻辑异运算。</span><span class="sxs-lookup"><span data-stu-id="76efe-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="76efe-119">如果恰好一个表达式的计算`True`结果为, 而不`Xor`是`True`同时返回, 则返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="76efe-120">如果两个表达式的`True`计算结果都为`False`, 或者`False`都为, `Xor`则返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="76efe-121">下面的示例演示`And`了、 `Or`和`Xor`运算符。</span><span class="sxs-lookup"><span data-stu-id="76efe-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="76efe-122">短路逻辑运算</span><span class="sxs-lookup"><span data-stu-id="76efe-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="76efe-123">[AndAlso 运算符](../../../../visual-basic/language-reference/operators/andalso-operator.md)与`And`运算符非常类似, 因为它还对两个`Boolean`表达式执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="76efe-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="76efe-124">这两者`AndAlso`之间的主要区别在于表现*短路*行为。</span><span class="sxs-lookup"><span data-stu-id="76efe-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="76efe-125">如果`AndAlso`表达式中的第一个表达式的计算`False`结果为, 则不会计算第二个表达式, 因为它不能更改`AndAlso`最终`False`结果, 并返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="76efe-126">同样, [OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)对两个`Boolean`表达式执行短路逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="76efe-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="76efe-127">如果`OrElse`表达式中的第一个表达式的计算`True`结果为, 则不会计算第二个表达式, 因为它不能更改`OrElse`最终`True`结果, 并返回。</span><span class="sxs-lookup"><span data-stu-id="76efe-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="76efe-128">短路权衡</span><span class="sxs-lookup"><span data-stu-id="76efe-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="76efe-129">短路可以通过不计算无法更改逻辑操作结果的表达式来提高性能。</span><span class="sxs-lookup"><span data-stu-id="76efe-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="76efe-130">但是, 如果该表达式执行其他操作, 则短路将跳过这些操作。</span><span class="sxs-lookup"><span data-stu-id="76efe-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="76efe-131">例如, 如果表达式包含对`Function`过程的调用, 则在表达式为短路时不会调用该过程, 并且中包含的`Function`任何其他代码都不会运行。</span><span class="sxs-lookup"><span data-stu-id="76efe-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="76efe-132">因此, 该函数可能会偶尔运行, 并且可能无法正确测试。</span><span class="sxs-lookup"><span data-stu-id="76efe-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="76efe-133">或程序逻辑可能依赖于中`Function`的代码。</span><span class="sxs-lookup"><span data-stu-id="76efe-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="76efe-134">下面的示例演示了、 `And` `Or`和其短路对应项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="76efe-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 <span data-ttu-id="76efe-135">在前面的示例中, 请注意, 当调用`checkIfValid()`短路时, 中的一些重要代码不会运行。</span><span class="sxs-lookup"><span data-stu-id="76efe-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="76efe-136">即使`12 > 45`返回`If` `checkIfValid()` ,第`And`一条语句也会调用, 因为不会进行短路。 `False`</span><span class="sxs-lookup"><span data-stu-id="76efe-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="76efe-137">第二`If`个语句不调用`checkIfValid()`, 因为当`12 > 45`返回`False`时`AndAlso` , 会将第二个表达式短路。</span><span class="sxs-lookup"><span data-stu-id="76efe-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="76efe-138">即使`12 < 45`返回`If` `checkIfValid()` ,第`Or`三条语句也会调用, 因为不会进行短路。 `True`</span><span class="sxs-lookup"><span data-stu-id="76efe-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="76efe-139">第四`If`个语句不调用`checkIfValid()`, 因为当`12 < 45`返回`True`时`OrElse` , 会将第二个表达式短路。</span><span class="sxs-lookup"><span data-stu-id="76efe-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="76efe-140">按位运算</span><span class="sxs-lookup"><span data-stu-id="76efe-140">Bitwise Operations</span></span>  
 <span data-ttu-id="76efe-141">按位运算以二进制 (以2为底) 形式计算两个整数值。</span><span class="sxs-lookup"><span data-stu-id="76efe-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="76efe-142">它们比较相应位置上的位, 然后基于比较分配值。</span><span class="sxs-lookup"><span data-stu-id="76efe-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="76efe-143">下面的示例阐释`And`运算符。</span><span class="sxs-lookup"><span data-stu-id="76efe-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 <span data-ttu-id="76efe-144">前面的示例将的`x`值设置为1。</span><span class="sxs-lookup"><span data-stu-id="76efe-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="76efe-145">出现这种情况的原因如下:</span><span class="sxs-lookup"><span data-stu-id="76efe-145">This happens for the following reasons:</span></span>  
  
- <span data-ttu-id="76efe-146">值被视为 binary:</span><span class="sxs-lookup"><span data-stu-id="76efe-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="76efe-147">二进制格式的 3 = 011</span><span class="sxs-lookup"><span data-stu-id="76efe-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="76efe-148">二进制格式的 5 = 101</span><span class="sxs-lookup"><span data-stu-id="76efe-148">5 in binary form = 101</span></span>  
  
- <span data-ttu-id="76efe-149">`And`运算符比较二进制表示形式, 一次比较一个二进制位置 (位)。</span><span class="sxs-lookup"><span data-stu-id="76efe-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="76efe-150">如果给定位置处的两个位均为 1, 则将1置于结果中的该位置。</span><span class="sxs-lookup"><span data-stu-id="76efe-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="76efe-151">如果任一位为 0, 则将0放入结果中的该位置。</span><span class="sxs-lookup"><span data-stu-id="76efe-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="76efe-152">在前面的示例中, 此过程如下所示:</span><span class="sxs-lookup"><span data-stu-id="76efe-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="76efe-153">011 (二进制格式的 3)</span><span class="sxs-lookup"><span data-stu-id="76efe-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="76efe-154">101 (二进制格式的 5)</span><span class="sxs-lookup"><span data-stu-id="76efe-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="76efe-155">001 (二进制格式的结果)</span><span class="sxs-lookup"><span data-stu-id="76efe-155">001 (The result, in binary form)</span></span>  
  
- <span data-ttu-id="76efe-156">结果被视为 decimal。</span><span class="sxs-lookup"><span data-stu-id="76efe-156">The result is treated as decimal.</span></span> <span data-ttu-id="76efe-157">值001是1的二进制表示形式, 因此`x` = 1。</span><span class="sxs-lookup"><span data-stu-id="76efe-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="76efe-158">按位`Or`运算类似, 不同之处在于, 如果两个比较位中有一个或两个均为 1, 则将1分配给结果位。</span><span class="sxs-lookup"><span data-stu-id="76efe-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="76efe-159">`Xor`如果一个比较位 (不是两者) 为 1, 则将1指定给结果位。</span><span class="sxs-lookup"><span data-stu-id="76efe-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="76efe-160">`Not`采用单个操作数并反转所有位 (包括符号位), 并将该值分配给结果。</span><span class="sxs-lookup"><span data-stu-id="76efe-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="76efe-161">这意味着, 对于有符号正数, `Not`始终返回负值, 对于负数, `Not`始终返回正值或零值。</span><span class="sxs-lookup"><span data-stu-id="76efe-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="76efe-162">`AndAlso` 和`OrElse`运算符不支持按位运算。</span><span class="sxs-lookup"><span data-stu-id="76efe-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76efe-163">只能对整数类型执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="76efe-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="76efe-164">必须先将浮点值转换为整数类型, 然后才能继续执行位运算。</span><span class="sxs-lookup"><span data-stu-id="76efe-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76efe-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="76efe-165">See also</span></span>

- [<span data-ttu-id="76efe-166">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76efe-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="76efe-167">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="76efe-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="76efe-168">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="76efe-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="76efe-169">Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="76efe-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="76efe-170">Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="76efe-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="76efe-171">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="76efe-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
