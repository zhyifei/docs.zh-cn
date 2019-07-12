---
title: OrElse 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 02be78c8f2b7529f1fb0e46e9fe610a3c66b0652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860146"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="35073-102">OrElse 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35073-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="35073-103">执行短路逻辑或运算对两个表达式。</span><span class="sxs-lookup"><span data-stu-id="35073-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35073-104">语法</span><span class="sxs-lookup"><span data-stu-id="35073-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="35073-105">部件</span><span class="sxs-lookup"><span data-stu-id="35073-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="35073-106">必需。</span><span class="sxs-lookup"><span data-stu-id="35073-106">Required.</span></span> <span data-ttu-id="35073-107">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="35073-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="35073-108">必需。</span><span class="sxs-lookup"><span data-stu-id="35073-108">Required.</span></span> <span data-ttu-id="35073-109">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="35073-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="35073-110">必需。</span><span class="sxs-lookup"><span data-stu-id="35073-110">Required.</span></span> <span data-ttu-id="35073-111">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="35073-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35073-112">备注</span><span class="sxs-lookup"><span data-stu-id="35073-112">Remarks</span></span>  
 <span data-ttu-id="35073-113">逻辑操作称为*短路*如果已编译的代码可以跳过一个具体取决于另一个表达式的结果表达式的计算。</span><span class="sxs-lookup"><span data-stu-id="35073-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="35073-114">如果计算的第一个表达式的结果确定该操作的最终结果，则无需评估的第二个表达式，因为它不能更改最终结果。</span><span class="sxs-lookup"><span data-stu-id="35073-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="35073-115">如果跳过的表达式很复杂，或如果它涉及过程调用，则短路可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="35073-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="35073-116">如果一个或两个表达式的计算结果为`True`，`result`是`True`。</span><span class="sxs-lookup"><span data-stu-id="35073-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="35073-117">下表说明了如何`result`确定。</span><span class="sxs-lookup"><span data-stu-id="35073-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="35073-118">如果`expression1`是</span><span class="sxs-lookup"><span data-stu-id="35073-118">If `expression1` is</span></span>|<span data-ttu-id="35073-119">和`expression2`是</span><span class="sxs-lookup"><span data-stu-id="35073-119">And `expression2` is</span></span>|<span data-ttu-id="35073-120">值`result`是</span><span class="sxs-lookup"><span data-stu-id="35073-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="35073-121">（不会评估）</span><span class="sxs-lookup"><span data-stu-id="35073-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="35073-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="35073-122">Data Types</span></span>  
 <span data-ttu-id="35073-123">`OrElse`仅对定义运算符[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="35073-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="35073-124">Visual Basic 将根据需要向每个操作数转换`Boolean`之前对表达式求值。</span><span class="sxs-lookup"><span data-stu-id="35073-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="35073-125">如果将结果分配到数值类型，Visual Basic 会将其转换从`Boolean`为该类型，以便`False`变得`0`和`True`变得`-1`。</span><span class="sxs-lookup"><span data-stu-id="35073-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="35073-126">有关详细信息，请参阅[布尔类型转换](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="35073-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="35073-127">重载</span><span class="sxs-lookup"><span data-stu-id="35073-127">Overloading</span></span>  
 <span data-ttu-id="35073-128">[或运算符](../../../visual-basic/language-reference/operators/or-operator.md)并[IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的相应类的类型或结构。</span><span class="sxs-lookup"><span data-stu-id="35073-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="35073-129">重载`Or`并`IsTrue`运算符影响的行为`OrElse`运算符。</span><span class="sxs-lookup"><span data-stu-id="35073-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="35073-130">如果你的代码使用`OrElse`上类或结构的重载`Or`和`IsTrue`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="35073-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="35073-131">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="35073-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35073-132">示例</span><span class="sxs-lookup"><span data-stu-id="35073-132">Example</span></span>  
 <span data-ttu-id="35073-133">下面的示例使用`OrElse`运算符对两个表达式执行逻辑或运算。</span><span class="sxs-lookup"><span data-stu-id="35073-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="35073-134">结果是`Boolean`值，该值表示两个表达式中是否有一个为 true。</span><span class="sxs-lookup"><span data-stu-id="35073-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="35073-135">如果第一个表达式是`True`，则不计算第二个。</span><span class="sxs-lookup"><span data-stu-id="35073-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="35073-136">前面的示例生成的结果`True`， `True`，和`False`分别。</span><span class="sxs-lookup"><span data-stu-id="35073-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="35073-137">中的计算`firstCheck`，因为第一个已不会计算第二个表达式`True`。</span><span class="sxs-lookup"><span data-stu-id="35073-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="35073-138">但是，第二个表达式计算的计算中`secondCheck`。</span><span class="sxs-lookup"><span data-stu-id="35073-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35073-139">示例</span><span class="sxs-lookup"><span data-stu-id="35073-139">Example</span></span>  
 <span data-ttu-id="35073-140">下面的示例演示`If`...`Then`包含两个过程调用语句。</span><span class="sxs-lookup"><span data-stu-id="35073-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="35073-141">如果第一次调用返回`True`，则不调用第二个过程。</span><span class="sxs-lookup"><span data-stu-id="35073-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="35073-142">如果第二个过程执行代码的本部分运行时应始终执行的重要任务，这可能产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="35073-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="35073-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="35073-143">See also</span></span>

- [<span data-ttu-id="35073-144">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35073-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="35073-145">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="35073-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="35073-146">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="35073-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="35073-147">Or 运算符</span><span class="sxs-lookup"><span data-stu-id="35073-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="35073-148">IsTrue 运算符</span><span class="sxs-lookup"><span data-stu-id="35073-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="35073-149">在 Visual Basic 中的逻辑和位运算符</span><span class="sxs-lookup"><span data-stu-id="35073-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
