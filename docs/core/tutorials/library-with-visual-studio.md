---
title: 在 Visual Studio 中生成 .NET Standard 类库
description: 了解如何使用 Visual Studio 生成以 C# 或 Visual Basic 编写的 .NET Standard 类库
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714011"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a>在 Visual Studio 中生成 .NET Standard 库

类库定义的是可以由应用程序调用的类型和方法  。 借助面向 .NET Standard 2.0 的类库，任何支持相应 .NET Standard 版本的 .NET 实现都可以调用库。 完成类库时，可以决定是要将其作为第三方组件进行分布，还是要将其作为与一个或多个应用程序捆绑在一起的组件进行添加。

> [!NOTE]
> 有关 .NET Standard 版本及其支持的平台列表，请参阅 [.NET Standard](../../standard/net-standard.md)。

在本主题中，将创建包含一个字符串处理方法的简单实用工具库。 我们将把它作为[扩展方法](../../csharp/programming-guide/classes-and-structs/extension-methods.md)进行实现，这样就可以把它作为 <xref:System.String> 类成员进行调用。

## <a name="create-a-visual-studio-solution"></a>创建 Visual Studio 解决方案

首先，创建一个空白解决方案来放置类库项目。 Visual Studio 解决方案用作一个或多个项目的容器。 如果继续学习本系列教程，你将向相同的解决方案添加其他相关项目。

创建空白解决方案：

1. 打开 Visual Studio。

2. 在“开始”窗口上，选择“创建新项目”  。

3. 在“创建新项目”  页面上，在搜索框中输入“解决方案”  。 选择“空白解决方案”  模板，然后选择“下一步”  。

   ![Visual Studio 中的空白解决方案模板](media/library-with-visual-studio/blank-solution.png)

4. 在“配置新项目”  页面上，在“项目名称”  框中输入“ClassLibraryProjects”  。 然后，选择“创建”  。

> [!TIP]
> 你还可以跳过此步骤，并让 Visual Studio 在下一步中创建项目时为你创建该解决方案。 在“配置新项目”  页上查找解决方案选项。

## <a name="create-a-class-library-project"></a>创建类库项目

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. 将名为“StringLibrary”的新 C# .NET Standard 类库项目添加到解决方案。

   1. 在“解决方案资源管理器”  中右键单击解决方案并选择“添加”   > “新建项目”  。

   1. 在“创建新项目”  页面上，在搜索框中输入“库”  。 从“语言”列表中选择“C#”  ，然后从“平台”列表中选择“所有平台”  。 选择“类库 (.NET Standard)”  模板，然后选择“下一步”  。

   1. 在“配置新项目”  页面，在“项目名称”  框中输入“StringLibrary”  。 然后，选择“创建”  。

1. 请检查以确保库面向 .NET Standard 的正确版本。 右键单击“解决方案资源管理器”  中的库项目，然后选择“属性”  。 “目标框架”  文本框显示项目面向 .NET Standard 2.0。

   ![类库的项目属性](./media/library-with-visual-studio/library-project-properties.png)

1. 将代码窗口中的代码替换为以下代码，并保存文件：

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   类库 `UtilityLibraries.StringLibrary`包含一个名为 `StartsWithUpper` 的方法。 此方法会返回 <xref:System.Boolean> 值，以指明当前字符串实例是否以大写字符开头。 Unicode 标准会区分大小写字符。 如果为大写字符，<xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 方法返回 `true`。

1. 在菜单栏中，选择“生成”   > “生成解决方案”  。

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. 将名为“StringLibrary”的新 Visual Basic .NET Standard 类库项目添加到解决方案。

   1. 在“解决方案资源管理器”  中右键单击解决方案并选择“添加”   > “新建项目”  。

   1. 在“创建新项目”  页面上，在搜索框中输入“库”  。 从“语言”列表中选择“Visual Basic”  ，然后从“平台”列表中选择“所有平台”  。 选择“类库 (.NET Standard)”  模板，然后选择“下一步”  。

   1. 在“配置新项目”  页面，在“项目名称”  框中输入“StringLibrary”  。 然后，选择“创建”  。

1. 请检查以确保库面向 .NET Standard 的正确版本。 右键单击“解决方案资源管理器”  中的库项目，然后选择“属性”  。 “目标框架”  文本框显示项目面向 .NET Standard 2.0。

   ![类库的项目属性](./media/library-with-visual-studio/vb/library-project-properties.png)

1. 在“属性”  对话框中，清除“根命名空间”  文本框中的文本。 对于每个项目，Visual Basic 会自动创建一个与项目名称对应的命名空间。 在本教程中，通过使用代码文件中的 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 关键字定义顶级命名空间。

1. 将代码窗口中的代码替换为以下代码，并保存文件：

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   类库 `UtilityLibraries.StringLibrary`包含一个名为 `StartsWithUpper` 的方法。 此方法会返回 <xref:System.Boolean> 值，以指明当前字符串实例是否以大写字符开头。 Unicode 标准会区分大小写字符。 如果为大写字符，<xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 方法返回 `true`。

1. 在菜单栏中，选择“生成”   > “生成解决方案”  。

---

   此项目的编译应该没有错误。

## <a name="next-steps"></a>后续步骤

已成功生成库。 由于尚未调用库的任何方法，因此还不知道它能否按预期运行。 开发库的下一步是测试库。

> [!div class="nextstepaction"]
> [创建单元测试项目](testing-library-with-visual-studio.md)
