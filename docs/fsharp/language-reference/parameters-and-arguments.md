---
title: 形参和实参
description: 了解 F# 语言对定义参数和将参数传递给函数、方法和属性的支持。
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401051"
---
# <a name="parameters-and-arguments"></a>形参和实参

本主题介绍定义参数和将参数传递给函数、方法和属性的语言支持。 它包括有关如何通过引用传递的信息，以及如何定义和使用可以采用可变参数数的方法。

## <a name="parameters-and-arguments"></a>形参和实参

术语*参数*用于描述预期提供的值的名称。 术语*参数*用于为每个参数提供的值。

参数可以以元组或咖喱形式指定，也可以以两者的某些组合指定。 可以使用显式参数名称传递参数。 方法的参数可以指定为可选，并给出默认值。

## <a name="parameter-patterns"></a>参数模式

提供给函数和方法的参数一般是由空格分隔的模式。 这意味着，原则上，[匹配表达式](match-expressions.md)中描述的任何模式都可以在函数或成员的参数列表中使用。

方法通常使用传递参数的元组形式。 从其他 .NET 语言的角度来看，这可实现更清晰的结果，因为元组形式与在 .NET 方法中传递参数的方式匹配。

咖喱窗体最常用于使用`let`绑定创建的函数。

下面的伪代码显示了元组和咖喱参数的示例。

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

当某些参数位于组合中，而有些参数不是时，可以组合形式。

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

其他模式也可以在参数列表中使用，但如果参数模式与所有可能的输入不匹配，则运行时可能存在不完全匹配。 当参数`MatchFailureException`的值与参数列表中指定的模式不匹配时，将生成异常。 当参数模式允许不完全匹配时，编译器发出警告。 至少有一个其他模式通常可用于参数列表，即通配符模式。 当您只想忽略提供的任何参数时，在参数列表中使用通配符模式。 以下代码说明了通配符模式在参数列表中的使用。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

当您不需要传入的参数（如程序的主入口点）时，当您对通常作为字符串数组提供的命令行参数不感兴趣时，通配符模式非常有用，如以下代码。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

参数中有时使用的其他模式是与受歧视的联合`as`和活动模式关联的模式和标识符模式。 可以使用单例区分联合模式，如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

输出如下所示。

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

活动模式可用作参数，例如，将参数转换为所需格式时，如以下示例所示：

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

可以使用`as`模式将匹配值存储为本地值，如下代码行所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

偶尔使用的另一种模式是一个函数，该函数通过提供 lambda 表达式（作为函数的正文）来保留最后一个参数未命名，该表达式将立即对隐式参数执行模式匹配。 例如以下代码行。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

此代码定义一个函数，该函数获取泛型列表`true`，并在列表为空时返回`false`，否则返回。 使用此类技术会使代码更难阅读。

有时，涉及不完全匹配的模式很有用，例如，如果您知道程序中的列表只有三个元素，则可以在参数列表中使用如下所示的模式。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

使用匹配不完全的模式最好保留用于快速原型设计和其他临时用途。 编译器将针对此类代码发出警告。 此类模式不能涵盖所有可能输入的一般情况，因此不适合组件 API。

## <a name="named-arguments"></a>命名实参

方法的参数可以按逗号分隔参数列表中的位置指定，也可以通过提供名称（后跟等符号和要传入的值）显式传递给方法。 如果通过提供名称指定，它们可以按与声明中使用的顺序不同的显示顺序显示。

命名参数可以使代码更具可读性，并更适应 API 中的某些类型的更改，例如方法参数的重新排序。

命名参数仅允许用于方法，不适用于`let`绑定函数、函数值或 lambda 表达式。

以下代码示例演示了命名参数的使用。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

在调用类构造函数时，可以使用类似于命名参数的语法来设置类的属性值。 下面的示例显示了此语法。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

有关详细信息，请参阅[构造函数 （F#）。](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)

## <a name="optional-parameters"></a>可选参数

可以使用参数名称前面的问号为方法指定可选参数。 可选参数被解释为 F# 选项类型，因此可以使用 的`match``Some`表达式 和 ，以查询选项类型的常规方式查询它们。 `None` 可选参数仅允许在成员上，不允许使用`let`绑定创建的函数。

可以按参数名称将现有可选值传递给方法，例如`?arg=None`或`?arg=Some(3)``?arg=arg`。 这在构建将可选参数传递给另一种方法的方法时非常有用。

您还可以使用 函数`defaultArg`，它设置可选参数的默认值。 函数`defaultArg`将可选参数作为第一个参数，将默认值作为第二个参数。

下面的示例说明了可选参数的使用。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

输出如下所示。

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

出于 C# 和 Visual Basic 互操作的目的，可以使用`[<Optional; DefaultParameterValue<(...)>]`F# 中的属性，以便调用方将参数视为可选参数。 这相当于在 C# 中将参数定义为可选参数，如`MyMethod(int i = 3)`在 中。

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

还可以指定新对象作为默认参数值。 例如，`Foo`成员可以改为具有可选`CancellationToken`作为输入：

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

作为参数给出的值`DefaultParameterValue`必须与参数的类型匹配。 例如，不允许使用以下内容：

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

在这种情况下，编译器将生成警告，并将完全忽略这两个属性。 请注意，需要对默认值`null`进行类型注释，否则编译器将推断错误的类型，即`[<Optional; DefaultParameterValue(null:obj)>] o:obj`。

## <a name="passing-by-reference"></a>通过引用传递

通过引用传递 F# 值涉及[byrefs，](byrefs.md)它们是托管指针类型。 使用哪种类型的指南如下所示：

- 如果`inref<'T>`只需要读取指针，请使用。
- 如果`outref<'T>`只需要写入指针，请使用。
- 如果需要`byref<'T>`同时读取指针并写入指针，请使用。

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

由于参数是指针，并且值是可变的，因此在执行函数后将保留对值的任何更改。

可以使用元组作为返回值，在 .NET 库`out`方法中存储任何参数。 或者，您可以将参数`out`视为参数。 `byref` 以下代码示例说明了这两种方法。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>参数数组

有时，需要定义一个函数，该函数采用异构类型的任意数量的参数。 创建所有可能的重载方法以考虑可以使用的所有类型是不现实的。 .NET 实现通过参数数组功能为这些方法提供支持。 在其签名中采用参数数组的方法可以提供任意数量的参数。 参数被放入数组中。 数组元素的类型确定可传递给函数的参数类型。 如果将参数数组`System.Object`定义为元素类型，则客户端代码可以传递任何类型的值。

在 F# 中，只能在方法中定义参数数组。 它们不能用于在模块中定义的独立函数或函数中。

通过使用`ParamArray`属性定义参数数组。 该`ParamArray`属性只能应用于最后一个参数。

以下代码说明了调用采用参数数组的 .NET 方法，以及 F# 中具有采用参数数组的方法的类型的定义。

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

在项目中运行时，前一个代码的输出如下所示：

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>另请参阅

- [成员](./members/index.md)
