---
title: '!= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 939b5664dba4345e62a43fb2f8d4d5379659d6aa
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610172"
---
# <a name="-operator-c-reference"></a>!= 运算符（C# 参考）

如果操作数不相等，不等于运算符 `!=` 返回 `true`，否则返回 `false`。 对于[内置类型](../keywords/built-in-types-table.md)的操作数，表达式 `x != y` 生成与表达式 `!(x == y)` 相同的结果。 有关详细信息，请参阅 [== 运算符](equality-comparison-operator.md)一文。

下面的示例演示 `!=` 运算符的用法：

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a>运算符可重载性

用户定义的类型可以[重载](../keywords/operator.md) `!=` 运算符。 如果类型重载不等于运算符 `!=`，它也必须重载[等于运算符](equality-comparison-operator.md) `==`。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- [相等性比较](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
