---
title: 在 Visual Studio 中使用 .NET Standard 库
description: 生成一个 .NET Core 应用程序，该应用程序使用 Visual Studio 2019 调用另一个类库的成员。
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920456"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a>在 Visual Studio 中使用 .NET Standard 库

创建 .NET Standard 类库、测试并生成库的发行版本后，下一步就是使其可供调用方使用。 可以通过以下两种方式执行此操作：

- 如果库将供一个解决方案使用（例如，如果它是一个大型应用程序中的组件），可以将其以项目的形式添加到解决方案中。
- 如果类库将公开发布，你可以以 NuGet 包的形式分发。

在本教程中，你将了解：
> [!div class="checklist"]
>
> - 向解决方案中添加引用 .NET Standard 库项目的控制台应用。
> - 创建包含 .NET Standard 库项目的 NuGet 包。

## <a name="add-a-console-app-to-your-solution"></a>向解决方案添加控制台应用

就像[在 Visual Studio 中测试 .NET Standard 库](testing-library-with-visual-studio.md)所述的将单元测试和类库添加到同一解决方案中一样，可以将应用程序添加到同一解决方案中。 例如，可在控制台应用程序中使用类库，此应用程序将提示用户输入字符串，并报告第一个字符是否为大写：

1. 打开在[在 Visual Studio 中生成 .NET Standard 库](library-with-visual-studio.md)一文中创建的 `ClassLibraryProjects` 解决方案。

1. 将名为“ShowCase”的新 .NET Core 控制台应用程序添加到解决方案。

   1. 在“解决方案资源管理器”  中右键单击解决方案并选择“添加”   > “新建项目”  。

   1. 在“创建新项目”  页面，在搜索框中输入“控制台”  。 从“语言”列表中选择“C#”  或“Visual Basic”  ，然后从“平台”列表中选择“所有平台”  。 选择“控制台应用 (.NET Core)”  模板，然后选择“下一步”  。

   1. 在“配置新项目”  页面，在“项目名称”  框中输入“ShowCase”  。 然后，选择“创建”  。

1. 在“**解决方案资源管理器**”中，右键单击“**ShowCase**”项目，在上下文菜单中选择“**设为启动项目**”。

   ![Visual Studio 中用于设置启动项目的项目上下文菜单](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. 项目一开始无权访问类库。 若要允许项目调用类库中的方法，可以创建对该类库的引用。 在“解决方案资源管理器”  中，右键单击 `ShowCase` 项目的“依赖项”  节点，并选择“添加引用”  。

   ![在 Visual Studio 中添加引用上下文菜单](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. 在“引用管理器”  对话框中，选择类库项目“StringLibrary”  ，然后选择“确定”  按钮。

   ![选择了“StringLibrary”的“引用管理器”对话框](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. 在“Program.cs”  或“Program.vb”  文件的代码窗口中，将所有代码替换为以下代码：

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   该代码使用 `row` 变量来维护写入到控制台窗口的数据行数计数。 如果大于或等于 25，该代码将清除控制台窗口，并向用户显示一条消息。

   该程序会提示用户输入字符串。 它会指明字符串是否以大写字符开头。 如果用户没有输入字符串就按 Enter 键，那么应用程序会终止，控制台窗口会关闭。

1. 必要时，将工具栏更改为编译 `ShowCase` 项目的“调试”  版本。 选择“ShowCase”  按钮上的绿色箭头，编译并运行程序。

   ![Visual Studio 中显示“调试”按钮的项目工具栏](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

可以按照[使用 Visual Studio 调试 C# 或 Visual Basic .NET Core Hello World 应用程序](debugging-with-visual-studio.md)和[使用 Visual Studio 发布 .NET Core Hello World 应用程序](publishing-with-visual-studio.md)中的步骤操作，调试并发布使用此库的应用程序。

## <a name="create-a-nuget-package"></a>创建 NuGet 包

可采用 NuGet 包的形式发布类库，让类库可供更多调用方使用。 Visual Studio 不支持创建 NuGet 包。 若要创建一个，需要使用 .NET Core CLI 命令：

1. 打开控制台窗口。

   例如，在 Windows 任务栏的搜索框中输入“命令提示符”  。 选择“命令提示符”  桌面应用或按 Enter  （如果已在搜索结果中选择）。

1. 转到类库的项目目录。 此目录包含源代码和项目文件 StringLibrary.csproj  或 StringLibrary.vbproj  。

1. 运行 [dotnet pack](../tools/dotnet-pack.md) 命令，以生成带 .nupkg  扩展的包：

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > 如果路径中没有包含 dotnet.exe  的目录，可以通过在控制台窗口中输入 `where dotnet.exe` 来找到它的位置。

若要详细了解如何创建 NuGet 包，请参阅[如何使用 .NET Core CLI 创建 NuGet 包](../deploying/creating-nuget-packages.md)。
