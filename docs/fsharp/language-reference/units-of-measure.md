---
title: "度量单位 (F#)"
description: "了解如何浮点并在 F # 中的带符号的整数值可以具有相关联的度量值，通常用来指示长度、 卷和大容量单位。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: cb2eb658-df6c-422e-afad-97422609c773
ms.openlocfilehash: 2d0683e864c5684a78c02e177c296d3067295723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="units-of-measure"></a>度量单位

F # 中的浮点点和带符号的整数值可以具有关联的度量值，通常用来指示长度、 体积、 成批，依次类推的单位。 通过使用带单位的数量，启用编译器验证算术关系具有正确的单位，从而有助于防止出现编程错误。


## <a name="syntax"></a>语法

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>备注
前面的语法定义*单元名称*作为一个单元的度量值。 可选部分用于定义新的度量值根据以前定义的单位。 例如，下面的行定义度量值`cm`（厘米）。

```fsharp
[<Measure>] type cm
```

下面的行定义度量值`ml`（毫升） 为立方厘米 (`cm^3`)。

```fsharp
[<Measure>] type ml = cm^3
```

在上述语法中，*度量值*是涉及单元的公式。 在涉及单元的公式，（正值和负值） 支持整数幂，单位之间的空格指示两个单元的产品`*`还指示单元的产品和`/`指示的单元的商。 对于倒数单位，可以使用负的整数幂或`/`，该值指示分子和单位公式的分母之间的分隔。 在分母中的多个单元应由括号括起来。 用后的空格分隔单元`/`都被解释为属于分母，但后面的任何单位`*`都被解释为分子的一部分。

在单元表达式中，或者单独以指示纲数量，或者与其他单元，如在分子，你可以使用 1。 例如，将为写入速率的单位`1/s`，其中`s`表示秒。 单元的公式中不使用括号。 不要到单元的公式; 中指定数值的转换常量但是，你可以单独使用的单位定义转换常量，并在单元检查计算中使用它们。

相同的含义的单元公式可以用不同的等效方法。 因此，编译器将转换为一致的格式，也不能将负数幂成倒数，组单元转换为单一的分子和分母中，按字母顺序排列的分子和分母中的单元的单元的公式。

例如，单元公式`kg m s^-2`和`m /s s * kg`均会转换为`kg m/s^2`。

在浮点表达式中使用的度量值的单位。 使用浮点数与关联的单元的度量值将添加另一个级别的类型安全，并有助于避免使用弱类型的浮点数时可以在公式中会发生的单元不匹配错误。 如果您编写的浮点使用单位的点表达式，在表达式中的单元必须与匹配。

还可以批注带有单元公式在尖括号中中的文本，如下面的示例中所示。

```fsharp
1.0<cm>
55.0<miles/hour>
```

不要放置数与尖括号; 之间存在空格但是，可以包括一个文本后缀例如`f`，如下面的示例。

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

此类批注的文本的类型更改从其基元类型 (如`float`) 为某个维度类型，如`float<cm>`或在这种情况下， `float<miles/hour>`。 一个类型的单元批注`<1>`指示纲数量和其类型是否等效于不带单元参数的基元类型。

一个度量单位类型是浮点数，或带符号整型类型以及在括号中指示的额外单元批注。 因此，当你编写的转换的类型时，才`g`（元语法） 到`kg`（千克），你将描述的类型，如下所示。

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

度量单位用于检查的编译时间单位，但不是会保留在运行时环境。 因此，它们不会影响性能。

度量单位可以应用于任何类型，而不仅仅浮点类型;但是，唯一的浮点类型，已签名的整数类型和十进制类型进行维度化的支持数量。 因此，它仅意义上基元类型和包含这些基元类型的聚合中使用的度量单位。

下面的示例演示如何使用度量单位。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
下面的代码示例演示了如何将从纲浮点数转换为维度的浮点值。 你只需乘以 1.0，1.0 到应用维度。 你可以在所示的函数到抽象这`degreesFahrenheit`。

此外，当您将维度的值传递给预期纲浮点数的函数时，则必须抵消单位或强制转换为`float`使用`float`运算符。 在此示例中，你除以`1.0<degC>`到的自变量`printf`因为`printf`需要纲数量。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

下面的示例会话显示的输出和对此代码的输入。

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>使用泛型的单元
你可以编写操作的泛型函数上具有一个关联的度量值单元的数据。 你执行此操作指定泛型单元以及一个类型作为类型参数，如下面的代码示例中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a>创建与泛型的单元的聚合类型
下面的代码演示如何创建包含单个浮点值具有都是泛型方法的单位聚合类型。 这使单个类型要创建适用于各种单位。 此外，泛型单位可以通过确保具有一套单位的泛型类型一组不同的单元相同的泛型类型的 type 不同保留类型安全。 此技术的基础是`Measure`特性可以应用于的类型参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a>在运行时的单位
度量单位用于静态类型检查。 当浮点值进行编译时，则是消除了的度量单位，因此单位在运行时都将丢失。 因此，不可能实现依赖于在运行时检查单位的功能的任何尝试。 例如，实现`ToString`函数来打印出单位不能。


## <a name="conversions"></a>转换
要转换的单元的类型 (例如， `float<'u>`) 向不具有单位的类型，你可以使用标准转换函数。 例如，你可以使用`float`将转换为`float`不具有单元，如下面的代码中所示的值。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

若要将无单位的值转换为具有单元的值，你可以乘以一个 1 或 1.0 的值进行批注，用适当的单位。 但是，用于编写互操作性层，也有一些可用于使用的单位将无单位的值转换为值的显式函数。 这些结果位于[Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3)模块。 例如，若要从无单位转换`float`到`float<cm>`，使用[FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a>F # Power 包中的度量单位
单元库是在 F # PowerPack 中可用。 单元库包含 SI 单位和物理常量。


## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)
