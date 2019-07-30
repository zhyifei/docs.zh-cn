---
title: Visual Studio 中F#的入门
description: 了解如何与 Visual F# Studio 配合使用。
ms.date: 07/03/2018
ms.openlocfilehash: 24c9a81cfa61dc904db9b2213224677696d7eb9b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629769"
---
# <a name="get-started-with-f-in-visual-studio"></a>Visual Studio 中F#的入门

F#visual Studio IDE F#支持可视化工具。

首先, 确保[ F#安装了 Visual Studio ](install-fsharp.md#install-f-with-visual-studio)。

## <a name="creating-a-console-application"></a>创建控制台应用程序

在 Visual Studio 中, 最基本的项目之一就是控制台应用程序。  以下是使用方法。  打开 Visual Studio 后:

1. 在 "**文件**" 菜单上, 指向 "**新建**", 然后选择 "**项目**"。

2. 在 "新建项目" 对话框中的 "**模板**" 下, 应会看到**视觉对象F#** 。  选择此显示F#模板。

3. 选择 **.Net Core 控制台应用程序**或**控制台应用程序**。

4. 选择 "确定 **" 按钮以**创建F#项目!  现在应会在解决方案资源管理器F#中看到一个项目。

## <a name="writing-your-code"></a>编写代码

让我们首先编写一些代码。  确保该`Program.fs`文件已打开, 然后将其内容替换为以下内容:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

在上面的代码示例中, 已`square`定义了一个函数, 该函数采用`x`一个名为的输入, 并将其与自身相乘。  由于F#使用[类型推理](../language-reference/type-inference.md), 因此不需要`x`指定的类型。  编译器了解乘法的有效类型, 并根据调用方式`square`将类型分配给`x`。 F#  如果将鼠标悬停`square`在上方, 应会看到以下内容:

```fsharp
val square: x:int -> int
```

这就是所谓函数的类型签名。  如下所示:"方形是一个函数, 它采用名为 x 的整数并生成一个整数"。  请注意, 编译器`square` `int`现在提供类型, 这是因为乘法在*所有*类型中都不是泛型的, 而是在一组封闭类型中是通用的。  此时F#会选取`int`编译器, 但如果您使用`float`其他输入类型 (如) 调用`square` , 则会调整类型签名。

定义了另`main`一个函数, 该函数`EntryPoint`用特性修饰, 以告知编译器程序F#执行应在此开始。  它遵循与其他[C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)相同的约定, 可以将命令行参数传递给此函数, 并且返回整数代码 (通常`0`为)。

在此函数中, 我们使用的`square` `12`参数调用了函数。  然后F# `square` , 编译器将`int -> int`的类型分配为 (即, 采用`int`并生成的`int`函数)。  对`printfn`的调用是一个格式化的打印函数, 它使用格式字符串 (类似于 C 样式编程语言)、与在格式字符串中指定的参数相对应的参数, 然后输出结果和新行。

## <a name="running-your-code"></a>运行代码

可以通过按**Ctrl**+**F5**来运行代码并查看结果。  这会在不调试的情况下运行程序, 并允许你查看结果。  或者, 你可以在 Visual Studio 中选择 "**调试**顶级" 菜单项, 然后选择 "**启动 (不调试**)"。

现在, 你应该看到以下内容打印到了 Visual Studio 弹出的控制台窗口:

```
12 squared is 144!
```

祝贺你！  已经在 Visual Studio 中F#创建了第一个项目, 编写F#了一个函数, 该函数将调用该函数的结果, 并运行该项目以查看一些结果。

## <a name="next-steps"></a>后续步骤

如果你尚未这样做, 请查看[的F#教程](../tour.md), 其中介绍了该F#语言的一些核心功能。  它将为你概述的某些功能F#, 并提供可复制到 Visual Studio 并运行的丰富代码示例。  本指南中还提供了一些可以使用的展示外部资源。 [ F# ](../index.md)

## <a name="see-also"></a>请参阅

- [F# 教程](../tour.md)
- [F#语言参考](../language-reference/index.md)
- [类型推理](../language-reference/type-inference.md)
- [符号和运算符引用](../language-reference/symbol-and-operator-reference/index.md)
