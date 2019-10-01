---
title: Or 运算符 (Visual Basic)
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
ms.openlocfilehash: 03decb4ad32e8ff2c03e3b64a272bce779282973
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701236"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="4963d-102">Or 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4963d-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="4963d-103">对两个 @no__t 0 个表达式执行逻辑或运算，或对两个数值表达式执行按位析取。</span><span class="sxs-lookup"><span data-stu-id="4963d-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4963d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4963d-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4963d-105">部件</span><span class="sxs-lookup"><span data-stu-id="4963d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="4963d-106">必需。</span><span class="sxs-lookup"><span data-stu-id="4963d-106">Required.</span></span> <span data-ttu-id="4963d-107">Any `Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="4963d-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="4963d-108">对于 `Boolean` 比较，`result` 是两个 @no__t 2 值的包含逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="4963d-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="4963d-109">对于按位运算，`result` 是一个数值，表示两个数值位模式的包含按位析取。</span><span class="sxs-lookup"><span data-stu-id="4963d-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="4963d-110">必需。</span><span class="sxs-lookup"><span data-stu-id="4963d-110">Required.</span></span> <span data-ttu-id="4963d-111">Any `Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="4963d-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4963d-112">必需。</span><span class="sxs-lookup"><span data-stu-id="4963d-112">Required.</span></span> <span data-ttu-id="4963d-113">Any `Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="4963d-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4963d-114">备注</span><span class="sxs-lookup"><span data-stu-id="4963d-114">Remarks</span></span>  
 <span data-ttu-id="4963d-115">对于 `Boolean` 比较，当且仅当 @no__t，`expression2` 的计算结果为 `False` 时，`result` `False`。</span><span class="sxs-lookup"><span data-stu-id="4963d-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="4963d-116">下表说明了如何确定 `result`。</span><span class="sxs-lookup"><span data-stu-id="4963d-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="4963d-117">如果`expression1`为</span><span class="sxs-lookup"><span data-stu-id="4963d-117">If `expression1` is</span></span>|<span data-ttu-id="4963d-118">并且`expression2`为</span><span class="sxs-lookup"><span data-stu-id="4963d-118">And `expression2` is</span></span>|<span data-ttu-id="4963d-119">@No__t 值为</span><span class="sxs-lookup"><span data-stu-id="4963d-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="4963d-120">在 @no__t 0 的比较中，@no__t 运算符始终计算两个表达式，这可能包括进行过程调用。</span><span class="sxs-lookup"><span data-stu-id="4963d-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="4963d-121">[OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)执行*短路*，这意味着如果 `expression1` `True`，则不会计算 `expression2`。</span><span class="sxs-lookup"><span data-stu-id="4963d-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="4963d-122">对于按位运算，@no__t 0 运算符执行两个数值表达式中的相同位置位的按位比较，并根据下表设置 `result` 中的相应位。</span><span class="sxs-lookup"><span data-stu-id="4963d-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="4963d-123">如果 @no__t 中的位为</span><span class="sxs-lookup"><span data-stu-id="4963d-123">If bit in `expression1` is</span></span>|<span data-ttu-id="4963d-124">@No__t 中的位是</span><span class="sxs-lookup"><span data-stu-id="4963d-124">And bit in `expression2` is</span></span>|<span data-ttu-id="4963d-125">@No__t-0 中的位是</span><span class="sxs-lookup"><span data-stu-id="4963d-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="4963d-126">1</span><span class="sxs-lookup"><span data-stu-id="4963d-126">1</span></span>|<span data-ttu-id="4963d-127">1</span><span class="sxs-lookup"><span data-stu-id="4963d-127">1</span></span>|<span data-ttu-id="4963d-128">1</span><span class="sxs-lookup"><span data-stu-id="4963d-128">1</span></span>|  
|<span data-ttu-id="4963d-129">1</span><span class="sxs-lookup"><span data-stu-id="4963d-129">1</span></span>|<span data-ttu-id="4963d-130">0</span><span class="sxs-lookup"><span data-stu-id="4963d-130">0</span></span>|<span data-ttu-id="4963d-131">1</span><span class="sxs-lookup"><span data-stu-id="4963d-131">1</span></span>|  
|<span data-ttu-id="4963d-132">0</span><span class="sxs-lookup"><span data-stu-id="4963d-132">0</span></span>|<span data-ttu-id="4963d-133">1</span><span class="sxs-lookup"><span data-stu-id="4963d-133">1</span></span>|<span data-ttu-id="4963d-134">1</span><span class="sxs-lookup"><span data-stu-id="4963d-134">1</span></span>|  
|<span data-ttu-id="4963d-135">0</span><span class="sxs-lookup"><span data-stu-id="4963d-135">0</span></span>|<span data-ttu-id="4963d-136">0</span><span class="sxs-lookup"><span data-stu-id="4963d-136">0</span></span>|<span data-ttu-id="4963d-137">0</span><span class="sxs-lookup"><span data-stu-id="4963d-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="4963d-138">由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确执行。</span><span class="sxs-lookup"><span data-stu-id="4963d-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="4963d-139">数据类型</span><span class="sxs-lookup"><span data-stu-id="4963d-139">Data Types</span></span>  
 <span data-ttu-id="4963d-140">如果操作数由一个 @no__t 0 表达式和一个数值表达式组成，则 Visual Basic 会将 `Boolean` 表达式转换为数值（-1 表示 `True`，0表示 `False`）并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="4963d-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="4963d-141">对于 0 @no__t 比较，结果的数据类型为 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="4963d-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="4963d-142">对于按位比较，结果数据类型是一种适合 `expression1` 和 `expression2` 的数据类型的数值类型。</span><span class="sxs-lookup"><span data-stu-id="4963d-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4963d-143">请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "关系和按位比较" 表。</span><span class="sxs-lookup"><span data-stu-id="4963d-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4963d-144">重载</span><span class="sxs-lookup"><span data-stu-id="4963d-144">Overloading</span></span>  
 <span data-ttu-id="4963d-145">@No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="4963d-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4963d-146">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="4963d-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4963d-147">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="4963d-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4963d-148">示例</span><span class="sxs-lookup"><span data-stu-id="4963d-148">Example</span></span>  
 <span data-ttu-id="4963d-149">下面的示例使用 `Or` 运算符对两个表达式执行包含逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="4963d-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="4963d-150">结果为 `Boolean` 值，该值表示两个表达式之一是否 @no__t 为-1。</span><span class="sxs-lookup"><span data-stu-id="4963d-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="4963d-151">前面的示例分别产生 `True`、`True` 和 `False` 的结果。</span><span class="sxs-lookup"><span data-stu-id="4963d-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4963d-152">示例</span><span class="sxs-lookup"><span data-stu-id="4963d-152">Example</span></span>  
 <span data-ttu-id="4963d-153">下面的示例使用 `Or` 运算符对两个数值表达式的单个位执行包含逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="4963d-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="4963d-154">如果操作数中的相应位均设置为1，则结果模式中的位将设置为1。</span><span class="sxs-lookup"><span data-stu-id="4963d-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="4963d-155">前面的示例分别生成10、14和14的结果。</span><span class="sxs-lookup"><span data-stu-id="4963d-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4963d-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="4963d-156">See also</span></span>

- [<span data-ttu-id="4963d-157">逻辑/按位运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="4963d-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="4963d-158">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="4963d-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4963d-159">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="4963d-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4963d-160">OrElse 运算符</span><span class="sxs-lookup"><span data-stu-id="4963d-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="4963d-161">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="4963d-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
