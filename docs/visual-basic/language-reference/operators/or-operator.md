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
ms.openlocfilehash: 0277b6f24e62ed5f0cad3dae225c86fffc4c09b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013512"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="08e9e-102">Or 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08e9e-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="08e9e-103">对两个执行逻辑或运算`Boolean`表达式或按位析取两个数值表达式。</span><span class="sxs-lookup"><span data-stu-id="08e9e-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08e9e-104">语法</span><span class="sxs-lookup"><span data-stu-id="08e9e-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="08e9e-105">部件</span><span class="sxs-lookup"><span data-stu-id="08e9e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="08e9e-106">必需。</span><span class="sxs-lookup"><span data-stu-id="08e9e-106">Required.</span></span> <span data-ttu-id="08e9e-107">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="08e9e-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="08e9e-108">有关`Boolean`比较，`result`是两个包含的逻辑析取`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="08e9e-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="08e9e-109">对于按位运算`result`是一个数值表示包含按位析取的两个数值位模式。</span><span class="sxs-lookup"><span data-stu-id="08e9e-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="08e9e-110">必需。</span><span class="sxs-lookup"><span data-stu-id="08e9e-110">Required.</span></span> <span data-ttu-id="08e9e-111">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="08e9e-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="08e9e-112">必需。</span><span class="sxs-lookup"><span data-stu-id="08e9e-112">Required.</span></span> <span data-ttu-id="08e9e-113">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="08e9e-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08e9e-114">备注</span><span class="sxs-lookup"><span data-stu-id="08e9e-114">Remarks</span></span>  
 <span data-ttu-id="08e9e-115">有关`Boolean`比较，`result`是`False`当且仅当`expression1`并`expression2`的计算结果为`False`。</span><span class="sxs-lookup"><span data-stu-id="08e9e-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="08e9e-116">下表说明了如何`result`确定。</span><span class="sxs-lookup"><span data-stu-id="08e9e-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="08e9e-117">如果`expression1`是</span><span class="sxs-lookup"><span data-stu-id="08e9e-117">If `expression1` is</span></span>|<span data-ttu-id="08e9e-118">和`expression2`是</span><span class="sxs-lookup"><span data-stu-id="08e9e-118">And `expression2` is</span></span>|<span data-ttu-id="08e9e-119">值`result`是</span><span class="sxs-lookup"><span data-stu-id="08e9e-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="08e9e-120">在中`Boolean`比较，`Or`运算符始终计算这两个表达式，它可能包含使过程调用。</span><span class="sxs-lookup"><span data-stu-id="08e9e-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="08e9e-121">[OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)执行*短路*，这意味着，如果`expression1`是`True`，然后`expression2`则不会评估。</span><span class="sxs-lookup"><span data-stu-id="08e9e-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="08e9e-122">对于按位运算`Or`运算符中两个数值表达式执行位置相同的位的按位比较，并设置相应的位中`result`根据下表。</span><span class="sxs-lookup"><span data-stu-id="08e9e-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="08e9e-123">如果位`expression1`是</span><span class="sxs-lookup"><span data-stu-id="08e9e-123">If bit in `expression1` is</span></span>|<span data-ttu-id="08e9e-124">和中位`expression2`是</span><span class="sxs-lookup"><span data-stu-id="08e9e-124">And bit in `expression2` is</span></span>|<span data-ttu-id="08e9e-125">中的位`result`是</span><span class="sxs-lookup"><span data-stu-id="08e9e-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="08e9e-126">1</span><span class="sxs-lookup"><span data-stu-id="08e9e-126">1</span></span>|<span data-ttu-id="08e9e-127">1</span><span class="sxs-lookup"><span data-stu-id="08e9e-127">1</span></span>|<span data-ttu-id="08e9e-128">1</span><span class="sxs-lookup"><span data-stu-id="08e9e-128">1</span></span>|  
|<span data-ttu-id="08e9e-129">1</span><span class="sxs-lookup"><span data-stu-id="08e9e-129">1</span></span>|<span data-ttu-id="08e9e-130">0</span><span class="sxs-lookup"><span data-stu-id="08e9e-130">0</span></span>|<span data-ttu-id="08e9e-131">1</span><span class="sxs-lookup"><span data-stu-id="08e9e-131">1</span></span>|  
|<span data-ttu-id="08e9e-132">0</span><span class="sxs-lookup"><span data-stu-id="08e9e-132">0</span></span>|<span data-ttu-id="08e9e-133">1</span><span class="sxs-lookup"><span data-stu-id="08e9e-133">1</span></span>|<span data-ttu-id="08e9e-134">1</span><span class="sxs-lookup"><span data-stu-id="08e9e-134">1</span></span>|  
|<span data-ttu-id="08e9e-135">0</span><span class="sxs-lookup"><span data-stu-id="08e9e-135">0</span></span>|<span data-ttu-id="08e9e-136">0</span><span class="sxs-lookup"><span data-stu-id="08e9e-136">0</span></span>|<span data-ttu-id="08e9e-137">0</span><span class="sxs-lookup"><span data-stu-id="08e9e-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="08e9e-138">由于逻辑和位运算符优先级低于其他算术和关系运算符，则任何按位运算应括在括号中以确保准确的执行。</span><span class="sxs-lookup"><span data-stu-id="08e9e-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="08e9e-139">数据类型</span><span class="sxs-lookup"><span data-stu-id="08e9e-139">Data Types</span></span>  
 <span data-ttu-id="08e9e-140">如果操作数包括一个`Boolean`Visual Basic 表达式和一个数值表达式，将转换`Boolean`为数字值的表达式 (– 1 表示`True`，使用 0 表示`False`)，并执行按位运算。</span><span class="sxs-lookup"><span data-stu-id="08e9e-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="08e9e-141">有关`Boolean`比较，结果的数据类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="08e9e-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="08e9e-142">有关按位比较，结果数据类型为适用于的数据类型的数值类型`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="08e9e-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="08e9e-143">请参阅中的"关系与按位比较"表[数据类型的运算符结果](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="08e9e-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="08e9e-144">重载</span><span class="sxs-lookup"><span data-stu-id="08e9e-144">Overloading</span></span>  
 <span data-ttu-id="08e9e-145">`Or`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="08e9e-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="08e9e-146">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="08e9e-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="08e9e-147">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="08e9e-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08e9e-148">示例</span><span class="sxs-lookup"><span data-stu-id="08e9e-148">Example</span></span>  
 <span data-ttu-id="08e9e-149">下面的示例使用`Or`运算符对两个表达式执行逻辑或运算。</span><span class="sxs-lookup"><span data-stu-id="08e9e-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="08e9e-150">结果是`Boolean`值，该值表示两个表达式之一是否`True`。</span><span class="sxs-lookup"><span data-stu-id="08e9e-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="08e9e-151">前面的示例生成的结果`True`， `True`，和`False`分别。</span><span class="sxs-lookup"><span data-stu-id="08e9e-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08e9e-152">示例</span><span class="sxs-lookup"><span data-stu-id="08e9e-152">Example</span></span>  
 <span data-ttu-id="08e9e-153">下面的示例使用`Or`运算符对两个数值表达式的单个位执行逻辑或运算。</span><span class="sxs-lookup"><span data-stu-id="08e9e-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="08e9e-154">如果任一操作数中的相应位设置为 1，在结果模式位被设置。</span><span class="sxs-lookup"><span data-stu-id="08e9e-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="08e9e-155">前面的示例分别生成 10、 14 和 14 的结果。</span><span class="sxs-lookup"><span data-stu-id="08e9e-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e9e-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="08e9e-156">See also</span></span>

- [<span data-ttu-id="08e9e-157">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08e9e-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="08e9e-158">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="08e9e-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="08e9e-159">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="08e9e-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="08e9e-160">OrElse 运算符</span><span class="sxs-lookup"><span data-stu-id="08e9e-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="08e9e-161">在 Visual Basic 中的逻辑和位运算符</span><span class="sxs-lookup"><span data-stu-id="08e9e-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
