---
title: 文本 (F#)
description: '了解有关在 F # 编程语言的文本类型。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 961d6a10122c5d5c691d394efa8d2b7b31a80453
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="literals"></a>文本

> [!NOTE]
这篇文章中的 API 引用链接将转到 MSDN （对于暂时）。

本主题提供演示如何在 F # 中指定文本的类型的表。

## <a name="literal-types"></a>文本类型
下表显示 F # 中的文本的类型。 表示以十六进制表示的数字的字符不区分大小写;标识类型的字符是区分大小写。

|类型|描述|后缀或前缀|示例|
|----|-----------|----------------|--------|
|sbyte|8 位有符号整数|y|`86y`<br /><br />`0b00000101y`|
|byte|无符号的 8 位自然数|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|16 位有符号整数|秒|`86s`|
|uint16|无符号的 16 位自然数|us|`86us`|
|int<br /><br />int32|32 位有符号整数|l 或无|`86`<br /><br />`86l`|
|uint<br /><br />uint32|无符号的 32 位自然数字|u 或 u l|`86u`<br /><br />`86ul`|
|unativeint|本机指针作为无符号的自然数字|取消|`0x00002D3Fun`|
|int64|64 位有符号整数|L|`86L`|
|uint64|无符号的 64 位自然数|UL|`86UL`|
|单个，float32|32 位浮点数字|F 或 f|`4.14F` 或 `4.14f`|
|||lf|`0x00000000lf`|
|float;双精度|64 位浮点数|无|`4.14` 或 `2.3E+32` 或 `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|不受限制为 64 位表示形式的整数|I|`9999999999999999999999999999I`|
|decimal|小数表示为固定的点或有理数|M 或 m|`0.7833M` 或 `0.7833m`|
|Char|Unicode 字符|无|`'a'`|
|String|Unicode 字符串|无|`"text\n"`<br /><br />或<br /><br />`@"c:\filename"`<br /><br />或<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />或<br /><br />`"string1" + "string2"`<br /><br />另请参阅[字符串](Strings.md)。|
|byte|ASCII 字符|B|`'a'B`|
|byte[]|ASCII 字符串|B|`"text"B`|
|字符串或字节]|逐字字符串|@ 前缀|`@"\\server\share"` (Unicode)<br /><br />`@"\\server\share"B` (ASCII)|

## <a name="remarks"></a>备注
Unicode 字符串可以包含你可以通过使用指定的显式编码`\u`跟一个 16 位十六进制代码或可以通过使用指定的 utf-32 编码`\U`跟 32 位十六进制表示的代码的 Unicode代理项对。

截至 F # 3.1 中，你可以使用`+`登录，以合并字符串文本。 你还可以使用的按位或 (`|||`) 运算符来组合枚举标志。 例如，下面的代码是在 F # 3.1 中合法的：

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

不允许其他按位运算符的使用。


## <a name="named-literals"></a>命名的文本
都应是常量的值可标记为[文本](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性。 此属性的效果的导致要编译为常量的值。

在匹配表达式的模式中，小写字符开头的标识符始终被视为变量绑定，而不是原义字符，因此你通常应使用首字母大写时定义的文本。

## <a name="integers-in-other-bases"></a>在其他基整数

32 位有符号的整数，还可以指定在十六进制、 八进制或二进制使用`0x`，`0o`或`0b`分别前缀。

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>数值中包含下划线

F # 4.1 开始，你可以分隔数字下划线字符开头 (`_`)。

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a>请参阅

[Core.LiteralAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
