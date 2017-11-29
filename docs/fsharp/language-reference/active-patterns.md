---
title: "活动模式 (F#)"
description: "了解如何使用活动模式可以定义将在 F # 编程语言的输入的数据的命名的分区。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 11a724ff-f9ff-4056-b5e0-87e9ed986f4a
ms.openlocfilehash: 845184e6150cf0b93393038ca3d39f0e6d898a2e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="active-patterns"></a>活动模式

*活动模式*使您能够定义将输入的数据的命名的分区，以便你可以在匹配表达式，就像可区分联合模式中使用这些名称。 可使用活动模式以自定义方式为每个分区分解数据。


## <a name="syntax"></a>语法

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>备注
在上述语法中，标识符都是由输入数据的分区名称*参数*，或，换而言之，名称参数的所有值集的子集。 活动模式定义中可以有最多七个分区。 *表达式*描述要将数据分解到窗体。 活动模式定义可用于定义用于确定哪些命名的分区按照自变量属于给定的值的规则。 (| 和 |) 符号被称为*香蕉夹*和调用函数创建的此类型的 let 绑定*active 识别器*。

作为示例，请考虑用参数的以下活动模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

在模式匹配表达式，如以下示例所示，可以使用活动的模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

此程序的输出如下所示：

```
7 is odd
11 is odd
32 is even
```

活动模式的另一个用途是将分解采用多种方式，例如在相同的基础数据具有各种可能的表示形式之间的数据类型。 例如，`Color`对象无法分解为一表示形式，RGB 或 HSB 表示形式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

上面的程序中的输出如下所示：

```
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

在组合中，使用活动的模式的这两种方式使您能够在分区和将数据分解为适当的形式为和最方便的计算窗体中的相应数据执行适当的计算。

生成的模式匹配表达式启用数据是非常可读，极大地简化潜在的复杂分支和数据分析代码的简便方式写入。


## <a name="partial-active-patterns"></a>分部活动模式
有时，你需要进行分区只输入空间的一部分。 在这种情况下，你编写一组分部模式，其中匹配某些输入，但不能匹配其他输入。 调用活动的模式，始终不会产生一个值*分部活动模式*; 它们具有一个返回值，是选项类型。 若要定义部分的活动模式，请在内部香蕉夹模式的列表的末尾使用通配符字符 (_)。 下面的代码演示如何使用分部活动模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

前面的示例的输出如下所示：

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

当使用部分活动模式时，有时各个选项可以是连续的或互斥的但它们不需要。 在下面的示例中，模式 Square 和多维数据集的模式不连续的因为一些数字平方和多维数据集，例如 64。 下面的程序将最多是平方和多维数据集的 1000000 输出所有的整数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

输出如下所示：

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a>参数化的活动模式
活动模式始终采用要匹配的项的至少一个自变量，但也可能会采用其他参数，这种情况下名称*参数化的活动模式*适用。 其他参数，可专用的常规模式。 例如，使用正则表达式分析字符串通常的活动模式包括正则表达式作为一个附加参数，如下面的代码，还会使用分部活动模式中所示`Integer`在前面的代码示例中定义。 在此示例中，提供用于各种日期格式的正则表达式的字符串的自定义常规 ParseRegex 活动模式。 使用整数 active 模式将匹配的字符串转换为可以传递给 DateTime 构造函数的整数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

上述代码的输出如下所示：

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

活动模式不受限制，只是为了模式匹配的表达式，你还可以让绑定上使用它们。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

上述代码的输出如下所示：

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)

[match 表达式](match-expressions.md)

