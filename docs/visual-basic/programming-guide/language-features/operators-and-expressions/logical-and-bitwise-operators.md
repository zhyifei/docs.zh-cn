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
ms.openlocfilehash: 23f3758527b787551ad83cbd4e19076b788c9dd8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649698"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="65245-102">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="65245-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="65245-103">逻辑运算符比较`Boolean`表达式，并返回`Boolean`结果。</span><span class="sxs-lookup"><span data-stu-id="65245-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="65245-104">`And`， `Or`， `AndAlso`， `OrElse`，并`Xor`运算符是*二进制*因为它们采用两个操作数，而`Not`运算符是*一元*因为它采用单个操作数。</span><span class="sxs-lookup"><span data-stu-id="65245-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="65245-105">这些运算符的一些可以执行对整数值的按位逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="65245-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="65245-106">一元逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="65245-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="65245-107">[Not 运算符](../../../../visual-basic/language-reference/operators/not-operator.md)执行逻辑*求反运算*上`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="65245-108">它将产生其操作数的逻辑反。</span><span class="sxs-lookup"><span data-stu-id="65245-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="65245-109">如果表达式的计算结果`True`，然后`Not`返回`False`; 如果表达式的计算结果`False`，然后`Not`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="65245-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="65245-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="65245-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="65245-111">二元逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="65245-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="65245-112">[And 运算符](../../../../visual-basic/language-reference/operators/and-operator.md)执行逻辑*一起*对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="65245-113">如果这两个表达式的计算结果为`True`，然后`And`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="65245-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="65245-114">如果至少一个表达式的计算结果为`False`，然后`And`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="65245-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="65245-115">[或运算符](../../../../visual-basic/language-reference/operators/or-operator.md)执行逻辑*析取*或*包含*对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="65245-116">如果任一表达式计算结果为`True`，或两者的计算结果`True`，然后`Or`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="65245-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="65245-117">如果任一表达式计算结果为`True`，`Or`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="65245-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="65245-118">[Xor 运算符](../../../../visual-basic/language-reference/operators/xor-operator.md)执行逻辑*排除*对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="65245-119">如果一个表达式的计算结果为`True`，但不是能同时`Xor`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="65245-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="65245-120">如果这两个表达式的计算结果为`True`或两者的计算结果`False`，`Xor`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="65245-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="65245-121">下面的示例阐释`And`， `Or`，和`Xor`运算符。</span><span class="sxs-lookup"><span data-stu-id="65245-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="65245-122">短路逻辑操作</span><span class="sxs-lookup"><span data-stu-id="65245-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="65245-123">[AndAlso 运算符](../../../../visual-basic/language-reference/operators/andalso-operator.md)非常类似于`And`运算符，在于它还对两个执行逻辑与运算`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="65245-124">这两个主要区别在于`AndAlso`表现出*短路*行为。</span><span class="sxs-lookup"><span data-stu-id="65245-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="65245-125">如果中的第一个表达式`AndAlso`表达式的计算结果`False`，然后第二个表达式未计算值，因为它不会改变最终结果，并`AndAlso`返回`False`。</span><span class="sxs-lookup"><span data-stu-id="65245-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="65245-126">同样， [OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)执行短路逻辑或运算，对两个`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="65245-127">如果中的第一个表达式`OrElse`表达式的计算结果`True`，然后第二个表达式未计算值，因为它不会改变最终结果，并`OrElse`返回`True`。</span><span class="sxs-lookup"><span data-stu-id="65245-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="65245-128">短路的权衡</span><span class="sxs-lookup"><span data-stu-id="65245-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="65245-129">短路可以通过不计算一个表达式，不能更改逻辑操作的结果来提高性能。</span><span class="sxs-lookup"><span data-stu-id="65245-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="65245-130">但是，如果该表达式执行其他操作，则短路将跳过这些操作。</span><span class="sxs-lookup"><span data-stu-id="65245-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="65245-131">例如，如果表达式包含调用`Function`过程中，如果该表达式，和中包含的任何其他代码不调用过程`Function`不会运行。</span><span class="sxs-lookup"><span data-stu-id="65245-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="65245-132">因此，该函数可能只是偶尔运行，并可能未正确测试。</span><span class="sxs-lookup"><span data-stu-id="65245-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="65245-133">程序逻辑可能依赖于中的代码或`Function`。</span><span class="sxs-lookup"><span data-stu-id="65245-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="65245-134">下面的示例说明了之间的差异`And`， `Or`，及其短路对应项。</span><span class="sxs-lookup"><span data-stu-id="65245-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 <span data-ttu-id="65245-135">在前面的示例，请注意，在一些重要代码`checkIfValid()`调用短路时不会运行。</span><span class="sxs-lookup"><span data-stu-id="65245-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="65245-136">第一个`If`语句也会调用`checkIfValid()`即使`12 > 45`返回`False`，这是因为`And`不会短路。</span><span class="sxs-lookup"><span data-stu-id="65245-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="65245-137">第二个`If`语句不会调用`checkIfValid()`，这是因为当`12 > 45`返回`False`，`AndAlso`会短路第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="65245-138">第三个`If`语句也会调用`checkIfValid()`即使`12 < 45`返回`True`，这是因为`Or`不会短路。</span><span class="sxs-lookup"><span data-stu-id="65245-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="65245-139">第四个`If`语句不会调用`checkIfValid()`，这是因为当`12 < 45`返回`True`，`OrElse`会短路第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="65245-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="65245-140">按位运算</span><span class="sxs-lookup"><span data-stu-id="65245-140">Bitwise Operations</span></span>  
 <span data-ttu-id="65245-141">按位运算的计算结果在二进制 (基数为 2) 窗体中的两个整数值。</span><span class="sxs-lookup"><span data-stu-id="65245-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="65245-142">它们进行比较的相应位置处的位，然后分配基于比较的值。</span><span class="sxs-lookup"><span data-stu-id="65245-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="65245-143">下面的示例演示`And`运算符。</span><span class="sxs-lookup"><span data-stu-id="65245-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 <span data-ttu-id="65245-144">前面的示例中设置的值`x`为 1。</span><span class="sxs-lookup"><span data-stu-id="65245-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="65245-145">由于以下原因发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="65245-145">This happens for the following reasons:</span></span>  
  
- <span data-ttu-id="65245-146">值被视为二进制文件：</span><span class="sxs-lookup"><span data-stu-id="65245-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="65245-147">以二进制形式的 3 = 011</span><span class="sxs-lookup"><span data-stu-id="65245-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="65245-148">以二进制形式的 5 = 101</span><span class="sxs-lookup"><span data-stu-id="65245-148">5 in binary form = 101</span></span>  
  
- <span data-ttu-id="65245-149">`And`运算符将二进制表示形式，一次的一个二进制位置 （位） 进行比较。</span><span class="sxs-lookup"><span data-stu-id="65245-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="65245-150">如果给定位置处的两个位都为 1，1 位于该位置在结果中。</span><span class="sxs-lookup"><span data-stu-id="65245-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="65245-151">如果任一位为 0，0 位于该位置在结果中。</span><span class="sxs-lookup"><span data-stu-id="65245-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="65245-152">在前面的示例这样，如下所示：</span><span class="sxs-lookup"><span data-stu-id="65245-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="65245-153">011 (3 以二进制形式)</span><span class="sxs-lookup"><span data-stu-id="65245-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="65245-154">101 (5 以二进制形式)</span><span class="sxs-lookup"><span data-stu-id="65245-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="65245-155">001 （以二进制形式，结果）</span><span class="sxs-lookup"><span data-stu-id="65245-155">001 (The result, in binary form)</span></span>  
  
- <span data-ttu-id="65245-156">结果将被视为小数。</span><span class="sxs-lookup"><span data-stu-id="65245-156">The result is treated as decimal.</span></span> <span data-ttu-id="65245-157">001 的值是 1 的二进制表示形式，因此`x`= 1。</span><span class="sxs-lookup"><span data-stu-id="65245-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="65245-158">按位`Or`操作类似，只是一个 1 分配给结果位，如果一个或两个比较位为 1。</span><span class="sxs-lookup"><span data-stu-id="65245-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="65245-159">`Xor` 如果恰好有一个比较位 （不能同时） 为 1，1 赋给结果位。</span><span class="sxs-lookup"><span data-stu-id="65245-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="65245-160">`Not` 采用单个操作数和反转所有位，包括符号位，并将该值分配到的结果。</span><span class="sxs-lookup"><span data-stu-id="65245-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="65245-161">这意味着，对于已签名的正数和负数`Not`始终返回一个负值，而对于负数，`Not`始终返回一个值为正或零值。</span><span class="sxs-lookup"><span data-stu-id="65245-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="65245-162">`AndAlso`和`OrElse`运算符不支持按位运算。</span><span class="sxs-lookup"><span data-stu-id="65245-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65245-163">只能对整型，可以执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="65245-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="65245-164">按位运算可以继续操作之前，必须是浮点值转换为整型类型。</span><span class="sxs-lookup"><span data-stu-id="65245-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65245-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="65245-165">See also</span></span>

- [<span data-ttu-id="65245-166">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65245-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="65245-167">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="65245-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="65245-168">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="65245-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="65245-169">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="65245-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="65245-170">在 Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="65245-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="65245-171">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="65245-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
