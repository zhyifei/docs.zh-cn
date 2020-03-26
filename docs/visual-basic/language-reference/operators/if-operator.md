---
title: If 运算符
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
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249482"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="82d25-102">If 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82d25-102">If Operator (Visual Basic)</span></span>

<span data-ttu-id="82d25-103">使用短路评估有条件地返回两个值之一。</span><span class="sxs-lookup"><span data-stu-id="82d25-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="82d25-104">可以使用`If`三个参数或两个参数调用运算符。</span><span class="sxs-lookup"><span data-stu-id="82d25-104">The `If` operator can be called with three arguments or with two arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="82d25-105">语法</span><span class="sxs-lookup"><span data-stu-id="82d25-105">Syntax</span></span>

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="82d25-106">如果运算符使用三个参数调用</span><span class="sxs-lookup"><span data-stu-id="82d25-106">If operator called with three arguments</span></span>

<span data-ttu-id="82d25-107">使用`If`三个参数调用时，第一个参数必须计算为可以转换为 的值`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="82d25-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="82d25-108">该`Boolean`值将确定计算并返回其他两个参数中的哪一个。</span><span class="sxs-lookup"><span data-stu-id="82d25-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="82d25-109">仅当使用三个参数调用运算符`If`时，以下列表才适用。</span><span class="sxs-lookup"><span data-stu-id="82d25-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="82d25-110">组成部分</span><span class="sxs-lookup"><span data-stu-id="82d25-110">Parts</span></span>

|<span data-ttu-id="82d25-111">术语</span><span class="sxs-lookup"><span data-stu-id="82d25-111">Term</span></span>|<span data-ttu-id="82d25-112">定义</span><span class="sxs-lookup"><span data-stu-id="82d25-112">Definition</span></span>|
|---|---|
|`argument1`|<span data-ttu-id="82d25-113">必需。</span><span class="sxs-lookup"><span data-stu-id="82d25-113">Required.</span></span> <span data-ttu-id="82d25-114">`Boolean`.</span><span class="sxs-lookup"><span data-stu-id="82d25-114">`Boolean`.</span></span> <span data-ttu-id="82d25-115">确定要计算和返回的其他参数。</span><span class="sxs-lookup"><span data-stu-id="82d25-115">Determines which of the other arguments to evaluate and return.</span></span>|
|`argument2`|<span data-ttu-id="82d25-116">必需。</span><span class="sxs-lookup"><span data-stu-id="82d25-116">Required.</span></span> <span data-ttu-id="82d25-117">`Object`.</span><span class="sxs-lookup"><span data-stu-id="82d25-117">`Object`.</span></span> <span data-ttu-id="82d25-118">如果`argument1`评估为`True`，则评估并返回。</span><span class="sxs-lookup"><span data-stu-id="82d25-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|
|`argument3`|<span data-ttu-id="82d25-119">必需。</span><span class="sxs-lookup"><span data-stu-id="82d25-119">Required.</span></span> <span data-ttu-id="82d25-120">`Object`.</span><span class="sxs-lookup"><span data-stu-id="82d25-120">`Object`.</span></span> <span data-ttu-id="82d25-121">`argument1`如果计算为`False`或`argument1`如果为"[无"](../../../visual-basic/language-reference/nothing.md)[的可无变量](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean`，则计算并返回。</span><span class="sxs-lookup"><span data-stu-id="82d25-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|

<span data-ttu-id="82d25-122">使用`If`三个参数调用的运算符的工作方式类似于函数`IIf`，只不过它使用短路计算。</span><span class="sxs-lookup"><span data-stu-id="82d25-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="82d25-123">函数`IIf`始终计算其所有三个参数，而具有三个`If`参数的运算符只计算其中两个参数。</span><span class="sxs-lookup"><span data-stu-id="82d25-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="82d25-124">计算第`If`一个`Boolean`参数，并将结果强制转换为值或`True``False`。</span><span class="sxs-lookup"><span data-stu-id="82d25-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="82d25-125">如果值为`True`，`argument2`则计算其值，但不`argument3`计算该值。</span><span class="sxs-lookup"><span data-stu-id="82d25-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="82d25-126">如果`Boolean`表达式的值为`False`，`argument3`则计算其值并返回其值，但不`argument2`计算。</span><span class="sxs-lookup"><span data-stu-id="82d25-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="82d25-127">以下示例说明了使用三个参数`If`时的使用：</span><span class="sxs-lookup"><span data-stu-id="82d25-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

<span data-ttu-id="82d25-128">下面的示例说明了短路评估的价值。</span><span class="sxs-lookup"><span data-stu-id="82d25-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="82d25-129">该示例显示两次尝试将变量`number`除以变量`divisor`除以`divisor`变量，但为零时除外。</span><span class="sxs-lookup"><span data-stu-id="82d25-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="82d25-130">在这种情况下，应返回 0，并且不应尝试执行除法，因为将导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="82d25-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="82d25-131">由于`If`表达式使用短路计算，因此根据第一个参数的值计算第二个或第三个参数。</span><span class="sxs-lookup"><span data-stu-id="82d25-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="82d25-132">如果第一个参数为 true，则除法不是零，可以安全地计算第二个参数并执行除法。</span><span class="sxs-lookup"><span data-stu-id="82d25-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="82d25-133">如果第一个参数为 false，则仅计算第三个参数并返回 0。</span><span class="sxs-lookup"><span data-stu-id="82d25-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="82d25-134">因此，当除法器为 0 时，不会尝试执行除法，也没有错误结果。</span><span class="sxs-lookup"><span data-stu-id="82d25-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="82d25-135">但是，由于`IIf`不使用短路计算，因此即使第一个参数为 false，也会计算第二个参数。</span><span class="sxs-lookup"><span data-stu-id="82d25-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="82d25-136">这将导致运行时除以零错误。</span><span class="sxs-lookup"><span data-stu-id="82d25-136">This causes a run-time divide-by-zero error.</span></span>

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="82d25-137">如果运算符使用两个参数调用</span><span class="sxs-lookup"><span data-stu-id="82d25-137">If operator called with two arguments</span></span>

<span data-ttu-id="82d25-138">`If`可以省略的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="82d25-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="82d25-139">这样，只需使用两个参数就可以调用运算符。</span><span class="sxs-lookup"><span data-stu-id="82d25-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="82d25-140">仅当使用两个参数调用运算符`If`时，以下列表才适用。</span><span class="sxs-lookup"><span data-stu-id="82d25-140">The following list applies only when the `If` operator is called with two arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="82d25-141">组成部分</span><span class="sxs-lookup"><span data-stu-id="82d25-141">Parts</span></span>

|<span data-ttu-id="82d25-142">术语</span><span class="sxs-lookup"><span data-stu-id="82d25-142">Term</span></span>|<span data-ttu-id="82d25-143">定义</span><span class="sxs-lookup"><span data-stu-id="82d25-143">Definition</span></span>|
|---|---|
|`argument2`|<span data-ttu-id="82d25-144">必需。</span><span class="sxs-lookup"><span data-stu-id="82d25-144">Required.</span></span> <span data-ttu-id="82d25-145">`Object`.</span><span class="sxs-lookup"><span data-stu-id="82d25-145">`Object`.</span></span> <span data-ttu-id="82d25-146">必须是引用值或空值类型。</span><span class="sxs-lookup"><span data-stu-id="82d25-146">Must be a reference or nullable value type.</span></span> <span data-ttu-id="82d25-147">当它评估到 以外的任何`Nothing`内容时，它进行评估并返回。</span><span class="sxs-lookup"><span data-stu-id="82d25-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|
|`argument3`|<span data-ttu-id="82d25-148">必需。</span><span class="sxs-lookup"><span data-stu-id="82d25-148">Required.</span></span> <span data-ttu-id="82d25-149">`Object`.</span><span class="sxs-lookup"><span data-stu-id="82d25-149">`Object`.</span></span> <span data-ttu-id="82d25-150">如果`argument2`评估为`Nothing`，则评估并返回。</span><span class="sxs-lookup"><span data-stu-id="82d25-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|

<span data-ttu-id="82d25-151">省略`Boolean`参数时，第一个参数必须是引用值类型或空值类型。</span><span class="sxs-lookup"><span data-stu-id="82d25-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable value type.</span></span> <span data-ttu-id="82d25-152">如果第一个参数计算到`Nothing`，则返回第二个参数的值。</span><span class="sxs-lookup"><span data-stu-id="82d25-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="82d25-153">在所有其他情况下，将返回第一个参数的值。</span><span class="sxs-lookup"><span data-stu-id="82d25-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="82d25-154">以下示例说明了此评估的工作原理：</span><span class="sxs-lookup"><span data-stu-id="82d25-154">The following example illustrates how this evaluation works:</span></span>

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a><span data-ttu-id="82d25-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="82d25-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="82d25-156">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="82d25-156">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="82d25-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="82d25-157">Nothing</span></span>](../nothing.md)
