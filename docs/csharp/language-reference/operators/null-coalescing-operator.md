---
title: ?? 运算符 - C# 参考
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: a19b5558da36ffb11dabd1b9bec419a3623a0f17
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67024992"
---
# <a name="-operator-c-reference"></a>?? 运算符（C# 参考）

如果左操作数的值不为 `null`，则 null 合并运算符 `??` 返回该值；否则，它会计算右操作数并返回其结果。 如果左操作数的计算结果为非 null，则 `??` 运算符不会计算其右操作数。

null 合并运算符为右联运算符，即形式如下的表达式

```csharp
a ?? b ?? c
```

计算结果为

```csharp
a ?? (b ?? c)
```

`??` 运算符在以下应用场景中很有用：

- 在包含 [null 条件运算符 ?. 和 ?[]](member-access-operators.md#null-conditional-operators--and-) 的表达式中，当包含 null 条件运算的表达式的结果为 `null` 时，可以使用 null 合并运算符来提供替代表达式用于计算：

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- 当使用[可以为 null 的值类型](../../programming-guide/nullable-types/index.md)并且需要提供基础值类型的值时，可以使用 null 合并运算符指定当可以为 null 的类型的值为 `null` 时要提供的值：

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  如果可以为 null 的类型的值为 `null` 时要使用的值应为基础值类型的默认值，请使用 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 方法。

- 从 C# 7.0 开始，可以使用 [`throw` 表达式](../keywords/throw.md#the-throw-expression)作为 null 合并运算符的右操作数，以使参数检查代码更简洁：

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  前面的示例还演示了如何使用 [expression-bodied 成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)来定义属性。

## <a name="operator-overloadability"></a>运算符可重载性

不能重载 null 合并运算符。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的 [null 合并运算符](~/_csharplang/spec/expressions.md#the-null-coalescing-operator)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [?. 和 ?[] 运算符](member-access-operators.md#null-conditional-operators--and-)
- [?: 运算符](conditional-operator.md)
