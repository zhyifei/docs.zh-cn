---
title: If 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 192309a7ca728feb300e867bf2340e669e9da16c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603959"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="401aa-102">If 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="401aa-102">If Operator (Visual Basic)</span></span>
<span data-ttu-id="401aa-103">使用短路计算有条件地返回两个值之一。</span><span class="sxs-lookup"><span data-stu-id="401aa-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="401aa-104">`If`使用三个自变量或两个自变量，可以调用运算符。</span><span class="sxs-lookup"><span data-stu-id="401aa-104">The `If` operator can be called with three arguments or with two arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401aa-105">语法</span><span class="sxs-lookup"><span data-stu-id="401aa-105">Syntax</span></span>  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="401aa-106">如果使用三个自变量调用的运算符</span><span class="sxs-lookup"><span data-stu-id="401aa-106">If Operator Called with Three Arguments</span></span>  
 <span data-ttu-id="401aa-107">当`If`调用通过使用三个自变量，第一个参数必须计算为一个值，可以强制转换为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="401aa-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="401aa-108">`Boolean`值将确定的其他两个自变量的计算并返回。</span><span class="sxs-lookup"><span data-stu-id="401aa-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="401aa-109">下面的列表适用时，才`If`调用通过使用三个自变量的运算符。</span><span class="sxs-lookup"><span data-stu-id="401aa-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="401aa-110">部件</span><span class="sxs-lookup"><span data-stu-id="401aa-110">Parts</span></span>  
  
|<span data-ttu-id="401aa-111">术语</span><span class="sxs-lookup"><span data-stu-id="401aa-111">Term</span></span>|<span data-ttu-id="401aa-112">定义</span><span class="sxs-lookup"><span data-stu-id="401aa-112">Definition</span></span>|  
|---|---|  
|`argument1`|<span data-ttu-id="401aa-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="401aa-113">Required.</span></span> <span data-ttu-id="401aa-114">`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="401aa-114">`Boolean`.</span></span> <span data-ttu-id="401aa-115">确定哪个要计算并返回的其他参数。</span><span class="sxs-lookup"><span data-stu-id="401aa-115">Determines which of the other arguments to evaluate and return.</span></span>|  
|`argument2`|<span data-ttu-id="401aa-116">必须的。</span><span class="sxs-lookup"><span data-stu-id="401aa-116">Required.</span></span> <span data-ttu-id="401aa-117">`Object`。</span><span class="sxs-lookup"><span data-stu-id="401aa-117">`Object`.</span></span> <span data-ttu-id="401aa-118">计算并返回如果`argument1`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="401aa-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|  
|`argument3`|<span data-ttu-id="401aa-119">必须的。</span><span class="sxs-lookup"><span data-stu-id="401aa-119">Required.</span></span> <span data-ttu-id="401aa-120">`Object`。</span><span class="sxs-lookup"><span data-stu-id="401aa-120">`Object`.</span></span> <span data-ttu-id="401aa-121">计算并返回如果`argument1`计算结果为`False`或如果`argument1`是[可以为 Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`变量计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="401aa-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|  
  
 <span data-ttu-id="401aa-122">`If`使用三个自变量调用的运算符的工作原理类似`IIf`函数，只不过前者使用短路计算。</span><span class="sxs-lookup"><span data-stu-id="401aa-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="401aa-123">`IIf`函数始终在所有三个参数，而`If`具有三个自变量的运算符都要都计算其中只有两个。</span><span class="sxs-lookup"><span data-stu-id="401aa-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="401aa-124">第一个`If`自变量的计算，并将结果转换为`Boolean`值，`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="401aa-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="401aa-125">如果值为`True`，`argument2`是计算并返回其值，但`argument3`则不会评估。</span><span class="sxs-lookup"><span data-stu-id="401aa-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="401aa-126">如果值`Boolean`表达式是`False`，`argument3`是计算并返回其值，但`argument2`则不会评估。</span><span class="sxs-lookup"><span data-stu-id="401aa-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="401aa-127">下面的示例演示如何使用`If`使用三个自变量时：</span><span class="sxs-lookup"><span data-stu-id="401aa-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 <span data-ttu-id="401aa-128">下面的示例说明了的价值短路计算。</span><span class="sxs-lookup"><span data-stu-id="401aa-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="401aa-129">该示例演示两次尝试将变量`number`变量`divisor`时除外`divisor`为零。</span><span class="sxs-lookup"><span data-stu-id="401aa-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="401aa-130">在这种情况下，应返回 0，并且不应尝试执行除法运算，否则会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="401aa-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="401aa-131">因为`If`使用表达式短路计算，其计算结果的第二个或第三个参数，具体取决于第一个自变量的值。</span><span class="sxs-lookup"><span data-stu-id="401aa-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="401aa-132">如果第一个参数为 true，除数不为零，则可以安全地评估第二个参数并执行该除法运算。</span><span class="sxs-lookup"><span data-stu-id="401aa-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="401aa-133">如果第一个参数为 false，仅第三个自变量的计算，并返回 0。</span><span class="sxs-lookup"><span data-stu-id="401aa-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="401aa-134">因此，除数为 0 时，不会执行除法并不会产生错误。</span><span class="sxs-lookup"><span data-stu-id="401aa-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="401aa-135">但是，因为`IIf`不使用短路计算，甚至当第一个参数为 false 时，才计算第二个参数。</span><span class="sxs-lookup"><span data-stu-id="401aa-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="401aa-136">这将导致运行时被零除错误。</span><span class="sxs-lookup"><span data-stu-id="401aa-136">This causes a run-time divide-by-zero error.</span></span>  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="401aa-137">如果使用两个自变量调用的运算符</span><span class="sxs-lookup"><span data-stu-id="401aa-137">If Operator Called with Two Arguments</span></span>  
 <span data-ttu-id="401aa-138">第一个参数`If`可以省略。</span><span class="sxs-lookup"><span data-stu-id="401aa-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="401aa-139">这使操作员能够使用仅有两个自变量进行调用。</span><span class="sxs-lookup"><span data-stu-id="401aa-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="401aa-140">下面的列表适用时，才`If`运算符调用带有两个参数。</span><span class="sxs-lookup"><span data-stu-id="401aa-140">The following list applies only when the `If` operator is called with two arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="401aa-141">部件</span><span class="sxs-lookup"><span data-stu-id="401aa-141">Parts</span></span>  
  
|<span data-ttu-id="401aa-142">术语</span><span class="sxs-lookup"><span data-stu-id="401aa-142">Term</span></span>|<span data-ttu-id="401aa-143">定义</span><span class="sxs-lookup"><span data-stu-id="401aa-143">Definition</span></span>|  
|---|---|  
|`argument2`|<span data-ttu-id="401aa-144">必须的。</span><span class="sxs-lookup"><span data-stu-id="401aa-144">Required.</span></span> <span data-ttu-id="401aa-145">`Object`。</span><span class="sxs-lookup"><span data-stu-id="401aa-145">`Object`.</span></span> <span data-ttu-id="401aa-146">必须是引用或可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="401aa-146">Must be a reference or nullable type.</span></span> <span data-ttu-id="401aa-147">其计算结果为任何内容以外时计算并返回`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="401aa-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|  
|`argument3`|<span data-ttu-id="401aa-148">必须的。</span><span class="sxs-lookup"><span data-stu-id="401aa-148">Required.</span></span> <span data-ttu-id="401aa-149">`Object`。</span><span class="sxs-lookup"><span data-stu-id="401aa-149">`Object`.</span></span> <span data-ttu-id="401aa-150">计算并返回如果`argument2`计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="401aa-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|  
  
 <span data-ttu-id="401aa-151">当`Boolean`忽略自变量，第一个参数必须是引用或可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="401aa-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable type.</span></span> <span data-ttu-id="401aa-152">如果第一个自变量的计算结果为`Nothing`，返回第二个参数的值。</span><span class="sxs-lookup"><span data-stu-id="401aa-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="401aa-153">在所有其他情况下，返回第一个自变量的值。</span><span class="sxs-lookup"><span data-stu-id="401aa-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="401aa-154">下面的示例阐释了这种计算的工作原理。</span><span class="sxs-lookup"><span data-stu-id="401aa-154">The following example illustrates how this evaluation works.</span></span>  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="401aa-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="401aa-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>  
 [<span data-ttu-id="401aa-156">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="401aa-156">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="401aa-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="401aa-157">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
