---
title: 字符串
description: 了解F# "string" 类型如何将不可变文本表示为 Unicode 字符序列。
ms.date: 07/05/2019
ms.openlocfilehash: 284de939c90c4d9d4ea064fb4db1fb90a37038e2
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627102"
---
# <a name="strings"></a>字符串

> [!NOTE]
> 本文中的 API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

`string`类型将不可变文本表示为 Unicode 字符序列。 `string` 是 .NET Framework 中 `System.String` 的别名。

## <a name="remarks"></a>备注

字符串文本用引号 (") 字符分隔。 反斜杠字符 ( \\ ) 用于对某些特殊字符进行编码。 反斜杠和下一个字符共同称为*转义序列*。 下表显示了F#字符串文本中支持的转义序列。

|字符|转义序列|
|---------|---------------|
|警报|`\a`|
|Backspace|`\b`|
|换页|`\f`|
|换行符|`\n`|
|回车|`\r`|
|Tab|`\t`|
|垂直制表符|`\v`|
|反斜杠|`\\`|
|引号|`\"`|
|撇号|`\'`|
|Unicode 字符|`\DDD`(其中`D`指示十进制数字; 范围为 000-255; 例如, `\231` = "ç")|
|Unicode 字符|`\xHH`(其中`H`指示十六进制数字; 00-FF 的范围; 例如, `\xE7` = "ç")|
|Unicode 字符|`\uHHHH`(UTF-16)(其中`H`指示十六进制数字; 0000-FFFF 范围; 例如, `\u00E7` = "ç")|
|Unicode 字符|`\U00HHHHHH`(UTF-32)(其中`H`指示十六进制数字; 10FFFF 的范围; 例如, `\U0001F47D` = "👽")|

> [!IMPORTANT]
> `\DDD`转义序列是十进制符号, 而不是八进制表示法, 这与大多数其他语言类似。 因此, 数字`8`和`9`是有效的`\032` , 序列表示空格 (U + 0020), 而八进制表示法中的码位就是`\040`。

> [!NOTE]
> 约束为 0-255 (0xff) 的范围, `\DDD`并且`\x`转义序列实际上是[ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)字符集, 因为它与第一个 256 Unicode 码位匹配。

如果前面带有 @ 符号, 则文本为逐字字符串。 这意味着将忽略任何转义序列, 只不过两个引号字符被解释为一个引号字符。

此外, 字符串可以用三个引号括起来。 在这种情况下, 将忽略所有转义序列, 包括双引号字符。 若要指定包含嵌入的带引号的字符串的字符串, 可以使用逐字字符串或带三个引号的字符串。 如果使用逐字字符串, 则必须指定两个引号字符来指示单引号字符。 如果使用三个带引号的字符串, 则可以使用单引号字符, 而不会将它们分析为字符串的末尾。 当使用包含嵌入引号的 XML 或其他结构时, 此方法会很有用。

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

在代码中, 将接受带有分行符的字符串, 分行符将按原义解释为换行符, 除非反斜杠字符为换行符前的最后一个字符。 使用反斜杠字符时, 将忽略下一行的前导空格。 下面的代码将生成一个`str1`字符串, 该`"abc\ndef"`字符串具有值`str2`和具有值`"abcdef"`的字符串。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

您可以使用类似数组的语法来访问字符串中的单个字符, 如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

输出为 `b`。

或者, 您可以使用数组切片语法来提取子字符串, 如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

输出如下所示。

```
abc
def
```

可以按无符号字节的数组 (类型`byte[]`) 表示 ASCII 字符串。 将后缀`B`添加到字符串文字, 以指示它是 ASCII 字符串。 与 byte 数组一起使用的 ASCII 字符串文本除了 Unicode 转义序列外, 与 Unicode 字符串支持相同的转义序列。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>字符串运算符

可以通过两种方式连接字符串: 通过使用`+`运算符或`^`使用运算符。 `+`运算符保持与 .NET Framework 字符串处理功能的兼容性。

下面的示例演示字符串串联。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>String 类

因为中F#的字符串类型实际上是 .NET Framework `System.String` `System.String`类型, 所以所有成员都可用。 这包括`+`用于连接字符串`Length` 、属性和`Chars`属性的运算符, 该运算符将字符串作为 Unicode 字符数组返回。 有关字符串的详细信息, 请`System.String`参阅。

通过使用`Chars`的`System.String`属性, 可以通过指定索引来访问字符串中的各个字符, 如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>字符串模块

命名`FSharp.Core`空间中的`String`模块包含了用于字符串处理的其他功能。 有关详细信息, 请参阅[Core 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
