---
title: And 运算符 (Visual Basic)
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
ms.openlocfilehash: e14dfd8ba200598084cad04d1faa05f3561f8dab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604635"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="a5dfc-102">And 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5dfc-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="a5dfc-103">对两个执行逻辑与`Boolean`表达式或对两个数值表达式位与运算。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5dfc-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5dfc-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a5dfc-105">部件</span><span class="sxs-lookup"><span data-stu-id="a5dfc-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a5dfc-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-106">Required.</span></span> <span data-ttu-id="a5dfc-107">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="a5dfc-108">有关布尔比较，`result`是逻辑的两个联合`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="a5dfc-109">对于按位运算，`result`表示两个数值的位模式的位与的数值。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="a5dfc-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-110">Required.</span></span> <span data-ttu-id="a5dfc-111">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a5dfc-112">必须的。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-112">Required.</span></span> <span data-ttu-id="a5dfc-113">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5dfc-114">备注</span><span class="sxs-lookup"><span data-stu-id="a5dfc-114">Remarks</span></span>  
 <span data-ttu-id="a5dfc-115">有关布尔比较，`result`是`True`当且仅当`expression1`和`expression2`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="a5dfc-116">下表说明了如何`result`确定。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="a5dfc-117">如果`expression1`是</span><span class="sxs-lookup"><span data-stu-id="a5dfc-117">If `expression1` is</span></span>|<span data-ttu-id="a5dfc-118">和`expression2`是</span><span class="sxs-lookup"><span data-stu-id="a5dfc-118">And `expression2` is</span></span>|<span data-ttu-id="a5dfc-119">值`result`是</span><span class="sxs-lookup"><span data-stu-id="a5dfc-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="a5dfc-120">在布尔比较中，`And`运算符始终在两个表达式，它可能包含使过程调用。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="a5dfc-121">[AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)执行*短路*，这意味着，如果`expression1`是`False`，然后`expression2`则不会评估。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="a5dfc-122">当应用于数值，`And`运算符在两个数值表达式执行位置相同的位的按位比较，并设置相应的中位`result`根据下表。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="a5dfc-123">如果在位`expression1`是</span><span class="sxs-lookup"><span data-stu-id="a5dfc-123">If bit in `expression1` is</span></span>|<span data-ttu-id="a5dfc-124">和中位`expression2`是</span><span class="sxs-lookup"><span data-stu-id="a5dfc-124">And bit in `expression2` is</span></span>|<span data-ttu-id="a5dfc-125">中的位`result`是</span><span class="sxs-lookup"><span data-stu-id="a5dfc-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="a5dfc-126">1</span><span class="sxs-lookup"><span data-stu-id="a5dfc-126">1</span></span>|<span data-ttu-id="a5dfc-127">1</span><span class="sxs-lookup"><span data-stu-id="a5dfc-127">1</span></span>|<span data-ttu-id="a5dfc-128">1</span><span class="sxs-lookup"><span data-stu-id="a5dfc-128">1</span></span>|  
|<span data-ttu-id="a5dfc-129">1</span><span class="sxs-lookup"><span data-stu-id="a5dfc-129">1</span></span>|<span data-ttu-id="a5dfc-130">0</span><span class="sxs-lookup"><span data-stu-id="a5dfc-130">0</span></span>|<span data-ttu-id="a5dfc-131">0</span><span class="sxs-lookup"><span data-stu-id="a5dfc-131">0</span></span>|  
|<span data-ttu-id="a5dfc-132">0</span><span class="sxs-lookup"><span data-stu-id="a5dfc-132">0</span></span>|<span data-ttu-id="a5dfc-133">1</span><span class="sxs-lookup"><span data-stu-id="a5dfc-133">1</span></span>|<span data-ttu-id="a5dfc-134">0</span><span class="sxs-lookup"><span data-stu-id="a5dfc-134">0</span></span>|  
|<span data-ttu-id="a5dfc-135">0</span><span class="sxs-lookup"><span data-stu-id="a5dfc-135">0</span></span>|<span data-ttu-id="a5dfc-136">0</span><span class="sxs-lookup"><span data-stu-id="a5dfc-136">0</span></span>|<span data-ttu-id="a5dfc-137">0</span><span class="sxs-lookup"><span data-stu-id="a5dfc-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a5dfc-138">因为逻辑和按位运算符的优先级低于其他算术和关系运算符，所以应将任何按位运算括在圆括号中以确保准确的结果。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="a5dfc-139">数据类型</span><span class="sxs-lookup"><span data-stu-id="a5dfc-139">Data Types</span></span>  
 <span data-ttu-id="a5dfc-140">如果操作数组成一个`Boolean`Visual Basic 表达式和一个数值表达式，将转换`Boolean`为数字值的表达式 (– 1 表示`True`和 0 `False`)，并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="a5dfc-141">对于布尔比较，结果的数据类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="a5dfc-142">有关的按位比较，结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="a5dfc-143">请参阅中的"关系和按位比较"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5dfc-144">`And`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a5dfc-145">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a5dfc-146">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5dfc-147">示例</span><span class="sxs-lookup"><span data-stu-id="a5dfc-147">Example</span></span>  
 <span data-ttu-id="a5dfc-148">下面的示例使用`And`运算符对两个表达式执行逻辑与。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="a5dfc-149">结果是`Boolean`值，该值表示两个表达式是否`True`。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 <span data-ttu-id="a5dfc-150">前面的示例将生成的结果`True`和`False`分别。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5dfc-151">示例</span><span class="sxs-lookup"><span data-stu-id="a5dfc-151">Example</span></span>  
 <span data-ttu-id="a5dfc-152">下面的示例使用`And`运算符对单个位进行运算的两个数值表达式执行逻辑与。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="a5dfc-153">如果操作数中的相应位均设置为 1，则结果模式中的位被设置。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 <span data-ttu-id="a5dfc-154">上面的示例分别产生 8，2，0，结果。</span><span class="sxs-lookup"><span data-stu-id="a5dfc-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dfc-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5dfc-155">See Also</span></span>  
 [<span data-ttu-id="a5dfc-156">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5dfc-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="a5dfc-157">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="a5dfc-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a5dfc-158">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="a5dfc-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a5dfc-159">AndAlso 运算符</span><span class="sxs-lookup"><span data-stu-id="a5dfc-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [<span data-ttu-id="a5dfc-160">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="a5dfc-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
