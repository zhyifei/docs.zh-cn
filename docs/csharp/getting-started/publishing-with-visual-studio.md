---
title: "使用 Visual Studio 2017 发布 Hello World 应用程序"
description: "发布应用程序会创建运行应用程序所需的一组文件。"
keywords: ".NET, .NET Core, 控制台应用程序, 发布, 部署"
author: BillWagner
ms.author: wiwagn
ms.date: 04/17/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2b1edd9ea1c4307a4709e4fa2661c271d5f1fe91
ms.contentlocale: zh-cn
ms.lasthandoff: 08/11/2017

---

# <a name="publishing-your-hello-world-application-with-visual-studio-2017"></a>使用 Visual Studio 2017 发布 Hello World 应用程序

在[使用 Visual Studio 2017 生成 C# .NET Core Hello World 应用程序](with-visual-studio.md)中，生成了 Hello World 控制台应用程序。 在[使用 Visual Studio 2017 调试 C# Hello World 应用程序](debugging-with-visual-studio.md)中，使用 Visual Studio 调试器对其进行了测试。 至此，你已确定应用程序能够按预期运行，可以发布它以供其他用户运行了。 发布应用程序会创建运行应用程序所需的一组文件；可以通过将这些文件复制到目标计算机来进行部署。

若要发布并运行应用程序，请执行以下操作： 

1. 请确保 Visual Studio 生成的是应用程序的发布版本。 必要时，将工具栏上的生成配置设置从“调试”更改为“发布”。

   ![Visual Studio 工具栏](media/publishing-with-visual-studio/toolbar.png)

1. 右键单击“HelloWorld”项目（而不是 HelloWorld 解决方案），然后选择菜单中的“发布”。 还可以选择**“生成”**Visual Studio 主菜单中的**“发布 HelloWorld”**。

   ![Visual Studio 工具栏](media/publishing-with-visual-studio/publish1.png)

1. 在“HelloWorld”发布窗口中，会在“选择文件夹”文本框中提供默认的发布输出文件夹。 选择“发布”按钮。

   ![Visual Studio 工具栏](media/publishing-with-visual-studio/publishwindow.png)

1. 打开控制台窗口。 例如，在 Windows 任务栏的“有问题尽管问我”文本框中，输入 `Command Prompt`（或缩写 `cmd`），然后选择“命令提示符”桌面应用或按 Enter（如果已在搜索结果中选中控制台窗口），打开控制台窗口。

1. 导航到已发布的应用程序，它位于应用程序项目目录的 `bin\release\PublishOutput` 子目录中。 如下图所示，已发布的输出包括以下四个文件：

      * HelloWorld.deps.json
      * HelloWorld.dll
      * HelloWorld.pdb（对于部署是可选的）
      * HelloWorld.runtimeconfig.json

   HelloWorld.pdb 文件包含调试符号。 尽管应在需要调试应用程序的已发布版本时保存此文件，但无需将此文件与应用程序一起部署。

   ![显示已发布文件的控制台窗口](media/publishing-with-visual-studio/publishedfiles.png)

发布过程中会生成依赖于框架的部署，在此类部署中，若系统上安装了 .NET Core，已发布的应用程序可在 .NET Core 支持的任何平台上运行。 用户可以通过在控制台窗口中发出 `dotnet HelloWorld.dll` 命令来运行应用程序。

若要详细了解如何发布和部署 .NET Core 应用程序，请参阅 [.NET Core 应用程序部署](../../core/deploying/index.md)。

