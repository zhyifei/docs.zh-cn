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
# <a name="consume-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="92dc8-103">在 Visual Studio 中使用 .NET Standard 库</span><span class="sxs-lookup"><span data-stu-id="92dc8-103">Consume a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="92dc8-104">创建 .NET Standard 类库、测试并生成库的发行版本后，下一步就是使其可供调用方使用。</span><span class="sxs-lookup"><span data-stu-id="92dc8-104">Once you've created a .NET Standard class library, tested it, and built a release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="92dc8-105">可以通过以下两种方式执行此操作：</span><span class="sxs-lookup"><span data-stu-id="92dc8-105">You can do this in two ways:</span></span>

- <span data-ttu-id="92dc8-106">如果库将供一个解决方案使用（例如，如果它是一个大型应用程序中的组件），可以将其以项目的形式添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="92dc8-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>
- <span data-ttu-id="92dc8-107">如果类库将公开发布，你可以以 NuGet 包的形式分发。</span><span class="sxs-lookup"><span data-stu-id="92dc8-107">If the library will be publicly available, you can distribute it as a NuGet package.</span></span>

<span data-ttu-id="92dc8-108">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="92dc8-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="92dc8-109">向解决方案中添加引用 .NET Standard 库项目的控制台应用。</span><span class="sxs-lookup"><span data-stu-id="92dc8-109">Add a console app to your solution that references a .NET Standard library project.</span></span>
> - <span data-ttu-id="92dc8-110">创建包含 .NET Standard 库项目的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="92dc8-110">Create a NuGet package that contains a .NET Standard library project.</span></span>

## <a name="add-a-console-app-to-your-solution"></a><span data-ttu-id="92dc8-111">向解决方案添加控制台应用</span><span class="sxs-lookup"><span data-stu-id="92dc8-111">Add a console app to your solution</span></span>

<span data-ttu-id="92dc8-112">就像[在 Visual Studio 中测试 .NET Standard 库](testing-library-with-visual-studio.md)所述的将单元测试和类库添加到同一解决方案中一样，可以将应用程序添加到同一解决方案中。</span><span class="sxs-lookup"><span data-stu-id="92dc8-112">Just as you included unit tests in the same solution as your class library in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), you can include your application as part of that solution.</span></span> <span data-ttu-id="92dc8-113">例如，可在控制台应用程序中使用类库，此应用程序将提示用户输入字符串，并报告第一个字符是否为大写：</span><span class="sxs-lookup"><span data-stu-id="92dc8-113">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

1. <span data-ttu-id="92dc8-114">打开在[在 Visual Studio 中生成 .NET Standard 库](library-with-visual-studio.md)一文中创建的 `ClassLibraryProjects` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="92dc8-114">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="92dc8-115">将名为“ShowCase”的新 .NET Core 控制台应用程序添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="92dc8-115">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="92dc8-116">在“解决方案资源管理器”  中右键单击解决方案并选择“添加”   > “新建项目”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-116">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="92dc8-117">在“创建新项目”  页面，在搜索框中输入“控制台”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-117">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="92dc8-118">从“语言”列表中选择“C#”  或“Visual Basic”  ，然后从“平台”列表中选择“所有平台”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-118">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="92dc8-119">选择“控制台应用 (.NET Core)”  模板，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-119">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="92dc8-120">在“配置新项目”  页面，在“项目名称”  框中输入“ShowCase”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-120">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="92dc8-121">然后，选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-121">Then, choose **Create**.</span></span>

1. <span data-ttu-id="92dc8-122">在“**解决方案资源管理器**”中，右键单击“**ShowCase**”项目，在上下文菜单中选择“**设为启动项目**”。</span><span class="sxs-lookup"><span data-stu-id="92dc8-122">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Visual Studio 中用于设置启动项目的项目上下文菜单](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="92dc8-124">项目一开始无权访问类库。</span><span class="sxs-lookup"><span data-stu-id="92dc8-124">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="92dc8-125">若要允许项目调用类库中的方法，可以创建对该类库的引用。</span><span class="sxs-lookup"><span data-stu-id="92dc8-125">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="92dc8-126">在“解决方案资源管理器”  中，右键单击 `ShowCase` 项目的“依赖项”  节点，并选择“添加引用”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-126">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![在 Visual Studio 中添加引用上下文菜单](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="92dc8-128">在“引用管理器”  对话框中，选择类库项目“StringLibrary”  ，然后选择“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="92dc8-128">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![选择了“StringLibrary”的“引用管理器”对话框](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="92dc8-130">在“Program.cs”  或“Program.vb”  文件的代码窗口中，将所有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="92dc8-130">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code:</span></span>

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="92dc8-131">该代码使用 `row` 变量来维护写入到控制台窗口的数据行数计数。</span><span class="sxs-lookup"><span data-stu-id="92dc8-131">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="92dc8-132">如果大于或等于 25，该代码将清除控制台窗口，并向用户显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="92dc8-132">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="92dc8-133">该程序会提示用户输入字符串。</span><span class="sxs-lookup"><span data-stu-id="92dc8-133">The program prompts the user to enter a string.</span></span> <span data-ttu-id="92dc8-134">它会指明字符串是否以大写字符开头。</span><span class="sxs-lookup"><span data-stu-id="92dc8-134">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="92dc8-135">如果用户没有输入字符串就按 Enter 键，那么应用程序会终止，控制台窗口会关闭。</span><span class="sxs-lookup"><span data-stu-id="92dc8-135">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="92dc8-136">必要时，将工具栏更改为编译 `ShowCase` 项目的“调试”  版本。</span><span class="sxs-lookup"><span data-stu-id="92dc8-136">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="92dc8-137">选择“ShowCase”  按钮上的绿色箭头，编译并运行程序。</span><span class="sxs-lookup"><span data-stu-id="92dc8-137">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Visual Studio 中显示“调试”按钮的项目工具栏](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

<span data-ttu-id="92dc8-139">可以按照[使用 Visual Studio 调试 C# 或 Visual Basic .NET Core Hello World 应用程序](debugging-with-visual-studio.md)和[使用 Visual Studio 发布 .NET Core Hello World 应用程序](publishing-with-visual-studio.md)中的步骤操作，调试并发布使用此库的应用程序。</span><span class="sxs-lookup"><span data-stu-id="92dc8-139">You can debug and publish the application that uses this library by following the steps in [Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio](debugging-with-visual-studio.md) and [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="92dc8-140">创建 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="92dc8-140">Create a NuGet package</span></span>

<span data-ttu-id="92dc8-141">可采用 NuGet 包的形式发布类库，让类库可供更多调用方使用。</span><span class="sxs-lookup"><span data-stu-id="92dc8-141">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="92dc8-142">Visual Studio 不支持创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="92dc8-142">Visual Studio doesn't support the creation of NuGet packages.</span></span> <span data-ttu-id="92dc8-143">若要创建一个，需要使用 .NET Core CLI 命令：</span><span class="sxs-lookup"><span data-stu-id="92dc8-143">To create one, you need to use the .NET Core CLI commands:</span></span>

1. <span data-ttu-id="92dc8-144">打开控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="92dc8-144">Open a console window.</span></span>

   <span data-ttu-id="92dc8-145">例如，在 Windows 任务栏的搜索框中输入“命令提示符”  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-145">For example, enter **Command Prompt** in the search box on the Windows task bar.</span></span> <span data-ttu-id="92dc8-146">选择“命令提示符”  桌面应用或按 Enter  （如果已在搜索结果中选择）。</span><span class="sxs-lookup"><span data-stu-id="92dc8-146">Select the **Command Prompt** desktop app or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="92dc8-147">转到类库的项目目录。</span><span class="sxs-lookup"><span data-stu-id="92dc8-147">Navigate to your library's project directory.</span></span> <span data-ttu-id="92dc8-148">此目录包含源代码和项目文件 StringLibrary.csproj  或 StringLibrary.vbproj  。</span><span class="sxs-lookup"><span data-stu-id="92dc8-148">The directory contains your source code and a project file, *StringLibrary.csproj* or *StringLibrary.vbproj*.</span></span>

1. <span data-ttu-id="92dc8-149">运行 [dotnet pack](../tools/dotnet-pack.md) 命令，以生成带 .nupkg  扩展的包：</span><span class="sxs-lookup"><span data-stu-id="92dc8-149">Run the [dotnet pack](../tools/dotnet-pack.md) command to generate a package with a *.nupkg* extension:</span></span>

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > <span data-ttu-id="92dc8-150">如果路径中没有包含 dotnet.exe  的目录，可以通过在控制台窗口中输入 `where dotnet.exe` 来找到它的位置。</span><span class="sxs-lookup"><span data-stu-id="92dc8-150">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="92dc8-151">若要详细了解如何创建 NuGet 包，请参阅[如何使用 .NET Core CLI 创建 NuGet 包](../deploying/creating-nuget-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="92dc8-151">For more information on creating NuGet packages, see [How to create a NuGet package with the .NET Core CLI](../deploying/creating-nuget-packages.md).</span></span>
