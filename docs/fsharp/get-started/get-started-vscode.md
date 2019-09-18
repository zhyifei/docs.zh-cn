---
title: Visual Studio Code 中的F#入门
description: 了解如何与 Visual Studio Code F#和 ionide 入门插件套件一起使用。
ms.date: 12/23/2018
ms.openlocfilehash: 2fa0518488d37b2130aaba96028ac92dac77eb97
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082986"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Visual Studio Code 中的F#入门

你可以使用F# [ionide 入门插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)编写[Visual Studio Code](https://code.visualstudio.com) ，通过 IntelliSense 和基本代码重构获取强大的跨平台、轻型集成开发环境（IDE）体验。 请访问[Ionide.io](http://ionide.io) ，了解有关该插件的详细信息。

若要开始，请确保已[ F#正确安装和 ionide 入门插件](install-fsharp.md#install-f-with-visual-studio-code)。

> [!NOTE]
> Ionide 入门将生成 .NET Framework F#项目，而不是 dotnet core，这可能会造成跨平台兼容性问题。 如果在**Linux**或**OSX**上运行，一种更简单的入门方法是使用[命令行工具](get-started-command-line.md)。

## <a name="creating-your-first-project-with-ionide"></a>用 Ionide 入门创建您的第一个项目

若要创建新F#项目，请在新文件夹中打开 Visual Studio Code （可将其命名为任何所需的名称）。

接下来，打开命令面板（**查看 > 命令面板**）并键入以下命令：

```console
> F# new project
```

这由[伪造](https://github.com/fsharp-editing/Forge)项目提供支持。

> [!NOTE]
> 如果看不到模板选项，请在命令面板中运行以下命令来尝试刷新模板： `>F#: Refresh Project Templates`。

选择 "F#：新项目 "，按**Enter**。 这会转到下一步，即选择项目模板。

选取模板并按**Enter。** `classlib`

接下来，选择要在其中创建项目的目录。 如果将其留空，它将使用当前目录。

最后，在最后一个步骤中将项目命名为。 F#对项目名称使用[Pascal 大小写](http://c2.com/cgi/wiki?PascalCase)。 本文使用`ClassLibraryDemo`作为名称。 输入要用于项目的名称后，按**Enter**。

如果执行了上一步，应会看到左侧的 "Visual Studio Code" 工作区显示如下：

1. F#项目本身，位于文件夹的`ClassLibraryDemo`下方。
2. 用于通过[`Paket`](https://fsprojects.github.io/Paket/)添加包的正确目录结构。
3. 使用[`FAKE`](https://fsharp.github.io/FAKE/)的跨平台生成脚本。
4. 可`paket.exe`执行的可提取包和解析依赖项的可执行文件。
5. 如果`.gitignore`要将此项目添加到基于 Git 的源代码管理，则为文件。

## <a name="writing-some-code"></a>编写一些代码

打开*ClassLibraryDemo*文件夹。  应会看到以下文件：

1. `ClassLibraryDemo.fs`，具有F#定义了类的实现文件。
2. `ClassLibraryDemo.fsproj`，用于F#生成此项目的项目文件。
3. `Script.fsx`，加载F#源文件的脚本文件。
4. `paket.references`，用于指定项目依赖项的 Paket 文件。

打开`Script.fsx`，并在它的末尾添加以下代码：

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

此函数将字转换为[Pig 拉丁](https://en.wikipedia.org/wiki/Pig_Latin)形式的单词。 下一步是使用F#交互式（fsi.exe）对其进行评估。

突出显示整个函数（长度应为11行）。 突出显示后，请按住**Alt**键，然后按**Enter**。 你会注意到下面的窗口弹出窗口，它应显示如下所示的内容：

![Ionide 入门的F#交互式输出示例](./media/getting-started-vscode/vscode-fsi.png)

这三个方面：

1. 它启动了 FSI.EXE 进程。
2. 它发送了你在 FSI.EXE 过程中突出显示的代码。
3. FSI.EXE 进程对你发送的代码进行评估。

由于发送的内容是一个[函数](../language-reference/functions/index.md)，因此你现在可以使用 fsi.exe 调用该函数！ 在交互窗口中，键入以下内容：

```fsharp
toPigLatin "banana";;
```

你应看到以下结果：

```fsharp
val it : string = "ananabay"
```

现在，让我们尝试使用元音作为第一个字母。 输入以下内容：

```fsharp
toPigLatin "apple";;
```

你应看到以下结果：

```fsharp
val it : string = "appleyay"
```

函数看起来像预期那样工作。 恭喜，你只是在 Visual Studio Code F#编写了第一个函数，并在 fsi.exe 中对其进行了评估！

> [!NOTE]
> 正如您可能已经注意到的，FSI.EXE 中的行`;;`以结尾。 这是因为 FSI.EXE 允许输入多个行。 结束`;;`时，fsi.exe 知道代码的完成时间。

## <a name="explaining-the-code"></a>解释代码

如果你不确定代码实际执行的操作，以下是一个循序渐进的步骤。

正如您所看到`toPigLatin`的，它是一个将单词作为其输入并将其转换为 Pig 的单词的表示形式的函数。 此操作的规则如下所示：

如果单词中的第一个字符以元音开头，则将 "yay" 添加到单词的结尾。 如果它不以元音开头，请将第一个字符移动到单词末尾，并向其添加 "ay"。

您可能已注意到 FSI.EXE 中的以下内容：

```fsharp
val toPigLatin : word:string -> string
```

这表明`toPigLatin`函数`string`作为输入（称为`word`），并返回另一个`string`。 这称为[函数的类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/)，这是理解F# F#代码的关键部分。 如果将鼠标悬停在 Visual Studio Code 的函数上，也会注意到这一点。

在函数体中，你会注意到两个不同的部分：

1. 一个名`isVowel`为的内部函数，通过检查给定字符（`c`）是否通过[模式匹配](../language-reference/pattern-matching.md)与提供的模式之一匹配来确定是否为元音：

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. 一个[`if..then..else`](../language-reference/conditional-expressions-if-then-else.md)表达式，用于检查第一个字符是否为元音，并根据第一个字符是否为元音，从输入字符中构造返回值：

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

这样的流`toPigLatin`就是：

检查输入词的第一个字符是否为元音。 如果是，请将 "yay" 附加到单词的结尾。 否则，将第一个字符移动到单词末尾，并向其添加 "ay"。

最后要注意的一点是：没有从函数返回的显式说明，这不同于其他许多语言。 这是因为F#基于表达式，而函数主体中的最后一个表达式是返回值。 由于`if..then..else`本身是一个表达式，因此将根据输入`then`值返回块体`else`或块体。

## <a name="moving-your-script-code-into-the-implementation-file"></a>将脚本代码移到实现文件中

本文前面的部分演示了编写F#代码的常见第一步：编写一个初始函数并使用 fsi.exe 以交互方式执行该函数。 这称为 "复制驱动开发"，其中，"[复制](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)" 代表 "读取-评估-打印循环"。 这是一种非常好的方法，可让你体验功能。

复制驱动开发的下一步是将工作代码移到F#实现文件中。 然后， F#编译器可以将它编译为可执行的程序集。

若要开始， `ClassLibraryDemo.fs`请打开。  你会注意到，其中已存在某些代码。 继续并删除类定义，但请确保将[`namespace`](../language-reference/namespaces.md)声明保留在顶部。

接下来，创建一个[`module`](../language-reference/modules.md)名`PigLatin`为的新`toPigLatin` ，并将函数复制到其中：

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

接下来，再次`Script.fsx`打开该文件并删除整个`toPigLatin`函数，但请确保在该文件中保留以下两行：

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

选择两行文本，并按 Alt + Enter 在 FSI.EXE 中执行这些行。 这会将 Pig 拉丁语库的内容加载到 fsi.exe 进程和`open` `ClassLibraryDemo`命名空间，以便您可以访问该功能。

接下来，在 fsi.exe 窗口中，调用函数，该`PigLatin`函数包含之前定义的模块：

```console
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

成功！ 您将获得与以前相同的结果，但现在是F#从实现文件加载的。 此处的主要差别在于， F#源文件编译成可在任意位置执行的程序集，而不只是在 fsi.exe 中执行。

## <a name="summary"></a>总结

本文介绍了以下内容：

1. 如何设置 Ionide 入门 Visual Studio Code。
2. 如何创建具有 Ionide 入门的F#第一个项目。
3. 如何使用F#脚本编写 ionide 入门中的第F#一个函数，然后在 fsi.exe 中执行它。
4. 如何将脚本代码迁移到F#源，然后从 fsi.exe 调用该代码。

现在，你可以使用 Visual Studio Code 和 Ionide 入门F#编写更多的代码。

## <a name="troubleshooting"></a>疑难解答

可以通过以下几种方法来解决你可能遇到的某些问题：

1. 若要获取 Ionide 入门的代码编辑功能，需要F#将文件保存到磁盘，并保存在 Visual Studio Code 工作区中打开的文件夹内。
2. 如果已对系统进行了更改或安装了 Visual Studio Code 的 Ionide 入门必备组件，请 Visual Studio Code 重新启动。
3. 检查是否可以从命令行F#使用编译器F#和交互式路径，而无需使用完全限定的路径。 为此，你可以在`fsc`命令行中键入F#编译器， `fsi`或`fsharpi`在 Windows 上的 Visual F# tools 和 Mac/Linux 上分别键入。
4. 如果项目目录中包含无效字符，则 Ionide 入门可能不起作用。  如果出现这种情况，请重命名项目目录。
5. 如果 Ionide 入门命令均不起作用，请检查你的[Visual Studio Code 键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)，以确定你是否会意外地替代它们。
6. 如果计算机上的 ionide 入门中断，并且上述任何内容都不能解决问题，请尝试删除`ionide-fsharp`计算机上的目录，并重新安装插件套件。

Ionide 入门是由F#社区成员构建和维护的开源项目。 请在[ionide 入门-VSCode 上报告问题并随意参与：Fsharp.core GitHub 存储](https://github.com/ionide/ionide-vscode-fsharp)库。

如果你有要报告的问题，请按照[说明来获取报告问题时要使用的日志](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)。

你还可以在[Ionide 入门 Gitter 通道](https://gitter.im/ionide/ionide-project)中请求 ionide 入门开发人员F#和社区提供进一步的帮助。

## <a name="next-steps"></a>后续步骤

若要了解有关F#语言的详细信息，请参阅[的F#教程](../tour.md)。
