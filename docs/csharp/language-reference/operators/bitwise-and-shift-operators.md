---
title: 位运算符和移位运算符 - C# 参考
description: 了解使用整数类型操作数执行位逻辑运算或移位运算的 C# 运算符。
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: 8068ec09f0c7d05d6d711e4e7a607b6183727b41
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424002"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="7b7b4-103">位运算符和移位运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7b7b4-103">Bitwise and shift operators (C# reference)</span></span>

<span data-ttu-id="7b7b4-104">以下运算符使用[整数类型](../builtin-types/integral-numeric-types.md)的操作数执行位运算或移位运算：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-104">The following operators perform bitwise or shift operations with operands of the [integral types](../builtin-types/integral-numeric-types.md):</span></span>

- <span data-ttu-id="7b7b4-105">一元 [`~`（按位求补）](#bitwise-complement-operator-)运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="7b7b4-106">二进制 [`<<`（向左移位）](#left-shift-operator-)和 [`>>`（向右移位）](#right-shift-operator-)移位运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="7b7b4-107">二进制 [`&`（逻辑 AND）](#logical-and-operator-)、[`|`（逻辑 OR）](#logical-or-operator-)和 [`^`（逻辑异或）](#logical-exclusive-or-operator-)运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="7b7b4-108">这些运算符是针对 `int`、`uint``long` 和 `ulong` 类型定义的。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="7b7b4-109">如果两个操作数都是其他整数类型（`sbyte`、`byte`、`short`、`ushort` 或 `char`），它们的值将转换为 `int` 类型，这也是一个运算的结果类型。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="7b7b4-110">如果操作数是不同的整数类型，它们的值将转换为最接近的包含整数类型。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="7b7b4-111">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[数值提升](~/_csharplang/spec/expressions.md#numeric-promotions)部分。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="7b7b4-112">`&`、`|` 和 `^` 运算符也是为 `bool` 类型的操作数定义的。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-112">The `&`, `|`, and `^` operators are also defined for the operands of the `bool` type.</span></span> <span data-ttu-id="7b7b4-113">有关详细信息，请参阅[布尔逻辑运算符](boolean-logical-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="7b7b4-114">位运算和移位运算永远不会导致溢出，并且不会在[已检查和未检查的](../keywords/checked-and-unchecked.md)上下文中产生相同的结果。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="7b7b4-115">按位求补运算符 ~</span><span class="sxs-lookup"><span data-stu-id="7b7b4-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="7b7b4-116">`~` 运算符通过反转每个位产生其操作数的按位求补：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="7b7b4-117">也可以使用 `~` 符号来声明终结器。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="7b7b4-118">有关详细信息，请参阅[终结器](../../programming-guide/classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="7b7b4-119">左移位运算符 \<\<</span><span class="sxs-lookup"><span data-stu-id="7b7b4-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="7b7b4-120">`<<` 运算符将其左侧操作数向左移动右侧操作数定义的位数。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-120">The `<<` operator shifts its left-hand operand left by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="7b7b4-121">左移运算会放弃超出结果类型范围的高阶位，并将低阶空位位置设置为零，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="7b7b4-122">由于移位运算符仅针对 `int`、`uint`、`long` 和 `ulong` 类型定义，因此运算的结果始终包含至少 32 位。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="7b7b4-123">如果左侧操作数是其他整数类型（`sbyte`、`byte`、`short`、`ushort` 或 `char`），则其值将转换为 `int` 类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-123">If the left-hand operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="7b7b4-124">有关 `<<` 运算符的右侧操作数如何定义移位计数的信息，请参阅[移位运算符的移位计数](#shift-count-of-the-shift-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-124">For information about how the right-hand operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="7b7b4-125">右移位运算符 >></span><span class="sxs-lookup"><span data-stu-id="7b7b4-125">Right-shift operator >></span></span>

<span data-ttu-id="7b7b4-126">`>>` 运算符将其左侧操作数向右移动右侧操作数定义的位数。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-126">The `>>` operator shifts its left-hand operand right by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="7b7b4-127">右移位运算会放弃低阶位，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="7b7b4-128">高顺序空位位置是根据左侧操作数类型设置的，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-128">The high-order empty bit positions are set based on the type of the left-hand operand as follows:</span></span>

- <span data-ttu-id="7b7b4-129">如果左侧操作数的类型是 [int](../builtin-types/integral-numeric-types.md) 或 [long](../builtin-types/integral-numeric-types.md)，右移运算符将执行算术  移位：左侧操作数的最高有效位（符号位）的值将传播到高顺序空位位置。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-129">If the left-hand operand is of type [int](../builtin-types/integral-numeric-types.md) or [long](../builtin-types/integral-numeric-types.md), the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the left-hand operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="7b7b4-130">也就是说，如果左侧操作数为非负，高顺序空位位置设置为零，如果为负，则将该位置设置为 1。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-130">That is, the high-order empty bit positions are set to zero if the left-hand operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="7b7b4-131">如果左侧操作数的类型是 [uint](../builtin-types/integral-numeric-types.md) 或 [ulong](../builtin-types/integral-numeric-types.md)，则右移运算符执行逻辑  移位：高顺序空位位置始终设置为零。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-131">If the left-hand operand is of type [uint](../builtin-types/integral-numeric-types.md) or [ulong](../builtin-types/integral-numeric-types.md), the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="7b7b4-132">有关 `>>` 运算符的右侧操作数如何定义移位计数的信息，请参阅[移位运算符的移位计数](#shift-count-of-the-shift-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-132">For information about how the right-hand operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="7b7b4-133">逻辑 AND 运算符 &amp;</span><span class="sxs-lookup"><span data-stu-id="7b7b4-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="7b7b4-134">`&` 运算符计算其操作数的位逻辑 AND：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="7b7b4-135">对于 `bool` 类型的操作数，`&` 运算符计算其操作数的[逻辑 AND](boolean-logical-operators.md#logical-and-operator-)。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-135">For the operands of the `bool` type, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="7b7b4-136">一元 `&` 运算符是 [address-of 运算符](pointer-related-operators.md#address-of-operator-)。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="7b7b4-137">逻辑异或运算符 ^</span><span class="sxs-lookup"><span data-stu-id="7b7b4-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="7b7b4-138">`^` 运算符计算其操作数的位逻辑异或，也称为位逻辑 XOR：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="7b7b4-139">对于 `bool` 类型的操作数，`^` 运算符计算其操作数的[逻辑异或](boolean-logical-operators.md#logical-exclusive-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-139">For the operands of the `bool` type, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="7b7b4-140">逻辑或运算符 |</span><span class="sxs-lookup"><span data-stu-id="7b7b4-140">Logical OR operator |</span></span>

<span data-ttu-id="7b7b4-141">`|` 运算符计算其操作数的位逻辑 OR：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="7b7b4-142">对于 `bool` 类型的操作数，`|` 运算符计算其操作数的[逻辑 OR](boolean-logical-operators.md#logical-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-142">For the operands of the `bool` type, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="7b7b4-143">复合赋值</span><span class="sxs-lookup"><span data-stu-id="7b7b4-143">Compound assignment</span></span>

<span data-ttu-id="7b7b4-144">对于二元运算符 `op`，窗体的复合赋值表达式</span><span class="sxs-lookup"><span data-stu-id="7b7b4-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="7b7b4-145">等效于</span><span class="sxs-lookup"><span data-stu-id="7b7b4-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="7b7b4-146">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="7b7b4-147">以下示例演示了使用位运算符和移位运算符的复合赋值的用法：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="7b7b4-148">由于[数值提升](~/_csharplang/spec/expressions.md#numeric-promotions)，`op`，运算的结果可能无法隐式转换为 `x` 的 `T` 类型。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="7b7b4-149">在这种情况下，如果 `op` 是预定义的运算符并且运算的结果可以显式转换为 `x` 的类型 `T`，则形式为 `x op= y` 的复合赋值表达式等效于 `x = (T)(x op y)`，但 `x` 仅计算一次。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="7b7b4-150">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="7b7b4-151">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="7b7b4-151">Operator precedence</span></span>

<span data-ttu-id="7b7b4-152">以下列表按位运算符和移位运算符从最高优先级到最低优先级排序：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="7b7b4-153">按位求补运算符 `~`</span><span class="sxs-lookup"><span data-stu-id="7b7b4-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="7b7b4-154">移位运算符 `<<` 和 `>>`</span><span class="sxs-lookup"><span data-stu-id="7b7b4-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="7b7b4-155">逻辑与运算符 `&`</span><span class="sxs-lookup"><span data-stu-id="7b7b4-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="7b7b4-156">逻辑异或运算符 `^`</span><span class="sxs-lookup"><span data-stu-id="7b7b4-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="7b7b4-157">逻辑或运算符 `|`</span><span class="sxs-lookup"><span data-stu-id="7b7b4-157">Logical OR operator `|`</span></span>

<span data-ttu-id="7b7b4-158">使用括号 `()` 可以更改运算符优先级决定的计算顺序：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="7b7b4-159">要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-159">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="7b7b4-160">移位运算符的移位计数</span><span class="sxs-lookup"><span data-stu-id="7b7b4-160">Shift count of the shift operators</span></span>

<span data-ttu-id="7b7b4-161">对于移位运算符 `<<` 和 `>>`，右侧操作数的类型必须为 [int](../builtin-types/integral-numeric-types.md) 或具有[预定义隐式数值转换](../keywords/implicit-numeric-conversions-table.md) 为 `int` 的类型。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-161">For the shift operators `<<` and `>>`, the type of the right-hand operand must be [int](../builtin-types/integral-numeric-types.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="7b7b4-162">对于 `x << count` 和 `x >> count` 表达式，实际移位计数取决于 `x` 的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="7b7b4-163">如果 `x` 的类型为 [int](../builtin-types/integral-numeric-types.md) 或 [unit](../builtin-types/integral-numeric-types.md)，则移位计数由右侧操作数的低阶五位定义  。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-163">If the type of `x` is [int](../builtin-types/integral-numeric-types.md) or [uint](../builtin-types/integral-numeric-types.md), the shift count is defined by the low-order *five* bits of the right-hand operand.</span></span> <span data-ttu-id="7b7b4-164">也就是说，移位计数通过 `count & 0x1F`（或 `count & 0b_1_1111`）计算得出。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="7b7b4-165">如果 `x` 的类型为 [long](../builtin-types/integral-numeric-types.md) 或 [unlong](../builtin-types/integral-numeric-types.md)，则移位计数由右侧操作数的低阶六位定义  。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-165">If the type of `x` is [long](../builtin-types/integral-numeric-types.md) or [ulong](../builtin-types/integral-numeric-types.md), the shift count is defined by the low-order *six* bits of the right-hand operand.</span></span> <span data-ttu-id="7b7b4-166">也就是说，移位计数通过 `count & 0x3F`（或 `count & 0b_11_1111`）计算得出。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="7b7b4-167">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a><span data-ttu-id="7b7b4-168">枚举逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-168">Enumeration logical operators</span></span>

<span data-ttu-id="7b7b4-169">还为所有[枚举](../keywords/enum.md)类型定义了 `~`、`&`、`|` 和 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-169">The `~`, `&`, `|`, and `^` operators are also defined for any [enumeration](../keywords/enum.md) type.</span></span> <span data-ttu-id="7b7b4-170">对于相同枚举类型的操作数，对底层整数类型的相应值执行逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-170">For the operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="7b7b4-171">例如，对于具有底层类型 `U` 的枚举类型 `T` 的任何 `x` 和 `y`，`x & y` 表达式生成与 `(T)((U)x & (U)y)` 表达式相同的结果。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-171">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="7b7b4-172">通常使用具有枚举类型的位逻辑运算符，该枚举类型使用 [Flags](xref:System.FlagsAttribute) 属性定义。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-172">You typically use bitwise logical operators with an enumeration type which is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="7b7b4-173">有关详细信息，请参阅[枚举类型](../../programming-guide/enumeration-types.md)一文的[作为位标记的枚举类型](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags)部分。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-173">For more information, see the [Enumeration types as bit flags](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../../programming-guide/enumeration-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="7b7b4-174">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="7b7b4-174">Operator overloadability</span></span>

<span data-ttu-id="7b7b4-175">用户定义的类型可以[重载](../keywords/operator.md) `~`、`<<`、`>>`、`&`、`|` 和 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-175">A user-defined type can [overload](../keywords/operator.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="7b7b4-176">重载二元运算符时，对应的复合赋值运算符也会隐式重载。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-176">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="7b7b4-177">用户定义类型不能显式重载复合赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-177">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="7b7b4-178">如果用户定义类型 `T` 重载 `<<` 或 `>>` 运算符，则左侧操作数的类型必须为 `T` 且右侧操作数的类型必须为 `int`。</span><span class="sxs-lookup"><span data-stu-id="7b7b4-178">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the left-hand operand must be `T` and the type of the right-hand operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7b7b4-179">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7b7b4-179">C# language specification</span></span>

<span data-ttu-id="7b7b4-180">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="7b7b4-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="7b7b4-181">按位求补运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-181">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="7b7b4-182">移位运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-182">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="7b7b4-183">逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-183">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="7b7b4-184">复合赋值</span><span class="sxs-lookup"><span data-stu-id="7b7b4-184">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="7b7b4-185">数值提升</span><span class="sxs-lookup"><span data-stu-id="7b7b4-185">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="7b7b4-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b7b4-186">See also</span></span>

- [<span data-ttu-id="7b7b4-187">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7b7b4-187">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7b7b4-188">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-188">C# operators</span></span>](index.md)
- [<span data-ttu-id="7b7b4-189">Boolean 逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="7b7b4-189">Boolean logical operators</span></span>](boolean-logical-operators.md)
