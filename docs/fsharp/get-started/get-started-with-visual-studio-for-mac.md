---
title: '开始使用 F # 在 Visual Studio for Mac'
description: '了解如何使用 F # 和 Visual Studio for mac。'
ms.date: 07/03/2018
ms.openlocfilehash: 200c3a8fee072797a54d15d8989937f4cadb33e2
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874648"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>开始使用 F # 在 Visual Studio for Mac

F # 和 Visual F # 工具支持在 Visual Studio for Mac IDE。 请确保已[Visual Studio for Mac 安装](install-fsharp.md#install-f-with-visual-studio-for-mac)。

## <a name="creating-a-console-application"></a>创建控制台应用程序

Visual Studio for Mac 中最基本的项目之一是控制台应用程序。  以下是使用方法。  打开 Visual Studio for Mac 后：

1. 上**文件**菜单，依次指向**新的解决方案**。

2.  在新建项目对话框中，有 2 个不同的模板的控制台应用程序。  在另一个-> 面向.NET Framework 的.NET。  其他模板位于.NET Core-> 应用程序以.NET Core 为目标。  对于本文，任一模板应适用。

3. 在控制台应用，C# 到 F # 根据需要更改。  选择**下一步**按钮继续推进工作 ！  

4. 为项目提供一个名称，并选择所需的应用的选项。  请注意，屏幕将显示将创建的目录结构的端到预览窗格中，基于所选的选项。  

5. 单击 **“创建”**。  现在应看到在解决方案资源管理器中的 F # 项目。

## <a name="writing-your-code"></a>编写代码

通过编写一些代码首先让我们开始吧。  请确保`Program.fs`文件已打开，，然后将其内容替换为以下：

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

在前面的代码示例，一个函数`square`具有已定义接受名为输入`x`并将其本身乘以。  因为 F # 运用[类型推断](../language-reference/type-inference.md)，类型`x`不需要指定。  F # 编译器了解有效，乘法的类型，并将分配到的类型`x`具体取决于`square`调用。  如果您悬停`square`，则应查看以下信息：

```
val square: x:int -> int
```

这是所谓的函数的类型签名。  它可以读取如下:"正方形是一个函数，它采用名为整数 x，并生成一个整数"。  请注意，编译器提供`square``int`类型现在-这是因为乘法不是泛型跨*所有*类型，但而不是跨一组已关闭的类型是泛型。  F # 编译器中选取`int`在此点，但它将调整类型签名调用`square`与其他输入类型，如`float`。

另一个函数`main`，定义，则这用修饰`EntryPoint`特性告诉 F # 编译器执行该程序应从这里开始。  它遵循的约定与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)，其中的命令行参数可以传递给此函数，并返回一个整数代码 (通常`0`)。

在我们调用此函数是`square`函数的参数和`12`。  F # 编译器然后将分配的类型`square`要`int -> int`(即，一个函数，它采用`int`，并生成`int`)。  对调用`printfn`是格式化的打印函数使用类似于 C 样式编程语言，它们分别对应于格式字符串中指定的参数的格式字符串，然后将打印结果和一个新行。

## <a name="running-your-code"></a>运行代码

可以运行该代码并查看结果，通过单击**运行**从顶级菜单，然后**启动但不调试**。  这将运行程序而不进行调试，并允许您以查看结果。

现在应看到以下输出到控制台窗口的 Visual Studio for Mac:

```
12 squared is 144!
```

祝贺你！  已在 Visual Studio for Mac 中创建第一个 F # 项目、 编写的 F # 函数输出调用该函数的结果，并运行项目以查看部分结果。

## <a name="using-f-interactive"></a>使用 F # Interactive

一个最佳功能的 Visual F # 工具在 Visual Studio for Mac 是 F # 交互窗口。  它允许您以将代码发送到的进程可以在此调用该代码，并以交互方式查看结果。

若要开始使用它，突出显示`square`在代码中定义的函数。  接下来，单击**编辑**从顶级菜单。  接下来，选择**到 F # Interactive 发送选定内容**。  这在 F # 交互窗口中执行的代码。  或者，可以右键单击所选内容上，选择**到 F # Interactive 发送选定内容**。  应会看到 F # 交互窗口显示在其中以下：

```
>

val square : x:int -> int

>
```

这将显示为相同的函数签名`square`你此前看到当悬停在该函数的函数。  因为`square`是现在，在 F # 交互式过程中定义，您可以使用不同的值调用它：

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

此执行该函数时，将结果绑定到一个新名称`it`，并显示类型和值`it`。  请注意，必须终止与每个行`;;`。  这是如何 F # Interactive 知道函数调用完成时。  此外可以在 F # Interactive 中定义新函数：

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

上面的定义一个新的函数`isOdd`，此方法采用`int`和检查，以查看它是否是奇数 ！  可以调用此函数可看到它使用不同的输入返回的内容。  您可以调用函数调用中的函数：

```
> isOdd (square 15);;
val it : bool = true
```

此外可以使用[管道进运算符](../language-reference/symbol-and-operator-reference/index.md)以输送到两个函数的值：

```
> 15 |> square |> isOdd;;
val it : bool = true
```

管道进运算符和的详细信息，在更高版本的教程中介绍。

这是仅了解一下如何使用 F # Interactive。  若要了解详细信息，请查看[使用 F # 进行交互式编程](../tutorials/fsharp-interactive/index.md)。

## <a name="next-steps"></a>后续步骤

如果你尚未这样做，请查看[F # 教程](../tour.md)，其中介绍了一些 F # 语言的核心功能。  它将为您提供的一些 F # 的功能的概述，并提供足够的代码示例，你可以将复制到 Visual Studio for Mac，并运行。  此外，还有一些有用的外部资源，您可以使用，在演示[F # 指南](../index.md)。

## <a name="see-also"></a>请参阅
 [Visual F#](../index.md)  
 [F# 教程](../tour.md)  
 [F # 语言参考](../language-reference/index.md)  
 [类型推理](../language-reference/type-inference.md)  
 [符号和运算符参考](../language-reference/symbol-and-operator-reference/index.md)  
