---
title: 形参和实参
description: 了解用于F#定义参数和将参数传递给函数、方法和属性的语言支持。
ms.date: 05/16/2016
ms.openlocfilehash: 67e82d031c4b22bc30a6f278d9698298ccff2e21
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106596"
---
# <a name="parameters-and-arguments"></a>形参和实参

本主题介绍用于定义参数和将参数传递给函数、方法和属性的语言支持。 它包括有关如何按引用传递的信息, 以及如何定义和使用可采用可变数量的自变量的方法。

## <a name="parameters-and-arguments"></a>形参和实参

术语*参数*用于描述应提供的值的名称。 术语*参数*用于为每个参数提供的值。

参数可以在元组或扩充形式中指定, 也可以在这两者的某种组合中指定。 可以通过使用显式参数名传递参数。 可以将方法的参数指定为 optional, 并为其指定默认值。

## <a name="parameter-patterns"></a>参数模式

通常情况下, 提供给函数和方法的参数是由空格分隔的模式。 这意味着, 可以在函数或成员的参数列表中使用[Match 表达式](match-expressions.md)中所述的任何模式。

方法通常使用元组形式传递参数。 这可以从其他 .NET 语言的角度获得更清晰的结果, 因为元组格式与在 .NET 方法中传递参数的方式匹配。

扩充形式最常用于使用`let`绑定创建的函数。

以下伪代码显示了元组和扩充参数的示例。

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

当某些参数在元组中时, 可能会组合窗体, 而有些参数则可能不存在。

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

其他模式也可用于参数列表中, 但如果参数模式与所有可能的输入都不匹配, 则在运行时可能会出现不完整的匹配项。 当参数`MatchFailureException`的值与参数列表中指定的模式不匹配时, 将生成异常。 当参数模式允许不完全匹配时, 编译器会发出警告。 至少一个其他模式对于参数列表通常很有用, 这是通配符模式。 如果只想忽略提供的任何参数, 请在参数列表中使用通配符模式。 下面的代码说明了参数列表中通配符模式的用法。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

如果不需要传入的参数 (例如, 在程序的主入口点中) 对通常作为字符串数组提供的命令行参数感兴趣, 则可以使用通配符模式, 如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

有时在参数中使用的`as`其他模式是模式, 以及与可区分的联合和活动模式关联的标识符模式。 可以按如下所示使用单用例可区分联合模式。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

输出如下所示。

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

活动模式可用作参数, 例如, 将参数转换为所需格式时, 如以下示例中所示:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

您可以使用`as`模式将匹配的值存储为本地值, 如下面的代码行所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

偶尔使用的另一种模式是将未命名的最后一个参数作为函数的主体提供, 该函数可立即对隐式参数执行模式匹配。 下面的代码行就是一个示例。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

此代码定义一个函数, 该函数采用泛型列表, `true`如果列表为空`false` , 则返回, 否则返回。 使用此类技术会使代码更难以阅读。

偶尔, 涉及不完整匹配的模式非常有用, 例如, 如果您知道程序中的列表只有三个元素, 则可以在参数列表中使用如下所示的模式。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

使用不完整匹配的模式最适合用于快速原型和其他临时用途。 编译器将为此类代码发出警告。 此类模式无法涵盖所有可能输入的常规情况, 因此不适合用于组件 Api。

## <a name="named-arguments"></a>命名实参

可以通过以逗号分隔的参数列表中的位置指定方法的参数, 也可以通过提供名称, 后跟一个等号和要传入的值, 来以显式方式将方法传递给方法。 如果通过提供名称指定, 它们的显示顺序可能与声明中使用的顺序不同。

命名参数可以使代码更具可读性, 更好地适应 API 中某些类型的更改, 如方法参数的重新排序。

命名参数只允许用于方法, 不`let`允许用于绑定函数、函数值或 lambda 表达式。

下面的代码示例演示如何使用命名参数。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

在对类构造函数的调用中, 可以通过使用类似于命名参数的语法来设置类的属性值。 下面的示例演示了此语法。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

有关详细信息, 请参阅[构造F#函数 ()](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)。

## <a name="optional-parameters"></a>可选参数

可以通过在参数名称前面使用问号来指定方法的可选参数。 F#可选参数被解释为选项类型, 因此, 你可以通过使用`match`带有`Some`和`None`的表达式, 以通过查询选项类型的常规方式查询它们。 仅允许在成员上使用可选参数, 而不允许使用`let`绑定创建的函数。

可以按参数名称 (如`?arg=None` `?arg=arg`或`?arg=Some(3)` ) 将现有可选值传递给方法。 这在生成将可选自变量传递给其他方法的方法时非常有用。

还可以使用函数`defaultArg`来设置可选参数的默认值。 `defaultArg`函数采用可选参数作为第一个参数, 将默认值作为第二个参数。

下面的示例阐释了可选参数的用法。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

输出如下所示。

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

出于C#和 Visual Basic 互操作, 可以使用中`[<Optional; DefaultParameterValue<(...)>]` F#的属性, 以便调用方将参数显示为可选。 这等效于将自变量定义为中的C#可选, `MyMethod(int i = 3)`如中所示。

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

你还可以将新的对象指定为默认参数值。 例如, `Foo`成员可以将可选`CancellationToken`作为输入:

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

作为的参数`DefaultParameterValue`提供的值必须与参数的类型匹配。 例如, 不允许使用以下项:

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

在这种情况下, 编译器将生成警告, 并将完全忽略这两个特性。 请注意, 默认值`null`需要为类型批注, 否则编译器将推断错误的类型, `[<Optional; DefaultParameterValue(null:obj)>] o:obj`即。

## <a name="passing-by-reference"></a>按引用传递

按引用F#传递值涉及[byref](byrefs.md), 它们是托管指针类型。 使用哪种类型的指南如下:

- 如果`inref<'T>`只需要读取指针, 请使用。
- 如果`outref<'T>`只需要写入指针, 请使用。
- 如果`byref<'T>`需要读取和写入指针, 请使用。

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

由于参数是一个指针, 并且值是可变的, 因此在执行函数后将保留对值所做的任何更改。

您可以使用元组作为返回值, 以在 .net `out`库方法中存储任何参数。 或者, 您可以将`out`参数`byref`视为参数。 下面的代码示例演示了这两种方法。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>参数数组

有时, 有必要定义一个函数, 该函数采用任意数量的异类类型的参数。 创建所有可能的重载方法以考虑可以使用的所有类型是不可行的。 .NET 实现通过参数数组功能为此类方法提供支持。 在其签名中采用参数数组的方法可以使用任意数量的参数提供。 参数放入数组中。 数组元素的类型决定了可传递给函数的参数类型。 如果用`System.Object`作为元素类型定义参数数组, 则客户端代码可以传递任何类型的值。

在F#中, 只能在方法中定义参数数组。 它们不能用于独立函数或模块中定义的函数。

使用`ParamArray`特性定义参数数组。 `ParamArray`特性只能应用于最后一个参数。

下面的代码演示了如何调用一个 .NET 方法, 该方法采用参数数组和中F#某个类型的定义, 该方法具有采用参数数组的方法。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

在项目中运行时, 上一代码的输出如下所示:

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

- [成员](./members/index.md)
