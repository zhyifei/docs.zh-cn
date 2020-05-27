---
title: 在 Visual Studio 中使用 .NET Core 创建 Hello World 应用程序
description: 了解如何使用 Visual Studio 在 C# 或 Visual Basic 中创建第一个 .NET Core 控制台应用程序。
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 738fc49a820c3c5d94fb35c1bf7a8b718ed75cb3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394829"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a>教程：在 Visual Studio 2019 中创建第一个 .NET Core 控制台应用程序

本文将逐步介绍如何在 Visual Studio 2019 中创建和运行 Hello World .NET Core 控制台应用程序。 通常使用 Hello World 应用程序向初学者介绍新的编程语言。 此程序只在屏幕上显示短语“Hello World!” 。

## <a name="prerequisites"></a>先决条件

- 安装了具有“.NET Core 跨平台开发”  工作负载的 [Visual Studio 2019 版本 16.4 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。 选择此工作负载时，将自动安装 .NET Core 3.1 SDK。

有关详细信息，请参阅[安装 .NET Core SDK](../install/sdk.md?pivots=os-windows) 一文中的[在 Visual Studio 中安装](../install/sdk.md?pivots=os-windows#install-with-visual-studio)部分。

## <a name="create-the-app"></a>创建应用

以下说明创建一个简单的 Hello World 控制台应用程序：

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

1. 打开 Visual Studio 2019。

1. 创建一个名为“HelloWorld”的新 C# .NET Core 控制台应用项目。

   1. 在“开始”窗口上，选择“创建新项目”  。

      ![在 Visual Studio“启动”窗口选择“创建新项目”按钮](./media/with-visual-studio/start-window.png)

   1. 在“创建新项目”  页面，在搜索框中输入“控制台”  。 接下来，从“语言”列表中选择“C#”  ，然后从“平台”列表中选择“所有平台”  。 选择“控制台应用 (.NET Core)”  模板，然后选择“下一步”  。

      ![使用所选筛选器创建新项目窗口](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > 如果看不到 .NET Core 模板，则可能缺少安装所需的工作负载。 在“找不到所需内容?”  消息下，选择“安装更多工具和功能”  链接。 Visual Studio 安装程序随即打开。 确保安装了“.NET Core 跨平台开发”  工作负载。

   1. 在“配置新项目”  页面，在“项目名称”  框中输入“HelloWorld”  。 然后，选择“创建”  。

      ![为新项目窗口配置“项目名称”、“位置”和“解决方案名称”字段](./media/with-visual-studio/configure-new-project.png)

   C# .NET Core 控制台应用程序模板会自动定义类 `Program` 和一个需要将 <xref:System.String> 数组用作自变量的方法 `Main`。 `Main` 是应用程序入口点，同时也是在应用程序启动时由运行时自动调用的方法。 *args* 数组中包含在应用程序启动时提供的所有命令行自变量。

   ![Visual Studio 和新建的 HelloWorld 项目](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. 打开 Visual Studio 2019。

1. 创建一个名为“HelloWorld”的新 Visual Basic .NET Core 控制台应用项目。

   1. 在“开始”窗口上，选择“创建新项目”  。

      ![在 Visual Studio“启动”窗口选择“创建新项目”按钮](./media/with-visual-studio/start-window.png)

   1. 在“创建新项目”  页面，在搜索框中输入“控制台”  。 接下来，从“语言”列表中选择“Visual Basic”  ，然后从“平台”列表中选择“所有平台”  。 选择“控制台应用 (.NET Core)”  模板，然后选择“下一步”  。

      ![为“控制台应用(.NET Framework)”选择 Visual Basic 模板](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > 如果看不到 .NET Core 模板，则可能缺少安装所需的工作负载。 在“找不到所需内容?”  消息下，选择“安装更多工具和功能”  链接。 Visual Studio 安装程序随即打开。 确保安装了“.NET Core 跨平台开发”  工作负载。

   1. 在“配置新项目”  页面，在“项目名称”  框中输入“HelloWorld”  。 然后，选择“创建”  。

   .NET Core 控制台应用程序模板会自动定义类 `Program` 和一个需要将 <xref:System.String> 数组用作自变量的方法 `Main`。 `Main` 是应用程序入口点，同时也是在应用程序启动时由运行时自动调用的方法。 `args` 参数中包含在应用程序启动时提供的所有命令行自变量。

   ![Visual Studio 和新建的 HelloWorld 项目](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   用于创建简单的“Hello World”应用程序的模板。 它通过调用 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 方法在控制台窗口中 显示文本字符串“Hello World!”。

## <a name="run-the-app"></a>运行应用

1. 若要运行程序，请在工具栏上选择“HelloWorld”  ，或按 F5  。

   ![已选择“HelloWorld 运行”按钮的 Visual Studio 工具栏](./media/with-visual-studio/run-program.png)

   此时将打开在屏幕上显示文本“Hello World!” 并附带一些 Visual Studio 调试信息的控制台窗口。

   ![控制台窗口，其中显示 Hello World Press any key to continue](./media/with-visual-studio/hello-world-console.png)

1. 按任意键关闭控制台窗口。

## <a name="enhance-the-app"></a>增强应用

改进应用程序，提示用户输入名字，并将其与日期和时间一同显示。 以下说明再次修改并运行应用：

# <a name="c"></a>[C#](#tab/csharp)

1. 将 `Main` 方法的内容（当前只是调用 `Console.WriteLine` 的行）替换为以下代码：

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/HelloWorld.cs#1)]

   此代码在控制台中显示“What is your name?”， 然后等待用户输入字符串并按 Enter 键。 它将此字符串存储到名为 `name` 的变量中。 它还会检索 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性的值（其中包含当前的本地时间），并将此值赋给 `date` 变量。 最后，使用[内插字符串](../../csharp/language-reference/tokens/interpolated.md)在控制台窗口中显示这些值。

1. 依次选择 **“生成”**  >  **“生成解决方案”** ，编译此程序。

1. 若要运行程序，请在工具栏上选择“HelloWorld”  ，或按 F5  。

1. 出现提示时，输入名称并按 Enter  键。

   ![控制台窗口，含已修改程序的输出](./media/with-visual-studio/hello-world-update.png)

1. 按任意键关闭控制台窗口。

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. 将 `Main` 方法的内容（当前只是调用 `Console.WriteLine` 的行）替换为以下代码：

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/Program.vb#1)]

   此代码在控制台中显示“What is your name?”， 然后等待用户输入字符串并按 Enter 键。 它将此字符串存储到名为 `name` 的变量中。 它还会检索 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性的值（其中包含当前的本地时间），并将此值赋给 `date` 变量。 最后，使用[内插字符串](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)在控制台窗口中显示这些值。

1. 依次选择 **“生成”**  >  **“生成解决方案”** ，编译此程序。

1. 若要运行程序，请在工具栏上选择“HelloWorld”  ，或按 F5  。

1. 出现提示时，输入名称并按 Enter  键。

   ![控制台窗口，含已修改程序的输出](./media/with-visual-studio/hello-world-update.png)

1. 按任意键关闭控制台窗口。

---

## <a name="next-steps"></a>后续步骤

在本文中，你已创建并运行第一个 .NET Core 应用程序。 下一步，调试应用。

> [!div class="nextstepaction"]
> [在 Visual Studio 中调试 .NET Core Hello World 应用程序](debugging-with-visual-studio.md)
