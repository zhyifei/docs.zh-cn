---
title: AndAlso 运算符
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
ms.openlocfilehash: b3801c7e05142e1bc793e3c9d49a6f6991756f9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350238"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="9c516-102">AndAlso 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c516-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="9c516-103">对两个表达式执行短路逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="9c516-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c516-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c516-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9c516-105">部件</span><span class="sxs-lookup"><span data-stu-id="9c516-105">Parts</span></span>  
  
|<span data-ttu-id="9c516-106">术语</span><span class="sxs-lookup"><span data-stu-id="9c516-106">Term</span></span>|<span data-ttu-id="9c516-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9c516-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="9c516-108">必需。</span><span class="sxs-lookup"><span data-stu-id="9c516-108">Required.</span></span> <span data-ttu-id="9c516-109">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="9c516-109">Any `Boolean` expression.</span></span> <span data-ttu-id="9c516-110">结果是对两个表达式进行比较 `Boolean` 结果。</span><span class="sxs-lookup"><span data-stu-id="9c516-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="9c516-111">必需。</span><span class="sxs-lookup"><span data-stu-id="9c516-111">Required.</span></span> <span data-ttu-id="9c516-112">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="9c516-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="9c516-113">必需。</span><span class="sxs-lookup"><span data-stu-id="9c516-113">Required.</span></span> <span data-ttu-id="9c516-114">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="9c516-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c516-115">备注</span><span class="sxs-lookup"><span data-stu-id="9c516-115">Remarks</span></span>  
 <span data-ttu-id="9c516-116">如果编译后的代码可以根据另一个表达式的结果跳过对一个表达式的计算，则将逻辑运算称为*短路*。</span><span class="sxs-lookup"><span data-stu-id="9c516-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="9c516-117">如果第一个表达式的计算结果确定了运算的最终结果，则不需要计算第二个表达式，因为它不能更改最终结果。</span><span class="sxs-lookup"><span data-stu-id="9c516-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="9c516-118">如果绕过的表达式较复杂，或者它涉及过程调用，则短路可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="9c516-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="9c516-119">如果两个表达式的计算结果都为 `True`，`result` `True`。</span><span class="sxs-lookup"><span data-stu-id="9c516-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="9c516-120">下表说明了如何确定 `result`。</span><span class="sxs-lookup"><span data-stu-id="9c516-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="9c516-121">如果 `expression1` 为</span><span class="sxs-lookup"><span data-stu-id="9c516-121">If `expression1` is</span></span>|<span data-ttu-id="9c516-122">并且 `expression2` 为</span><span class="sxs-lookup"><span data-stu-id="9c516-122">And `expression2` is</span></span>|<span data-ttu-id="9c516-123">`result` 的值是</span><span class="sxs-lookup"><span data-stu-id="9c516-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="9c516-124">（未计算）</span><span class="sxs-lookup"><span data-stu-id="9c516-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="9c516-125">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c516-125">Data Types</span></span>  
 <span data-ttu-id="9c516-126">仅为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)定义 `AndAlso` 运算符。</span><span class="sxs-lookup"><span data-stu-id="9c516-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="9c516-127">Visual Basic 在计算表达式之前，根据需要将每个操作数转换为 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="9c516-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="9c516-128">如果将结果赋给数值类型，Visual Basic 会将其从 `Boolean` 转换为该类型，以便 `False` 成为 `0`，`True` 变为 `-1`。</span><span class="sxs-lookup"><span data-stu-id="9c516-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="9c516-129">有关详细信息，请参阅[布尔类型转换](../data-types/boolean-data-type.md#type-conversions)。</span><span class="sxs-lookup"><span data-stu-id="9c516-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="9c516-130">重载</span><span class="sxs-lookup"><span data-stu-id="9c516-130">Overloading</span></span>  
 <span data-ttu-id="9c516-131">[And 运算符](../../../visual-basic/language-reference/operators/and-operator.md)和[IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)可以*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义它们的行为。</span><span class="sxs-lookup"><span data-stu-id="9c516-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9c516-132">重载 `And` 和 `IsFalse` 运算符会影响 `AndAlso` 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="9c516-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="9c516-133">如果你的代码对 `And` 和 `IsFalse`重载的类或结构使用 `AndAlso`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="9c516-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="9c516-134">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="9c516-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c516-135">示例</span><span class="sxs-lookup"><span data-stu-id="9c516-135">Example</span></span>  
 <span data-ttu-id="9c516-136">下面的示例使用 `AndAlso` 运算符对两个表达式执行逻辑与运算。</span><span class="sxs-lookup"><span data-stu-id="9c516-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="9c516-137">结果是一个 `Boolean` 值，该值表示整个联合表达式是否为 true。</span><span class="sxs-lookup"><span data-stu-id="9c516-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="9c516-138">如果 `False`第一个表达式，则不计算第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="9c516-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="9c516-139">前面的示例分别产生 `True`、`False`和 `False`的结果。</span><span class="sxs-lookup"><span data-stu-id="9c516-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="9c516-140">在 `secondCheck`的计算中，不计算第二个表达式，因为第一个表达式已 `False`。</span><span class="sxs-lookup"><span data-stu-id="9c516-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="9c516-141">但是，在 `thirdCheck`的计算中计算第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="9c516-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c516-142">示例</span><span class="sxs-lookup"><span data-stu-id="9c516-142">Example</span></span>  
 <span data-ttu-id="9c516-143">下面的示例演示了一个 `Function` 过程，该过程在数组的元素中搜索给定的值。</span><span class="sxs-lookup"><span data-stu-id="9c516-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="9c516-144">如果数组为空，或超出了数组长度，则 `While` 语句不会对照搜索值测试数组元素。</span><span class="sxs-lookup"><span data-stu-id="9c516-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="9c516-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c516-145">See also</span></span>

- [<span data-ttu-id="9c516-146">逻辑/按位运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="9c516-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="9c516-147">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="9c516-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9c516-148">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="9c516-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9c516-149">And 运算符</span><span class="sxs-lookup"><span data-stu-id="9c516-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="9c516-150">IsFalse 运算符</span><span class="sxs-lookup"><span data-stu-id="9c516-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="9c516-151">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="9c516-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
