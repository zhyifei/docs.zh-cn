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
ms.openlocfilehash: bf42a53a89676f457d3d2df8d193a83299c3e4cc
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758370"
---
# <a name="bitwise-and-shift-operators-c-reference"></a>位运算符和移位运算符（C# 参考）

以下运算符使用[整数类型](../keywords/integral-types-table.md)的操作数执行位运算或移位运算：

- 一元 [`~`（按位求补）](#bitwise-complement-operator-)运算符
- 二进制 [`<<`（向左移位）](#left-shift-operator-)和 [`>>`（向右移位）](#right-shift-operator-)移位运算符
- 二进制 [`&`（逻辑 AND）](#logical-and-operator-)、[`|`（逻辑 OR）](#logical-or-operator-)和 [`^`（逻辑异或）](#logical-exclusive-or-operator-)运算符

这些运算符是针对 `int`、`uint``long` 和 `ulong` 类型定义的。 如果两个操作数都是其他整数类型（`sbyte`、`byte`、`short`、`ushort` 或 `char`），它们的值将转换为 `int` 类型，这也是一个运算的结果类型。 如果操作数是不同的整数类型，它们的值将转换为最接近的包含整数类型。 有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[数值提升](~/_csharplang/spec/expressions.md#numeric-promotions)部分。

`&`、`|` 和 `^` 运算符也是为 `bool` 类型的操作数定义的。 有关详细信息，请参阅[布尔逻辑运算符](boolean-logical-operators.md)。

位运算和移位运算永远不会导致溢出，并且不会在[已检查和未检查的](../keywords/checked-and-unchecked.md)上下文中产生相同的结果。

## <a name="bitwise-complement-operator-"></a>按位求补运算符 ~

`~` 运算符通过反转每个位产生其操作数的按位求补：

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

也可以使用 `~` 符号来声明终结器。 有关详细信息，请参阅[终结器](../../programming-guide/classes-and-structs/destructors.md)。

## <a name="left-shift-operator-"></a>左移位运算符 \<\<

`<<` 运算符将其第一个操作数向左移动第二个操作数定义的位数。

左移运算会放弃超出结果类型范围的高阶位，并将低阶空位位置设置为零，如以下示例所示：

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

由于移位运算符仅针对 `int`、`uint`、`long` 和 `ulong` 类型定义，因此运算的结果始终包含至少 32 位。 如果第一个操作数是其他整数类型（`sbyte`、`byte`、`short`、`ushort` 或 `char`），则其值将转换为 `int` 类型，如以下示例所示：

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

有关 `<<` 运算符的第二个操作数如何定义移位计数的信息，请参阅[移位运算符的移位计数](#shift-count-of-the-shift-operators)部分。

## <a name="right-shift-operator-"></a>右移位运算符 >>

`>>` 运算符将其第一个操作数向右移动第二个操作数定义的位数。

右移位运算会放弃低阶位，如以下示例所示：

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

高顺序空位位置是根据第一个操作数类型设置的，如下所示：

- 如果第一个操作数的类型是 [int](../keywords/int.md) 或 [long](../keywords/long.md)，右移运算符将执行算术  移位：第一个操作数的最高有效位（符号位）的值将传播到高顺序空位位置。 也就是说，如果第一个操作数为非负，高顺序空位位置设置为零，如果为负，则将该位置设置为 1。

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- 如果第一个操作数的类型是 [uint](../keywords/uint.md) 或 [ulong](../keywords/ulong.md)，则右移运算符执行逻辑  移位：高顺序空位位置始终设置为零。

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

有关 `>>` 运算符的第二个操作数如何定义移位计数的信息，请参阅[移位运算符的移位计数](#shift-count-of-the-shift-operators)部分。

## <a name="logical-and-operator-amp"></a>逻辑与运算符 &amp;

`&` 运算符计算其操作数的位逻辑 AND：

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

对于 `bool` 类型的操作数，`&` 运算符计算其操作数的[逻辑 AND](boolean-logical-operators.md#logical-and-operator-)。 一元 `&` 运算符是 [address-of 运算符](pointer-related-operators.md#address-of-operator-)。

## <a name="logical-exclusive-or-operator-"></a>逻辑异或运算符 ^

`^` 运算符计算其操作数的位逻辑异或，也称为位逻辑 XOR：

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

对于 `bool` 类型的操作数，`^` 运算符计算其操作数的[逻辑异或](boolean-logical-operators.md#logical-exclusive-or-operator-)。

## <a name="logical-or-operator-"></a>逻辑或运算符 |

`|` 运算符计算其操作数的位逻辑 OR：

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

对于 `bool` 类型的操作数，`|` 运算符计算其操作数的[逻辑 OR](boolean-logical-operators.md#logical-or-operator-)。

## <a name="compound-assignment"></a>复合赋值

对于二元运算符 `op`，窗体的复合赋值表达式

```csharp
x op= y
```

等效于

```csharp
x = x op y
```

不同的是 `x` 只计算一次。

以下示例演示了使用位运算符和移位运算符的复合赋值的用法：

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

由于[数值提升](~/_csharplang/spec/expressions.md#numeric-promotions)，`op`，运算的结果可能无法隐式转换为 `x` 的 `T` 类型。 在这种情况下，如果 `op` 是预定义的运算符并且运算的结果可以显式转换为 `x` 的类型 `T`，则形式为 `x op= y` 的复合赋值表达式等效于 `x = (T)(x op y)`，但 `x` 仅计算一次。 以下示例演示了该行为：

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a>运算符优先级

以下列表按位运算符和移位运算符从最高优先级到最低优先级排序：

- 按位求补运算符 `~`
- 移位运算符 `<<` 和 `>>`
- 逻辑与运算符 `&`
- 逻辑异或运算符 `^`
- 逻辑或运算符 `|`

使用括号 `()` 可以更改运算符优先级决定的计算顺序：

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](index.md)。

## <a name="shift-count-of-the-shift-operators"></a>移位运算符的移位计数

对于移位运算符 `<<` 和 `>>`，第二个操作数的类型必须为 [int](../keywords/int.md) 或具有[预定义隐式数值转换](../keywords/implicit-numeric-conversions-table.md) 为 `int` 的类型。

对于 `x << count` 和 `x >> count` 表达式，实际移位计数取决于 `x` 的类型，如下所示：

- 如果 `x` 的类型为 [int](../keywords/int.md) 或 [unit](../keywords/uint.md)，则移位计数由第二个操作数的低阶五位定义  。 也就是说，移位计数通过 `count & 0x1F`（或 `count & 0b_1_1111`）计算得出。

- 如果 `x` 的类型为 [long](../keywords/long.md) 或 [unlong](../keywords/ulong.md)，则移位计数由第二个操作数的低阶六位定义  。 也就是说，移位计数通过 `count & 0x3F`（或 `count & 0b_11_1111`）计算得出。

以下示例演示了该行为：

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a>枚举逻辑运算符

还为所有[枚举](../keywords/enum.md)类型定义了 `~`、`&`、`|` 和 `^` 运算符。 对于相同枚举类型的操作数，对底层整数类型的相应值执行逻辑运算。 例如，对于具有底层类型 `U` 的枚举类型 `T` 的任何 `x` 和 `y`，`x & y` 表达式生成与 `(T)((U)x & (U)y)` 表达式相同的结果。

通常使用具有枚举类型的位逻辑运算符，该枚举类型使用 [Flags](xref:System.FlagsAttribute) 属性定义。 有关详细信息，请参阅[枚举类型](../../programming-guide/enumeration-types.md)一文的[作为位标记的枚举类型](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags)部分。

## <a name="operator-overloadability"></a>运算符可重载性

用户定义的类型可以[重载](../keywords/operator.md) `~`、`<<`、`>>`、`&`、`|` 和 `^` 运算符。 重载二元运算符时，对应的复合赋值运算符也会隐式重载。 用户定义类型不能显式重载复合赋值运算符。

如果用户定义类型 `T` 重载 `<<` 或 `>>` 运算符，则第一个操作数的类型必须为 `T` 且第二个操作数的类型必须为 `int`。

## <a name="c-language-specification"></a>C# 语言规范

有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：

- [按位求补运算符](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [移位运算符](~/_csharplang/spec/expressions.md#shift-operators)
- [逻辑运算符](~/_csharplang/spec/expressions.md#logical-operators)
- [复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)
- [数值提升](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- [Boolean 逻辑运算符](boolean-logical-operators.md)
