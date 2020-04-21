---
title: 字符串
description: 了解 F# "字符串"类型如何表示不可变文本作为 Unicode 字符序列。
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739569"
---
# <a name="strings"></a>字符串

> [!NOTE]
> 本文中的 API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

该`string`类型表示不可变文本为 Unicode 字符序列。 `string` 是 .NET Framework 中 `System.String` 的别名。

## <a name="remarks"></a>备注

字符串文本由引号 （"） 字符分隔。 反斜杠字符\\（ ） 用于编码某些特殊字符。 反斜杠和下一个字符一起被称为*转义序列*。 F# 字符串文本中支持的转义序列显示在下表中。

|字符|转义序列|
|---------|---------------|
|警报|`\a`|
|退格键|`\b`|
|换页符|`\f`|
|换行符|`\n`|
|回车符|`\r`|
|选项卡|`\t`|
|垂直制表符|`\v`|
|反斜杠|`\\`|
|引号|`\"`|
|撇号|`\'`|
|Unicode 字符|`\DDD`（其中`D`表示小数数字;范围为 000 - 255;`\231`例如，= "*"）|
|Unicode 字符|`\xHH`（其中`H`指示十六进制数字;范围为 00 - FF;例如，= `\xE7` "*"）|
|Unicode 字符|`\uHHHH`（UTF-16）（其中`H`表示十六进制数字;范围为 0000 - FFFF; 例如，= `\u00E7` "*"）|
|Unicode 字符|`\U00HHHHHH`（UTF-32）（其中`H`表示十六进制数字;范围为 000000 - 10FFFF; 例如，= `\U0001F47D` """）👽|

> [!IMPORTANT]
> `\DDD`转义序列是十进制表示法，不像大多数其他语言那样的八进制表示法。 因此，数字`8`和`9`有效，并且序列`\032`表示空格 （U+0020），而八进制表示法中的同一代码点将是`\040`。

> [!NOTE]
> 被限制到 0 - 255 （0xFF） `\DDD` `\x`的范围， 和转义序列实际上是[ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)字符集， 因为它匹配前 256 个 Unicode 点。

## <a name="verbatim-strings"></a>逐字字符串

如果前面有 + 符号，则文本是逐字字符串。 这意味着忽略任何转义序列，只不过两个引号字符被解释为一个引号字符。

## <a name="triple-quoted-strings"></a>三重报价字符串

此外，字符串可以用三重引号括起来。 在这种情况下，将忽略所有转义序列，包括双引号字符。 要指定包含嵌入引用字符串的字符串，可以使用逐字字符串或三重引号字符串。 如果使用逐字字符串，则必须指定两个引号字符以指示单个引号字符。 如果使用三重引号字符串，则可以使用单个引号字符，而无需将它们解析为字符串的末尾。 当您使用 XML 或其他包含嵌入引号的结构时，此方法非常有用。

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

在代码中，接受具有换行符的字符串，并且换行符从字面上解释为换行符，除非反斜杠字符是换行符之前的最后一个字符。 使用反斜杠字符时，将忽略下一行的前导空格。 `str1`以下代码生成具有值`"abc\ndef"`的字符串和具有 值`str2``"abcdef"`的字符串。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>字符串索引和切片

可以使用类似于数组的语法访问字符串中的单个字符，如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

输出为 `b`。

或者，您可以使用数组切片语法提取子字符串，如以下代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

输出如下所示。

```console
abc
def
```

您可以按未签名字节的数组表示 ASCII 字符串，类型`byte[]`为 。 将后缀`B`添加到字符串文本，以指示它是 ASCII 字符串。 与字节数组一起使用的 ASCII 字符串文本支持与 Unicode 字符串相同的转义序列，Unicode 转义序列除外。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>字符串运算符

该`+`运算符可用于串联字符串，保持与 .NET 框架字符串处理功能的兼容性。 下面的示例演示了字符串串联。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>字符串类

由于 F# 中的字符串类型实际上是 .NET`System.String`框架类型，`System.String`因此所有成员都可用。 这包括`+`运算符，该运算符用于串联字符串、`Length`属性和`Chars`属性，后者将字符串作为 Unicode 字符的数组返回。 有关字符串的详细信息，请参阅`System.String`。

通过使用 属性`Chars``System.String`，可以通过指定索引来访问字符串中的单个字符，如下代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>字符串模块

`FSharp.Core`命名空间中的`String`模块中包括字符串处理的其他功能。 有关详细信息，请参阅[Core.String 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)。

## <a name="see-also"></a>另请参阅

- [F# 语言参考](index.md)
