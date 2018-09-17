---
title: '% 运算符（C# 参考）'
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: 9cd2f7ad3856feb34667686979c942ecb21887c2
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45645913"
---
# <a name="-operator-c-reference"></a>% 运算符（C# 参考）

余数运算符 `%` 计算第一个操作数除以第二个操作数后的余数。 用户定义的类型可以[重载](../keywords/operator.md) `%` 运算符。 当 `%` 重载时，[余数赋值运算符](remainder-assignment-operator.md) `%=` 也会隐式重载。

所有数值类型都支持余数运算符。

## <a name="integer-remainder"></a>整数余数
  
对于整数操作数，`a % b` 的结果是由 `a - (a / b) * b` 生成的值。 非零余数的符号与第一个操作数的符号相同，如下例所示：

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a>浮点余数

对于[浮点](../keywords/float.md)和[双精度型](../keywords/double.md)操作数，有限的 `x` 和 `y` 的 `x % y` 的结果是值 `z`，使得

- 如果不是零，则 `z` 的符号与 `x` 的符号相同；
- `z` 的绝对值是 `|x| - n * |y|` 生成的值，其中 `n` 是小于或等于 `|x| / |y|` 的最大可能整数，`|x|` 和 `|y|` 分别是 `x` 和 `y` 的绝对值。

有关非限定操作数的 `%` 运算符行为的信息，请参阅 [C# 语言规范](/dotnet/csharp/language-reference/language-specification/index)的[余数运算符](/dotnet/csharp/language-reference/language-specification/expressions#remainder-operator)章节。

> [!NOTE]
> 计算余数的此方法类似于用于整数操作数的方法，但与 IEEE 754 不同。 如果需要符合 IEEE 754 的余数运算，使用 <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> 方法。

下面的示例演示 `float` 和 `double` 操作数的余数运算符的行为：

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

请注意与浮点类型相关联的舍入错误。

有关[十进制](../keywords/decimal.md)操作数，余数运算符 `%` 等效于 <xref:System.Decimal?displayProperty=nameWithType> 类型的[余数运算符](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>)。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
