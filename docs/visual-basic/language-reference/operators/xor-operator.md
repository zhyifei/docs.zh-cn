---
title: 异或运算符
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: c5c7ec87bc173f724f8c670395bc3b0458444df6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335408"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="32e67-102">异或运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32e67-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="32e67-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span><span class="sxs-lookup"><span data-stu-id="32e67-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e67-104">语法</span><span class="sxs-lookup"><span data-stu-id="32e67-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="32e67-105">部件</span><span class="sxs-lookup"><span data-stu-id="32e67-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="32e67-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="32e67-106">Required.</span></span> <span data-ttu-id="32e67-107">Any `Boolean` or numeric variable.</span><span class="sxs-lookup"><span data-stu-id="32e67-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="32e67-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span><span class="sxs-lookup"><span data-stu-id="32e67-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="32e67-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span><span class="sxs-lookup"><span data-stu-id="32e67-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="32e67-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="32e67-110">Required.</span></span> <span data-ttu-id="32e67-111">Any `Boolean` or numeric expression.</span><span class="sxs-lookup"><span data-stu-id="32e67-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="32e67-112">必须的。</span><span class="sxs-lookup"><span data-stu-id="32e67-112">Required.</span></span> <span data-ttu-id="32e67-113">Any `Boolean` or numeric expression.</span><span class="sxs-lookup"><span data-stu-id="32e67-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32e67-114">备注</span><span class="sxs-lookup"><span data-stu-id="32e67-114">Remarks</span></span>  
 <span data-ttu-id="32e67-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span><span class="sxs-lookup"><span data-stu-id="32e67-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="32e67-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span><span class="sxs-lookup"><span data-stu-id="32e67-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="32e67-117">The following table illustrates how `result` is determined.</span><span class="sxs-lookup"><span data-stu-id="32e67-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="32e67-118">If `expression1` is</span><span class="sxs-lookup"><span data-stu-id="32e67-118">If `expression1` is</span></span>|<span data-ttu-id="32e67-119">And `expression2` is</span><span class="sxs-lookup"><span data-stu-id="32e67-119">And `expression2` is</span></span>|<span data-ttu-id="32e67-120">The value of `result` is</span><span class="sxs-lookup"><span data-stu-id="32e67-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="32e67-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span><span class="sxs-lookup"><span data-stu-id="32e67-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="32e67-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span><span class="sxs-lookup"><span data-stu-id="32e67-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="32e67-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="32e67-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="32e67-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span><span class="sxs-lookup"><span data-stu-id="32e67-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="32e67-125">If bit in `expression1` is</span><span class="sxs-lookup"><span data-stu-id="32e67-125">If bit in `expression1` is</span></span>|<span data-ttu-id="32e67-126">And bit in `expression2` is</span><span class="sxs-lookup"><span data-stu-id="32e67-126">And bit in `expression2` is</span></span>|<span data-ttu-id="32e67-127">The bit in `result` is</span><span class="sxs-lookup"><span data-stu-id="32e67-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="32e67-128">1</span><span class="sxs-lookup"><span data-stu-id="32e67-128">1</span></span>|<span data-ttu-id="32e67-129">1</span><span class="sxs-lookup"><span data-stu-id="32e67-129">1</span></span>|<span data-ttu-id="32e67-130">0</span><span class="sxs-lookup"><span data-stu-id="32e67-130">0</span></span>|  
|<span data-ttu-id="32e67-131">1</span><span class="sxs-lookup"><span data-stu-id="32e67-131">1</span></span>|<span data-ttu-id="32e67-132">0</span><span class="sxs-lookup"><span data-stu-id="32e67-132">0</span></span>|<span data-ttu-id="32e67-133">1</span><span class="sxs-lookup"><span data-stu-id="32e67-133">1</span></span>|  
|<span data-ttu-id="32e67-134">0</span><span class="sxs-lookup"><span data-stu-id="32e67-134">0</span></span>|<span data-ttu-id="32e67-135">1</span><span class="sxs-lookup"><span data-stu-id="32e67-135">1</span></span>|<span data-ttu-id="32e67-136">1</span><span class="sxs-lookup"><span data-stu-id="32e67-136">1</span></span>|  
|<span data-ttu-id="32e67-137">0</span><span class="sxs-lookup"><span data-stu-id="32e67-137">0</span></span>|<span data-ttu-id="32e67-138">0</span><span class="sxs-lookup"><span data-stu-id="32e67-138">0</span></span>|<span data-ttu-id="32e67-139">0</span><span class="sxs-lookup"><span data-stu-id="32e67-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="32e67-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span><span class="sxs-lookup"><span data-stu-id="32e67-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="32e67-141">For example, 5 `Xor` 3 is 6.</span><span class="sxs-lookup"><span data-stu-id="32e67-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="32e67-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span><span class="sxs-lookup"><span data-stu-id="32e67-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="32e67-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span><span class="sxs-lookup"><span data-stu-id="32e67-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="32e67-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="32e67-144">Data Types</span></span>  
 <span data-ttu-id="32e67-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span><span class="sxs-lookup"><span data-stu-id="32e67-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="32e67-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="32e67-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="32e67-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span><span class="sxs-lookup"><span data-stu-id="32e67-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="32e67-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="32e67-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="32e67-149">重载</span><span class="sxs-lookup"><span data-stu-id="32e67-149">Overloading</span></span>  
 <span data-ttu-id="32e67-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="32e67-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="32e67-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="32e67-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="32e67-152">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="32e67-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32e67-153">示例</span><span class="sxs-lookup"><span data-stu-id="32e67-153">Example</span></span>  
 <span data-ttu-id="32e67-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span><span class="sxs-lookup"><span data-stu-id="32e67-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="32e67-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span><span class="sxs-lookup"><span data-stu-id="32e67-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="32e67-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span><span class="sxs-lookup"><span data-stu-id="32e67-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32e67-157">示例</span><span class="sxs-lookup"><span data-stu-id="32e67-157">Example</span></span>  
 <span data-ttu-id="32e67-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span><span class="sxs-lookup"><span data-stu-id="32e67-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="32e67-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span><span class="sxs-lookup"><span data-stu-id="32e67-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="32e67-160">The previous example produces results of 2, 12, and 14, respectively.</span><span class="sxs-lookup"><span data-stu-id="32e67-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e67-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="32e67-161">See also</span></span>

- [<span data-ttu-id="32e67-162">Logical/Bitwise Operators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32e67-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="32e67-163">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="32e67-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="32e67-164">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="32e67-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="32e67-165">Logical and Bitwise Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32e67-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
