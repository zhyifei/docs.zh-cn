---
title: 模块 (F#)
description: '了解如何 F # 模块是 F # 代码，例如值、 类型和函数值，F # 程序中的分组。'
ms.date: 04/24/2017
ms.openlocfilehash: b503a78abed34cbb56a7a1ceaba61f851a125831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="modules"></a>模块

F # 语言的上下文中*模块*是 F # 代码，例如值、 类型和函数值，F # 程序中的分组。 对模块中的代码进行分组有助于将相关代码放在一起，并有助于避免程序中的名称冲突。

## <a name="syntax"></a>语法

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a>备注
F # 模块是分组，如类型、 值、 函数值和中的代码的 F # 代码构造的`do`绑定。 它只包含静态成员的公共语言运行时 (CLR) 类作为实现。 有两种类型的模块声明，具体取决于该模块中是否包含整个文件： 顶级模块声明和本地模块声明。 顶级模块声明的模块中包括整个文件。 顶级模块声明可以显示仅为一个文件中的第一个声明。

可选的顶级模块声明的语法中*限定命名空间*是包含该模块的序列的嵌套命名空间名称。 限定的命名空间没有以前声明。

无需缩进顶级模块中的声明。 你不必要缩进本地模块中的所有声明。 在本地模块声明中，仅将该模块声明之下缩进的声明是模块的一部分。

如果代码文件不以开头的顶级模块声明或命名空间声明中，整个文件的内容，包括任何本地模块，将成为文件，而不进行扩展，与具有相同名称的隐式创建顶级模块的一部分与第一个字母转换为大写形式。 例如，考虑下面的文件。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

此文件将进行编译，就像这种方式编写：

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

如果你有多个模块文件中，你必须为每个模块使用本地模块声明。 如果声明为外层命名空间，这些模块是封闭命名空间的一部分。 如果不声明外层命名空间，模块将成为隐式创建的顶级模块的一部分。 下面的代码示例显示包含多个模块的代码文件。 编译器隐式创建一个名为的顶级模块`Multiplemodules`，和`MyModule1`和`MyModule2`嵌套在该顶级模块。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

如果你有多个文件的项目中或在单个编译中，或如果你要构建库，则必须包含命名空间声明或模块文件顶部的声明。 F # 编译器仅确定模块名称隐式当在项目或编译命令行中，只有一个文件并且你要创建的应用。

*可访问性修饰符*可以是以下之一： `public`， `private`， `internal`。 有关详细信息，请参阅[访问控制](access-control.md)。 默认值为 public。


## <a name="referencing-code-in-modules"></a>引用的模块中的代码
在从另一个模块引用函数、 类型和值时，你必须使用限定的名称或打开该模块。 如果你使用的限定的名称，则必须指定命名空间、 模块和所需的程序元素的标识符。 如下所示带有圆点 （.） 分隔每个部分限定的路径。

`Namespace1.Namespace2.ModuleName.Identifier`

你可以打开该模块或一个或多个要简化代码的命名空间。 有关打开命名空间和模块的详细信息，请参阅[导入声明：`open`关键字](import-declarations-the-open-keyword.md)。

下面的代码示例显示一个包含最多文件末尾的所有代码的顶级模块。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

若要从同一项目中的另一个文件中使用此代码，你使用限定的名称或打开该模块，然后使用这些函数，如下面的示例中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>嵌套的模块
可以嵌套模块。 内部模块必须与外部模块声明，以指示它们是内部模块，而不是新模块缩进。 例如，比较下面两个示例。 模块`Z`是下面的代码中一个内部模块。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

但模块`Z`是模块同级`Y`下面的代码中。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
模块`Z`也是在以下代码中，是同级模块，因为它不会与其他模块中声明缩进`Y`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
最后，如果外部模块不包含任何声明，并且立即跟另一个模块声明，新的模块声明被假定为一个内部模块，但编译器会警告你如果第二个模块定义不会缩进 farther 比第一个。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
若要消除此警告，缩进的内部模块。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
如果你想要在单个外部模块中的文件中的所有代码，你都需要使用内部模块外部模块不需要在等号和声明，包括任何内部模块声明，会在外部模块中无需进行缩进。 在内部模块声明的声明必须存在要缩进。 下面的代码演示了这种情况。

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>递归模块

F # 4.1 引入了允许的所有包含的代码要相互递归的模块的概念。  这是通过`module rec`。  利用`module rec`可以减轻中无法编写类型和模块之间的相互引用代码的一些难题。  下面是此示例：

```fsharp
module rec RecursiveModule =
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

    module private BananaHelpers =
        let peel (b : Banana) =
            let flip banana =
                match banana.Orientation with
                | Up -> 
                    banana.Orientation <- Down
                    banana
                | Down -> banana

            let peelSides banana =
                for side in banana.Sides do
                    if side = Unpeeled then
                        side <- Peeled

            match b.Orientation with
            | Up ->   b |> flip |> peelSides
            | Down -> b |> peelSides
```

请注意，异常`DontSqueezeTheBananaException`和类`Banana`同时相互引用。  此外，该模块`BananaHelpers`和类`Banana`也相互引用。  这将不可能表示在 F # 中，如果你删除`rec`关键字从`RecursiveModule`模块。

此功能，还可以在[命名空间](namespaces.md)F # 4.1。

## <a name="see-also"></a>请参阅

[F # 语言参考](index.md)
[命名空间](namespaces.md)
[F # RFC FS-1009-允许通过在文件内的较大作用域的互相引用的类型和模块](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
