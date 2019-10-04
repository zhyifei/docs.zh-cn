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
ms.openlocfilehash: 8290e642db3ec76a931bdd2febe427309457bc86
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835234"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="a1052-102">OrElse 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1052-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="a1052-103">对两个表达式执行短路包含逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="a1052-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1052-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1052-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a1052-105">部件</span><span class="sxs-lookup"><span data-stu-id="a1052-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a1052-106">必需。</span><span class="sxs-lookup"><span data-stu-id="a1052-106">Required.</span></span> <span data-ttu-id="a1052-107">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="a1052-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="a1052-108">必需。</span><span class="sxs-lookup"><span data-stu-id="a1052-108">Required.</span></span> <span data-ttu-id="a1052-109">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="a1052-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a1052-110">必需。</span><span class="sxs-lookup"><span data-stu-id="a1052-110">Required.</span></span> <span data-ttu-id="a1052-111">任何 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="a1052-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1052-112">备注</span><span class="sxs-lookup"><span data-stu-id="a1052-112">Remarks</span></span>  
 <span data-ttu-id="a1052-113">如果编译后的代码可以根据另一个表达式的结果跳过对一个表达式的计算，则将逻辑运算称为*短路*。</span><span class="sxs-lookup"><span data-stu-id="a1052-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="a1052-114">如果第一个表达式的计算结果确定了运算的最终结果，则不需要计算第二个表达式，因为它不能更改最终结果。</span><span class="sxs-lookup"><span data-stu-id="a1052-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="a1052-115">如果绕过的表达式较复杂，或者它涉及过程调用，则短路可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="a1052-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="a1052-116">如果任意一个或两个表达式的计算结果都为 `True`，`result` `True`。</span><span class="sxs-lookup"><span data-stu-id="a1052-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="a1052-117">下表说明了如何确定 `result`。</span><span class="sxs-lookup"><span data-stu-id="a1052-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="a1052-118">如果`expression1`为</span><span class="sxs-lookup"><span data-stu-id="a1052-118">If `expression1` is</span></span>|<span data-ttu-id="a1052-119">并且`expression2`为</span><span class="sxs-lookup"><span data-stu-id="a1052-119">And `expression2` is</span></span>|<span data-ttu-id="a1052-120">@No__t 值为</span><span class="sxs-lookup"><span data-stu-id="a1052-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="a1052-121">（未计算）</span><span class="sxs-lookup"><span data-stu-id="a1052-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="a1052-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="a1052-122">Data Types</span></span>  
 <span data-ttu-id="a1052-123">仅为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)定义 `OrElse` 运算符。</span><span class="sxs-lookup"><span data-stu-id="a1052-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="a1052-124">Visual Basic 在计算表达式之前，根据需要将每个操作数转换为 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a1052-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="a1052-125">如果将结果赋给数值类型，Visual Basic 会将其从 @no__t 0 转换为该类型，以便 `False` 变为 `0`，@no__t 为 @no__t。</span><span class="sxs-lookup"><span data-stu-id="a1052-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="a1052-126">有关详细信息，请参阅[布尔类型转换](../data-types/boolean-data-type.md#type-conversions)。</span><span class="sxs-lookup"><span data-stu-id="a1052-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="a1052-127">重载</span><span class="sxs-lookup"><span data-stu-id="a1052-127">Overloading</span></span>  
 <span data-ttu-id="a1052-128">可以*重载* [Or 运算符](../../../visual-basic/language-reference/operators/or-operator.md)和[IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="a1052-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a1052-129">重载 @no__t 0 和 @no__t 1 运算符会影响 @no__t 2 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="a1052-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="a1052-130">如果你的代码在重载 `Or` 和 `IsTrue` 的类或结构上使用 @no__t 0，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="a1052-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="a1052-131">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="a1052-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1052-132">示例</span><span class="sxs-lookup"><span data-stu-id="a1052-132">Example</span></span>  
 <span data-ttu-id="a1052-133">下面的示例使用 `OrElse` 运算符对两个表达式执行逻辑析取。</span><span class="sxs-lookup"><span data-stu-id="a1052-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="a1052-134">结果为 `Boolean` 值，该值表示两个表达式之一是否为 true。</span><span class="sxs-lookup"><span data-stu-id="a1052-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="a1052-135">如果第一个表达式为 `True`，则不计算第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="a1052-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="a1052-136">前面的示例分别产生 `True`、`True` 和 `False` 的结果。</span><span class="sxs-lookup"><span data-stu-id="a1052-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="a1052-137">在 `firstCheck` 的计算中，不计算第二个表达式，因为第一个表达式已 @no__t 为-1。</span><span class="sxs-lookup"><span data-stu-id="a1052-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="a1052-138">但是，第二个表达式的计算结果为 `secondCheck`。</span><span class="sxs-lookup"><span data-stu-id="a1052-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1052-139">示例</span><span class="sxs-lookup"><span data-stu-id="a1052-139">Example</span></span>  
 <span data-ttu-id="a1052-140">下面的示例演示一个 `If` ... @no__t 语句，其中包含两个过程调用。</span><span class="sxs-lookup"><span data-stu-id="a1052-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="a1052-141">如果第一个调用返回 `True`，则不会调用第二个过程。</span><span class="sxs-lookup"><span data-stu-id="a1052-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="a1052-142">如果第二个过程执行的重要任务应始终在此部分代码运行时执行，这可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="a1052-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="a1052-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1052-143">See also</span></span>

- [<span data-ttu-id="a1052-144">逻辑/按位运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="a1052-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="a1052-145">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="a1052-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a1052-146">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="a1052-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a1052-147">Or 运算符</span><span class="sxs-lookup"><span data-stu-id="a1052-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="a1052-148">IsTrue 运算符</span><span class="sxs-lookup"><span data-stu-id="a1052-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="a1052-149">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="a1052-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
