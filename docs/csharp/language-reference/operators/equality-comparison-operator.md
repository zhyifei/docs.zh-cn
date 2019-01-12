---
title: == 运算符 - C# 参考
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655954"
---
# <a name="-operator-c-reference"></a>== 运算符（C# 参考）

如果操作数相等，等于运算符 `==` 返回 `true`，否则返回 `false`。

## <a name="value-types-equality"></a>值类型的相等性

如果[内置值类型](../keywords/value-types-table.md)的值相等，则其操作数相等：

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> 对于关系运算符 `==`、`>`、`<`、`>=` 和 `<=`，如果任何操作数不是数字 (<xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType>)，操作数的结果为 `false`。 这意味着 `NaN` 值不大于、小于或等于任何其他 `double` （或 `float`）值。 有关更多信息和示例，请参阅 <xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType> 参考文章。

如果基本整数类型的相应值相等，则相同[枚举](../keywords/enum.md)类型的两个操作数相等。

默认情况下，没有为用户定义的[结构](../keywords/struct.md)类型定义 `==` 运算符。 用户定义的类型可以[重载](#operator-overloadability) `==` 运算符。

从 C# 7.3 开始，`==` 和 [`!=`](not-equal-operator.md) 运算符由 C# [元组](../../tuples.md)支持。 有关详细信息，请参阅 [C# 元组类型](../../tuples.md)一文的[相等性和元组](../../tuples.md#equality-and-tuples)部分。

## <a name="string-equality"></a>字符串相等性

如果两个字符串均为 `null` 或者两个字符串实例具有相等长度且在每个字符位置有相同字符，则这两个[字符串](../keywords/string.md)操作数相等：

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

这就是区分大小写的序号比较。 有关如何比较字符串的详细信息，请参阅[如何在 C# 中比较字符串](../../how-to/compare-strings.md)。

## <a name="reference-types-equality"></a>引用类型的相等性

当两个非 `string` 引用类型引用同一对象时，其操作数相等：

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

该示例表明，`==` 运算符由用户定义的引用类型支持。 但是，用户定义的引用类型可以重载 `==` 运算符。 如果引用类型重载 `==` 运算符，使用 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> 方法来检查该类型的两个引用是否引用同一对象。

## <a name="operator-overloadability"></a>运算符可重载性

用户定义的类型可以[重载](../keywords/operator.md) `==` 运算符。 如果类型重载等于运算符 `==`，它也必须重载[不等于运算符](not-equal-operator.md) `!=`。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- [相等性比较](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
