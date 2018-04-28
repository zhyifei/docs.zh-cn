---
title: '开始使用 Visual Studio 中的 F # 适用于 Mac'
description: '了解如何使用 F # Visual Studio for mac。'
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 232235952ec43f682dc21de4ef7dde9c1b553364
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>开始使用 Visual Studio 中的 F # 适用于 Mac

F # 和 Visual F # 工具支持在 Visual Studio Mac IDE。  若要开始，你应[下载适用于 Mac 的 Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)，如果你尚未。  本文使用 Visual Studio 社区 2017 for Mac，但你可以使用 F # 与所选的版本。

## <a name="installing-f"></a>正在安装 F # #

下载适用于 Mac 的 Visual Studio 后, 它将提示你选择你想要安装。  为了进行这篇文章中我们将保留的默认设置。  与 Visual Studio for Windows，你不需要专门安装 F # 支持。  按"安装"以继续。

安装完成后，选择"启动 Visual Studio"。  你也可以启动它通过 Finder 在 macOS 上。

## <a name="creating-a-console-application"></a>创建一个控制台应用程序

适用于 Mac 的 Visual Studio 中最基本的项目之一是控制台应用程序。  以下是使用方法。  打开 Visual Studio for Mac 后：

1. 上**文件**菜单上，指向**新解决方案**。

2.  在新项目对话框中，有 2 个不同的模板为控制台应用程序。  还有一个在其他-> 面向.NET Framework 的.NET。  其他模板位于.NET 核心-> 应用程序以.NET 核心为目标。  任一模板应工作本文的目的。

3. 在控制台应用程序，将更改 C# 为 F # 必要。  选择**下一步**按钮前移 ！  

4. 为你的项目指定名称，然后选择你希望应用程序的选项。  请注意，将创建的目录结构基于所选的选项将显示在屏幕的一端，对预览窗格。  

5. 单击“创建” 。  你现在应该看到解决方案资源管理器中的 F # 项目。

## <a name="writing-your-code"></a>编写代码

让我们开始吧通过首先编写一些代码。  请确保`Program.fs`文件已打开，，然后将其内容替换为以下：

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

在前面的代码示例，函数`square`具有已定义接受名为输入`x`和乘以它本身。  因为 F # 使用[类型推理](../language-reference/type-inference.md)的一种`x`不需要指定。  F # 编译器了解有效，乘法的类型，将分配到的类型`x`具体取决于`square`调用。  如果将鼠标悬停在`square`，则应查看以下信息：

```
val square: x:int -> int
```

这就是所谓的函数的类型签名。  它可以读取如下:"平方形是一个函数，将名为一个整数 x，并生成一个整数"。  请注意，编译器会为提供`square``int`类型现在-这是因为乘法不是泛型跨*所有*类型，但而是泛型类型的封闭集。  F # 编译器选取`int`在这点，但它将调整类型签名如果调用`square`替换为其他输入类型，如`float`。

另一个函数， `main`，定义，这用修饰`EntryPoint`属性指示该程序执行的 F # 编译器应从那里开始。  它遵循相同的约定与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)，其中可以对此函数，传递命令行自变量，则返回的整数代码 (通常`0`)。

我们调用此函数在`square`用参数的函数`12`。  F # 编译器然后将分配的一种`square`要`int -> int`(即，采用的函数`int`并生成`int`)。  调用`printfn`是格式化的打印函数使用类似于 C 样式编程语言，它们分别对应于格式字符串中指定的参数的格式字符串，然后输出结果和新行。

## <a name="running-your-code"></a>运行代码

你可以运行该代码并查看结果，通过单击**运行**从顶级菜单，然后**启动但不调试**。  这将运行程序而不进行调试，并允许你以查看结果。

你现在应看到以下输出到控制台窗口的 Visual Studio for Mac 弹出：

```
12 squared is 144!
```

祝贺你！  你在 Visual Studio 中为 Mac 创建第一个 F # 项目、 编写 F # 函数打印调用该函数的结果并运行项目以查看部分结果。

## <a name="using-f-interactive"></a>使用 F # Interactive

最佳功能的 Visual F # 工具在 Visual Studio 中，用于 Mac 之一是 F # 交互式窗口。  它允许您通过代码发送到的进程可以在此调用该代码，并以交互方式查看结果。

若要开始使用它，突出显示`square`你代码中定义的函数。  接下来，单击**编辑**从顶级菜单。  接下来选择**选择发送至 F # Interactive**。  这在 F # 交互式窗口中执行代码。  或者，你可以右键单击所选内容，并选择**选择发送至 F # Interactive**。  你应看到 F # 交互式窗口中它的以下一起显示：

```
>

val square : x:int -> int

>
```

下面的示例演示的相同函数签名`square`函数，你此前看到当悬停在该函数。  因为`square`是现在在 F # Interactive 的过程中定义，则可以调用它时使用不同的值：

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

此程序执行的函数，请将结果绑定到的新名称`it`，并显示类型和值`it`。  请注意，必须终止与每个行`;;`。  这是如何 F # Interactive 知道函数调用完成时。  你还可以在 F # Interactive 中定义新的函数：

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

上述定义了一个新的函数， `isOdd`，此方法采用`int`和检查，以查看它是否是奇数 ！  你可以调用此函数可看到它使用不同的输入返回。  你可以调用函数调用中的函数：

```
> isOdd (square 15);;
val it : bool = true
```

你还可以使用[管道进运算符](../language-reference/symbol-and-operator-reference/index.md)管线值传输到两个函数：

```
> 15 |> square |> isOdd;;
val it : bool = true
```

管道进运算符，和的详细信息，详见更高版本的教程。

这是仅一下如何使用 F # Interactive。  若要了解详细信息，请查看[使用 F # 进行交互式编程](../tutorials/fsharp-interactive/index.md)。

## <a name="next-steps"></a>后续步骤

如果你尚未这样做，请查看[教程的 F #](../tour.md)，其中介绍了一些 F # 语言的核心功能。  它将为你提供一些 F # 的功能的概述，并提供充足的代码示例，你可以将复制到 Visual Studio for Mac 并运行。  此外还有一些有用的外部资源，你可以使用，在演示了[F # 指南](../index.md)。

## <a name="see-also"></a>请参阅
 [Visual F#](../index.md)  
 [F# 教程](../tour.md)  
 [F # 语言参考](../language-reference/index.md)  
 [类型推理](../language-reference/type-inference.md)  
 [符号和运算符参考](../language-reference/symbol-and-operator-reference/index.md)  
