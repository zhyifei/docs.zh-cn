---
title: '要开始使用 Visual Studio 中的 F #'
description: '了解如何使用 Visual Studio 中使用 F #。'
ms.date: 02/13/2017
ms.openlocfilehash: 22fbe8086ec133605e1d9b4b28e524fe2ed8ac28
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728529"
---
# <a name="get-started-with-f-in-visual-studio"></a>要开始使用 Visual Studio 中的 F #

在 Visual Studio IDE 中支持 F # 和 Visual F # 工具。  若要开始，你应[下载 Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)，如果你尚未。  本文章将使用 Visual Studio 2017 Community Edition，但你可以使用 F # 与所选的版本。

## <a name="installing-f"></a>正在安装 F # #

如果您正在第一次下载 Visual Studio，它将首先安装 Visual Studio 安装程序。  从安装程序安装任何版本的 Visual Studio 2017。 如果你已安装，请单击**修改**。

接下来，你将看到一份工作负荷。 你可以安装 F # 通过任何以下工作负荷：

|工作负荷|操作|
|--------|------|
| .NET Core 跨平台开发 | 默认情况下不安装任何操作-F # |
| ASP.NET 和 Web 开发 | 默认情况下不安装任何操作-F # |
| Azure 开发 | 默认情况下不安装任何操作-F # |
| 使用 .NET 的移动开发 | 默认情况下不安装任何操作-F # |
| 数据科学和分析应用程序 | 默认情况下不安装任何操作-F # |
| .NET 桌面开发 | 选择**F # 桌面语言支持**从右侧 |
| 数据存储和处理 | 选择**F # 桌面语言支持**从右侧 |

接下来，单击**修改**的右下方中。  这将安装您选择的所有内容。  随后可打开 Visual Studio 2017 使用 F # 语言支持通过单击**启动**。

## <a name="creating-a-console-application"></a>创建一个控制台应用程序

Visual Studio 中最基本的项目之一是控制台应用程序。  以下是使用方法。  打开 Visual Studio 后：

1. 上**文件**菜单上，指向**新建**，然后选择**项目**。

2.  在新建项目对话框中下,**模板**，你应该会看到**Visual F #**。  选择此选项可显示 F # 模板。

3. 选择 **.NET Core 控制台应用程序**或**控制台应用程序**。

3. 选择**好**按钮以创建 F # 项目 ！  你现在应该看到解决方案资源管理器中的 F # 项目。

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

你可以运行该代码并查看结果，通过按**ctrl-f5**。  这将运行程序而不进行调试，并允许你以查看结果。  或者，你可以选择**调试**顶级菜单项在 Visual Studio 中，然后选择**启动但不调试**。

你现在应看到以下输出到控制台窗口的 Visual Studio 弹出：

```
12 squared is 144!
```

祝贺你！  你在 Visual Studio 中创建第一个 F # 项目、 编写 F # 函数打印调用该函数的结果并运行项目以查看部分结果。

## <a name="next-steps"></a>后续步骤

如果你尚未这样做，请查看[教程的 F #](../tour.md)，其中介绍了一些 F # 语言的核心功能。  它将为你提供一些 F # 的功能的概述，并提供充足的代码示例，你可以将复制到 Visual Studio 并运行。  此外还有一些有用的外部资源，你可以使用，在演示了[F # 指南](../index.md)。

## <a name="see-also"></a>请参阅
 [Visual F#](index.md)  
 [F# 教程](../tour.md)  
 [F # 语言参考](../language-reference/index.md)  
 [类型推理](../language-reference/type-inference.md)  
 [符号和运算符参考](../language-reference/symbol-and-operator-reference/index.md)  
