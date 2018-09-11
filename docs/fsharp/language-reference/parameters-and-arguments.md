---
title: 参数和自变量 (F#)
description: '了解有关 F # 语言支持对定义形参并将参数传递给函数、 方法和属性。'
ms.date: 05/16/2016
ms.openlocfilehash: a1e2a70ca560bbb09d2cd10f47485cbe5c5e029d
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338254"
---
# <a name="parameters-and-arguments"></a>形参和实参

本主题介绍对定义形参并将参数传递给函数、 方法和属性的语言支持。 它包括有关如何将传递的引用，以及如何定义和使用可以采用可变数量的参数的方法的信息。

## <a name="parameters-and-arguments"></a>形参和实参

术语*参数*用于描述的预期提供的值的名称。 术语*自变量*用于为每个参数提供的值。

元组或扩充窗体，或两者的某种组合中，可以指定参数。 可以通过使用显式参数名称传递参数。 方法的参数可以是指定为可选，指定的默认值。

## <a name="parameter-patterns"></a>参数模式

一般情况下，提供给函数和方法的参数是由空格分隔的模式。 这意味着，从原理上讲，任何模式中所述[匹配表达式](match-expressions.md)可用于在参数列表中的函数或成员。

方法通常会使用元组形式传递自变量。 这实现了从其他.NET 语言的角度来看更加清晰的结果，因为元组形式与.NET 方法中传递参数的方法相匹配。

通过使用创建的函数最常使用扩充的形式`let`绑定。

下面的伪代码显示了元组和扩充的参数的示例。

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

组合的窗体时，某些参数是在元组中，有些则不然。

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

其他模式还可用于在参数列表中，但如果参数模式与所有可能的输入不匹配，则可能是不完整的匹配项在运行时。 异常`MatchFailureException`自变量的值与参数列表中指定的模式不匹配时生成。 当参数模式允许的不完整的匹配项时，编译器将发出警告。 至少一个其他模式在通常可用于参数列表，这就是通配符模式。 如果只是想要忽略提供的任何自变量参数列表中使用通配符模式。 下面的代码演示如何使用参数列表中的通配符模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

您不感兴趣通常提供作为一个字符串数组，如以下代码所示的命令行参数时，可能很有用，只要不需要传入的参数，如主入口点到程序中，通配符模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

有时使用参数中的其他模式包括`as`模式，且可区分的联合和活动模式与相关联的标识符模式。 可以使用单用例可区分联合模式，如下所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

输出如下所示。

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

活动模式可作为参数，例如，如果将参数转换为所需的格式，如以下示例所示：

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

可以使用`as`模式匹配的值存储为本地值，如以下代码行中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

偶尔使用的另一种模式是离开通过提供，作为函数的正文未命名的最后一个参数的函数、 隐式的自变量将立即执行模式匹配的 lambda 表达式。 此示例为以下代码行。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

此代码定义一个函数接受一个泛型列表，并返回`true`如果列表为空，和`false`否则为。 使用此类技术可以使代码更难以阅读。

有时，涉及不完整的匹配项的模式是有用的例如，如果您知道您的程序中的列表具有只有三个元素，您可以使用如下所示的模式参数列表中。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

最好保留以供快速原型制作和其他临时使用具有不完全匹配的模式的使用。 编译器将发出此类代码的警告。 此类模式无法涵盖所有可能的输入的一般情况下，并因此不适合组件 Api。

## <a name="named-arguments"></a>命名实参

可以通过在逗号分隔参数列表中，位置指定的方法参数或它们可以显式传递给方法通过提供名称后, 跟一个等号和要在中传递的值。 如果指定通过提供的名称，它们可以出现在不同的声明中使用的顺序。

命名的自变量可以对某些类型的 API，如方法参数的重新排序中的更改使代码更具可读性且更适应能力更强。

命名的参数只允许在方法，不能用于`let`-绑定函数、 函数或 lambda 表达式。

下面的代码示例演示如何将命名参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

在类构造函数调用中，可以使用类似于的命名参数的语法来设置类的属性的值。 下面的示例显示了此语法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

有关详细信息，请参阅[构造函数 （F #）](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)。

## <a name="optional-parameters"></a>可选参数

可以通过使用参数名称前面的问号指定一种方法的可选参数。 可选参数被解释为 F # 选项类型，因此您可以将这些查询，查询选项类型，通过常规方式`match`与表达式`Some`和`None`。 仅在成员上，通过使用创建的函数上不允许使用可选参数`let`绑定。

此外可以使用一个函数`defaultArg`，用于设置默认值为可选的参数。 `defaultArg`函数使用的第一个参数的可选参数，以及为第二个的默认值。

下面的示例演示如何使用可选参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

输出如下所示。

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>按引用传递

按引用传递的 F # 值涉及[byref](byrefs.md)，哪些是托管的指针类型。 对于要使用的类型是，如下所示的指南：

* 使用`inref<'T>`如果只需要读取指针。
* 使用`outref<'T>`如果只需编写的指针。
* 使用`byref<'T>`如果你需要同时读取和写入到的指针。

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

因为参数是一个指针，值为可变，对值的任何更改将保留后执行函数。

可以使用一个元组作为返回值来存储任何`out`中.NET 库方法的参数。 或者，您可以将`out`参数作为`byref`参数。 下面的代码示例说明了这两种方式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>参数数组

有时有必要定义采用任意数量的异构类型的参数的函数。 它不会实际创建所有可能的重载的方法来应对可能使用的所有类型。 .NET 实现为此类方法的参数数组功能通过提供支持。 可以有任意数量的参数提供的签名中使用参数数组的方法。 参数被放入数组中。 数组元素的类型确定可以传递给函数的参数类型。 如果定义数组，该参数数组`System.Object`与元素类型，然后客户端代码可以通过任何类型的值。

在 F # 中，只能在方法中定义参数数组。 它们不能独立函数或模块中定义的函数中使用。

使用定义的参数数组`ParamArray`属性。 `ParamArray`属性只能应用到的最后一个参数。

以下代码演示了这两个调用 F # 具有采用参数数组的方法中使用参数数组和类型的定义的.NET 方法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

当运行在项目中，上述代码的输出如下所示：

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>请参阅

- [成员](members/index.md)
