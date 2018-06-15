---
title: '要开始使用 Visual Studio 代码中的 F #'
description: '了解如何使用 F # 使用 Visual Studio Code 和 Ionide 插件套件。'
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728623"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>要开始使用 Visual Studio 代码中的 F #

你可以编写 F # [Visual Studio Code](https://code.visualstudio.com)与[Ionide 插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)，若要获取与 IntelliSense 和基本代码的极佳跨平台的轻型集成开发环境 (IDE) 体验重构。 请访问[Ionide.io](http://ionide.io)若要了解有关该插件套件的详细信息。

## <a name="prerequisites"></a>系统必备

你必须具有[安装 git](https://git-scm.com/download)并在你的路径，以使上可用的项目模板中 Ionide 使用。 你可以验证它正确安装了，通过键入`git --version`在命令提示符处并按**Enter**。

### <a name="macostabmacos"></a>[macOS](#tab/macos)

Ionide 使用[Mono](http://www.mono-project.com)。 在 macOS 上安装 Mono 的最简单方法是通过 Homebrew。 只需在你的终端键入以下内容：

```
brew install mono
```

你还必须安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

在 Linux 上 Ionide 还使用[Mono](https://www.mono-project.com)。 如果要在 Debian 或 Ubuntu 上，你可以使用以下各项：

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

你还必须安装[.NET Core SDK](https://www.microsoft.com/net/download)。

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

如果你在 Windows 上，你必须[使用 F # 支持安装 Visual Studio](get-started-visual-studio.md#installing-f)。 这将安装所有必需的组件来编写、 编译和执行 F # 代码。

你还必须安装[.NET Core SDK](https://www.microsoft.com/net/download/)。

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a>安装 Visual Studio Code 和 Ionide 插件

你可以安装从 Visual Studio Code [code.visualstudio.com](https://code.visualstudio.com)网站。

接下来，请单击扩展图标和"Ionide"搜索:

F # 中，Visual Studio Code 中支持所需的唯一插件[Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。 但是，你还可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)获取[虚设](https://fsharp.github.io/FAKE/)支持和[Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[Paket](https://fsprojects.github.io/Paket/)支持。 但是，伪造 Paket 以及其他 F # 社区工具来生成项目并管理依赖项，分别。

## <a name="creating-your-first-project-with-ionide"></a>使用 Ionide 创建第一个项目

若要创建新的 F # 项目，打开 （你可以将其任意命名） 的新文件夹中的 Visual Studio Code。

接下来，打开命令调色板 (**视图 > 命令调色板**) 并键入以下命令：

```
> F# new project
```

这由提供支持[伪造](https://github.com/fsharp-editing/Forge)项目。

> [!NOTE]
如果你未看到模板选项，请尝试通过在命令控制板中运行以下命令刷新模板： `>F#: Refresh Project Templates`。

选择"F #:: 新项目"通过点击**Enter**。 将你转到下一步，即对于选择的项目模板。

选取`classlib`模板和命中**Enter**。

接下来，选择一个目录来创建的项目中。 如果你将其留空，则使用当前目录。

最后，命名你的项目中的最后一步。 F # 使用[Pascal case](http://c2.com/cgi/wiki?PascalCase)项目名称。 本文章将使用`ClassLibraryDemo`作为名称。 已输入所需为你的项目的名称后, 命中**Enter**。

如果您遵循上一步，你会获得 Visual Studio 代码上的工作区的左侧显示替换为以下内容：

1. F # 项目本身，底层`ClassLibraryDemo`文件夹。
2. 添加通过包的正确的目录结构[ `Paket` ](https://fsprojects.github.io/Paket/)。
3. 跨平台生成脚本[ `FAKE` ](https://fsharp.github.io/FAKE/)。
4. `paket.exe`可以提取包并为你解决依赖项的可执行文件。
5. A`.gitignore`文件如果你想要将此项目添加到基于 Git 的源控制。

## <a name="writing-some-code"></a>编写一些代码

打开*ClassLibraryDemo*文件夹。  你应看到以下文件：

1. `ClassLibraryDemo.fs`定义的类具有的 F # 实现文件。
2. `ClassLibraryDemo.fsproj`用于生成此项目的 F # 项目文件。
3. `Script.fsx`加载的源文件的 F # 脚本文件。
4. `paket.references`指定项目依赖项的 Paket 文件。

打开`Script.fsx`，并在末尾添加以下代码：

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

此函数将一个单词转换为一种形式的[Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)。 下一步是评估使用 F # 交互式 (FSI)。

突出显示整个函数 （它应为长达 11 行）。 一旦将突出显示，保存**Alt**密钥并点击**Enter**。 你会注意到下面，弹出一个窗口，并且它应显示类似如下内容：

![与 Ionide F # Interactive 输出的示例](media/getting-started-vscode/vscode-fsi.png)

这未三项操作：

1. 它启动了 FSI 进程。
2. 它通过 FSI 过程发送您突出显示的代码。
3. FSI 过程评估通过发送的代码。

因为通过发送[函数](../language-reference/functions/index.md)，现在，您可以调用该函数使用 FSI ！ 在交互式窗口中，键入以下命令：

```fsharp
toPigLatin "banana";;
```

你应看到以下结果：

```fsharp
val it : string = "ananabay"
```

现在，让我们以作为第一个字母元音并重试。 输入以下内容：

```fsharp
toPigLatin "apple";;
```

你应看到以下结果：

```fsharp
val it : string = "appleyay"
```

该函数似乎按预期方式工作。 祝贺你，你只需在 Visual Studio 代码中编写 F # 第一个函数，因此它使用评估 FSI ！

>[!NOTE]
你可能已经注意到，用来终止 FSI 中行`;;`。 这是因为 FSI 可以输入多行。 `;;`末尾允许 FSI 知道完成代码。

## <a name="explaining-the-code"></a>说明代码

如果你不确定的代码实际如何操作，以下是分步向导。

如你所见，`toPigLatin`是一个函数，它接受将单词设置为其输入，并将其转换为该单词的 Pig Latin 表示形式。 此规则如下所示：

如果在 word 中的第一个字符以元音开头，添加到单词末尾的"yay"。 如果它不会开始元音，移到单词末尾的第一个字符，并将"在"添加到它。

你可能已经注意到 FSI 中的以下：

```fsharp
val toPigLatin : word:string -> string
```

这表明`toPigLatin`是采用一个函数`string`作为输入 (调用`word`)，并返回另一个`string`。 这称为[函数类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/)，F # 的关键在于了解 F # 代码的基础部分。 如果将鼠标悬停在 Visual Studio 代码中的函数，将还会发现此情况。

在函数正文中，你会注意到两个不同的部分：

1. 内部函数调用`isVowel`，如果给定的字符，它确定 (`c`) 元音方法是检查如果它通过提供的模式之一匹配的[模式匹配](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md)检查是否第一个字符为元音的元素，并基于 if 的第一个字符构造外的输入字符的返回值的表达式是元音还是失败：

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

流`toPigLatin`因此它也是：

检查输入的单词的第一个字符是否元音。 如果是，附加到单词末尾的"yay"。 否则为移动到单词末尾的第一个字符并将"在"添加到它。

没有最后一件要有关此注意的事情： 没有返回从函数，不同于很多其他语言有无显式指令。 这是因为 F # 是基于表达式的和的函数体中的最后一个表达式是返回值。 因为`if..then..else`本身是一个表达式，正文`then`块或正文`else`块将根据输入的值返回。

## <a name="moving-your-script-code-into-the-implementation-file"></a>将你的脚本代码移动到实现文件

在本文前面部分所示编写 F # 代码的常见第一步： 编写初始函数，然后以交互方式使用 FSI 执行它。 这称为 REPL 驱动开发，其中[REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)代表"读取-计算-打印循环"。 它是在将某产品投入使用之前，尝试使用功能的好方法。

REPL 驱动的开发的下一步是将运行的代码移到 F # 实现文件。 它可以然后编译器编译的 F # 到可执行的程序集中。

若要开始，打开`ClassLibraryDemo.fs`。  你会注意到某些代码已在存在。 请继续并删除类定义中，但请确保让[ `namespace` ](../language-reference/namespaces.md)顶部的声明。

接下来，创建一个新[ `module` ](../language-reference/modules.md)调用`PigLatin`和复制`toPigLatin`函数导入到它在这种：

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

接下来，打开`Script.fsx`再次，文件并删除整个`toPigLatin`起作用，但请确保在文件中保留以下两行：

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

FSI 编写脚本来加载需要的第一行`ClassLibraryDemo.fs`。 第二行是一种便于： 省略它是可选的但你将需要键入`open ClassLibraryDemo`FSI 窗口如果你想要使中`ToPigLatin`纳入范围的模块。

接下来，在 FSI 窗口中，调用具有的函数`PigLatin`前面定义的模块：

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

成功！ 获取与之前相同的结果，但现在从 F # 实现文件加载。 此处的主要区别是，将 F # 源代码文件编译成可以不只是在 FSI 中任意位置，执行的程序集。

## <a name="summary"></a>总结

在本文中，你已了解：

1. 如何设置与 Ionide 的 Visual Studio 代码。
2. 如何使用 Ionide 创建第一个 F # 项目。
3. 如何使用 F # 脚本在 Ionide 中编写 F # 第一个函数，则在 FSI 中执行它。
4. 如何将你的脚本代码迁移到 F # 源代码，然后从 FSI 调用该代码。

你现在正在配备编写更多的 F # 代码使用 Visual Studio Code 和 Ionide。

## <a name="troubleshooting"></a>疑难解答

以下是可解决可能会遇到某些问题的几个方法：

1. 若要获取的代码编辑功能 Ionide，F # 文件需要保存到磁盘，以及在 Visual Studio Code 工作区中处于打开状态的文件夹内。
2. 如果你对系统进行更改或使用打开的 Visual Studio Code 安装 Ionide 系统必备组件，重新启动 Visual Studio Code。
3. 检查可使用 F # 编译器和 F # interactive 中没有的完全限定路径的命令行。 你可以通过键入来实现`fsc`F # 编译器的命令行中和`fsi`或`fsharpi`Visual F # 工具在 Windows 和 Mac/Linux 上的 Mono 上分别。
4. 如果你已在你项目目录中的无效字符，Ionide 可能无法工作。  如果出现这种情况，重命名你的项目目录。
5. 如果使用无 Ionide 命令，请检查你[Visual Studio Code 键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)若要查看如果你要重写这些意外。
6. 如果在您的计算机上中断 Ionide 和上述任何具有固定你的问题，请尝试删除`ionide-fsharp`目录在你的计算机上，然后重新安装的插件套件。

Ionide 是开放源代码项目生成和维护由 F # 社区的成员。 请报告问题并随意在参与[Ionide VSCode: FSharp GitHub 存储库](https://github.com/ionide/ionide-vscode-fsharp)。

如果你有报告的问题，请遵循[获取日志报告问题时要使用的说明](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)。

你还可以请求更多帮助从 Ionide 开发人员和 F # 中的社区[Ionide Gitter 通道](https://gitter.im/ionide/ionide-project)。

## <a name="next-steps"></a>后续步骤

若要了解有关 F # 和语言的功能的详细信息，请查看[教程的 F #](../tour.md)。
