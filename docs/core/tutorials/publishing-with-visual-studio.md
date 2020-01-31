---
title: 使用 Visual Studio 发布 .NET Core Hello World 应用程序
description: 发布会创建运行 .NET Core 应用程序所需的一组文件。
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: a82934fd2ea9568681a3bec82c3b15513decc926
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741564"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a>使用 Visual Studio 发布 .NET Core Hello World 应用程序

在[在 Visual Studio 中使用 .NET Core 创建 Hello World 应用程序](with-visual-studio.md)中，生成了 Hello World 控制台应用程序。 在[使用 Visual Studio 调试 Hello World 应用程序](debugging-with-visual-studio.md)中，使用 Visual Studio 调试程序测试了应用程序。 至此，你已确定应用程序能够按预期运行，可以发布它以供其他用户运行了。 发布应用程序会创建运行应用程序所需的一组文件。 若要部署文件，请将文件复制到目标计算机。

## <a name="publish-the-app"></a>发布应用

1. 请确保 Visual Studio 生成的是应用程序的发布版本。 必要时，将工具栏上的生成配置设置从“调试”  更改为“发布”  。

   ![选定发布版本的 Visual Studio 工具栏](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. 右键单击“HelloWorld”  项目（而不是 HelloWorld 解决方案），然后选择菜单中的“发布”  。 （还可以选择“生成”  主菜单中的“发布 HelloWorld”  。）

   ![Visual Studio 发布上下文菜单](media/publishing-with-visual-studio/publish-context-menu.png)
   
1. 在“选择发布目标”  页上，选择“文件夹”  ，然后选择“创建配置文件”  。

   ![在 Visual Studio 中选择发布目标](media/publishing-with-visual-studio/pick-publish-target.png)
   
1. 在“发布”  页上，选择“发布”  。

   ![Visual Studio 发布窗口](media/publishing-with-visual-studio/publish-page.png)
   
## <a name="inspect-the-files"></a>检查文件

发布过程中会生成依赖于框架的部署，在此类部署中，若系统上安装了 .NET Core，已发布的应用程序可在 .NET Core 支持的任何平台上运行。 用户可以通过双击可执行文件或从命令提示符发出 `dotnet HelloWorld.dll` 命令来运行发布的应用。

在下面的步骤中，查看由发布过程创建的文件。

1. 打开命令提示。

   打开命令提示符的一种方法是，在 Windows 任务栏上的搜索框中输入“命令提示符”  （或简写的“cmd”  ）。 选择“命令提示符”  桌面应用或按 Enter  （如果已在搜索结果中选择）。

1. 导航到已发布的应用程序，它位于应用程序项目目录的 bin\Release\netcoreapp3.1\publish  子目录中。

   ![显示已发布文件的控制台窗口](media/publishing-with-visual-studio/published-files-output.png)

   如下图所示，已发布的输出包括以下文件：

      * HelloWorld.deps.json 

         这是应用程序的运行时依赖项文件。 它定义了运行应用程序所需的 .NET Core 组件和库（包括包含该应用程序的动态链接库）。 有关详细信息，请参阅[运行时配置文件](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)。

      * HelloWorld.dll 

         这是应用程序的[依赖于框架的部署](../deploying/deploy-with-cli.md#framework-dependent-deployment)版本。 若要执行此动态链接库，请在命令提示符处输入 `dotnet HelloWorld.dll`。

      * *HelloWorld.exe*
      
         这是应用程序的[依赖于框架的可执行文件](../deploying/deploy-with-cli.md#framework-dependent-executable)版本。 若要运行该版本，请在命令提示符处输入 `HelloWorld.exe`。

      * HelloWorld.pdb  （对于部署是可选的）

         这是调试符号文件。 尽管应在需要调试应用程序的已发布版本时保存此文件，但无需将此文件与应用程序一起部署。

      * HelloWorld.runtimeconfig.json 

         这是应用程序的运行时配置文件。 它标识用于运行应用程序的 .NET Core 版本。 还可向其添加配置选项。 有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。

## <a name="additional-resources"></a>其他资源

- [.NET Core 应用程序部署](../deploying/index.md)
