---
title: 命名空间 (F#)
description: '了解如何使用 F # 命名空间，可将代码组织到相关的功能区域，通过使你能够将名称附加到的程序元素分组。'
ms.date: 04/24/2017
ms.openlocfilehash: 151079864f18fff79dac108889b68b3acf1566a1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957757"
---
# <a name="namespaces"></a>命名空间

命名空间通过使你能够将名称附加一组程序元素，实现将代码整理到相关的功能区域。


## <a name="syntax"></a>语法

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a>备注
如果你想要将代码放在一个命名空间，该文件中的第一个声明必须声明命名空间。 文件的全部内容然后会变得命名空间的一部分。

值和函数，不能直接包含命名空间。 相反，必须在模块中，包括值和函数，模块包含在命名空间。 命名空间可以包含类型和模块。

命名空间可以显式声明命名空间关键字，或隐式声明模块时。 若要显式声明命名空间，使用命名空间关键字后跟的命名空间名称。 下面的示例演示使用类型和模块包含在该命名空间中声明一个命名空间小组件的代码文件。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

如果该文件的整个内容都位于一个模块，你也可以声明命名空间隐式使用`module`关键字并提供完全限定的模块名称中的新命名空间名称。 下面的示例演示声明一个命名空间的代码文件`Widgets`和模块`WidgetsModule`，其中包含一个函数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

下面的代码是等效于前面的代码，但该模块是一个本地模块声明。 在这种情况下，命名空间必须显示在各占一行。

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

如果多个模块需要在一个或多个命名空间中的相同文件，则必须使用本地模块声明。 当使用本地模块声明时，不能在模块声明中使用限定的命名空间。 下面的代码演示具有命名空间声明和两个本地模块声明的文件。 在这种情况下，模块会直接包含在该命名空间。没有任何文件具有相同名称的隐式创建的模块。 任何其他代码在文件中，如`do`绑定，属于命名空间中但不是在内部的模块，因此你需要限定模块成员`widgetFunction`通过使用模块名称。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

此示例的输出如下所示。

```fsharp
Module1 10 20
Module2 5 6
```

有关详细信息，请参阅[模块](modules.md)。

## <a name="nested-namespaces"></a>嵌套的命名空间
当你创建一个嵌套命名空间时，则必须完全限定它。 否则，您创建新的顶级命名空间。 在命名空间声明中将忽略缩进。

下面的示例演示如何声明嵌套的命名空间。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>在文件和程序集的命名空间
命名空间可以跨多个文件中的单个项目或编译。 术语*命名空间片段*描述在一个文件中包含的命名空间的一部分。 命名空间还可以跨多个程序集。 例如，`System`命名空间包括整个.NET Framework 中，也不能跨越多个程序集包含许多嵌套命名空间。


## <a name="global-namespace"></a>全局 Namespace
使用预定义的命名空间`global`放置在.NET 顶级命名空间中的名称。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

你还可以使用全局若要引用的顶级的.NET 命名空间，例如，若要解决与其他命名空间的名称冲突。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>递归命名空间

F # 4.1 引入了允许的所有包含的代码要相互递归的命名空间的概念。  这是通过`namespace rec`。  利用`namespace rec`可以减轻中无法编写类型和模块之间的相互引用代码的一些难题。  下面是此示例：

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

请注意，异常`DontSqueezeTheBananaException`和类`Banana`同时相互引用。  此外，该模块`BananaHelpers`和类`Banana`也相互引用。  这将不可能表示在 F # 中，如果你删除`rec`关键字从`MutualReferences`命名空间。

此功能也是可用于顶级[模块](modules.md)在 F # 4.1 或更高版本。

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[模块](modules.md)

[F # RFC FS-1009-允许通过在文件内的较大作用域的互相引用的类型和模块](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
