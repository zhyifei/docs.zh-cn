---
title: Or 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 8f28026b526c29a6122725b2689e53b7f6ee7327
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348251"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="373bf-102">Or 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="373bf-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="373bf-103">对两个 `Boolean` 表达式执行逻辑或运算，或对两个数值表达式执行按位析取。</span><span class="sxs-lookup"><span data-stu-id="373bf-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="373bf-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="373bf-105">部件</span><span class="sxs-lookup"><span data-stu-id="373bf-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="373bf-106">必需。</span><span class="sxs-lookup"><span data-stu-id="373bf-106">Required.</span></span> <span data-ttu-id="373bf-107">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="373bf-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="373bf-108">对于 `Boolean` 比较，`result` 是两个 `Boolean` 值的包含逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="373bf-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="373bf-109">对于按位运算，`result` 是表示两个数值位模式的包含按位析取的数值。</span><span class="sxs-lookup"><span data-stu-id="373bf-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="373bf-110">必需。</span><span class="sxs-lookup"><span data-stu-id="373bf-110">Required.</span></span> <span data-ttu-id="373bf-111">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="373bf-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="373bf-112">必需。</span><span class="sxs-lookup"><span data-stu-id="373bf-112">Required.</span></span> <span data-ttu-id="373bf-113">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="373bf-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="373bf-114">备注</span><span class="sxs-lookup"><span data-stu-id="373bf-114">Remarks</span></span>  
 <span data-ttu-id="373bf-115">对于 `Boolean` 比较，当且仅当 `expression1` 和 `expression2` 的计算结果都为 `False`时，`result` 为 `False`。</span><span class="sxs-lookup"><span data-stu-id="373bf-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="373bf-116">下表说明了如何确定 `result`。</span><span class="sxs-lookup"><span data-stu-id="373bf-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="373bf-117">如果 `expression1` 为</span><span class="sxs-lookup"><span data-stu-id="373bf-117">If `expression1` is</span></span>|<span data-ttu-id="373bf-118">并且 `expression2` 为</span><span class="sxs-lookup"><span data-stu-id="373bf-118">And `expression2` is</span></span>|<span data-ttu-id="373bf-119">`result` 的值是</span><span class="sxs-lookup"><span data-stu-id="373bf-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="373bf-120">在 `Boolean` 比较中，`Or` 运算符始终计算两个表达式，这可能包括进行过程调用。</span><span class="sxs-lookup"><span data-stu-id="373bf-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="373bf-121">[OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)执行*短路*，这意味着如果 `True``expression1`，则不会计算 `expression2`。</span><span class="sxs-lookup"><span data-stu-id="373bf-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="373bf-122">对于按位运算，`Or` 运算符对两个数值表达式中的相同位置执行按位比较，并根据下表设置 `result` 中的相应位。</span><span class="sxs-lookup"><span data-stu-id="373bf-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="373bf-123">如果 `expression1` 中有位</span><span class="sxs-lookup"><span data-stu-id="373bf-123">If bit in `expression1` is</span></span>|<span data-ttu-id="373bf-124">`expression2` 中的位是</span><span class="sxs-lookup"><span data-stu-id="373bf-124">And bit in `expression2` is</span></span>|<span data-ttu-id="373bf-125">`result` 中的位是</span><span class="sxs-lookup"><span data-stu-id="373bf-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="373bf-126">1</span><span class="sxs-lookup"><span data-stu-id="373bf-126">1</span></span>|<span data-ttu-id="373bf-127">1</span><span class="sxs-lookup"><span data-stu-id="373bf-127">1</span></span>|<span data-ttu-id="373bf-128">1</span><span class="sxs-lookup"><span data-stu-id="373bf-128">1</span></span>|  
|<span data-ttu-id="373bf-129">1</span><span class="sxs-lookup"><span data-stu-id="373bf-129">1</span></span>|<span data-ttu-id="373bf-130">0</span><span class="sxs-lookup"><span data-stu-id="373bf-130">0</span></span>|<span data-ttu-id="373bf-131">1</span><span class="sxs-lookup"><span data-stu-id="373bf-131">1</span></span>|  
|<span data-ttu-id="373bf-132">0</span><span class="sxs-lookup"><span data-stu-id="373bf-132">0</span></span>|<span data-ttu-id="373bf-133">1</span><span class="sxs-lookup"><span data-stu-id="373bf-133">1</span></span>|<span data-ttu-id="373bf-134">1</span><span class="sxs-lookup"><span data-stu-id="373bf-134">1</span></span>|  
|<span data-ttu-id="373bf-135">0</span><span class="sxs-lookup"><span data-stu-id="373bf-135">0</span></span>|<span data-ttu-id="373bf-136">0</span><span class="sxs-lookup"><span data-stu-id="373bf-136">0</span></span>|<span data-ttu-id="373bf-137">0</span><span class="sxs-lookup"><span data-stu-id="373bf-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="373bf-138">由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确执行。</span><span class="sxs-lookup"><span data-stu-id="373bf-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="373bf-139">数据类型</span><span class="sxs-lookup"><span data-stu-id="373bf-139">Data Types</span></span>  
 <span data-ttu-id="373bf-140">如果操作数由一个 `Boolean` 表达式和一个数值表达式组成，则 Visual Basic 会将 `Boolean` 表达式转换为数值（对于 `True` 为–1，对于 `False`为0）并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="373bf-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="373bf-141">对于 `Boolean` 比较，将 `Boolean`结果的数据类型。</span><span class="sxs-lookup"><span data-stu-id="373bf-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="373bf-142">对于按位比较，结果数据类型是一种适合 `expression1` 和 `expression2`的数据类型的数值类型。</span><span class="sxs-lookup"><span data-stu-id="373bf-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="373bf-143">请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。</span><span class="sxs-lookup"><span data-stu-id="373bf-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="373bf-144">重载</span><span class="sxs-lookup"><span data-stu-id="373bf-144">Overloading</span></span>  
 <span data-ttu-id="373bf-145">可以*重载*`Or` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="373bf-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="373bf-146">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="373bf-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="373bf-147">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="373bf-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="373bf-148">示例</span><span class="sxs-lookup"><span data-stu-id="373bf-148">Example</span></span>  
 <span data-ttu-id="373bf-149">下面的示例使用 `Or` 运算符对两个表达式执行包含逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="373bf-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="373bf-150">结果是一个 `Boolean` 值，该值表示两个表达式之一是否 `True`。</span><span class="sxs-lookup"><span data-stu-id="373bf-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="373bf-151">前面的示例分别产生 `True`、`True`和 `False`的结果。</span><span class="sxs-lookup"><span data-stu-id="373bf-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="373bf-152">示例</span><span class="sxs-lookup"><span data-stu-id="373bf-152">Example</span></span>  
 <span data-ttu-id="373bf-153">下面的示例使用 `Or` 运算符对两个数值表达式的各个位执行包含逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="373bf-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="373bf-154">如果操作数中的相应位均设置为1，则结果模式中的位将设置为1。</span><span class="sxs-lookup"><span data-stu-id="373bf-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="373bf-155">前面的示例分别生成10、14和14的结果。</span><span class="sxs-lookup"><span data-stu-id="373bf-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="373bf-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="373bf-156">See also</span></span>

- [<span data-ttu-id="373bf-157">逻辑/按位运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="373bf-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="373bf-158">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="373bf-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="373bf-159">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="373bf-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="373bf-160">OrElse 运算符</span><span class="sxs-lookup"><span data-stu-id="373bf-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="373bf-161">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="373bf-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
