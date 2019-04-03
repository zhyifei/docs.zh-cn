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
ms.openlocfilehash: 7e25f25677fa684427bdaf00cea73916ffbad655
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818613"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="96623-102">And 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96623-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="96623-103">对两个执行逻辑与运算`Boolean`表达式或对两个数值表达式位与运算。</span><span class="sxs-lookup"><span data-stu-id="96623-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96623-104">语法</span><span class="sxs-lookup"><span data-stu-id="96623-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="96623-105">部件</span><span class="sxs-lookup"><span data-stu-id="96623-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="96623-106">必需。</span><span class="sxs-lookup"><span data-stu-id="96623-106">Required.</span></span> <span data-ttu-id="96623-107">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="96623-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="96623-108">对于布尔比较`result`是两个逻辑与运算`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="96623-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="96623-109">对于按位运算`result`是数字值表示两个数值位模式位与运算。</span><span class="sxs-lookup"><span data-stu-id="96623-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="96623-110">必需。</span><span class="sxs-lookup"><span data-stu-id="96623-110">Required.</span></span> <span data-ttu-id="96623-111">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="96623-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="96623-112">必需。</span><span class="sxs-lookup"><span data-stu-id="96623-112">Required.</span></span> <span data-ttu-id="96623-113">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="96623-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96623-114">备注</span><span class="sxs-lookup"><span data-stu-id="96623-114">Remarks</span></span>  
 <span data-ttu-id="96623-115">对于布尔比较`result`是`True`当且仅当`expression1`并`expression2`的计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="96623-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="96623-116">下表说明了如何`result`确定。</span><span class="sxs-lookup"><span data-stu-id="96623-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="96623-117">如果`expression1`是</span><span class="sxs-lookup"><span data-stu-id="96623-117">If `expression1` is</span></span>|<span data-ttu-id="96623-118">和`expression2`是</span><span class="sxs-lookup"><span data-stu-id="96623-118">And `expression2` is</span></span>|<span data-ttu-id="96623-119">值`result`是</span><span class="sxs-lookup"><span data-stu-id="96623-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="96623-120">在布尔比较中，`And`运算符始终计算这两个表达式，它可能包含使过程调用。</span><span class="sxs-lookup"><span data-stu-id="96623-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="96623-121">[AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)执行*短路*，这意味着，如果`expression1`是`False`，然后`expression2`则不会评估。</span><span class="sxs-lookup"><span data-stu-id="96623-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="96623-122">当应用于数字值时`And`运算符中两个数值表达式执行位置相同的位的按位比较，并设置相应的位中`result`根据下表。</span><span class="sxs-lookup"><span data-stu-id="96623-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="96623-123">如果位`expression1`是</span><span class="sxs-lookup"><span data-stu-id="96623-123">If bit in `expression1` is</span></span>|<span data-ttu-id="96623-124">和中位`expression2`是</span><span class="sxs-lookup"><span data-stu-id="96623-124">And bit in `expression2` is</span></span>|<span data-ttu-id="96623-125">中的位`result`是</span><span class="sxs-lookup"><span data-stu-id="96623-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="96623-126">1</span><span class="sxs-lookup"><span data-stu-id="96623-126">1</span></span>|<span data-ttu-id="96623-127">1</span><span class="sxs-lookup"><span data-stu-id="96623-127">1</span></span>|<span data-ttu-id="96623-128">1</span><span class="sxs-lookup"><span data-stu-id="96623-128">1</span></span>|  
|<span data-ttu-id="96623-129">1</span><span class="sxs-lookup"><span data-stu-id="96623-129">1</span></span>|<span data-ttu-id="96623-130">0</span><span class="sxs-lookup"><span data-stu-id="96623-130">0</span></span>|<span data-ttu-id="96623-131">0</span><span class="sxs-lookup"><span data-stu-id="96623-131">0</span></span>|  
|<span data-ttu-id="96623-132">0</span><span class="sxs-lookup"><span data-stu-id="96623-132">0</span></span>|<span data-ttu-id="96623-133">1</span><span class="sxs-lookup"><span data-stu-id="96623-133">1</span></span>|<span data-ttu-id="96623-134">0</span><span class="sxs-lookup"><span data-stu-id="96623-134">0</span></span>|  
|<span data-ttu-id="96623-135">0</span><span class="sxs-lookup"><span data-stu-id="96623-135">0</span></span>|<span data-ttu-id="96623-136">0</span><span class="sxs-lookup"><span data-stu-id="96623-136">0</span></span>|<span data-ttu-id="96623-137">0</span><span class="sxs-lookup"><span data-stu-id="96623-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="96623-138">由于逻辑和位运算符优先级低于其他算术和关系运算符，则任何按位运算应括在括号中以确保准确的结果。</span><span class="sxs-lookup"><span data-stu-id="96623-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="96623-139">数据类型</span><span class="sxs-lookup"><span data-stu-id="96623-139">Data Types</span></span>  
 <span data-ttu-id="96623-140">如果操作数包括一个`Boolean`Visual Basic 表达式和一个数值表达式，将转换`Boolean`为数字值的表达式 (– 1 表示`True`，使用 0 表示`False`)，并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="96623-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="96623-141">对于布尔比较，结果的数据类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="96623-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="96623-142">有关按位比较，结果数据类型为适用于的数据类型的数值类型`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="96623-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="96623-143">请参阅中的"关系与按位比较"表[数据类型的运算符结果](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="96623-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96623-144">`And`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="96623-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="96623-145">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="96623-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="96623-146">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="96623-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96623-147">示例</span><span class="sxs-lookup"><span data-stu-id="96623-147">Example</span></span>  
 <span data-ttu-id="96623-148">下面的示例使用`And`运算符对两个表达式执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="96623-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="96623-149">结果是`Boolean`值，该值表示两个表达式是否`True`。</span><span class="sxs-lookup"><span data-stu-id="96623-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="96623-150">前面的示例生成的结果`True`和`False`分别。</span><span class="sxs-lookup"><span data-stu-id="96623-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96623-151">示例</span><span class="sxs-lookup"><span data-stu-id="96623-151">Example</span></span>  
 <span data-ttu-id="96623-152">下面的示例使用`And`运算符对两个数值表达式的单个位执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="96623-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="96623-153">如果操作数中的相应位均为这两个设置为 1，在结果模式位被设置。</span><span class="sxs-lookup"><span data-stu-id="96623-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="96623-154">前面的示例分别生成 8、 2 和 0，的结果。</span><span class="sxs-lookup"><span data-stu-id="96623-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96623-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="96623-155">See also</span></span>

- [<span data-ttu-id="96623-156">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96623-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="96623-157">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="96623-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="96623-158">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="96623-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="96623-159">AndAlso 运算符</span><span class="sxs-lookup"><span data-stu-id="96623-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="96623-160">在 Visual Basic 中的逻辑和位运算符</span><span class="sxs-lookup"><span data-stu-id="96623-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
