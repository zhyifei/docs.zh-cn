---
title: 异或运算符 (Visual Basic)
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
ms.openlocfilehash: bc3df1fdee5405445b4534a6982383c49b369b01
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980433"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="ce8e6-102">异或运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce8e6-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="ce8e6-103">执行逻辑异或对两个`Boolean`表达式或对两个数值表达式按位异运算。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce8e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce8e6-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="ce8e6-105">部件</span><span class="sxs-lookup"><span data-stu-id="ce8e6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="ce8e6-106">必需。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-106">Required.</span></span> <span data-ttu-id="ce8e6-107">任何`Boolean`或数值变量。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="ce8e6-108">对于布尔比较`result`是两个逻辑异运算 （排他逻辑析取）`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="ce8e6-109">对于按位运算`result`是数字值，该值表示两个数值位模式的按位异 （排他的按位析取）。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="ce8e6-110">必需。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-110">Required.</span></span> <span data-ttu-id="ce8e6-111">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="ce8e6-112">必需。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-112">Required.</span></span> <span data-ttu-id="ce8e6-113">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce8e6-114">备注</span><span class="sxs-lookup"><span data-stu-id="ce8e6-114">Remarks</span></span>  
 <span data-ttu-id="ce8e6-115">对于布尔比较`result`是`True`当且仅当之一`expression1`和`expression2`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="ce8e6-116">也就是说，当且仅当`expression1`并`expression2`评估为相反`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="ce8e6-117">下表说明了如何`result`确定。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="ce8e6-118">如果`expression1`是</span><span class="sxs-lookup"><span data-stu-id="ce8e6-118">If `expression1` is</span></span>|<span data-ttu-id="ce8e6-119">和`expression2`是</span><span class="sxs-lookup"><span data-stu-id="ce8e6-119">And `expression2` is</span></span>|<span data-ttu-id="ce8e6-120">值`result`是</span><span class="sxs-lookup"><span data-stu-id="ce8e6-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="ce8e6-121">在布尔比较中，`Xor`运算符始终计算这两个表达式，它可能包含使过程调用。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="ce8e6-122">没有任何短路`Xor`，因为结果始终取决于两个操作数。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="ce8e6-123">有关*短路*逻辑运算符，请参阅[AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)并[OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="ce8e6-124">对于按位运算`Xor`运算符中两个数值表达式执行位置相同的位的按位比较，并设置相应的位中`result`根据下表。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="ce8e6-125">如果位`expression1`是</span><span class="sxs-lookup"><span data-stu-id="ce8e6-125">If bit in `expression1` is</span></span>|<span data-ttu-id="ce8e6-126">和中位`expression2`是</span><span class="sxs-lookup"><span data-stu-id="ce8e6-126">And bit in `expression2` is</span></span>|<span data-ttu-id="ce8e6-127">中的位`result`是</span><span class="sxs-lookup"><span data-stu-id="ce8e6-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="ce8e6-128">1</span><span class="sxs-lookup"><span data-stu-id="ce8e6-128">1</span></span>|<span data-ttu-id="ce8e6-129">1</span><span class="sxs-lookup"><span data-stu-id="ce8e6-129">1</span></span>|<span data-ttu-id="ce8e6-130">0</span><span class="sxs-lookup"><span data-stu-id="ce8e6-130">0</span></span>|  
|<span data-ttu-id="ce8e6-131">1</span><span class="sxs-lookup"><span data-stu-id="ce8e6-131">1</span></span>|<span data-ttu-id="ce8e6-132">0</span><span class="sxs-lookup"><span data-stu-id="ce8e6-132">0</span></span>|<span data-ttu-id="ce8e6-133">1</span><span class="sxs-lookup"><span data-stu-id="ce8e6-133">1</span></span>|  
|<span data-ttu-id="ce8e6-134">0</span><span class="sxs-lookup"><span data-stu-id="ce8e6-134">0</span></span>|<span data-ttu-id="ce8e6-135">1</span><span class="sxs-lookup"><span data-stu-id="ce8e6-135">1</span></span>|<span data-ttu-id="ce8e6-136">1</span><span class="sxs-lookup"><span data-stu-id="ce8e6-136">1</span></span>|  
|<span data-ttu-id="ce8e6-137">0</span><span class="sxs-lookup"><span data-stu-id="ce8e6-137">0</span></span>|<span data-ttu-id="ce8e6-138">0</span><span class="sxs-lookup"><span data-stu-id="ce8e6-138">0</span></span>|<span data-ttu-id="ce8e6-139">0</span><span class="sxs-lookup"><span data-stu-id="ce8e6-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ce8e6-140">由于逻辑和位运算符优先级低于其他算术和关系运算符，则任何按位运算应括在括号中以确保准确的执行。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="ce8e6-141">例如，5 `Xor` 3 为 6。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="ce8e6-142">若要查看其中的原因，将 5 和 3 转换为其二进制表示形式、 101 和 011。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="ce8e6-143">然后使用上表来确定 101 Xor 011 是为 110 时，即十进制数 6 的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="ce8e6-144">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce8e6-144">Data Types</span></span>  
 <span data-ttu-id="ce8e6-145">如果操作数包括一个`Boolean`Visual Basic 表达式和一个数值表达式，将转换`Boolean`为数字值的表达式 (– 1 表示`True`，使用 0 表示`False`)，并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="ce8e6-146">有关`Boolean`比较，结果的数据类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="ce8e6-147">有关按位比较，结果数据类型为适用于的数据类型的数值类型`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="ce8e6-148">请参阅中的"关系与按位比较"表[数据类型的运算符结果](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ce8e6-149">重载</span><span class="sxs-lookup"><span data-stu-id="ce8e6-149">Overloading</span></span>  
 <span data-ttu-id="ce8e6-150">`Xor`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ce8e6-151">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="ce8e6-152">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce8e6-153">示例</span><span class="sxs-lookup"><span data-stu-id="ce8e6-153">Example</span></span>  
 <span data-ttu-id="ce8e6-154">下面的示例使用`Xor`运算符对两个表达式执行逻辑异运算 （互斥逻辑析）。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="ce8e6-155">结果是`Boolean`值，该值表示是否恰好有一个表达式是`True`。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="ce8e6-156">前面的示例生成的结果`False`， `True`，和`False`分别。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce8e6-157">示例</span><span class="sxs-lookup"><span data-stu-id="ce8e6-157">Example</span></span>  
 <span data-ttu-id="ce8e6-158">下面的示例使用`Xor`运算符对两个数值表达式的单个位执行逻辑异运算 （互斥逻辑析）。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="ce8e6-159">在结果模式位设置如果恰好有一个操作数中的相应位设置为 1。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="ce8e6-160">前面的示例分别生成 2，12 和 14 的结果。</span><span class="sxs-lookup"><span data-stu-id="ce8e6-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8e6-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce8e6-161">See also</span></span>
- [<span data-ttu-id="ce8e6-162">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce8e6-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="ce8e6-163">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="ce8e6-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ce8e6-164">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="ce8e6-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ce8e6-165">在 Visual Basic 中的逻辑和位运算符</span><span class="sxs-lookup"><span data-stu-id="ce8e6-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
