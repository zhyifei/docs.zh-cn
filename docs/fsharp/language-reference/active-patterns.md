---
title: 活动模式
description: 了解如何使用活动模式定义在 F# 编程语言中细分输入数据的命名分区。
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187063"
---
# <a name="active-patterns"></a>活动模式

*活动模式*使您能够定义细分输入数据的命名分区，以便可以在模式匹配表达式中使用这些名称，就像对受歧视联合一样。 可使用活动模式以自定义方式为每个分区分解数据。

## <a name="syntax"></a>语法

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a>备注

在前面的语法中，标识符是由*参数*表示的输入数据分区的名称，或者换句话说，是参数所有值集的子集的名称。 活动模式定义中最多只能有七个分区。 表达式*描述*要将数据分解到的窗体。 可以使用活动模式定义定义规则，以确定作为参数给定的值属于哪个命名分区。 （* 和 |） 符号称为*香蕉剪辑*，这种类型的 let 绑定创建的函数称为*活动识别器*。

例如，请考虑以下具有参数的活动模式。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

您可以在模式匹配表达式中使用活动模式，如以下示例所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

此程序的输出如下：

```console
7 is odd
11 is odd
32 is even
```

活动模式的另一个用途是以多种方式分解数据类型，例如当同一基础数据具有各种可能的表示形式时。 例如，`Color`对象可以分解为 RGB 表示形式或汇丰表示形式。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

上述程序的输出如下：

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

结合，这两种使用活动模式的方法使您能够将数据分区和分解为适当的形式，并在最方便的计算形式中对适当的数据执行适当的计算。

生成的模式匹配表达式使数据能够以易于读的便捷方式写入，从而大大简化了潜在的复杂分支和数据分析代码。

## <a name="partial-active-patterns"></a>部分活动模式

有时，您只需要分区部分输入空间。 在这种情况下，您编写一组部分模式，每个模式与某些输入匹配，但无法匹配其他输入。 并不总是生成值的活动模式称为*部分活动模式*;它们具有作为选项类型的返回值。 要定义部分活动模式，请使用在香蕉夹内模式列表末尾\_的通配符 （ ） 。 以下代码说明了部分活动模式的使用。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

上一个示例的输出如下所示：

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

使用部分活动模式时，有时各个选项可以是脱节的，也可以是互斥的，但它们不需要。 在下面的示例中，模式方形和模式立方体并不脱节，因为某些数字既是正方形，也是立方体，如 64。 以下程序使用 AND 模式组合方形和立方体模式。 它打印出所有整数最多 1000 个，这些整数既是正方形和立方体，也是仅多维数据集的整数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

输出如下所示：

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a>参数化活动模式

活动模式始终对要匹配的项至少采用一个参数，但它们也可能采用其他参数，在这种情况下，名称*参数化的活动模式*适用。 其他参数允许将常规模式专门化。 例如，使用正则表达式解析字符串的活动模式通常包括正则表达式作为额外参数，如以下代码，该代码还使用前一个代码示例中定义的部分活动模式`Integer`。 在此示例中，为各种日期格式提供正则表达式的字符串用于自定义常规 ParseRegex 活动模式。 整数活动模式用于将匹配的字符串转换为可传递给 DateTime 构造函数的整数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

前一个代码的输出如下：

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

活动模式不仅局限于模式匹配表达式，还可以在 let 绑定上使用它们。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

前一个代码的输出如下：

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>另请参阅

- [F# 语言参考](index.md)
- [Match 表达式](match-expressions.md)
