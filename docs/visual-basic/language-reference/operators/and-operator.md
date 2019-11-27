---
title: And 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 78a65843a449bd15d5615710e1685f40d94c37f7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350257"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="f634e-102">And 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f634e-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="f634e-103">对两个 `Boolean` 表达式执行逻辑与运算，或对两个数值表达式执行位与运算。</span><span class="sxs-lookup"><span data-stu-id="f634e-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f634e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f634e-104">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="f634e-105">部件</span><span class="sxs-lookup"><span data-stu-id="f634e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f634e-106">必需。</span><span class="sxs-lookup"><span data-stu-id="f634e-106">Required.</span></span> <span data-ttu-id="f634e-107">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f634e-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="f634e-108">对于布尔值比较，`result` 是两个 `Boolean` 值的逻辑与。</span><span class="sxs-lookup"><span data-stu-id="f634e-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="f634e-109">对于按位运算，`result` 是表示两个数值位模式的按位 "与" 的数值。</span><span class="sxs-lookup"><span data-stu-id="f634e-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="f634e-110">必需。</span><span class="sxs-lookup"><span data-stu-id="f634e-110">Required.</span></span> <span data-ttu-id="f634e-111">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f634e-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="f634e-112">必需。</span><span class="sxs-lookup"><span data-stu-id="f634e-112">Required.</span></span> <span data-ttu-id="f634e-113">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f634e-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f634e-114">备注</span><span class="sxs-lookup"><span data-stu-id="f634e-114">Remarks</span></span>  
 <span data-ttu-id="f634e-115">对于布尔值比较，当且仅当 `expression1` 和 `expression2` 的计算结果都为 `True`时，`result` `True`。</span><span class="sxs-lookup"><span data-stu-id="f634e-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="f634e-116">下表说明了如何确定 `result`。</span><span class="sxs-lookup"><span data-stu-id="f634e-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="f634e-117">如果 `expression1` 为</span><span class="sxs-lookup"><span data-stu-id="f634e-117">If `expression1` is</span></span>|<span data-ttu-id="f634e-118">并且 `expression2` 为</span><span class="sxs-lookup"><span data-stu-id="f634e-118">And `expression2` is</span></span>|<span data-ttu-id="f634e-119">`result` 的值是</span><span class="sxs-lookup"><span data-stu-id="f634e-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="f634e-120">在布尔比较中，`And` 运算符始终计算两个表达式，这可能包括进行过程调用。</span><span class="sxs-lookup"><span data-stu-id="f634e-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="f634e-121">[AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)执行*短路*，这意味着如果 `False``expression1`，则不会计算 `expression2`。</span><span class="sxs-lookup"><span data-stu-id="f634e-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="f634e-122">当应用于数值时，`And` 运算符将对两个数值表达式中的相同位置执行按位比较，并根据下表设置 `result` 中的相应位。</span><span class="sxs-lookup"><span data-stu-id="f634e-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="f634e-123">如果 `expression1` 中有位</span><span class="sxs-lookup"><span data-stu-id="f634e-123">If bit in `expression1` is</span></span>|<span data-ttu-id="f634e-124">`expression2` 中的位是</span><span class="sxs-lookup"><span data-stu-id="f634e-124">And bit in `expression2` is</span></span>|<span data-ttu-id="f634e-125">`result` 中的位是</span><span class="sxs-lookup"><span data-stu-id="f634e-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="f634e-126">1</span><span class="sxs-lookup"><span data-stu-id="f634e-126">1</span></span>|<span data-ttu-id="f634e-127">1</span><span class="sxs-lookup"><span data-stu-id="f634e-127">1</span></span>|<span data-ttu-id="f634e-128">1</span><span class="sxs-lookup"><span data-stu-id="f634e-128">1</span></span>|  
|<span data-ttu-id="f634e-129">1</span><span class="sxs-lookup"><span data-stu-id="f634e-129">1</span></span>|<span data-ttu-id="f634e-130">0</span><span class="sxs-lookup"><span data-stu-id="f634e-130">0</span></span>|<span data-ttu-id="f634e-131">0</span><span class="sxs-lookup"><span data-stu-id="f634e-131">0</span></span>|  
|<span data-ttu-id="f634e-132">0</span><span class="sxs-lookup"><span data-stu-id="f634e-132">0</span></span>|<span data-ttu-id="f634e-133">1</span><span class="sxs-lookup"><span data-stu-id="f634e-133">1</span></span>|<span data-ttu-id="f634e-134">0</span><span class="sxs-lookup"><span data-stu-id="f634e-134">0</span></span>|  
|<span data-ttu-id="f634e-135">0</span><span class="sxs-lookup"><span data-stu-id="f634e-135">0</span></span>|<span data-ttu-id="f634e-136">0</span><span class="sxs-lookup"><span data-stu-id="f634e-136">0</span></span>|<span data-ttu-id="f634e-137">0</span><span class="sxs-lookup"><span data-stu-id="f634e-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f634e-138">由于逻辑运算符和位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确的结果。</span><span class="sxs-lookup"><span data-stu-id="f634e-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="f634e-139">数据类型</span><span class="sxs-lookup"><span data-stu-id="f634e-139">Data Types</span></span>  
 <span data-ttu-id="f634e-140">如果操作数由一个 `Boolean` 表达式和一个数值表达式组成，则 Visual Basic 会将 `Boolean` 表达式转换为数值（对于 `True` 为–1，对于 `False`为0）并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="f634e-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="f634e-141">对于布尔值比较，结果的数据类型为 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="f634e-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="f634e-142">对于按位比较，结果数据类型是一种适合 `expression1` 和 `expression2`的数据类型的数值类型。</span><span class="sxs-lookup"><span data-stu-id="f634e-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="f634e-143">请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。</span><span class="sxs-lookup"><span data-stu-id="f634e-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f634e-144">可以*重载*`And` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="f634e-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f634e-145">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="f634e-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f634e-146">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f634e-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f634e-147">示例</span><span class="sxs-lookup"><span data-stu-id="f634e-147">Example</span></span>  
 <span data-ttu-id="f634e-148">下面的示例使用 `And` 运算符对两个表达式执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="f634e-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="f634e-149">结果是 `Boolean` 值，该值表示两个表达式是否 `True`。</span><span class="sxs-lookup"><span data-stu-id="f634e-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="f634e-150">前面的示例分别产生 `True` 和 `False`的结果。</span><span class="sxs-lookup"><span data-stu-id="f634e-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f634e-151">示例</span><span class="sxs-lookup"><span data-stu-id="f634e-151">Example</span></span>  
 <span data-ttu-id="f634e-152">下面的示例使用 `And` 运算符对两个数值表达式的单个位执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="f634e-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="f634e-153">如果操作数中的相应位均设置为1，则结果模式中的位将设置为1。</span><span class="sxs-lookup"><span data-stu-id="f634e-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="f634e-154">前面的示例分别生成8、2和0的结果。</span><span class="sxs-lookup"><span data-stu-id="f634e-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f634e-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f634e-155">See also</span></span>

- [<span data-ttu-id="f634e-156">逻辑/按位运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="f634e-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="f634e-157">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="f634e-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f634e-158">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="f634e-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f634e-159">AndAlso 运算符</span><span class="sxs-lookup"><span data-stu-id="f634e-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="f634e-160">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="f634e-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
