---
title: AndAlso 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: c9f4d9c880e189eb0ad4834736bdc664eb5b4376
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703557"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="c2274-102">AndAlso 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2274-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="c2274-103">执行短路逻辑与运算，对两个表达式。</span><span class="sxs-lookup"><span data-stu-id="c2274-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2274-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2274-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c2274-105">部件</span><span class="sxs-lookup"><span data-stu-id="c2274-105">Parts</span></span>  
  
|<span data-ttu-id="c2274-106">术语</span><span class="sxs-lookup"><span data-stu-id="c2274-106">Term</span></span>|<span data-ttu-id="c2274-107">定义</span><span class="sxs-lookup"><span data-stu-id="c2274-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="c2274-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c2274-108">Required.</span></span> <span data-ttu-id="c2274-109">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="c2274-109">Any `Boolean` expression.</span></span> <span data-ttu-id="c2274-110">结果是`Boolean`比较两个表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="c2274-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="c2274-111">必需。</span><span class="sxs-lookup"><span data-stu-id="c2274-111">Required.</span></span> <span data-ttu-id="c2274-112">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="c2274-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="c2274-113">必需。</span><span class="sxs-lookup"><span data-stu-id="c2274-113">Required.</span></span> <span data-ttu-id="c2274-114">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="c2274-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2274-115">备注</span><span class="sxs-lookup"><span data-stu-id="c2274-115">Remarks</span></span>  
 <span data-ttu-id="c2274-116">逻辑操作称为*短路*如果已编译的代码可以跳过一个具体取决于另一个表达式的结果表达式的计算。</span><span class="sxs-lookup"><span data-stu-id="c2274-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="c2274-117">如果计算的第一个表达式的结果确定该操作的最终结果，则无需评估的第二个表达式，因为它不能更改最终结果。</span><span class="sxs-lookup"><span data-stu-id="c2274-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="c2274-118">如果跳过的表达式很复杂，或如果它涉及过程调用，则短路可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="c2274-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="c2274-119">如果这两个表达式的计算结果为`True`，`result`是`True`。</span><span class="sxs-lookup"><span data-stu-id="c2274-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="c2274-120">下表说明了如何`result`确定。</span><span class="sxs-lookup"><span data-stu-id="c2274-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c2274-121">如果`expression1`是</span><span class="sxs-lookup"><span data-stu-id="c2274-121">If `expression1` is</span></span>|<span data-ttu-id="c2274-122">和`expression2`是</span><span class="sxs-lookup"><span data-stu-id="c2274-122">And `expression2` is</span></span>|<span data-ttu-id="c2274-123">值`result`是</span><span class="sxs-lookup"><span data-stu-id="c2274-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="c2274-124">（不会评估）</span><span class="sxs-lookup"><span data-stu-id="c2274-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="c2274-125">数据类型</span><span class="sxs-lookup"><span data-stu-id="c2274-125">Data Types</span></span>  
 <span data-ttu-id="c2274-126">`AndAlso`仅对定义运算符[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="c2274-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="c2274-127">Visual Basic 将根据需要向每个操作数`Boolean`，并执行全部操作`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="c2274-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="c2274-128">如果将结果分配到数值类型，Visual Basic 会将其转换从`Boolean`为该类型。</span><span class="sxs-lookup"><span data-stu-id="c2274-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="c2274-129">这可能产生意外的行为。</span><span class="sxs-lookup"><span data-stu-id="c2274-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="c2274-130">例如，`5 AndAlso 12`会导致`–1`转换为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="c2274-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c2274-131">重载</span><span class="sxs-lookup"><span data-stu-id="c2274-131">Overloading</span></span>  
 <span data-ttu-id="c2274-132">[And 运算符](../../../visual-basic/language-reference/operators/and-operator.md)并[IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)可以是*重载*，这意味着，类或结构可以重新定义其行为时，操作数的类型，类或结构。</span><span class="sxs-lookup"><span data-stu-id="c2274-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c2274-133">重载`And`并`IsFalse`运算符影响的行为`AndAlso`运算符。</span><span class="sxs-lookup"><span data-stu-id="c2274-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="c2274-134">如果你的代码使用`AndAlso`上类或结构的重载`And`和`IsFalse`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="c2274-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="c2274-135">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="c2274-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2274-136">示例</span><span class="sxs-lookup"><span data-stu-id="c2274-136">Example</span></span>  
 <span data-ttu-id="c2274-137">下面的示例使用`AndAlso`运算符对两个表达式执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="c2274-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="c2274-138">结果是`Boolean`值，该值表示是否整个联合表达式为 true。</span><span class="sxs-lookup"><span data-stu-id="c2274-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="c2274-139">如果第一个表达式是`False`，则不计算第二个。</span><span class="sxs-lookup"><span data-stu-id="c2274-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 <span data-ttu-id="c2274-140">前面的示例生成的结果`True`， `False`，和`False`分别。</span><span class="sxs-lookup"><span data-stu-id="c2274-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="c2274-141">中的计算`secondCheck`，因为第一个已不会计算第二个表达式`False`。</span><span class="sxs-lookup"><span data-stu-id="c2274-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="c2274-142">但是，第二个表达式计算的计算中`thirdCheck`。</span><span class="sxs-lookup"><span data-stu-id="c2274-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2274-143">示例</span><span class="sxs-lookup"><span data-stu-id="c2274-143">Example</span></span>  
 <span data-ttu-id="c2274-144">下面的示例演示`Function`搜索给定值的数组元素中的过程。</span><span class="sxs-lookup"><span data-stu-id="c2274-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="c2274-145">如果数组为空，或已超过数组长度，`While`语句不会测试针对搜索值的数组元素。</span><span class="sxs-lookup"><span data-stu-id="c2274-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c2274-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2274-146">See also</span></span>
- [<span data-ttu-id="c2274-147">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2274-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="c2274-148">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="c2274-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c2274-149">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="c2274-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c2274-150">And 运算符</span><span class="sxs-lookup"><span data-stu-id="c2274-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="c2274-151">IsFalse 运算符</span><span class="sxs-lookup"><span data-stu-id="c2274-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="c2274-152">在 Visual Basic 中的逻辑和位运算符</span><span class="sxs-lookup"><span data-stu-id="c2274-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
