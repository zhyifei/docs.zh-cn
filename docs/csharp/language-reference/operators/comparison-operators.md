---
title: 比较运算符 - C# 参考
description: 了解可用于检查数值顺序的 C# 比较运算符。
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 6d3751ff1ee2c6ee2f058eeda4ffd5db188a988e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633763"
---
# <a name="comparison-operators-c-reference"></a>比较运算符（C# 参考）

[`<`（小于）](#less-than-operator-)、[`>`（大于）](#greater-than-operator-)、[`<=`（小于或等于）](#less-than-or-equal-operator-)和 [`>=`（大于或等于）](#greater-than-or-equal-operator-)比较（也称为关系）运算符比较其操作数。 这些运算符支持所有[整型](../keywords/integral-types-table.md)和[浮动](../keywords/floating-point-types-table.md)数值类型。

> [!NOTE]
> 对于 `==`、`<`、`>`、`<=` 和 `>=` 运算符，如果所有操作数都不是数字（<xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType>），则运算结果为 `false`。 这意味着 `NaN` 值不大于、小于或等于任何其他 `double`（或 `float`）值，包括 `NaN`。 有关更多信息和示例，请参阅 <xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType> 参考文章。

枚举类型也支持比较运算符。 对于相同[枚举](../keywords/enum.md)类型的操作数，基础整数类型的相应值会进行比较。

[`==` 和 `!=` 运算符](equality-operators.md)检查其操作数是否相等。

## <a name="less-than-operator-"></a>小于运算符 \<

如果第一个操作数小于第二个操作数，`<` 运算符返回 `true`，否则返回 `false`：

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="greater-than-operator-"></a>大于运算符 >

如果第一个操作数大于第二个操作数，`>` 运算符返回 `true`，否则返回 `false`：

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>小于或等于运算符 \<=

如果第一个操作数小于或等于第二个操作数，`<=` 运算符返回 `true`，否则返回 `false`：

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>大于或等于运算符 >=

如果第一个操作数大于或等于第二个操作数，`>=` 运算符返回 `true`，否则返回 `false`：

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>运算符可重载性

用户定义类型可以[重载](../keywords/operator.md) `<`、`>`、`<=` 和 `>=` 运算符。

如果某类型重载 `<` 或 `>` 运算符之一，它必须同时重载 `<` 和 `>`。 如果某类型重载 `<=` 或 `>=` 运算符之一，它必须同时重载 `<=` 和 `>=`。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [相等运算符](equality-operators.md)
