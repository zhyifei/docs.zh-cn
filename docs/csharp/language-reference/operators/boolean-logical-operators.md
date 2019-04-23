---
title: 布尔逻辑运算符 - C# 参考
description: 了解使用布尔操作数执行逻辑非、逻辑与、逻辑或和逻辑异或运算的 C# 运算符。
ms.date: 04/08/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: de621b26334bbc9679ba7e48a9d5a0cbaec67eab
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427313"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="5f538-103">布尔逻辑运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5f538-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="5f538-104">以下运算符使用 [bool](../keywords/bool.md) 操作数执行逻辑运算：</span><span class="sxs-lookup"><span data-stu-id="5f538-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="5f538-105">一元 [`!`（逻辑非）](#logical-negation-operator-)运算符。</span><span class="sxs-lookup"><span data-stu-id="5f538-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="5f538-106">二元 [`&`（逻辑与）](#logical-and-operator-)、[`|`（逻辑或）](#logical-or-operator-)和 [`^`（逻辑异或）](#logical-exclusive-or-operator-)运算符。</span><span class="sxs-lookup"><span data-stu-id="5f538-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="5f538-107">这些运算符始终计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="5f538-108">二元 [`&&`（条件逻辑与）](#conditional-logical-and-operator-)和 [`||`（条件逻辑或）](#conditional-logical-or-operator-)运算符。</span><span class="sxs-lookup"><span data-stu-id="5f538-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="5f538-109">这些运算符仅在必要时才计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="5f538-110">对于[整型](../keywords/integral-types-table.md)类型操作数，`&`、`|` 和 `^` 运算符执行位逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="5f538-110">For the operands of [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="5f538-111">逻辑非运算符 !</span><span class="sxs-lookup"><span data-stu-id="5f538-111">Logical negation operator !</span></span>

<span data-ttu-id="5f538-112">`!` 运算符计算操作数的逻辑非。</span><span class="sxs-lookup"><span data-stu-id="5f538-112">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="5f538-113">也就是说，如果操作数的计算结果为 `false`，它生成 `true`；如果操作数的计算结果为 `true`，它生成 `false`：</span><span class="sxs-lookup"><span data-stu-id="5f538-113">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="5f538-114">逻辑与运算符 &amp;</span><span class="sxs-lookup"><span data-stu-id="5f538-114">Logical AND operator &amp;</span></span>

<span data-ttu-id="5f538-115">`&` 运算符计算操作数的逻辑与。</span><span class="sxs-lookup"><span data-stu-id="5f538-115">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="5f538-116">如果 `x` 和 `y` 的计算结果都为 `true`，则 `x & y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5f538-116">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="5f538-117">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f538-117">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="5f538-118">即使第一个操作数计算结果为 `false`，`&` 运算符也会计算这两个操作数，而在这种情况下，无论第二个操作数的值为何，结果都肯定为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f538-118">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="5f538-119">在下面的示例中，`&` 运算符的第二个操作数是方法调用，无论第一个操作数的值如何，都会执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="5f538-119">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="5f538-120">[条件逻辑与运算符](#conditional-logical-and-operator-) `&&` 也计算操作数的逻辑与，但如果第一个操作数的计算结果为 `false`，它就不会计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-120">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="5f538-121">对于整型类型的操作数，`&` 运算符计算操作数的[位逻辑与](and-operator.md#integer-logical-bitwise-and-operator)。</span><span class="sxs-lookup"><span data-stu-id="5f538-121">For the operands of integral types, the `&` operator computes [bitwise logical AND](and-operator.md#integer-logical-bitwise-and-operator) of its operands.</span></span> <span data-ttu-id="5f538-122">一元 `&` 运算符是 [address-of 运算符](and-operator.md#unary-address-of-operator)。</span><span class="sxs-lookup"><span data-stu-id="5f538-122">The unary `&` operator is the [address-of operator](and-operator.md#unary-address-of-operator).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="5f538-123">逻辑异或运算符 ^</span><span class="sxs-lookup"><span data-stu-id="5f538-123">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="5f538-124">`^` 运算符计算操作数的逻辑异或（亦称为“逻辑 XOR”）。</span><span class="sxs-lookup"><span data-stu-id="5f538-124">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="5f538-125">如果 `x` 计算结果为 `true` 且 `y` 计算结果为 `false`，或者 `x` 计算结果为 `false` 且 `y` 计算结果为 `true`，那么 `x ^ y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5f538-125">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="5f538-126">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f538-126">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5f538-127">也就是说，对于 `bool` 操作数，`^` 运算符的计算结果与[不等运算符](equality-operators.md#inequality-operator-) `!=` 相同。</span><span class="sxs-lookup"><span data-stu-id="5f538-127">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="5f538-128">对于整型类型的操作数，`^` 运算符计算操作数的[位逻辑异或](xor-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="5f538-128">For the operands of integral types, the `^` operator computes [bitwise logical exclusive OR](xor-operator.md) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="5f538-129">逻辑或运算符 |</span><span class="sxs-lookup"><span data-stu-id="5f538-129">Logical OR operator |</span></span>

<span data-ttu-id="5f538-130">`|` 运算符计算操作数的逻辑或。</span><span class="sxs-lookup"><span data-stu-id="5f538-130">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="5f538-131">如果 `x` 或 `y` 的计算结果为 `true`，则 `x | y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5f538-131">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="5f538-132">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f538-132">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="5f538-133">即使第一个操作数计算结果为 `true`，`|` 运算符也会计算这两个操作数，而在这种情况下，无论第二个操作数的值为何，结果都肯定为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5f538-133">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="5f538-134">在下面的示例中，`|` 运算符的第二个操作数是方法调用，无论第一个操作数的值如何，都会执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="5f538-134">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="5f538-135">[条件逻辑或运算符](#conditional-logical-or-operator-) `||` 也计算操作数的逻辑或，但如果第一个操作数的计算结果为 `true`，它就不会计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-135">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="5f538-136">对于整型类型的操作数，`|` 运算符计算操作数的[位逻辑或](or-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="5f538-136">For the operands of integral types, the `|` operator computes [bitwise logical OR](or-operator.md) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="5f538-137">条件逻辑与运算符 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="5f538-137">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="5f538-138">条件逻辑与运算符 `&&`（亦称为“短路”逻辑与运算符）计算操作数的逻辑与。</span><span class="sxs-lookup"><span data-stu-id="5f538-138">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="5f538-139">如果 `x` 和 `y` 的计算结果都为 `true`，则 `x && y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5f538-139">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="5f538-140">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f538-140">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5f538-141">如果第一个操作数的计算结果为 `false`，它就不会计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-141">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="5f538-142">在下面的示例中，`&&` 运算符的第二个操作数是方法调用，如果第一个操作数的计算结果为 `false`，就不执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="5f538-142">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="5f538-143">[逻辑与运算符](#logical-and-operator-) `&` 也计算操作数的逻辑与，但始终计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-143">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="5f538-144">条件逻辑或运算符 ||</span><span class="sxs-lookup"><span data-stu-id="5f538-144">Conditional logical OR operator ||</span></span>

<span data-ttu-id="5f538-145">条件逻辑或运算符 `||`（亦称为“短路”逻辑或运算符）计算操作数的逻辑或。</span><span class="sxs-lookup"><span data-stu-id="5f538-145">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="5f538-146">如果 `x` 或 `y` 的计算结果为 `true`，则 `x || y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5f538-146">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="5f538-147">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f538-147">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5f538-148">如果第一个操作数的计算结果为 `true`，它就不会计算第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-148">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="5f538-149">在下面的示例中，`||` 运算符的第二个操作数是方法调用，如果第一个操作数的计算结果为 `true`，就不执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="5f538-149">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="5f538-150">[逻辑或运算符](#logical-or-operator-) `|` 也计算操作数的逻辑或，但始终计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-150">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="5f538-151">可以为 null 的布尔逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-151">Nullable Boolean logical operators</span></span>

<span data-ttu-id="5f538-152">对于 `bool?` 操作数，`&` 和 `|` 运算符支持三值逻辑。</span><span class="sxs-lookup"><span data-stu-id="5f538-152">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="5f538-153">由下表定义这些运算符的语义：</span><span class="sxs-lookup"><span data-stu-id="5f538-153">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="5f538-154">x</span><span class="sxs-lookup"><span data-stu-id="5f538-154">x</span></span>|<span data-ttu-id="5f538-155">y</span><span class="sxs-lookup"><span data-stu-id="5f538-155">y</span></span>|<span data-ttu-id="5f538-156">x 和 y</span><span class="sxs-lookup"><span data-stu-id="5f538-156">x&y</span></span>|<span data-ttu-id="5f538-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="5f538-157">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="5f538-158">true</span><span class="sxs-lookup"><span data-stu-id="5f538-158">true</span></span>|<span data-ttu-id="5f538-159">true</span><span class="sxs-lookup"><span data-stu-id="5f538-159">true</span></span>|<span data-ttu-id="5f538-160">true</span><span class="sxs-lookup"><span data-stu-id="5f538-160">true</span></span>|<span data-ttu-id="5f538-161">true</span><span class="sxs-lookup"><span data-stu-id="5f538-161">true</span></span>|  
|<span data-ttu-id="5f538-162">true</span><span class="sxs-lookup"><span data-stu-id="5f538-162">true</span></span>|<span data-ttu-id="5f538-163">False</span><span class="sxs-lookup"><span data-stu-id="5f538-163">false</span></span>|<span data-ttu-id="5f538-164">false</span><span class="sxs-lookup"><span data-stu-id="5f538-164">false</span></span>|<span data-ttu-id="5f538-165">true</span><span class="sxs-lookup"><span data-stu-id="5f538-165">true</span></span>|  
|<span data-ttu-id="5f538-166">true</span><span class="sxs-lookup"><span data-stu-id="5f538-166">true</span></span>|<span data-ttu-id="5f538-167">null</span><span class="sxs-lookup"><span data-stu-id="5f538-167">null</span></span>|<span data-ttu-id="5f538-168">null</span><span class="sxs-lookup"><span data-stu-id="5f538-168">null</span></span>|<span data-ttu-id="5f538-169">true</span><span class="sxs-lookup"><span data-stu-id="5f538-169">true</span></span>|  
|<span data-ttu-id="5f538-170">False</span><span class="sxs-lookup"><span data-stu-id="5f538-170">false</span></span>|<span data-ttu-id="5f538-171">true</span><span class="sxs-lookup"><span data-stu-id="5f538-171">true</span></span>|<span data-ttu-id="5f538-172">False</span><span class="sxs-lookup"><span data-stu-id="5f538-172">false</span></span>|<span data-ttu-id="5f538-173">true</span><span class="sxs-lookup"><span data-stu-id="5f538-173">true</span></span>|  
|<span data-ttu-id="5f538-174">False</span><span class="sxs-lookup"><span data-stu-id="5f538-174">false</span></span>|<span data-ttu-id="5f538-175">False</span><span class="sxs-lookup"><span data-stu-id="5f538-175">false</span></span>|<span data-ttu-id="5f538-176">False</span><span class="sxs-lookup"><span data-stu-id="5f538-176">false</span></span>|<span data-ttu-id="5f538-177">False</span><span class="sxs-lookup"><span data-stu-id="5f538-177">false</span></span>|  
|<span data-ttu-id="5f538-178">False</span><span class="sxs-lookup"><span data-stu-id="5f538-178">false</span></span>|<span data-ttu-id="5f538-179">null</span><span class="sxs-lookup"><span data-stu-id="5f538-179">null</span></span>|<span data-ttu-id="5f538-180">False</span><span class="sxs-lookup"><span data-stu-id="5f538-180">false</span></span>|<span data-ttu-id="5f538-181">null</span><span class="sxs-lookup"><span data-stu-id="5f538-181">null</span></span>|  
|<span data-ttu-id="5f538-182">null</span><span class="sxs-lookup"><span data-stu-id="5f538-182">null</span></span>|<span data-ttu-id="5f538-183">true</span><span class="sxs-lookup"><span data-stu-id="5f538-183">true</span></span>|<span data-ttu-id="5f538-184">null</span><span class="sxs-lookup"><span data-stu-id="5f538-184">null</span></span>|<span data-ttu-id="5f538-185">true</span><span class="sxs-lookup"><span data-stu-id="5f538-185">true</span></span>|  
|<span data-ttu-id="5f538-186">null</span><span class="sxs-lookup"><span data-stu-id="5f538-186">null</span></span>|<span data-ttu-id="5f538-187">False</span><span class="sxs-lookup"><span data-stu-id="5f538-187">false</span></span>|<span data-ttu-id="5f538-188">False</span><span class="sxs-lookup"><span data-stu-id="5f538-188">false</span></span>|<span data-ttu-id="5f538-189">null</span><span class="sxs-lookup"><span data-stu-id="5f538-189">null</span></span>|  
|<span data-ttu-id="5f538-190">null</span><span class="sxs-lookup"><span data-stu-id="5f538-190">null</span></span>|<span data-ttu-id="5f538-191">null</span><span class="sxs-lookup"><span data-stu-id="5f538-191">null</span></span>|<span data-ttu-id="5f538-192">null</span><span class="sxs-lookup"><span data-stu-id="5f538-192">null</span></span>|<span data-ttu-id="5f538-193">null</span><span class="sxs-lookup"><span data-stu-id="5f538-193">null</span></span>|  

<span data-ttu-id="5f538-194">这些运算符的行为不同于值类型可以为 null 的典型运算符行为。</span><span class="sxs-lookup"><span data-stu-id="5f538-194">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="5f538-195">通常情况下，为值类型的操作数定义的运算符也能与值类型可以为 null 的相应操作数一起使用。</span><span class="sxs-lookup"><span data-stu-id="5f538-195">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="5f538-196">如果任何操作数是 `null`，此类运算符都会生成 `null`。</span><span class="sxs-lookup"><span data-stu-id="5f538-196">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="5f538-197">不过，即使操作数之一是 `null`，`&` 和 `|` 运算符也可以生成非 null。</span><span class="sxs-lookup"><span data-stu-id="5f538-197">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="5f538-198">若要详细了解值类型可以为 null 的运算符行为，请参阅[使用可以为 null 的类型](../../programming-guide/nullable-types/using-nullable-types.md)一文的[运算符](../../programming-guide/nullable-types/using-nullable-types.md#operators)部分。</span><span class="sxs-lookup"><span data-stu-id="5f538-198">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="5f538-199">还可以将 `!` 和 `^` 运算符与 `bool?` 操作数结合使用，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="5f538-199">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="5f538-200">条件逻辑运算符 `&&` 和 `||` 不支持 `bool?` 操作数。</span><span class="sxs-lookup"><span data-stu-id="5f538-200">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="5f538-201">复合赋值</span><span class="sxs-lookup"><span data-stu-id="5f538-201">Compound assignment</span></span>

<span data-ttu-id="5f538-202">对于二元运算符 `op`，窗体的复合赋值表达式</span><span class="sxs-lookup"><span data-stu-id="5f538-202">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="5f538-203">等效于</span><span class="sxs-lookup"><span data-stu-id="5f538-203">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="5f538-204">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="5f538-204">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="5f538-205">`&`、`|` 和 `^` 运算符支持复合赋值，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="5f538-205">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="5f538-206">条件逻辑运算符 `&&` 和 `||` 不支持复合赋值。</span><span class="sxs-lookup"><span data-stu-id="5f538-206">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="5f538-207">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="5f538-207">Operator precedence</span></span>

<span data-ttu-id="5f538-208">以下列表按优先级从高到低的顺序对逻辑运算符进行排序：</span><span class="sxs-lookup"><span data-stu-id="5f538-208">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="5f538-209">逻辑非运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-209">Logical negation operator</span></span> `!`
- <span data-ttu-id="5f538-210">逻辑 AND 运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-210">Logical AND operator</span></span> `&`
- <span data-ttu-id="5f538-211">逻辑异或运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-211">Logical exclusive OR operator</span></span> `^`
- <span data-ttu-id="5f538-212">逻辑 OR 运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-212">Logical OR operator</span></span> `|`
- <span data-ttu-id="5f538-213">条件逻辑与运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-213">Conditional logical AND operator</span></span> `&&`
- <span data-ttu-id="5f538-214">条件逻辑或运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-214">Conditional logical OR operator</span></span> `||`

<span data-ttu-id="5f538-215">使用括号 `()` 可以更改运算符优先级决定的计算顺序：</span><span class="sxs-lookup"><span data-stu-id="5f538-215">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="5f538-216">要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="5f538-216">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5f538-217">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="5f538-217">Operator overloadability</span></span>

<span data-ttu-id="5f538-218">用户定义类型可以[重载](../keywords/operator.md) `!`、`&`、`|` 和 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="5f538-218">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="5f538-219">重载二元运算符时，对应的复合赋值运算符也会隐式重载。</span><span class="sxs-lookup"><span data-stu-id="5f538-219">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="5f538-220">用户定义类型不能显式重载复合赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="5f538-220">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="5f538-221">用户定义类型无法重载条件逻辑运算符 `&&` 和 `||`。</span><span class="sxs-lookup"><span data-stu-id="5f538-221">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="5f538-222">不过，如果用户定义类型以某种方式重载 [true 和 false 运算符](../keywords/true-false-operators.md)以及 `&` 或 `|` 运算符，可以对相应类型的操作数执行 `&&` 或 `||` 运算。</span><span class="sxs-lookup"><span data-stu-id="5f538-222">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="5f538-223">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="5f538-223">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5f538-224">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5f538-224">C# language specification</span></span>

<span data-ttu-id="5f538-225">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="5f538-225">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="5f538-226">逻辑非运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-226">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="5f538-227">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-227">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="5f538-228">条件逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-228">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)

## <a name="see-also"></a><span data-ttu-id="5f538-229">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f538-229">See also</span></span>

- [<span data-ttu-id="5f538-230">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5f538-230">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5f538-231">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5f538-231">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5f538-232">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5f538-232">C# Operators</span></span>](index.md)
