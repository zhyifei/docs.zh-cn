---
title: 参数和自变量 (F#)
description: '了解有关定义参数并将自变量传递给函数、 方法和属性的 F # 语言支持。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e146ec4e877bb89f10e2f3daad2d8356c29fa81f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="parameters-and-arguments"></a>形参和实参

本主题介绍用于定义参数并将自变量传递给函数、 方法和属性的语言支持。 它包括有关如何通过引用传递以及如何定义和使用可以采用数量可变的自变量的方法的信息。


## <a name="parameters-and-arguments"></a>形参和实参
术语*参数*用于描述应提供的值的名称。 术语*参数*用于为每个参数提供的值。

元组或扩充窗体，或两个的某种组合中，可以指定参数。 可以使用显式参数名称传递参数。 可以指定为可选并给定一个默认值的方法的参数。


## <a name="parameter-patterns"></a>参数模式
一般情况下，提供给函数和方法的参数都是由空格分隔的模式。 这意味着，原则上，任何的模式中所述[匹配表达式](match-expressions.md)可以用于在参数列表的函数或成员。

方法通常使用传递自变量的元组形式。 这能实现从其他.NET 语言的角度来看更加清晰的结果，因为元组形式与在.NET 方法中传递自变量的方式相匹配。

扩充窗体最常用于通过使用创建的函数`let`绑定。

下面的伪代码演示元组和扩充自变量的示例。

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

组合的窗体还可能某些自变量是元组中，还有一些不是。

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

其他模式还可用于在参数列表中，但如果参数的模式不匹配所有可能的输入，则可能有不完整的匹配项在运行时。 异常`MatchFailureException`自变量的值与参数列表中指定的模式不匹配时，将生成。 当参数模式允许的不完整的匹配项时，编译器会发出警告。 至少一个其他的模式是通常用于参数列表和通配符模式。 你只想要忽略提供任何自变量时，可使用参数列表中的通配符模式。 下面的代码演示如何使用自变量列表中的通配符模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

通配符模式可以是在不需要传递中的自变量时很有用，如所到某个程序的主入口点时您不感兴趣通常提供作为字符串数组，如以下代码所示的命令行自变量。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

有时使用自变量中的其他模式包括`as`模式，且可区分的联合以及活动模式与关联的标识符模式。 可以使用单一大小写的可区分联合模式，如下所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

输出如下所示。

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

活动模式作为参数，例如，如果可将自变量转换为所需的格式，如以下示例所示：

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

你可以使用`as`模式将匹配的值存储为本地值，如以下代码行所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

偶尔使用的另一种模式是离开通过提供作为函数的正文未命名的最后一个参数的函数，对的隐式的自变量将立即执行模式匹配的 lambda 表达式。 此示例是代码的下面行。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

此代码定义一个函数，它接受泛型列表，并返回`true`如果列表为空，和`false`否则为。 此类技术的使用会使代码更难阅读。

有时，涉及不完整的匹配项的模式非常有用，例如，如果你知道你的程序中的列表具有只有三个元素，则可能使用类似于下面的模式参数列表中。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

利用具有不完全匹配的模式最留待快速原型制作和其他临时使用。 编译器会发出此类代码的警告。 这种模式不能涵盖所有可能的输入的一般情况下，因此不适合组件 Api。

## <a name="named-arguments"></a>命名实参
可以按位置在以逗号分隔的自变量列表中，指定方法的参数，或可以将它们传递到方法显式通过提供名称后, 跟一个等号和要在中传递的值。 如果指定提供名称，它们可以出现在不同的声明中所用顺序。

命名自变量可使代码更具可读性且更适应某些类型的 API，如重新排序方法参数中的更改。

命名自变量仅允许使用方法，不能为`let`-绑定函数、 函数值或 lambda 表达式。

下面的代码示例演示了利用命名自变量。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

在类构造函数的调用中，你可以通过使用类似于命名自变量的语法设置类的属性的值。 下面的示例演示了此语法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

有关详细信息，请参阅[构造函数 （F #）](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)。

## <a name="optional-parameters"></a>可选参数
可以使用问号的前面的参数名称来指定一种方法的可选参数。 可选参数将解释为 F # 选项类型，因此你可以查询它们中的查询选项类型，通过使用正则方式`match`具有表达式`Some`和`None`。 仅适用于成员，通过使用创建的函数上不允许使用可选参数`let`绑定。

你还可以使用一个函数`defaultArg`，这会设置默认值为可选自变量。 `defaultArg`函数使用的第一个参数的可选参数，以及为第二个的默认值。

下面的示例演示如何使用可选参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

输出如下所示。

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>通过引用传递
F # 支持`byref`关键字，用于指定通过引用传递参数。 这意味着后执行函数将保留任何更改的值。 值提供给`byref`参数必须是可变。 或者，你可以将传递适当类型的引用单元格。

作为一种方法，以从函数返回多个值发展的.NET 语言中的引用进行传递。 在 F # 中，可以为此，返回一个元组，或使用作为参数的可变的引用单元格。 `byref`与.NET 库互操作性的主要提供参数。

下面的示例演示如何使用`byref`关键字。 请注意，当你使用作为参数的引用单元格，你必须创建引用单元格作为命名值并将其用作参数，不只是添加`ref`运算符首次调用中所示`Increment`下面的代码中。 创建引用单元格创建基础值的副本，因为第一个调用只会递增的临时值。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

可以使用一个元组作为返回值来存储任何`out`.NET 库方法中的参数。 或者，您可以将`out`参数作为`byref`参数。 下面的代码示例阐释了这两种方式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>参数数组
有时是需要定义采用任意数目的异类类型参数的函数。 它不会实际创建所有可能的重载的方法以解决可能使用的所有类型。 .NET 实现此类方法的参数数组功能通过提供支持。 可以具有任意数量的参数提供的签名中使用参数数组的方法。 参数被放入数组中。 数组元素的类型确定可以传递给函数的参数类型。 如果你定义的参数数组`System.Object`作为元素类型，然后客户端代码可以通过任何类型的值。

在 F # 中，仅在方法中定义参数数组。 它们不能在独立函数或模块中定义的函数。

使用定义的参数数组`ParamArray`属性。 `ParamArray`属性只能应用到的最后一个参数。

下面的代码阐释了这两个调用采用 F # 具有方法接受参数数组中的一个参数数组和类型定义的.NET 方法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

一个项目在运行时，上述代码的输出如下所示：

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>请参阅
[成员](members/index.md)
