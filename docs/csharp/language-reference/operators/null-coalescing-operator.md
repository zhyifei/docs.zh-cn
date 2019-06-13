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
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816006"
---
# <a name="-operator-c-reference"></a>?? 运算符（C# 参考）

Null 合并运算符`??`返回其左操作数的值，如果不是`null`; 否则为它右操作数的计算结果并返回其结果。 `??`运算符不会评估其右操作数，如果左操作数的计算结果为非 null。

Null 合并运算符是右结合运算符，即在窗体的表达式

```csharp
a ?? b ?? c
```

计算结果为

```csharp
a ?? (b ?? c)
```

`??`运算符可用于以下方案：

- 在表达式中使用[null 条件运算符？。 和？]](member-access-operators.md#null-conditional-operators--and-)，可以使用 null 合并运算符以提供用于计算表达式与 null 条件操作的结果是替代表达式`null`:

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- 当您处理[可以为 null 的值类型](../../programming-guide/nullable-types/index.md)，需要提供基础值类型的值，请使用 null 合并运算符来指定要为 null 的类型值时提供的值`null`:

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  使用<xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>方法如果值为 null 的类型值时要使用`null`应基础值类型的默认值。

- 从C#7.0 中，可以使用[`throw`表达式](../keywords/throw.md#the-throw-expression)为要使参数检查代码更加简洁的 null 合并运算符的右侧操作数：

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  前面的示例还演示如何使用[expression-bodied 成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)定义属性。

## <a name="operator-overloadability"></a>运算符可重载性

Null 合并运算符无法进行重载。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅[null 合并运算符](~/_csharplang/spec/expressions.md#the-null-coalescing-operator)一部分[C#语言规范](~/_csharplang/spec/introduction.md)。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- [?. 和 ?[] 运算符](member-access-operators.md#null-conditional-operators--and-)
- [?: 运算符](conditional-operator.md)
