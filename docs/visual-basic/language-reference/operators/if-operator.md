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
ms.openlocfilehash: 9ab01755d75c91ce87acf83e7f406b26c466aef6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834629"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="a2b5e-102">If 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2b5e-102">If Operator (Visual Basic)</span></span>
<span data-ttu-id="a2b5e-103">使用短路计算有条件地返回两个值之一。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="a2b5e-104">`If`带有三个参数或两个参数，可以调用运算符。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-104">The `If` operator can be called with three arguments or with two arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b5e-105">语法</span><span class="sxs-lookup"><span data-stu-id="a2b5e-105">Syntax</span></span>  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="a2b5e-106">如果使用三个自变量调用运算符</span><span class="sxs-lookup"><span data-stu-id="a2b5e-106">If Operator Called with Three Arguments</span></span>  
 <span data-ttu-id="a2b5e-107">当`If`调用通过使用三个参数，第一个参数必须为一个值，可以强制转换为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="a2b5e-108">`Boolean`值将确定哪些其他两个参数是进行计算并返回。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="a2b5e-109">下面的列表仅适用于`If`使用三个自变量调用运算符。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="a2b5e-110">部件</span><span class="sxs-lookup"><span data-stu-id="a2b5e-110">Parts</span></span>  
  
|<span data-ttu-id="a2b5e-111">术语</span><span class="sxs-lookup"><span data-stu-id="a2b5e-111">Term</span></span>|<span data-ttu-id="a2b5e-112">定义</span><span class="sxs-lookup"><span data-stu-id="a2b5e-112">Definition</span></span>|  
|---|---|  
|`argument1`|<span data-ttu-id="a2b5e-113">必需。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-113">Required.</span></span> <span data-ttu-id="a2b5e-114">`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-114">`Boolean`.</span></span> <span data-ttu-id="a2b5e-115">确定哪些要计算并返回的其他参数。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-115">Determines which of the other arguments to evaluate and return.</span></span>|  
|`argument2`|<span data-ttu-id="a2b5e-116">必需。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-116">Required.</span></span> <span data-ttu-id="a2b5e-117">`Object`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-117">`Object`.</span></span> <span data-ttu-id="a2b5e-118">计算并返回 if`argument1`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|  
|`argument3`|<span data-ttu-id="a2b5e-119">必需。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-119">Required.</span></span> <span data-ttu-id="a2b5e-120">`Object`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-120">`Object`.</span></span> <span data-ttu-id="a2b5e-121">计算并返回 if`argument1`计算结果为`False`或者如果`argument1`是[Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`变量的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|  
  
 <span data-ttu-id="a2b5e-122">`If`运算符，它使用三个自变量调用的工作方式类似于`IIf`函数，但它使用短路计算。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="a2b5e-123">`IIf`函数始终计算所有三个参数，而`If`具有三个自变量的运算符都要都计算其中只有两个。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="a2b5e-124">第一个`If`自变量计算并将结果转换为`Boolean`值，`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="a2b5e-125">如果值为`True`，`argument2`是进行计算并返回其值，但`argument3`则不会评估。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="a2b5e-126">如果的值`Boolean`表达式是`False`，`argument3`是进行计算并返回其值，但`argument2`则不会评估。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="a2b5e-127">下面的示例说明如何使用`If`使用了三个参数：</span><span class="sxs-lookup"><span data-stu-id="a2b5e-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 <span data-ttu-id="a2b5e-128">下面的示例说明了的价值短路计算。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="a2b5e-129">该示例显示了两次尝试将变量`number`由变量`divisor`例外`divisor`为零。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="a2b5e-130">在这种情况下，应返回 0，并且不应尝试执行该除法运算，否则会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="a2b5e-131">因为`If`中使用表达式短路计算时，将计算第二个或第三个参数，具体取决于第一个参数的值。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="a2b5e-132">如果第一个参数为 true，除数不为零，则可以安全地评估第二个参数，并执行该除法运算。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="a2b5e-133">如果第一个参数为 false，计算仅第三个参数，并返回 0。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="a2b5e-134">因此，如果除数为 0，任何尝试执行除法并不会产生错误。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="a2b5e-135">但是，因为`IIf`不使用短路计算，即使第一个参数为 false，则计算第二个参数。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="a2b5e-136">这将导致运行时被零除错误。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-136">This causes a run-time divide-by-zero error.</span></span>  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="a2b5e-137">如果使用两个自变量调用运算符</span><span class="sxs-lookup"><span data-stu-id="a2b5e-137">If Operator Called with Two Arguments</span></span>  
 <span data-ttu-id="a2b5e-138">第一个参数`If`可以省略。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="a2b5e-139">这使操作员能够使用仅两个参数进行调用。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="a2b5e-140">下面的列表仅适用于`If`使用两个自变量调用运算符。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-140">The following list applies only when the `If` operator is called with two arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="a2b5e-141">部件</span><span class="sxs-lookup"><span data-stu-id="a2b5e-141">Parts</span></span>  
  
|<span data-ttu-id="a2b5e-142">术语</span><span class="sxs-lookup"><span data-stu-id="a2b5e-142">Term</span></span>|<span data-ttu-id="a2b5e-143">定义</span><span class="sxs-lookup"><span data-stu-id="a2b5e-143">Definition</span></span>|  
|---|---|  
|`argument2`|<span data-ttu-id="a2b5e-144">必需。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-144">Required.</span></span> <span data-ttu-id="a2b5e-145">`Object`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-145">`Object`.</span></span> <span data-ttu-id="a2b5e-146">必须是引用或为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-146">Must be a reference or nullable type.</span></span> <span data-ttu-id="a2b5e-147">进行计算并返回到的任何内容不是评估时`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|  
|`argument3`|<span data-ttu-id="a2b5e-148">必需。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-148">Required.</span></span> <span data-ttu-id="a2b5e-149">`Object`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-149">`Object`.</span></span> <span data-ttu-id="a2b5e-150">计算并返回 if`argument2`计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|  
  
 <span data-ttu-id="a2b5e-151">当`Boolean`省略参数，第一个参数必须是引用或为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable type.</span></span> <span data-ttu-id="a2b5e-152">如果第一个参数的计算结果为`Nothing`，返回的第二个参数的值。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="a2b5e-153">在所有其他情况下，返回第一个参数的值。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="a2b5e-154">以下示例演示了如何进行此评估版。</span><span class="sxs-lookup"><span data-stu-id="a2b5e-154">The following example illustrates how this evaluation works.</span></span>  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="a2b5e-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2b5e-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="a2b5e-156">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="a2b5e-156">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="a2b5e-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="a2b5e-157">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
