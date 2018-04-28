---
title: 类型扩展 (F#)
description: '了解如何 F # 类型扩展允许将新成员添加到以前定义的对象类型。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 3399778799fbf0f8eee56e332135656150918a60
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="type-extensions"></a>类型扩展

类型扩展允许你将新成员添加到以前定义的对象类型。

## <a name="syntax"></a>语法

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a>备注
有两种形式的具有略有不同的语法和行为的类型扩展。 *内部扩展*作为要扩展的类型是相同的命名空间或模块中，在同一源文件中，，而在同一程序集 （DLL 或可执行文件） 的扩展。 *可选扩展*是显示原始的模块、 命名空间或要扩展的类型的程序集外部的扩展。 类型检查通过反射，但可选扩展不这样做时，内部扩展会出现在类型上。 可选扩展必须在模块中，并且它们是仅在作用域中打开包含扩展的模块时。

在上述语法中， *typename*表示要扩展的类型。 可以扩展可访问任何类型，但类型名称必须是一个实际类型名称，而不是类型缩写。 一种类型扩展中，可以定义多个成员。 *自我标识符*表示正在调用，就像普通成员中一样的对象的实例。

`end`关键字是轻量语法中可选的。

类型扩展中定义的成员可对类类型上的其他成员一样。 与其他成员一样，它们可以是静态或实例成员。 这些方法是也称为*扩展方法*; 属性被称为*扩展属性*，依次类推。 可选扩展成员被编译到的对象实例隐式作为传递的第一个参数的静态成员。 但是，它们充当就像它们是实例成员或根据声明方式的静态成员。 隐式扩展成员包括作为该类型的成员，可以使用不受限制。

扩展方法不能为虚拟或抽象方法。 它们可以重载具有相同名称的其他方法，但编译器则报告首选项设置为对于不明确的调用的非扩展方法。

如果一个类型的存在多个内部类型扩展，所有成员必须都是唯一的。 对于可选类型扩展，为同一类型的不同类型扩展中的成员可以具有相同的名称。 仅当客户端代码将打开两个不同的作用域定义相同的成员名称，则会出现多义性错误。

在下面的示例中，模块中的类型有内部类型扩展。 外部模块的客户端代码，类型扩展将显示为在所有方面的类型的常规成员。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

内部类型扩展可用于分隔成不同的部分类型的定义。 这可以是用于管理大型类型定义，例如，保持编译器生成的代码和编写的代码单独或组合在一起创建的不同的人或不同的功能与关联的代码。

在下面的示例中，可选类型扩展将扩展`System.Int32`类型的扩展方法与`FromString`调用静态成员`Parse`。 `testFromString`方法演示新成员称为就像任何实例成员一样。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

新的实例成员将出现的任何其他方法一样`Int32`类型在 IntelliSense 中，而只包含扩展模块作用域中是打开或以其他方式。

## <a name="generic-extension-methods"></a>泛型扩展方法
在 F # 3.1 之前, 的 F # 编译器不支持使用 C# 的样式与泛型类型变量、 数组类型、 元组类型或 F # 函数类型作为"this"参数的扩展方法。 F # 3.1 支持这些扩展成员使用。

例如，在 F # 3.1 代码中，你可以使用与类似于以下语法在 C# 中的签名的扩展方法：

```csharp
static member Method<T>(this T input, T other)
```

约束的泛型类型参数时，这种方法是特别有用。 此外，你现在可以声明如下 F # 代码中的扩展成员并定义其他的、 在语义上丰富的一组扩展方法。 在 F # 中，你通常扩展成员定义如下面的示例所示：

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

但是，对于泛型类型，类型变量可能不受到约束。 你现在可以声明一个 C# 的 F # 若要解决此限制中的样式扩展成员。 在你合并此类声明使用 F # 的内联功能，你可以作为扩展成员呈现泛型算法。

请考虑以下声明：

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

通过使用此声明，可以编写类似于下面的示例代码。

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

在此代码中，相同的泛型算术代码应用于两个类型的列表的如果没有重载，通过定义单个的扩展成员。


## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[成员](members/index.md)
