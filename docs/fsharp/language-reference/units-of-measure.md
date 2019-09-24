---
title: 度量单位
description: 了解中的F#浮点和有符号整数值如何可以具有关联的度量单位，这些度量值通常用于指示长度、数量和质量。
ms.date: 05/16/2016
ms.openlocfilehash: a81f7760301dc580e333d4659a72e6259d2c916b
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216685"
---
# <a name="units-of-measure"></a>度量单位

中的F#浮点和有符号整数值可以具有关联的度量单位，这通常用于指示长度、数量和质量等。 通过使用具有单位的数量，可以使编译器验证算术关系是否具有正确的单位，这有助于防止编程错误。

## <a name="syntax"></a>语法

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>备注

前面的语法将*单位名称*定义为度量单位。 可选部分用于根据以前定义的单元定义新的度量值。 例如，以下行定义了度量值`cm` （厘米）。

```fsharp
[<Measure>] type cm
```

以下行将度量值`ml` （milliliter）定义为三厘米（`cm^3`）。

```fsharp
[<Measure>] type ml = cm^3
```

在前面的语法中， *measure*是涉及单元的公式。 在涉及单元的公式中，支持整数幂（正和负），单位之间的空格指示两个单位的积， `*`还指示单位的积，并`/`指示单位的商。 对于倒数单元，可以使用负整数幂或`/`指示单元公式的分子和分母之间的分隔。 分母中的多个单元应括在括号中。 后面由空格分隔的`/`单位被解释为分母的一部分，但后面的`*`任何单位会被解释为作为分子的一部分。

您可以在单位表达式中使用1，而不是将其用于表示一种单量维度，也可以与其他单位（如分子）一起使用。 例如，费率的单位将写为`1/s`，其中`s`指示秒。 单元公式中不使用括号。 不在单元公式中指定数值转换常量;但是，您可以单独定义单位的转换常量，并在单元检查计算中使用它们。

可以采用各种等效方式编写表示相同内容的单位公式。 因此，编译器将单元公式转换为一致的窗体，该窗体将负幂转换为 reciprocals，将单位分组为单个分子和分母，并 alphabetizes 分子和分母中的单位。

例如，单位公式`kg m s^-2`和`m /s s * kg`都转换为`kg m/s^2`。

在浮点表达式中使用度量单位。 将浮点数与关联的度量单位一起使用可以添加另一个级别的安全性，并有助于避免使用弱类型化浮点数时，公式中可能发生的单元不匹配错误。 如果您编写使用单元的浮点表达式，则表达式中的单位必须匹配。

您可以使用尖括号中的单元公式来注释文本，如下面的示例中所示。

```fsharp
1.0<cm>
55.0<miles/hour>
```

不在数字与尖括号之间放置空格;但是，可以包含文本后缀（如`f`），如下面的示例中所示。

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

此`float`类批注`float<cm>`将文本的类型从其基元类型（如）更改为已标注类型（在本例中为）。 `float<miles/hour>` 的`<1>`单位批注指示一个有量的量，其类型等效于不带 unit 参数的基元类型。

度量单位的类型是一个浮点型或有符号整型，以及一个额外的单位批注，用方括号括起来。 因此，当您将转换类型从`g` （克`kg` ）写入（千克）时，您将按如下所示描述类型。

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

度量单位用于编译时单元检查，但不会在运行时环境中保留。 因此，它们不会影响性能。

度量单位可以应用于任何类型，而不只是浮点类型;但是，只有浮点类型、有符号的整数类型和 decimal 类型支持已标注数量。 因此，只对基元类型和包含这些基元类型的聚合使用度量单位有意义。

下面的示例阐释了度量单位的用法。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

下面的代码示例演示如何从有量可变浮点数转换为有尺寸的浮点值。 你只需乘以1.0，然后将维度应用于1.0。 可以将此抽象到类似`degreesFahrenheit`的函数。

此外，当你将已确定维度的值传递到需要有量维度浮点数的函数时，必须`float` `float`使用运算符取消单元或强制转换为。 在此示例中，将`1.0<degC>`对的`printf`自变量进行除数`printf` ，因为需要有量维度。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

下面的示例会话显示了输出以及此代码的输入。

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>使用通用单位

您可以编写对具有关联的度量单位的数据进行操作的泛型函数。 为此，可将一个类型与一个泛型单元一起指定为类型参数，如以下代码示例中所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>用通用单位创建聚合类型

下面的代码演示如何创建一个聚合类型，该类型由具有泛型单元的单个浮点值组成。 这样，便可以创建适用于各种单位的单一类型。 此外，通过确保具有一组单位的泛型类型与具有不同单位集的相同泛型类型的类型不同，泛型单位会保留类型安全性。 此方法的基础是`Measure`特性可以应用于类型参数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>运行时单位

度量单位用于静态类型检查。 在编译浮点值时，将消除度量单位，以便在运行时单元丢失。 因此，尝试实现依赖于在运行时检查单元的功能是不可能的。 例如，不能实现`ToString`函数来打印单元。

## <a name="conversions"></a>转换

若要将具有单位的类型（例如， `float<'u>`）转换为不具有单位的类型，则可以使用标准转换函数。 例如，可以使用`float`将转换`float`为不具有单位的值，如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

若要将无单位的值转换为具有单位的值，可以将使用适当单位批注的1或1.0 值相乘。 但是，为了编写互操作性层，还可以使用某些显式函数将无单位值转换为具有单位的值。 它们位于[fsharp.core](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3)模块中。 例如，若要从`float`无单位转换`float<cm>`为，请使用[FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)，如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>F#核心库中的度量单位

`FSharp.Data.UnitSystems.SI`命名空间中提供了一个单元库。 它以`UnitSymbols`子命名空间中的符号形式（类似`m`于计量方式）以及`UnitNames`子命名空间中的全名（如`meter` for 计量）包含 SI 单位。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
