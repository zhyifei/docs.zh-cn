---
title: '&amp;&amp; 运算符（C# 参考）'
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: d0e6d9a5aedc7dc87393e3dea070bf442b3268dc
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "43529230"
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp; 运算符（C# 参考）

条件逻辑 AND 运算符 `&&`（也称为“短路”逻辑 AND 运算符）计算其 [bool](../keywords/bool.md) 操作数的逻辑 AND。 如果 `x` 和 `y` 的计算结果都为 `true`，则 `x && y` 的结果为 `true`。 否则，结果为 `false`。 如果第一个操作数的计算结果为 `false`，则不会计算第二个操作数且运算结果为 `false`。 以下示例演示了该行为：

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

[逻辑 AND 运算符](and-operator.md) `&` 也会计算其 `bool` 操作数的逻辑 AND，但始终会计算两个操作数。

## <a name="operator-overloadability"></a>运算符可重载性

用户定义类型不能重载条件逻辑 AND 运算符。 但是，如果用户定义类型以某种方式重载了 [逻辑 AND](and-operator.md)、[true](../keywords/true-operator.md) 和 [false](../keywords/false-operator.md) 运算符，则可以对该类型的操作数进行 `&&` 运算。 有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[条件逻辑运算符](~/_csharplang/spec/expressions.md#conditional-logical-operators)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- [|| 运算符](conditional-or-operator.md)
- [\! 运算符](logical-negation-operator.md)
- [& 运算符](and-operator.md)
