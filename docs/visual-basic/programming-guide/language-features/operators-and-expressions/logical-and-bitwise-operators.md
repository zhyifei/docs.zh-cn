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
ms.openlocfilehash: 371d28629b39fb2808ca018ea69da3306a31f50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656147"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="6326a-102">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="6326a-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="6326a-103">逻辑运算符比较`Boolean`表达式，并返回`Boolean`结果。</span><span class="sxs-lookup"><span data-stu-id="6326a-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="6326a-104">`And`， `Or`， `AndAlso`， `OrElse`，和`Xor`运算符是*二进制*由于它们采用两个操作数，而`Not`运算符是*一元*因为它采用一个操作数。</span><span class="sxs-lookup"><span data-stu-id="6326a-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="6326a-105">某些这些运算符还可以执行对整数值的按位逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="6326a-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="6326a-106">一元逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="6326a-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="6326a-107">[Not 运算符](../../../../visual-basic/language-reference/operators/not-operator.md)执行逻辑*求反*上`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="6326a-108">它将产生其操作数的逻辑相反。</span><span class="sxs-lookup"><span data-stu-id="6326a-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="6326a-109">如果表达式计算结果为`True`，然后`Not`返回`False`; 如果表达式计算结果为`False`，然后`Not`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="6326a-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="6326a-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="6326a-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="6326a-111">二进制逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="6326a-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="6326a-112">[And 运算符](../../../../visual-basic/language-reference/operators/and-operator.md)执行逻辑*一起*对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="6326a-113">如果两个表达式的计算结果为`True`，然后`And`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="6326a-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="6326a-114">如果至少一个表达式计算结果为`False`，然后`And`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="6326a-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="6326a-115">[或运算符](../../../../visual-basic/language-reference/operators/or-operator.md)执行逻辑*析取*或*包含*对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="6326a-116">如果其中任何一个表达式的计算结果为`True`，或两者的计算结果`True`，然后`Or`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="6326a-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="6326a-117">如果表达式都不计算结果为`True`，`Or`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="6326a-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="6326a-118">[异或运算符](../../../../visual-basic/language-reference/operators/xor-operator.md)执行逻辑*排除*对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="6326a-119">如果只有一个表达式的计算结果为`True`，但不是两个`Xor`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="6326a-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="6326a-120">如果两个表达式的计算结果为`True`或两者的计算结果`False`，`Xor`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="6326a-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="6326a-121">下面的示例演示`And`， `Or`，和`Xor`运算符。</span><span class="sxs-lookup"><span data-stu-id="6326a-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="6326a-122">短路逻辑操作</span><span class="sxs-lookup"><span data-stu-id="6326a-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="6326a-123">[AndAlso 运算符](../../../../visual-basic/language-reference/operators/andalso-operator.md)非常类似于`And`运算符，在于它还执行逻辑与对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="6326a-124">两者之间的主要区别在于`AndAlso`表现出*短路*行为。</span><span class="sxs-lookup"><span data-stu-id="6326a-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="6326a-125">如果中的第一个表达式`AndAlso`表达式计算结果为`False`，则因为它不会改变最终结果，不会计算第二个表达式和`AndAlso`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="6326a-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="6326a-126">同样， [OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)执行短路逻辑或运算，对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="6326a-127">如果中的第一个表达式`OrElse`表达式计算结果为`True`，则因为它不会改变最终结果，不会计算第二个表达式和`OrElse`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="6326a-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="6326a-128">短路权衡</span><span class="sxs-lookup"><span data-stu-id="6326a-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="6326a-129">短路可以通过不计算表达式，无法更改逻辑操作的结果中提高性能。</span><span class="sxs-lookup"><span data-stu-id="6326a-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="6326a-130">但是，如果该表达式执行其他操作，则短路将跳过这些操作。</span><span class="sxs-lookup"><span data-stu-id="6326a-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="6326a-131">例如，如果表达式包含对的调用`Function`过程，如果表达式是短路，和中包含的任何其他代码不调用过程`Function`不会运行。</span><span class="sxs-lookup"><span data-stu-id="6326a-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="6326a-132">因此，该函数仅偶尔可能会运行，并可能未正确测试。</span><span class="sxs-lookup"><span data-stu-id="6326a-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="6326a-133">程序逻辑可能依赖于中的代码或`Function`。</span><span class="sxs-lookup"><span data-stu-id="6326a-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="6326a-134">下面的示例演示之间的差异`And`， `Or`，与其短路副本。</span><span class="sxs-lookup"><span data-stu-id="6326a-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 <span data-ttu-id="6326a-135">在前面的示例中，请注意，在一些重要代码`checkIfValid()`调用短路时不会运行。</span><span class="sxs-lookup"><span data-stu-id="6326a-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="6326a-136">第一个`If`语句也会调用`checkIfValid()`即使`12 > 45`返回`False`，这是因为`And`不会短路。</span><span class="sxs-lookup"><span data-stu-id="6326a-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="6326a-137">第二个`If`语句不会调用`checkIfValid()`，因为当`12 > 45`返回`False`，`AndAlso`会使短路第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="6326a-138">第三个`If`语句也会调用`checkIfValid()`即使`12 < 45`返回`True`，这是因为`Or`不会短路。</span><span class="sxs-lookup"><span data-stu-id="6326a-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="6326a-139">第四个`If`语句不会调用`checkIfValid()`，因为当`12 < 45`返回`True`，`OrElse`会使短路第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="6326a-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="6326a-140">按位运算</span><span class="sxs-lookup"><span data-stu-id="6326a-140">Bitwise Operations</span></span>  
 <span data-ttu-id="6326a-141">按位运算的计算结果在二进制 (基数为 2) 窗体中的两个整数值。</span><span class="sxs-lookup"><span data-stu-id="6326a-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="6326a-142">它们比较相应位置处的位，然后分配基于比较的值。</span><span class="sxs-lookup"><span data-stu-id="6326a-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="6326a-143">下面的示例演示`And`运算符。</span><span class="sxs-lookup"><span data-stu-id="6326a-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 <span data-ttu-id="6326a-144">前面的示例设置的值`x`为 1。</span><span class="sxs-lookup"><span data-stu-id="6326a-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="6326a-145">由于以下原因发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="6326a-145">This happens for the following reasons:</span></span>  
  
-   <span data-ttu-id="6326a-146">以二进制形式处理值：</span><span class="sxs-lookup"><span data-stu-id="6326a-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="6326a-147">以二进制形式的 3 = 011</span><span class="sxs-lookup"><span data-stu-id="6326a-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="6326a-148">以二进制形式的 5 = 101</span><span class="sxs-lookup"><span data-stu-id="6326a-148">5 in binary form = 101</span></span>  
  
-   <span data-ttu-id="6326a-149">`And`运算符比较二进制表示形式，一次的一个二进制位置 （位）。</span><span class="sxs-lookup"><span data-stu-id="6326a-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="6326a-150">如果位于给定位置两个位均为 1，1 都放在结果中的此位置。</span><span class="sxs-lookup"><span data-stu-id="6326a-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="6326a-151">如果其中一个位是 0，0 被置于结果中的此位置。</span><span class="sxs-lookup"><span data-stu-id="6326a-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="6326a-152">在前面的示例正常，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6326a-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="6326a-153">011 (3 以二进制形式)</span><span class="sxs-lookup"><span data-stu-id="6326a-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="6326a-154">101 (5 以二进制形式)</span><span class="sxs-lookup"><span data-stu-id="6326a-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="6326a-155">001 （以二进制形式，结果）</span><span class="sxs-lookup"><span data-stu-id="6326a-155">001 (The result, in binary form)</span></span>  
  
-   <span data-ttu-id="6326a-156">结果将被视为小数。</span><span class="sxs-lookup"><span data-stu-id="6326a-156">The result is treated as decimal.</span></span> <span data-ttu-id="6326a-157">001 的值是 1，二进制表示形式，因此`x`= 1。</span><span class="sxs-lookup"><span data-stu-id="6326a-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="6326a-158">按位`Or`操作非常相似，只不过 1 分配给结果位，如果一个或两个比较位为 1。</span><span class="sxs-lookup"><span data-stu-id="6326a-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="6326a-159">`Xor` 如果完全之一 （不是两者） 的比较位是 1，1 赋给结果位。</span><span class="sxs-lookup"><span data-stu-id="6326a-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="6326a-160">`Not` 采用单个操作数和反转所有位，包括符号位，并将该值赋给结果。</span><span class="sxs-lookup"><span data-stu-id="6326a-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="6326a-161">这意味着，对于有符号正数，`Not`始终返回一个负值，而对于负数，`Not`始终返回一个值为正或零值。</span><span class="sxs-lookup"><span data-stu-id="6326a-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="6326a-162">`AndAlso`和`OrElse`运算符不支持按位运算。</span><span class="sxs-lookup"><span data-stu-id="6326a-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6326a-163">只能对整型，可以执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="6326a-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="6326a-164">按位运算可以继续操作之前，必须为整型转换浮点值。</span><span class="sxs-lookup"><span data-stu-id="6326a-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6326a-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="6326a-165">See Also</span></span>  
 [<span data-ttu-id="6326a-166">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6326a-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="6326a-167">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="6326a-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="6326a-168">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="6326a-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="6326a-169">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="6326a-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="6326a-170">在 Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="6326a-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [<span data-ttu-id="6326a-171">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="6326a-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
