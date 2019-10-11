---
title: 布尔逻辑运算符 - C# 参考
description: 了解使用布尔操作数执行逻辑非、逻辑与、逻辑或和逻辑异或运算的 C# 运算符。
ms.date: 09/27/2019
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
ms.openlocfilehash: cc25d4bfd444dc0acb30fc1c6e6c3c9918af537c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698679"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="a9528-103">布尔逻辑运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a9528-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="a9528-104">以下运算符使用 [bool](../keywords/bool.md) 操作数执行逻辑运算：</span><span class="sxs-lookup"><span data-stu-id="a9528-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="a9528-105">一元 [`!`（逻辑非）](#logical-negation-operator-)运算符。</span><span class="sxs-lookup"><span data-stu-id="a9528-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="a9528-106">二元 [`&`（逻辑与）](#logical-and-operator-)、[`|`（逻辑或）](#logical-or-operator-)和 [`^`（逻辑异或）](#logical-exclusive-or-operator-)运算符。</span><span class="sxs-lookup"><span data-stu-id="a9528-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="a9528-107">这些运算符始终计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="a9528-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="a9528-108">二元 [`&&`（条件逻辑与）](#conditional-logical-and-operator-)和 [`||`（条件逻辑或）](#conditional-logical-or-operator-)运算符。</span><span class="sxs-lookup"><span data-stu-id="a9528-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="a9528-109">这些运算符仅在必要时才计算右侧操作数。</span><span class="sxs-lookup"><span data-stu-id="a9528-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="a9528-110">对于[整型](../builtin-types/integral-numeric-types.md)类型的操作数，`&`、`|` 和 `^` 运算符执行位逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="a9528-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="a9528-111">有关详细信息，请参阅[位运算符和移位运算符](bitwise-and-shift-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="a9528-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="a9528-112">逻辑非运算符 !</span><span class="sxs-lookup"><span data-stu-id="a9528-112">Logical negation operator !</span></span>

<span data-ttu-id="a9528-113">`!` 运算符计算操作数的逻辑非。</span><span class="sxs-lookup"><span data-stu-id="a9528-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="a9528-114">也就是说，如果操作数的计算结果为 `false`，它生成 `true`；如果操作数的计算结果为 `true`，它生成 `false`：</span><span class="sxs-lookup"><span data-stu-id="a9528-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="a9528-115">从 C# 8.0 起，一元后缀 `!` 运算符为 null 包容运算符。</span><span class="sxs-lookup"><span data-stu-id="a9528-115">Starting with C# 8.0, the unary postfix `!` operator is a null-forgiving operator.</span></span> <span data-ttu-id="a9528-116">在已启用的可为空的注释上下文中，可以使用它来声明可为空的引用类型的表达式 `x` 不为 null：`x!`。</span><span class="sxs-lookup"><span data-stu-id="a9528-116">In an enabled nullable annotation context, you use it to declare that expression `x` of a nullable reference type isn't null: `x!`.</span></span> <span data-ttu-id="a9528-117">有关详细信息，请参阅[可为空引用类型](../../nullable-references.md)。</span><span class="sxs-lookup"><span data-stu-id="a9528-117">For more information, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="a9528-118">逻辑 AND 运算符 &amp;</span><span class="sxs-lookup"><span data-stu-id="a9528-118">Logical AND operator &amp;</span></span>

<span data-ttu-id="a9528-119">`&` 运算符计算操作数的逻辑与。</span><span class="sxs-lookup"><span data-stu-id="a9528-119">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="a9528-120">如果 `x` 和 `y` 的计算结果都为 `true`，则 `x & y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a9528-120">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="a9528-121">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9528-121">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="a9528-122">即使左侧操作数计算结果为 `false`，`&` 运算符也会计算这两个操作数，而在这种情况下，无论右侧操作数的值为何，结果都肯定为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9528-122">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="a9528-123">在下面的示例中，`&` 运算符的右侧操作数是方法调用，无论左侧操作数的值如何，都会执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="a9528-123">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="a9528-124">[条件逻辑 AND 运算符](#conditional-logical-and-operator-) `&&` 也计算操作数的逻辑 AND，但如果左侧操作数的计算结果为 `false`，它就不会计算右侧操作数。</span><span class="sxs-lookup"><span data-stu-id="a9528-124">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="a9528-125">对于整型类型的操作数，`&` 运算符计算其操作数的[位逻辑 AND](bitwise-and-shift-operators.md#logical-and-operator-)。</span><span class="sxs-lookup"><span data-stu-id="a9528-125">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="a9528-126">一元 `&` 运算符是 [address-of 运算符](pointer-related-operators.md#address-of-operator-)。</span><span class="sxs-lookup"><span data-stu-id="a9528-126">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="a9528-127">逻辑异或运算符 ^</span><span class="sxs-lookup"><span data-stu-id="a9528-127">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="a9528-128">`^` 运算符计算操作数的逻辑异或（亦称为“逻辑 XOR”）。</span><span class="sxs-lookup"><span data-stu-id="a9528-128">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="a9528-129">如果 `x` 计算结果为 `true` 且 `y` 计算结果为 `false`，或者 `x` 计算结果为 `false` 且 `y` 计算结果为 `true`，那么 `x ^ y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a9528-129">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="a9528-130">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9528-130">Otherwise, the result is `false`.</span></span> <span data-ttu-id="a9528-131">也就是说，对于 `bool` 操作数，`^` 运算符的计算结果与[不等运算符](equality-operators.md#inequality-operator-) `!=` 相同。</span><span class="sxs-lookup"><span data-stu-id="a9528-131">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="a9528-132">对于整型类型的操作数，`^` 运算符计算其操作数的[位逻辑异或](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="a9528-132">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="a9528-133">逻辑或运算符 |</span><span class="sxs-lookup"><span data-stu-id="a9528-133">Logical OR operator |</span></span>

<span data-ttu-id="a9528-134">`|` 运算符计算操作数的逻辑或。</span><span class="sxs-lookup"><span data-stu-id="a9528-134">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="a9528-135">如果 `x` 或 `y` 的计算结果为 `true`，则 `x | y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a9528-135">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="a9528-136">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9528-136">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="a9528-137">即使左侧操作数计算结果为 `true`，`|` 运算符也会计算这两个操作数，而在这种情况下，无论右侧操作数的值为何，结果都肯定为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a9528-137">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="a9528-138">在下面的示例中，`|` 运算符的右侧操作数是方法调用，无论左侧操作数的值如何，都会执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="a9528-138">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="a9528-139">[条件逻辑 OR 运算符](#conditional-logical-or-operator-) `||` 也计算操作数的逻辑 OR，但如果左侧操作数的计算结果为 `true`，它就不会计算右侧操作数。</span><span class="sxs-lookup"><span data-stu-id="a9528-139">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="a9528-140">对于整型类型的操作数，`|` 运算符计算其操作数的[位逻辑 OR](bitwise-and-shift-operators.md#logical-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="a9528-140">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="a9528-141">条件逻辑 AND 运算符 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="a9528-141">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="a9528-142">条件逻辑与运算符 `&&`（亦称为“短路”逻辑与运算符）计算操作数的逻辑与。</span><span class="sxs-lookup"><span data-stu-id="a9528-142">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="a9528-143">如果 `x` 和 `y` 的计算结果都为 `true`，则 `x && y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a9528-143">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="a9528-144">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9528-144">Otherwise, the result is `false`.</span></span> <span data-ttu-id="a9528-145">如果 `x` 的计算结果为 `false`，则不计算 `y`。</span><span class="sxs-lookup"><span data-stu-id="a9528-145">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="a9528-146">在下面的示例中，`&&` 运算符的右侧操作数是方法调用，如果左侧操作数的计算结果为 `false`，就不执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="a9528-146">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="a9528-147">[逻辑与运算符](#logical-and-operator-) `&` 也计算操作数的逻辑与，但始终计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="a9528-147">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="a9528-148">条件逻辑或运算符 ||</span><span class="sxs-lookup"><span data-stu-id="a9528-148">Conditional logical OR operator ||</span></span>

<span data-ttu-id="a9528-149">条件逻辑或运算符 `||`（亦称为“短路”逻辑或运算符）计算操作数的逻辑或。</span><span class="sxs-lookup"><span data-stu-id="a9528-149">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="a9528-150">如果 `x` 或 `y` 的计算结果为 `true`，则 `x || y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a9528-150">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="a9528-151">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9528-151">Otherwise, the result is `false`.</span></span> <span data-ttu-id="a9528-152">如果 `x` 的计算结果为 `true`，则不计算 `y`。</span><span class="sxs-lookup"><span data-stu-id="a9528-152">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="a9528-153">在下面的示例中，`||` 运算符的右侧操作数是方法调用，如果左侧操作数的计算结果为 `true`，就不执行方法调用：</span><span class="sxs-lookup"><span data-stu-id="a9528-153">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="a9528-154">[逻辑或运算符](#logical-or-operator-) `|` 也计算操作数的逻辑或，但始终计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="a9528-154">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="a9528-155">可以为 null 的布尔逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="a9528-155">Nullable Boolean logical operators</span></span>

<span data-ttu-id="a9528-156">对于 `bool?` 操作数，`&` 和 `|` 运算符支持三值逻辑。</span><span class="sxs-lookup"><span data-stu-id="a9528-156">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="a9528-157">由下表定义这些运算符的语义：</span><span class="sxs-lookup"><span data-stu-id="a9528-157">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="a9528-158">x</span><span class="sxs-lookup"><span data-stu-id="a9528-158">x</span></span>|<span data-ttu-id="a9528-159">y</span><span class="sxs-lookup"><span data-stu-id="a9528-159">y</span></span>|<span data-ttu-id="a9528-160">x 和 y</span><span class="sxs-lookup"><span data-stu-id="a9528-160">x&y</span></span>|<span data-ttu-id="a9528-161">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="a9528-161">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="a9528-162">true</span><span class="sxs-lookup"><span data-stu-id="a9528-162">true</span></span>|<span data-ttu-id="a9528-163">true</span><span class="sxs-lookup"><span data-stu-id="a9528-163">true</span></span>|<span data-ttu-id="a9528-164">true</span><span class="sxs-lookup"><span data-stu-id="a9528-164">true</span></span>|<span data-ttu-id="a9528-165">true</span><span class="sxs-lookup"><span data-stu-id="a9528-165">true</span></span>|  
|<span data-ttu-id="a9528-166">true</span><span class="sxs-lookup"><span data-stu-id="a9528-166">true</span></span>|<span data-ttu-id="a9528-167">false</span><span class="sxs-lookup"><span data-stu-id="a9528-167">false</span></span>|<span data-ttu-id="a9528-168">false</span><span class="sxs-lookup"><span data-stu-id="a9528-168">false</span></span>|<span data-ttu-id="a9528-169">true</span><span class="sxs-lookup"><span data-stu-id="a9528-169">true</span></span>|  
|<span data-ttu-id="a9528-170">true</span><span class="sxs-lookup"><span data-stu-id="a9528-170">true</span></span>|<span data-ttu-id="a9528-171">null</span><span class="sxs-lookup"><span data-stu-id="a9528-171">null</span></span>|<span data-ttu-id="a9528-172">null</span><span class="sxs-lookup"><span data-stu-id="a9528-172">null</span></span>|<span data-ttu-id="a9528-173">true</span><span class="sxs-lookup"><span data-stu-id="a9528-173">true</span></span>|  
|<span data-ttu-id="a9528-174">false</span><span class="sxs-lookup"><span data-stu-id="a9528-174">false</span></span>|<span data-ttu-id="a9528-175">true</span><span class="sxs-lookup"><span data-stu-id="a9528-175">true</span></span>|<span data-ttu-id="a9528-176">false</span><span class="sxs-lookup"><span data-stu-id="a9528-176">false</span></span>|<span data-ttu-id="a9528-177">true</span><span class="sxs-lookup"><span data-stu-id="a9528-177">true</span></span>|  
|<span data-ttu-id="a9528-178">false</span><span class="sxs-lookup"><span data-stu-id="a9528-178">false</span></span>|<span data-ttu-id="a9528-179">false</span><span class="sxs-lookup"><span data-stu-id="a9528-179">false</span></span>|<span data-ttu-id="a9528-180">false</span><span class="sxs-lookup"><span data-stu-id="a9528-180">false</span></span>|<span data-ttu-id="a9528-181">false</span><span class="sxs-lookup"><span data-stu-id="a9528-181">false</span></span>|  
|<span data-ttu-id="a9528-182">false</span><span class="sxs-lookup"><span data-stu-id="a9528-182">false</span></span>|<span data-ttu-id="a9528-183">null</span><span class="sxs-lookup"><span data-stu-id="a9528-183">null</span></span>|<span data-ttu-id="a9528-184">false</span><span class="sxs-lookup"><span data-stu-id="a9528-184">false</span></span>|<span data-ttu-id="a9528-185">null</span><span class="sxs-lookup"><span data-stu-id="a9528-185">null</span></span>|  
|<span data-ttu-id="a9528-186">null</span><span class="sxs-lookup"><span data-stu-id="a9528-186">null</span></span>|<span data-ttu-id="a9528-187">true</span><span class="sxs-lookup"><span data-stu-id="a9528-187">true</span></span>|<span data-ttu-id="a9528-188">null</span><span class="sxs-lookup"><span data-stu-id="a9528-188">null</span></span>|<span data-ttu-id="a9528-189">true</span><span class="sxs-lookup"><span data-stu-id="a9528-189">true</span></span>|  
|<span data-ttu-id="a9528-190">null</span><span class="sxs-lookup"><span data-stu-id="a9528-190">null</span></span>|<span data-ttu-id="a9528-191">false</span><span class="sxs-lookup"><span data-stu-id="a9528-191">false</span></span>|<span data-ttu-id="a9528-192">false</span><span class="sxs-lookup"><span data-stu-id="a9528-192">false</span></span>|<span data-ttu-id="a9528-193">null</span><span class="sxs-lookup"><span data-stu-id="a9528-193">null</span></span>|  
|<span data-ttu-id="a9528-194">null</span><span class="sxs-lookup"><span data-stu-id="a9528-194">null</span></span>|<span data-ttu-id="a9528-195">null</span><span class="sxs-lookup"><span data-stu-id="a9528-195">null</span></span>|<span data-ttu-id="a9528-196">null</span><span class="sxs-lookup"><span data-stu-id="a9528-196">null</span></span>|<span data-ttu-id="a9528-197">null</span><span class="sxs-lookup"><span data-stu-id="a9528-197">null</span></span>|  

<span data-ttu-id="a9528-198">这些运算符的行为不同于值类型可以为 null 的典型运算符行为。</span><span class="sxs-lookup"><span data-stu-id="a9528-198">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="a9528-199">通常情况下，为值类型的操作数定义的运算符也能与值类型可以为 null 的相应操作数一起使用。</span><span class="sxs-lookup"><span data-stu-id="a9528-199">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="a9528-200">如果任何操作数是 `null`，此类运算符都会生成 `null`。</span><span class="sxs-lookup"><span data-stu-id="a9528-200">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="a9528-201">不过，即使操作数之一是 `null`，`&` 和 `|` 运算符也可以生成非 null。</span><span class="sxs-lookup"><span data-stu-id="a9528-201">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="a9528-202">若要详细了解值类型可为空的运算符行为，请参阅[使用可为空的值类型](../../programming-guide/nullable-types/using-nullable-types.md)一文的[运算符](../../programming-guide/nullable-types/using-nullable-types.md#operators)部分。</span><span class="sxs-lookup"><span data-stu-id="a9528-202">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable value types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="a9528-203">还可以将 `!` 和 `^` 运算符与 `bool?` 操作数结合使用，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="a9528-203">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="a9528-204">条件逻辑运算符 `&&` 和 `||` 不支持 `bool?` 操作数。</span><span class="sxs-lookup"><span data-stu-id="a9528-204">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="a9528-205">复合赋值</span><span class="sxs-lookup"><span data-stu-id="a9528-205">Compound assignment</span></span>

<span data-ttu-id="a9528-206">对于二元运算符 `op`，窗体的复合赋值表达式</span><span class="sxs-lookup"><span data-stu-id="a9528-206">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="a9528-207">等效于</span><span class="sxs-lookup"><span data-stu-id="a9528-207">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="a9528-208">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="a9528-208">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="a9528-209">`&`、`|` 和 `^` 运算符支持复合赋值，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="a9528-209">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="a9528-210">条件逻辑运算符 `&&` 和 `||` 不支持复合赋值。</span><span class="sxs-lookup"><span data-stu-id="a9528-210">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="a9528-211">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="a9528-211">Operator precedence</span></span>

<span data-ttu-id="a9528-212">以下列表按优先级从高到低的顺序对逻辑运算符进行排序：</span><span class="sxs-lookup"><span data-stu-id="a9528-212">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="a9528-213">逻辑非运算符 `!`</span><span class="sxs-lookup"><span data-stu-id="a9528-213">Logical negation operator `!`</span></span>
- <span data-ttu-id="a9528-214">逻辑与运算符 `&`</span><span class="sxs-lookup"><span data-stu-id="a9528-214">Logical AND operator `&`</span></span>
- <span data-ttu-id="a9528-215">逻辑异或运算符 `^`</span><span class="sxs-lookup"><span data-stu-id="a9528-215">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="a9528-216">逻辑或运算符 `|`</span><span class="sxs-lookup"><span data-stu-id="a9528-216">Logical OR operator `|`</span></span>
- <span data-ttu-id="a9528-217">条件逻辑与运算符 `&&`</span><span class="sxs-lookup"><span data-stu-id="a9528-217">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="a9528-218">条件逻辑或运算符 `||`</span><span class="sxs-lookup"><span data-stu-id="a9528-218">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="a9528-219">使用括号 `()` 可以更改运算符优先级决定的计算顺序：</span><span class="sxs-lookup"><span data-stu-id="a9528-219">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="a9528-220">要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="a9528-220">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a9528-221">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="a9528-221">Operator overloadability</span></span>

<span data-ttu-id="a9528-222">用户定义类型可以[重载](operator-overloading.md) `!`、`&`、`|` 和 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="a9528-222">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="a9528-223">重载二元运算符时，对应的复合赋值运算符也会隐式重载。</span><span class="sxs-lookup"><span data-stu-id="a9528-223">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="a9528-224">用户定义类型不能显式重载复合赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="a9528-224">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="a9528-225">用户定义类型无法重载条件逻辑运算符 `&&` 和 `||`。</span><span class="sxs-lookup"><span data-stu-id="a9528-225">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="a9528-226">不过，如果用户定义类型以某种方式重载 [true 和 false 运算符](true-false-operators.md)以及 `&` 或 `|` 运算符，可以对相应类型的操作数执行 `&&` 或 `||` 运算。</span><span class="sxs-lookup"><span data-stu-id="a9528-226">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="a9528-227">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="a9528-227">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a9528-228">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a9528-228">C# language specification</span></span>

<span data-ttu-id="a9528-229">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="a9528-229">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="a9528-230">逻辑非运算符</span><span class="sxs-lookup"><span data-stu-id="a9528-230">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="a9528-231">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="a9528-231">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="a9528-232">条件逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="a9528-232">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="a9528-233">复合赋值</span><span class="sxs-lookup"><span data-stu-id="a9528-233">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="a9528-234">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9528-234">See also</span></span>

- [<span data-ttu-id="a9528-235">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a9528-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a9528-236">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="a9528-236">C# operators</span></span>](index.md)
- [<span data-ttu-id="a9528-237">位运算符和移位运算符</span><span class="sxs-lookup"><span data-stu-id="a9528-237">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
