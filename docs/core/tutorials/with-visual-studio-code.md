---
title: "要开始使用 C# 和 Visual Studio 代码-C# 指南"
description: "了解如何使用 Visual Studio Code 创建和调试首个 C# .NET Core 应用。"
keywords: "C#, 入门, 获取, 安装, Visual Studio Code, 跨平台"
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.openlocfilehash: 3a9de689946507e4b6d89f684461d65049b3375a
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-c-and-visual-studio-code"></a>C# 和 Visual Studio Code 入门

.NET Core 提供了快速运行的模块化平台，用于创建在 Windows、Linux 和 macOS 上运行的应用程序。 带 C# 扩展的 Visual Studio Code 提供功能强大的编辑体验，完全支持 C# IntelliSense（智能代码填充）和调试。

## <a name="prerequisites"></a>先决条件

1. 安装 [Visual Studio Code](https://code.visualstudio.com/)。
2. 获取 [.NET Core SDK](https://www.microsoft.com/net/download/core)。
3. 从 Visual Studio Code 应用商店安装 [C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。

## <a name="hello-world"></a>Hello World

让我们从 .NET Core 上的一个简单“Hello World”程序入手：

1. 打开项目：

    * 打开 Visual Studio Code。
    * 依次单击左侧菜单上的“资源管理器”图标和**“打开文件夹”**。
    * 选择**文件** > **打开文件夹**想从主菜单打开文件夹 C# 项目中并单击**选择文件夹**。 对于我们的示例，我们要为我们名为的项目中创建一个文件夹*HelloWorld*。

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. 初始化 C# 项目：
    * 通过选择从 Visual Studio Code 打开集成终端**视图** > **集成终端**从主菜单。
    * 在终端窗口中，键入“`dotnet new console`”。
    * 此命令创建`Program.cs`在文件夹中，已写入，以及名为的 C# 项目文件的简单"Hello World"程序文件`HelloWorld.csproj`。

      ![dotnet new 命令](media/with-visual-studio-code/dotnetnew.png)

3. 解析生成资产：

    * 有关**.NET 核心 1.x**，类型`dotnet restore`。 运行 `dotnet restore` 后，便有权访问生成项目所需的 .NET Core 包。

      ![dotnet restore 命令](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. 运行“Hello World”程序：

    * 键入 `dotnet run`。 

      ![dotnet run 命令](media/with-visual-studio-code/dotnetrun.png)

还可以观看简短的视频教程，以获取更多关于在 [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core)、[macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 或 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) 上进行安装的帮助。

## <a name="debug"></a>调试

1. 单击打开 *Program.cs*。 在 Visual Studio 代码，请打开一个 C# 文件的第一个时间[OmniSharp](http://www.omnisharp.net/)在编辑器中加载。

    ![打开 Program.cs 文件](media/with-visual-studio-code/opencs.png)

2. Visual Studio Code 应提示你添加缺少的资产，以生成和调试你的应用程序。 选择**“是”**。 

    ![提示添加缺少的资产](media/with-visual-studio-code/missing-assets.png)

3. 若要打开调试视图，请单击左侧菜单上的“调试”图标。

    ![打开“调试”选项卡](media/with-visual-studio-code/opendebug.png)

4. 找到窗格最上面的绿色箭头。 请确保已选择旁边下拉列表中的“`.NET Core Launch (console)`”。

    ![选择 .NET Core](media/with-visual-studio-code/selectcore.png)

5. 将断点添加到你的项目中，通过单击**编辑器边距**，它是在编辑器中，第 9 行旁边的行号左侧空格。

    ![设置断点](media/with-visual-studio-code/setbreakpoint.png)

6. 若要开始调试时，选择<kbd>F5</kbd>或绿色箭头。 在到达你在上一步中设置的断点时，调试器会停止执行程序。
    * 调试时，你可以在左窗格的顶部中查看你的本地变量，或使用调试控制台。

    ![运行和调试](media/with-visual-studio-code/rundebug.png)

7. 选择最上面的绿色箭头以继续调试，或选择最上面的红色方块以停止调试。

> [!TIP] 
> 若要详细了解如何使用 OmniSharp 在 Visual Studio Code 中进行 .NET Core 调试，以及相关的疑难解答提示，请参阅[有关设置 .NET Core 调试器的说明](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。

## <a name="see-also"></a>请参阅
[设置 Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)   
[在 Visual Studio Code 中进行调试](https://code.visualstudio.com/Docs/editor/debugging)
