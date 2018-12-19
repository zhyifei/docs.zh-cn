---
title: /= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286515"
---
# <a name="-operator-c-reference"></a>/= 运算符（C# 参考）

除法赋值运算符。

使用 `/=` 运算符的表达式，例如

```csharp
x /= y
```

等效于

```csharp
x = x / y
```

不同的是 `x` 只计算一次。

[除法运算符](division-operator.md) `/` 用它的第一个操作数除以第二个操作数。 它受所有数值类型支持。

下面的示例演示 `/=` 运算符的用法：

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a>运算符可重载性

如果用户定义类型[重载](../keywords/operator.md)[除法运算符](division-operator.md) `/`，除法赋值运算符 `/=` 会隐式重载。 用户定义类型不得显式重载除法赋值运算符。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
