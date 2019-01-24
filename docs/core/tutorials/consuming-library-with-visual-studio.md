---
title: 在 Visual Studio 2017 中使用 .NET Standard 库
description: 生成一个 .NET Core 应用程序，该应用程序使用 Visual Studio 2017 调用另一个类库的成员。
author: BillWagner
ms.author: wiwagn
ms.date: 06/05/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 7689d45b341dbe9dbfae40beec3a7663e2bd0366
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362387"
---
# <a name="consume-a-net-standard-library-in-visual-studio-2017"></a><span data-ttu-id="fd941-103">在 Visual Studio 2017 中使用 .NET Standard 库</span><span class="sxs-lookup"><span data-stu-id="fd941-103">Consume a .NET Standard library in Visual Studio 2017</span></span>

<span data-ttu-id="fd941-104">如果已按照[使用 Visual Studio 2017 生成 C# .NET Core 类库](./library-with-visual-studio.md)或[使用 Visual Studio 2017 生成 Visual Basic .NET Core 类库](vb-library-with-visual-studio.md)以及[使用 Visual Studio 2017 测试 .NET Core 类库](testing-library-with-visual-studio.md)中的步骤创建并测试 .NET Standard 类库，并且已生成库的发布版本，下一步就是使其可供调用方使用。</span><span class="sxs-lookup"><span data-stu-id="fd941-104">Once you've created a .NET Standard class library by following the steps in [Building a C# class library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) or [Building a Visual Basic class library with .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), tested it in [Testing a class library with .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md), and built a Release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="fd941-105">可以通过以下两种方式执行此操作：</span><span class="sxs-lookup"><span data-stu-id="fd941-105">You can do this in two ways:</span></span>

* <span data-ttu-id="fd941-106">如果库将供一个解决方案使用（例如，如果它是一个大型应用程序中的组件），可以将其以项目的形式添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="fd941-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>

* <span data-ttu-id="fd941-107">如果类库将供更多调用方使用，可以 NuGet 包的形式分发它。</span><span class="sxs-lookup"><span data-stu-id="fd941-107">If the library will be generally accessible, you can distribute it as a NuGet package.</span></span>

## <a name="including-a-library-as-a-project-in-a-solution"></a><span data-ttu-id="fd941-108">将类库以项目的形式添加到解决方案中</span><span class="sxs-lookup"><span data-stu-id="fd941-108">Including a library as a project in a solution</span></span>

<span data-ttu-id="fd941-109">就像将单元测试和类库添加到同一解决方案中一样，可以将应用程序添加到同一解决方案中。</span><span class="sxs-lookup"><span data-stu-id="fd941-109">Just as you included unit tests in the same solution as your class library, you can include your application as part of that solution.</span></span> <span data-ttu-id="fd941-110">例如，可在控制台应用程序中使用类库，此应用程序将提示用户输入字符串，并报告第一个字符是否为大写：</span><span class="sxs-lookup"><span data-stu-id="fd941-110">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="fd941-111">C#</span><span class="sxs-lookup"><span data-stu-id="fd941-111">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="fd941-112">打开在[使用 Visual Studio 2017 生成 C# .NET Core 类库](./library-with-visual-studio.md)主题中创建的 `ClassLibraryProjects` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="fd941-112">Open the `ClassLibraryProjects` solution you created in the [Building a C# Class Library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="fd941-113">在“解决方案资源管理器”中，右键单击“ClassLibraryProjects”解决方案，然后从上下文菜单依次选择“添加” > “新项目”。</span><span class="sxs-lookup"><span data-stu-id="fd941-113">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="fd941-114">在“添加新项目”对话框中，展开“Visual C#”节点，再依次选择“.NET Core”节点和“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="fd941-114">In the **Add New Project** dialog, expand the **Visual C#** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="fd941-115">在“名称”文本框中，键入“ShowCase”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="fd941-115">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![Visual Studio“添加新项目”对话框 - C#](./media/consuming-library-with-visual-studio/add-new-project-dialog.png)

1. <span data-ttu-id="fd941-117">在“**解决方案资源管理器**”中，右键单击“**ShowCase**”项目，在上下文菜单中选择“**设为启动项目**”。</span><span class="sxs-lookup"><span data-stu-id="fd941-117">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Visual Studio 中用于设置启动项目的项目上下文菜单 - C#](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="fd941-119">项目一开始无权访问类库。</span><span class="sxs-lookup"><span data-stu-id="fd941-119">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="fd941-120">若要允许项目调用类库中的方法，可以创建对该类库的引用。</span><span class="sxs-lookup"><span data-stu-id="fd941-120">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="fd941-121">在“解决方案资源管理器”中，右键单击 `ShowCase` 项目的“依赖项”节点，并选择“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="fd941-121">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Visual Studio 项目添加引用上下文菜单 - C#](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="fd941-123">在“引用管理器”对话框中，选择类库项目“StringLibrary”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="fd941-123">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![Visual Studio“管理引用”对话框 - C#](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="fd941-125">在“Program.cs”文件的代码窗口中，将所有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="fd941-125">In the code window for the *Program.cs* file, replace all of the code with the following code:</span></span>

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   <span data-ttu-id="fd941-126">该代码使用 `row` 变量来维护写入到控制台窗口的数据行数计数。</span><span class="sxs-lookup"><span data-stu-id="fd941-126">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="fd941-127">如果大于或等于 25，该代码将清除控制台窗口，并向用户显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="fd941-127">Whenever it is greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="fd941-128">该程序会提示用户输入字符串。</span><span class="sxs-lookup"><span data-stu-id="fd941-128">The program prompts the user to enter a string.</span></span> <span data-ttu-id="fd941-129">它会指明字符串是否以大写字符开头。</span><span class="sxs-lookup"><span data-stu-id="fd941-129">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="fd941-130">如果用户没有输入字符串就按 Enter 键，应用程序会终止且控制台窗口会关闭。</span><span class="sxs-lookup"><span data-stu-id="fd941-130">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="fd941-131">必要时，将工具栏更改为编译 `ShowCase` 项目的“调试”版本。</span><span class="sxs-lookup"><span data-stu-id="fd941-131">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="fd941-132">选择“ShowCase”按钮上的绿色箭头，编译并运行程序。</span><span class="sxs-lookup"><span data-stu-id="fd941-132">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Visual Studio 中显示“调试”按钮的项目工具栏 - C#](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)
# <a name="visual-basictabvb"></a>[<span data-ttu-id="fd941-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fd941-134">Visual Basic</span></span>](#tab/vb)
1. <span data-ttu-id="fd941-135">打开在[使用 Visual Studio 2017 生成 Visual Basic .NET Core 类库](vb-library-with-visual-studio.md)主题中创建的 `ClassLibraryProjects` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="fd941-135">Open the `ClassLibraryProjects` solution you created in the [Building a class Library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="fd941-136">在“解决方案资源管理器”中，右键单击“ClassLibraryProjects”解决方案，然后从上下文菜单依次选择“添加” > “新项目”。</span><span class="sxs-lookup"><span data-stu-id="fd941-136">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="fd941-137">在“添加新项目”对话框中，展开“Visual Basic”节点，再依次选择“.NET Core”节点和“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="fd941-137">In the **Add New Project** dialog, expand the **Visual Basic** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="fd941-138">在“名称”文本框中，键入“ShowCase”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="fd941-138">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![Visual Studio“添加新项目”对话框 - Visual Basic](./media/consuming-library-with-visual-studio/add-new-vb-project-dialog.png)

1. <span data-ttu-id="fd941-140">在“**解决方案资源管理器**”中，右键单击“**ShowCase**”项目，在上下文菜单中选择“**设为启动项目**”。</span><span class="sxs-lookup"><span data-stu-id="fd941-140">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span> 

   ![Visual Studio 中用于设置启动项目的项目上下文菜单 - Visual Basic](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="fd941-142">项目一开始无权访问类库。</span><span class="sxs-lookup"><span data-stu-id="fd941-142">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="fd941-143">若要允许项目调用类库中的方法，可以创建对该类库的引用。</span><span class="sxs-lookup"><span data-stu-id="fd941-143">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="fd941-144">在“解决方案资源管理器”中，右键单击 `ShowCase` 项目的“依赖项”节点，并选择“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="fd941-144">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Visual Studio 项目添加引用上下文菜单 - Visual Basic](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="fd941-146">在“引用管理器”对话框中，选择类库项目“StringLibrary”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="fd941-146">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![Visual Studio“管理引用”对话框 - Visual Basic](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="fd941-148">在“Program.vb”文件的代码窗口中，将所有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="fd941-148">In the code window for the *Program.vb* file, replace all of the code with the following code:</span></span>

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="fd941-149">该代码使用 `row` 变量来维护写入到控制台窗口的数据行数计数。</span><span class="sxs-lookup"><span data-stu-id="fd941-149">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="fd941-150">如果大于或等于 25，该代码将清除控制台窗口，并向用户显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="fd941-150">Whenever it is greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="fd941-151">该程序会提示用户输入字符串。</span><span class="sxs-lookup"><span data-stu-id="fd941-151">The program prompts the user to enter a string.</span></span> <span data-ttu-id="fd941-152">它会指明字符串是否以大写字符开头。</span><span class="sxs-lookup"><span data-stu-id="fd941-152">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="fd941-153">如果用户没有输入字符串就按 Enter 键，应用程序会终止且控制台窗口会关闭。</span><span class="sxs-lookup"><span data-stu-id="fd941-153">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="fd941-154">必要时，将工具栏更改为编译 `ShowCase` 项目的“调试”版本。</span><span class="sxs-lookup"><span data-stu-id="fd941-154">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="fd941-155">选择“ShowCase”按钮上的绿色箭头，编译并运行程序。</span><span class="sxs-lookup"><span data-stu-id="fd941-155">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![在工具栏上调试 - Visual Basic](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)
---

<span data-ttu-id="fd941-157">可以按照[使用 Visual Studio 2017 调试 Hello World 应用程序](debugging-with-visual-studio.md)和[使用 Visual Studio 2017 发布 Hello World 应用程序](publishing-with-visual-studio.md)中的步骤操作，调试并发布使用此库的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd941-157">You can debug and publish the application that uses this library by following the steps in [Debugging your Hello World application with Visual Studio 2017](debugging-with-visual-studio.md) and [Publishing your Hello World Application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="distributing-the-library-in-a-nuget-package"></a><span data-ttu-id="fd941-158">以 NuGet 包的形式分发类库</span><span class="sxs-lookup"><span data-stu-id="fd941-158">Distributing the library in a NuGet package</span></span>

<span data-ttu-id="fd941-159">可采用 NuGet 包的形式发布类库，让类库可供更多调用方使用。</span><span class="sxs-lookup"><span data-stu-id="fd941-159">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="fd941-160">Visual Studio 不支持创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="fd941-160">Visual Studio does not support the creation of NuGet packages.</span></span> <span data-ttu-id="fd941-161">若要创建 NuGet 包，请使用 [`dotnet` 命令行实用工具](../../core/tools/dotnet.md)：</span><span class="sxs-lookup"><span data-stu-id="fd941-161">To create one, you use the [`dotnet` command line utility](../../core/tools/dotnet.md):</span></span>

1. <span data-ttu-id="fd941-162">打开控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="fd941-162">Open a console window.</span></span> <span data-ttu-id="fd941-163">例如，在 Windows 任务栏的“有问题尽管问我”文本框中，输入 `Command Prompt`（或缩写 `cmd`），然后选择“命令提示符”桌面应用或按 Enter（如果已在搜索结果中选中控制台窗口），打开控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="fd941-163">For example in the **Ask me anything** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="fd941-164">转到类库的项目目录。</span><span class="sxs-lookup"><span data-stu-id="fd941-164">Navigate to your library's project directory.</span></span> <span data-ttu-id="fd941-165">除非重新配置了典型文件位置，否则文件通常位于 Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary 目录中。</span><span class="sxs-lookup"><span data-stu-id="fd941-165">Unless you've reconfigured the typical file location, it's in the *Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary* directory.</span></span> <span data-ttu-id="fd941-166">此目录包含源代码和项目文件 StringLibrary.csproj。</span><span class="sxs-lookup"><span data-stu-id="fd941-166">The directory contains your source code and a project file, *StringLibrary.csproj*.</span></span>

1. <span data-ttu-id="fd941-167">发出命令 `dotnet pack --no-build`。</span><span class="sxs-lookup"><span data-stu-id="fd941-167">Issue the command `dotnet pack --no-build`.</span></span> <span data-ttu-id="fd941-168">此时，`dotnet` 实用工具会生成一个扩展名为 .nupkg 的包。</span><span class="sxs-lookup"><span data-stu-id="fd941-168">The `dotnet` utility generates a package with a *.nupkg* extension.</span></span>

   > [!TIP]
   > <span data-ttu-id="fd941-169">如果路径中没有包含 dotnet.exe 的目录，可以通过在控制台窗口中输入 `where dotnet.exe` 来找到它的位置。</span><span class="sxs-lookup"><span data-stu-id="fd941-169">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="fd941-170">若要详细了解如何创建 NuGet 包，请参阅[如何使用跨平台工具创建 NuGet 包](../../core/deploying/creating-nuget-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="fd941-170">For more information on creating NuGet packages, see [How to Create a NuGet Package with Cross Platform Tools](../../core/deploying/creating-nuget-packages.md).</span></span>
