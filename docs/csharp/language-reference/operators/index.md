---
title: C# 运算符 - C# 参考
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 0e49c28f05d52c704a46806559407381c7eb3530
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971253"
---
# <a name="c-operators-c-reference"></a>C# 运算符（C# 参考）

C# 提供了许多由内置类型支持的预定义运算符。 例如，[算术运算符](arithmetic-operators.md)使用内置数值类型的操作数执行算术运算，[布尔逻辑运算符](boolean-logical-operators.md)使用 [bool](../keywords/bool.md) 操作数执行逻辑运算。

用户定义类型可以重载某些运算符来定义该类型的操作数的相应行为。 有关详细信息，请参阅[运算符重载](operator-overloading.md)。

下表按最高优先级到最低优先级的顺序列出 C# 运算符。 每行中运算符的优先级相同。

| 运算符 | 类别或名称 |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-operator-)、[x?.y](member-access-operators.md#null-conditional-operators--and-)、[x?[y]](member-access-operators.md#null-conditional-operators--and-)、[f(x)](member-access-operators.md#invocation-operator-)、[a&#91;x&#93;](member-access-operators.md#indexer-operator-)、[x++](arithmetic-operators.md#increment-operator-)、[x--](arithmetic-operators.md#decrement-operator---)、[new](new-operator.md)、[typeof](type-testing-and-conversion-operators.md#typeof-operator)、[checked](../keywords/checked.md)、[unchecked](../keywords/unchecked.md)、[default](default.md)、[nameof](nameof.md)、[delegate](delegate-operator.md)、[sizeof](sizeof.md)、[stackalloc](stackalloc.md)、[->](pointer-related-operators.md#pointer-member-access-operator--) | 基本 |
| [+x](addition-operator.md)、[-x](subtraction-operator.md)、[\!x](boolean-logical-operators.md#logical-negation-operator-)、[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-)、[++x](arithmetic-operators.md#increment-operator-)、[--x](arithmetic-operators.md#decrement-operator---)、[(T)x](type-testing-and-conversion-operators.md#cast-operator-)、[await](../keywords/await.md)、[&x](pointer-related-operators.md#address-of-operator-)、[*x](pointer-related-operators.md#pointer-indirection-operator-)、[true 和 false](true-false-operators.md) | 一元 |
| [x * y](arithmetic-operators.md#multiplication-operator-)、[x / y](arithmetic-operators.md#division-operator-)、[x % y](arithmetic-operators.md#remainder-operator-) | 乘法|
| [x + y](arithmetic-operators.md#addition-operator-)、[x – y](arithmetic-operators.md#subtraction-operator--) | 加法 |
| [x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-)、[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | 移位 |
| [x \< y](comparison-operators.md#less-than-operator-)、[x > y](comparison-operators.md#greater-than-operator-)、[x \<= y](comparison-operators.md#less-than-or-equal-operator-)、[x >= y](comparison-operators.md#greater-than-or-equal-operator-)、[is](type-testing-and-conversion-operators.md#is-operator)、[as](type-testing-and-conversion-operators.md#as-operator) | 关系和类型测试 |
| [x == y](equality-operators.md#equality-operator-)、[x != y](equality-operators.md#inequality-operator-) | 相等 |
| `x & y` | [布尔逻辑 AND](boolean-logical-operators.md#logical-and-operator-) 或[按位逻辑 AND](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [布尔逻辑 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) 或[按位逻辑 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [布尔逻辑 OR](boolean-logical-operators.md#logical-or-operator-) 或[按位逻辑 OR](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | 条件“与” |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | 条件“或” |
| [x ?? y](null-coalescing-operator.md) | Null 合并运算符 |
| [t ? x : y](conditional-operator.md) | 条件运算符 |
| [x = y](assignment-operator.md)、[x += y](arithmetic-operators.md#compound-assignment)、[x -= y](arithmetic-operators.md#compound-assignment)、[x *= y](arithmetic-operators.md#compound-assignment)、[x /= y](arithmetic-operators.md#compound-assignment)、[x %= y](arithmetic-operators.md#compound-assignment)、[x &= y](boolean-logical-operators.md#compound-assignment)、[x &#124;= y](boolean-logical-operators.md#compound-assignment)、[x ^= y](boolean-logical-operators.md#compound-assignment)、[x <<= y](bitwise-and-shift-operators.md#compound-assignment)、[x >>= y](bitwise-and-shift-operators.md#compound-assignment)、[=>](lambda-operator.md) | 赋值和 lambda 声明 |

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [运算符](../../programming-guide/statements-expressions-operators/operators.md)
