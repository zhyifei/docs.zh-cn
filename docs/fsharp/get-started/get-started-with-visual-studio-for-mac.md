---
title: Visual Studio for Mac 中的F#入门
description: 了解如何使用F#与 Visual Studio for Mac。
ms.date: 07/03/2018
ms.openlocfilehash: 679ed1ea28f5d0e0d910dbd407b38d1d2f0314f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629754"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Visual Studio for Mac 中的F#入门

F#Visual Studio for Mac IDE 中F#支持可视化工具。 确保已[安装 Visual Studio for Mac](install-fsharp.md#install-f-with-visual-studio-for-mac)。

## <a name="creating-a-console-application"></a>创建控制台应用程序

Visual Studio for Mac 中最基本的项目之一是控制台应用程序。  以下是使用方法。  打开 Visual Studio for Mac 后:

1. 在 "**文件**" 菜单上, 指向 "**新建解决方案**"。

2. 在 "新建项目" 对话框中, 控制台应用程序有两个不同的模板。  在其他 > 的 .NET 中有一个面向 .NET Framework 的。  其他模板位于.NET Core-> 应用程序以.NET Core 为目标。  这两个模板都适用于本文的目的。

3. 在 "控制台应用" C#下F# , 根据需要将更改为。  选择 "**下一步**" 按钮继续!  

4. 为项目命名, 并为应用选择所需的选项。  请注意, 屏幕右侧的预览窗格将显示将根据所选选项创建的目录结构。  

5. 单击 **“创建”** 。  现在应会在解决方案资源管理器F#中看到一个项目。

## <a name="writing-your-code"></a>编写代码

让我们首先编写一些代码。  确保该`Program.fs`文件已打开, 然后将其内容替换为以下内容:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

在上面的代码示例中, 已`square`定义了一个函数, 该函数采用`x`一个名为的输入, 并将其与自身相乘。  由于F#使用[类型推理](../language-reference/type-inference.md), 因此不需要`x`指定的类型。  编译器了解乘法的有效类型, 并根据调用方式`square`将类型分配给`x`。 F#  如果将鼠标悬停`square`在上方, 应会看到以下内容:

```
val square: x:int -> int
```

这就是所谓函数的类型签名。  如下所示:"方形是一个函数, 它采用名为 x 的整数并生成一个整数"。  请注意, 编译器`square` `int`现在提供类型, 这是因为乘法在*所有*类型中都不是泛型的, 而是在一组封闭类型中是通用的。  此时F#会选取`int`编译器, 但如果您使用`float`其他输入类型 (如) 调用`square` , 则会调整类型签名。

定义了另`main`一个函数, 该函数`EntryPoint`用特性修饰, 以告知编译器程序F#执行应在此开始。  它遵循与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)相同的约定, 可以将命令行参数传递给此函数, 并且返回整数代码 (通常`0`为)。

在此函数中, 我们使用的`square` `12`参数调用了函数。  然后F# `square` , 编译器将`int -> int`的类型分配为 (即, 采用`int`并生成的`int`函数)。  对`printfn`的调用是一个格式化的打印函数, 它使用格式字符串 (类似于 C 样式编程语言)、与在格式字符串中指定的参数相对应的参数, 然后输出结果和新行。

## <a name="running-your-code"></a>运行代码

可以通过单击顶级菜单中的 "**运行**" 来运行代码并查看结果, 然后在**不调试的情况下启动**。  这将在不调试的情况下运行程序, 并允许你查看结果。

现在, 应会看到以下输出到 Visual Studio for Mac 弹出的控制台窗口:

```
12 squared is 144!
```

祝贺你！  已在 Visual Studio for Mac 中创建F#了第一个项目, 并F#编写了一个函数, 该函数将调用该函数的结果打印出来, 并运行该项目以查看某些结果。

## <a name="using-f-interactive"></a>使用F#交互式

Visual Studio for Mac 中的可视化F#工具的最佳功能之一是F#交互窗口。  它允许你将代码发送到可调用该代码并以交互方式查看结果的进程。

若要开始使用它, 请`square`突出显示代码中定义的函数。  接下来, 单击顶部菜单中的 "**编辑**"。  接下来 **, 选择 " F#将所选内容发送到交互**"。  这会在F#交互窗口中执行代码。  也可以右键单击所选内容, 然后选择 "**将所选F#内容发送到交互**"。  应该会看到F#交互式窗口出现, 其中包含以下内容:

```
>

val square : x:int -> int

>
```

这会显示`square`函数的相同函数签名, 在您前面悬停该函数时, 您会看到此函数签名。  由于`square`现在是在F#交互式进程中定义的, 因此可以对其调用不同的值:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

这会执行函数, 将结果绑定到新名称`it`, 并显示的`it`类型和值。  请注意, 必须用`;;`终止每行。  这是F#交互式知道函数调用的完成时间。  还可以在交互式中F#定义新函数:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

上面定义了一个新函数, `isOdd`该函数`int`采用并检查它是否为奇数!  您可以调用此函数, 以查看它如何返回不同的输入。  可以在函数调用中调用函数:

```
> isOdd (square 15);;
val it : bool = true
```

还可以使用[管道转发运算符](../language-reference/symbol-and-operator-reference/index.md)将值传递给两个函数:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

后面的教程中介绍了管道转发运算符等。

这只是一种熟悉交互式操作的方式F# 。  若要了解详细信息, 请查看[的F#交互式编程](../tutorials/fsharp-interactive/index.md)。

## <a name="next-steps"></a>后续步骤

如果你尚未这样做, 请查看[的F#教程](../tour.md), 其中介绍了该F#语言的一些核心功能。  它将为你概述的某些功能F#, 并提供可复制到 Visual Studio for Mac 并运行的充足代码示例。  本指南中还提供了一些可以使用的展示外部资源。 [ F# ](../index.md)

## <a name="see-also"></a>请参阅

- [Visual F#](../index.md)
- [F# 教程](../tour.md)
- [F#语言参考](../language-reference/index.md)
- [类型推理](../language-reference/type-inference.md)
- [符号和运算符引用](../language-reference/symbol-and-operator-reference/index.md)
