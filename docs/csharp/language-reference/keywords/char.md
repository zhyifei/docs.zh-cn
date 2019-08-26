---
title: char 关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 754c04bfc3b4090906420d55d55e51606b72f187
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605949"
---
# <a name="char-c-reference"></a>char（C# 参考）

`char` 关键字用于声明 <xref:System.Char?displayProperty=nameWithType> 结构的实例，.NET Framework 使用该结构来表示 Unicode 字符。 `Char` 对象的值为 16 位的数字（序号）值。

 Unicode 字符用于表示世界各地大多数的书面语言。

|类型|范围|大小|.NET 类型|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 到 U+FFFF|Unicode 16 位字符|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>文本

`char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。 还可转换整型字符代码。 在下面的示例中，使用相同的字符 `X` 对四个 `char` 变量进行初始化：

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>转换

`char` 可隐式转换为 [ushort](../builtin-types/integral-numeric-types.md)、[int](../builtin-types/integral-numeric-types.md)、[uint](../builtin-types/integral-numeric-types.md)、[double](../builtin-types/floating-point-numeric-types.md) 或 [decimal](../builtin-types/floating-point-numeric-types.md)。 但是无法将其他类型隐式转换为 `char` 类型。

<xref:System.Char?displayProperty=nameWithType> 类型提供多种适用于 `char` 值的静态方法。

## <a name="c-language-specification"></a>C# 语言规范  

有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[整型类型](~/_csharplang/spec/types.md#integral-types)。 该语言规范是 C# 语法和用法的权威资料。

## <a name="see-also"></a>请参阅

- <xref:System.Char>
- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](./index.md)
- [整型类型](../builtin-types/integral-numeric-types.md)
- [内置类型表](./built-in-types-table.md)
- [隐式数值转换表](./implicit-numeric-conversions-table.md)
- [显式数值转换表](./explicit-numeric-conversions-table.md)
- [可以为 null 的类型](../../programming-guide/nullable-types/index.md)
- [字符串](../../programming-guide/strings/index.md)
