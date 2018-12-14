---
title: ++ 运算符（C# 参考）
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: b29f4f1ab00c0f8026f118cb72b090e3b728bfc5
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2018
ms.locfileid: "48030458"
---
# <a name="-operator-c-reference"></a>++ 运算符（C# 参考）

一元增量运算符 `++` 按 1 递增其操作数。 它以两种形式进行支持：后缀增量运算符`x++` 和前缀增量运算符 `++x`。

## <a name="postfix-increment-operator"></a>后缀递增运算符

`x++` 的结果是此操作前的 `x` 的值，如以下示例所示：

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a>前缀增量运算符

`++x` 的结果是此操作后的 `x` 的值，如以下示例所示：

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a>备注

增量运算符是为所有[整型类型](../keywords/integral-types-table.md)（包括[字符](../keywords/char.md)型）、[浮点型](../keywords/floating-point-types-table.md)和任何[枚举](../keywords/enum.md)类型预定义的。

增量运算符的操作数必须是变量、[属性](../../programming-guide/classes-and-structs/properties.md)访问或[索引器](../../../csharp/programming-guide/indexers/index.md)访问。

## <a name="operator-overloadability"></a>运算符可重载性

用户定义的类型可以[重载](../keywords/operator.md) `++` 运算符。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[后缀增量和减量运算符](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)和[前缀增量和减量运算符](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
- [-- 运算符](decrement-operator.md)
- [如何：递增和递减指针](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
