---
title: "字符串 (F#)"
description: "了解如何 F # 'string' 类型表示不可变的文本为 Unicode 字符序列。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: df7624e5-ca6c-4e77-9e2b-87ca7e5e6f52
ms.openlocfilehash: 96a398ebcd53681481b10d1a2bee5f1e5442a5cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="strings"></a>字符串

> [!NOTE]
本文中的 API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

`string`类型不可变的文本表示为 Unicode 字符序列。 `string` 是 .NET Framework 中 `System.String` 的别名。

## <a name="remarks"></a>备注
由引号 （"） 字符分隔字符串。 反斜杠字符 (\)使用某些特殊字符进行编码。 反斜杠和组合在一起的下一个字符被称为*转义序列*。 转义序列在 F # 字符串文本显示在下表中受支持。

|字符|转义序列|
|---------|---------------|
|Backspace|\b|
|换行符|\n|
|回车|\r|
|Tab|\t|
|反斜杠|\\|
|引号|\"|
|单引号|\'|
|Unicode 字符|\u*XXXX*或 \U*XXXXXXXX* (其中*X*指示一个十六进制数字)|

如果以 @ 符号，则该文本是原义字符串。 这意味着，任何转义序列将被忽略，只不过两个引号字符解释为一个引号字符。

此外，可能由三个引号括字符串。 在这种情况下，将忽略所有转义序列，包括双引号字符。 若要指定包含嵌入的带引号的字符串的字符串，你可以使用原义字符串或三引号的字符串。 如果你使用原义字符串，则必须指定两个引号字符来表示单引号字符。 如果使用三引号字符串，你可以使用单引号字符，如果没有它们解析为字符串的末尾。 当您使用 XML 或包含嵌入的引号其他结构时，此技术很有用。

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

在代码中，接受字符串的分行符和换行符处换行是按原义解释为换行符，除非反斜杠字符是换行之前的最后一个字符。 使用反斜杠字符时，将忽略在下一行的前导空格。 下面的代码产生的字符串`str1`值`"abc\n     def"`和字符串`str2`值`"abcdef"`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

你可以通过类似数组的语法，如下所示访问字符串中的单个字符。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

输出为 `b`。

或者，可以使用数组的切片语法，通过提取子字符串，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

输出如下所示。

```
abc
def
```

您可以通过无符号字节，类型的数组表示 ASCII 字符串`byte[]`。 添加后缀`B`到字符串文本以指示它是 ASCII 字符串。 使用的字节数组的 ASCII 字符串文字支持为 Unicode 字符串，除 Unicode 转义序列相同的转义序列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a>字符串运算符
有两种方法将字符串串联： 通过使用`+`运算符或通过使用`^`运算符。 `+`运算符维护与.NET Framework 字符串处理功能的兼容性。

下面的示例阐释了字符串串联。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a>字符串类
因为在 F # 中的字符串类型是一个.NET 框架，实际`System.String`键入所有`System.String`成员均可。 这包括`+`运算符，用于将字符串串联`Length`属性，与`Chars`属性，作为 Unicode 字符数组中返回的字符串。 有关字符串的详细信息，请参阅`System.String`。

通过使用`Chars`属性`System.String`，你可以通过指定索引，如下面的代码中所示访问字符串中的每个字符。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a>字符串模块
用于字符串处理的其他功能包含在`String`中的模块`FSharp.Core`命名空间。 有关详细信息，请参阅[Core.String 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)。

## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)
