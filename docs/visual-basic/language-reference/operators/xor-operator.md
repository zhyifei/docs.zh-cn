---
title: Xor 运算符
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
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="f6059-102">异或运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6059-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="f6059-103">对两个 `Boolean` 表达式执行逻辑异运算，或对两个数值表达式执行位异运算。</span><span class="sxs-lookup"><span data-stu-id="f6059-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6059-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6059-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="f6059-105">部件</span><span class="sxs-lookup"><span data-stu-id="f6059-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f6059-106">必需。</span><span class="sxs-lookup"><span data-stu-id="f6059-106">Required.</span></span> <span data-ttu-id="f6059-107">任何 `Boolean` 或数值变量。</span><span class="sxs-lookup"><span data-stu-id="f6059-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="f6059-108">对于布尔值比较，`result` 是两个 `Boolean` 值的逻辑异运算（互斥逻辑析取）。</span><span class="sxs-lookup"><span data-stu-id="f6059-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="f6059-109">对于按位运算，`result` 是表示两个数值位模式的按位异运算（互斥按位析取）的数字值。</span><span class="sxs-lookup"><span data-stu-id="f6059-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="f6059-110">必需。</span><span class="sxs-lookup"><span data-stu-id="f6059-110">Required.</span></span> <span data-ttu-id="f6059-111">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f6059-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="f6059-112">必需。</span><span class="sxs-lookup"><span data-stu-id="f6059-112">Required.</span></span> <span data-ttu-id="f6059-113">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f6059-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6059-114">备注</span><span class="sxs-lookup"><span data-stu-id="f6059-114">Remarks</span></span>  
 <span data-ttu-id="f6059-115">对于布尔值比较，当且仅当 `expression1` 和 `expression2` 的值都为 `True`时，才 `True` `result`。</span><span class="sxs-lookup"><span data-stu-id="f6059-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="f6059-116">即，当且仅当 `expression1` 和 `expression2` 的计算结果为相反 `Boolean` 值时。</span><span class="sxs-lookup"><span data-stu-id="f6059-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="f6059-117">下表说明了如何确定 `result`。</span><span class="sxs-lookup"><span data-stu-id="f6059-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="f6059-118">如果 `expression1` 为</span><span class="sxs-lookup"><span data-stu-id="f6059-118">If `expression1` is</span></span>|<span data-ttu-id="f6059-119">并且 `expression2` 为</span><span class="sxs-lookup"><span data-stu-id="f6059-119">And `expression2` is</span></span>|<span data-ttu-id="f6059-120">`result` 的值是</span><span class="sxs-lookup"><span data-stu-id="f6059-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="f6059-121">在布尔比较中，`Xor` 运算符始终计算两个表达式，这可能包括进行过程调用。</span><span class="sxs-lookup"><span data-stu-id="f6059-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="f6059-122">`Xor`没有短路，因为结果总是依赖于这两个操作数。</span><span class="sxs-lookup"><span data-stu-id="f6059-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="f6059-123">对于*短路*逻辑运算符，请参阅[AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="f6059-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="f6059-124">对于按位运算，`Xor` 运算符对两个数值表达式中的相同位置执行按位比较，并根据下表设置 `result` 中的相应位。</span><span class="sxs-lookup"><span data-stu-id="f6059-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="f6059-125">如果 `expression1` 中有位</span><span class="sxs-lookup"><span data-stu-id="f6059-125">If bit in `expression1` is</span></span>|<span data-ttu-id="f6059-126">`expression2` 中的位是</span><span class="sxs-lookup"><span data-stu-id="f6059-126">And bit in `expression2` is</span></span>|<span data-ttu-id="f6059-127">`result` 中的位是</span><span class="sxs-lookup"><span data-stu-id="f6059-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="f6059-128">1</span><span class="sxs-lookup"><span data-stu-id="f6059-128">1</span></span>|<span data-ttu-id="f6059-129">1</span><span class="sxs-lookup"><span data-stu-id="f6059-129">1</span></span>|<span data-ttu-id="f6059-130">0</span><span class="sxs-lookup"><span data-stu-id="f6059-130">0</span></span>|  
|<span data-ttu-id="f6059-131">1</span><span class="sxs-lookup"><span data-stu-id="f6059-131">1</span></span>|<span data-ttu-id="f6059-132">0</span><span class="sxs-lookup"><span data-stu-id="f6059-132">0</span></span>|<span data-ttu-id="f6059-133">1</span><span class="sxs-lookup"><span data-stu-id="f6059-133">1</span></span>|  
|<span data-ttu-id="f6059-134">0</span><span class="sxs-lookup"><span data-stu-id="f6059-134">0</span></span>|<span data-ttu-id="f6059-135">1</span><span class="sxs-lookup"><span data-stu-id="f6059-135">1</span></span>|<span data-ttu-id="f6059-136">1</span><span class="sxs-lookup"><span data-stu-id="f6059-136">1</span></span>|  
|<span data-ttu-id="f6059-137">0</span><span class="sxs-lookup"><span data-stu-id="f6059-137">0</span></span>|<span data-ttu-id="f6059-138">0</span><span class="sxs-lookup"><span data-stu-id="f6059-138">0</span></span>|<span data-ttu-id="f6059-139">0</span><span class="sxs-lookup"><span data-stu-id="f6059-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f6059-140">由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确执行。</span><span class="sxs-lookup"><span data-stu-id="f6059-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="f6059-141">例如，5 `Xor` 3 为6。</span><span class="sxs-lookup"><span data-stu-id="f6059-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="f6059-142">若要查看此操作的原因，请将5和3转换为其二进制表示形式101和011。</span><span class="sxs-lookup"><span data-stu-id="f6059-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="f6059-143">然后，使用上表来确定 101 Xor 011 为110，这是十进制数字6的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="f6059-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="f6059-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="f6059-144">Data Types</span></span>  
 <span data-ttu-id="f6059-145">如果操作数由一个 `Boolean` 表达式和一个数值表达式组成，则 Visual Basic 会将 `Boolean` 表达式转换为数值（对于 `True` 为–1，对于 `False`为0）并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="f6059-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="f6059-146">对于 `Boolean` 比较，将 `Boolean`结果的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6059-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="f6059-147">对于按位比较，结果数据类型是一种适合 `expression1` 和 `expression2`的数据类型的数值类型。</span><span class="sxs-lookup"><span data-stu-id="f6059-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="f6059-148">请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。</span><span class="sxs-lookup"><span data-stu-id="f6059-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f6059-149">重载</span><span class="sxs-lookup"><span data-stu-id="f6059-149">Overloading</span></span>  
 <span data-ttu-id="f6059-150">可以*重载*`Xor` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="f6059-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f6059-151">如果代码对这样的类或结构使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="f6059-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="f6059-152">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f6059-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6059-153">示例</span><span class="sxs-lookup"><span data-stu-id="f6059-153">Example</span></span>  
 <span data-ttu-id="f6059-154">下面的示例使用 `Xor` 运算符对两个表达式执行逻辑异运算（互斥逻辑析取）。</span><span class="sxs-lookup"><span data-stu-id="f6059-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="f6059-155">结果是一个 `Boolean` 值，该值表示是否确实 `True`其中一个表达式。</span><span class="sxs-lookup"><span data-stu-id="f6059-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="f6059-156">前面的示例分别产生 `False`、`True`和 `False`的结果。</span><span class="sxs-lookup"><span data-stu-id="f6059-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6059-157">示例</span><span class="sxs-lookup"><span data-stu-id="f6059-157">Example</span></span>  
 <span data-ttu-id="f6059-158">下面的示例使用 `Xor` 运算符对两个数值表达式的各个位执行逻辑异运算（互斥逻辑析取）。</span><span class="sxs-lookup"><span data-stu-id="f6059-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="f6059-159">如果操作数中的相应位中正好有一个设置为1，则结果模式中的位将设置为1。</span><span class="sxs-lookup"><span data-stu-id="f6059-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="f6059-160">前面的示例分别产生2、12和14的结果。</span><span class="sxs-lookup"><span data-stu-id="f6059-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6059-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6059-161">See also</span></span>

- [<span data-ttu-id="f6059-162">逻辑/按位运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="f6059-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="f6059-163">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="f6059-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f6059-164">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="f6059-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f6059-165">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="f6059-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
