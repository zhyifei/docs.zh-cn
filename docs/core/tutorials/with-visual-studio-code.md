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
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="763ce-104">C# 和 Visual Studio Code 入门</span><span class="sxs-lookup"><span data-stu-id="763ce-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="763ce-105">.NET Core 提供了快速运行的模块化平台，用于创建在 Windows、Linux 和 macOS 上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="763ce-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="763ce-106">带 C# 扩展的 Visual Studio Code 提供功能强大的编辑体验，完全支持 C# IntelliSense（智能代码填充）和调试。</span><span class="sxs-lookup"><span data-stu-id="763ce-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="763ce-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="763ce-107">Prerequisites</span></span>

1. <span data-ttu-id="763ce-108">安装 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="763ce-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="763ce-109">获取 [.NET Core SDK](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="763ce-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="763ce-110">从 Visual Studio Code 应用商店安装 [C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="763ce-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="763ce-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="763ce-111">Hello World</span></span>

<span data-ttu-id="763ce-112">让我们从 .NET Core 上的一个简单“Hello World”程序入手：</span><span class="sxs-lookup"><span data-stu-id="763ce-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="763ce-113">打开项目：</span><span class="sxs-lookup"><span data-stu-id="763ce-113">Open a project:</span></span>

    * <span data-ttu-id="763ce-114">打开 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="763ce-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="763ce-115">依次单击左侧菜单上的“资源管理器”图标和**“打开文件夹”**。</span><span class="sxs-lookup"><span data-stu-id="763ce-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="763ce-116">选择**文件** > **打开文件夹**想从主菜单打开文件夹 C# 项目中并单击**选择文件夹**。</span><span class="sxs-lookup"><span data-stu-id="763ce-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="763ce-117">对于我们的示例，我们要为我们名为的项目中创建一个文件夹*HelloWorld*。</span><span class="sxs-lookup"><span data-stu-id="763ce-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="763ce-119">初始化 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="763ce-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="763ce-120">通过选择从 Visual Studio Code 打开集成终端**视图** > **集成终端**从主菜单。</span><span class="sxs-lookup"><span data-stu-id="763ce-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="763ce-121">在终端窗口中，键入“`dotnet new console`”。</span><span class="sxs-lookup"><span data-stu-id="763ce-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="763ce-122">此命令创建`Program.cs`在文件夹中，已写入，以及名为的 C# 项目文件的简单"Hello World"程序文件`HelloWorld.csproj`。</span><span class="sxs-lookup"><span data-stu-id="763ce-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![dotnet new 命令](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="763ce-124">解析生成资产：</span><span class="sxs-lookup"><span data-stu-id="763ce-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="763ce-125">有关**.NET 核心 1.x**，类型`dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="763ce-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="763ce-126">运行 `dotnet restore` 后，便有权访问生成项目所需的 .NET Core 包。</span><span class="sxs-lookup"><span data-stu-id="763ce-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![dotnet restore 命令](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="763ce-128">运行“Hello World”程序：</span><span class="sxs-lookup"><span data-stu-id="763ce-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="763ce-129">键入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="763ce-129">Type `dotnet run`.</span></span> 

      ![dotnet run 命令](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="763ce-131">还可以观看简短的视频教程，以获取更多关于在 [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core)、[macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 或 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) 上进行安装的帮助。</span><span class="sxs-lookup"><span data-stu-id="763ce-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="763ce-132">调试</span><span class="sxs-lookup"><span data-stu-id="763ce-132">Debug</span></span>

1. <span data-ttu-id="763ce-133">单击打开 *Program.cs*。</span><span class="sxs-lookup"><span data-stu-id="763ce-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="763ce-134">在 Visual Studio 代码，请打开一个 C# 文件的第一个时间[OmniSharp](http://www.omnisharp.net/)在编辑器中加载。</span><span class="sxs-lookup"><span data-stu-id="763ce-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![打开 Program.cs 文件](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="763ce-136">Visual Studio Code 应提示你添加缺少的资产，以生成和调试你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="763ce-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="763ce-137">选择**“是”**。</span><span class="sxs-lookup"><span data-stu-id="763ce-137">Select **Yes**.</span></span> 

    ![提示添加缺少的资产](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="763ce-139">若要打开调试视图，请单击左侧菜单上的“调试”图标。</span><span class="sxs-lookup"><span data-stu-id="763ce-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![打开“调试”选项卡](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="763ce-141">找到窗格最上面的绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="763ce-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="763ce-142">请确保已选择旁边下拉列表中的“`.NET Core Launch (console)`”。</span><span class="sxs-lookup"><span data-stu-id="763ce-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![选择 .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="763ce-144">将断点添加到你的项目中，通过单击**编辑器边距**，它是在编辑器中，第 9 行旁边的行号左侧空格。</span><span class="sxs-lookup"><span data-stu-id="763ce-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9.</span></span>

    ![设置断点](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="763ce-146">若要开始调试时，选择<kbd>F5</kbd>或绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="763ce-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="763ce-147">在到达你在上一步中设置的断点时，调试器会停止执行程序。</span><span class="sxs-lookup"><span data-stu-id="763ce-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="763ce-148">调试时，你可以在左窗格的顶部中查看你的本地变量，或使用调试控制台。</span><span class="sxs-lookup"><span data-stu-id="763ce-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![运行和调试](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="763ce-150">选择最上面的绿色箭头以继续调试，或选择最上面的红色方块以停止调试。</span><span class="sxs-lookup"><span data-stu-id="763ce-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="763ce-151">若要详细了解如何使用 OmniSharp 在 Visual Studio Code 中进行 .NET Core 调试，以及相关的疑难解答提示，请参阅[有关设置 .NET Core 调试器的说明](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。</span><span class="sxs-lookup"><span data-stu-id="763ce-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="763ce-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="763ce-152">See also</span></span>
<span data-ttu-id="763ce-153">[设置 Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span><span class="sxs-lookup"><span data-stu-id="763ce-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
[<span data-ttu-id="763ce-154">在 Visual Studio Code 中进行调试</span><span class="sxs-lookup"><span data-stu-id="763ce-154">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
