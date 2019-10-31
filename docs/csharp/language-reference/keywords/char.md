---
title: char 关键字 - C# 参考
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771799"
---
# <a name="char-c-reference"></a>char（C# 参考）

`char` 类型关键字是 .NET <xref:System.Char?displayProperty=nameWithType> 结构类型的别名，它表示 Unicode UTF-16 字符：

|类型|范围|大小|.NET 类型|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 到 U+FFFF|16 位|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>文本

`char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。 也可以将整型字符代码强制转换为相应的 `char` 值。 在下面的示例中，使用相同的字符 `X` 对 `char` 数组的四个元素进行初始化：

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>转换

`char` 类型可隐式转换为以下[整型](../builtin-types/integral-numeric-types.md)类型：`ushort`、`int`、`uint`、`long` 和 `ulong`。 它也可以隐式转换为内置[浮点](../builtin-types/floating-point-numeric-types.md)数值类型：`float`、`double` 和 `decimal`。 它可以显式转换为 `sbyte`、`byte` 和 `short` 整型类型。

无法将其他类型隐式转换为 `char` 类型。 但是，任何[整型](../builtin-types/integral-numeric-types.md)或[浮点](../builtin-types/floating-point-numeric-types.md)数值类型都可显式转换为 `char`。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[整型类型](~/_csharplang/spec/types.md#integral-types)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 关键字](./index.md)
- [内置类型表](./built-in-types-table.md)
- [字符串](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
