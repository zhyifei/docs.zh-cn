---
title: "C# 和 Visual Studio Code 入门 - C# 指南 | Microsoft Docs"
description: "了解如何使用 Visual Studio Code 创建和调试首个 C# .NET Core 应用。"
keywords: "C#, 入门, 获取, 安装, Visual Studio Code, 跨平台"
author: kendrahavens
ms.author: mairaw
ms.date: 8/01/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.translationtype: HT
ms.sourcegitcommit: 3bd8800e7410ae4a3b89f5962af957789edd48b0
ms.openlocfilehash: a10fda5663f0a49069388ee8ee7a9ebb575cd549
ms.contentlocale: zh-cn
ms.lasthandoff: 08/03/2017

---

# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="5ec75-104">C# 和 Visual Studio Code 入门</span><span class="sxs-lookup"><span data-stu-id="5ec75-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="5ec75-105">.NET Core 提供了快速运行的模块化平台，用于创建在 Windows、Linux 和 macOS 上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ec75-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="5ec75-106">带 C# 扩展的 Visual Studio Code 提供功能强大的编辑体验，完全支持 C# IntelliSense（智能代码填充）和调试。</span><span class="sxs-lookup"><span data-stu-id="5ec75-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ec75-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="5ec75-107">Prerequisites</span></span>

1. <span data-ttu-id="5ec75-108">安装 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="5ec75-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="5ec75-109">获取 [.NET Core SDK](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="5ec75-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="5ec75-110">从 Visual Studio Code 应用商店安装 [C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="5ec75-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="5ec75-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="5ec75-111">Hello World</span></span>

<span data-ttu-id="5ec75-112">让我们从 .NET Core 上的一个简单“Hello World”程序入手：</span><span class="sxs-lookup"><span data-stu-id="5ec75-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="5ec75-113">打开项目：</span><span class="sxs-lookup"><span data-stu-id="5ec75-113">Open a project:</span></span>

    * <span data-ttu-id="5ec75-114">打开 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="5ec75-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="5ec75-115">依次单击左侧菜单上的“资源管理器”图标和**“打开文件夹”**。</span><span class="sxs-lookup"><span data-stu-id="5ec75-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="5ec75-116">选择要在其中放置 C# 项目的文件夹，然后单击**“选择文件夹”**。</span><span class="sxs-lookup"><span data-stu-id="5ec75-116">Select the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="5ec75-117">在我们的示例中，我们将把项目文件夹命名为“HelloWorld”。</span><span class="sxs-lookup"><span data-stu-id="5ec75-117">For our example, we'll create a folder for our project named 'HelloWorld'.</span></span> 

  ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

    * <span data-ttu-id="5ec75-119">或者，可以在主菜单上依次选择**“文件”** > **“打开文件夹”**，打开项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="5ec75-119">Alternatively, you can select **File** > **Open Folder** from the main menu to open your project folder.</span></span>

2. <span data-ttu-id="5ec75-120">初始化 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="5ec75-120">Initialize a C# project:</span></span>
    * <span data-ttu-id="5ec75-121">键入“<kbd>CTRL</kbd>+<kbd>\\`</kbd>”（反引号），在 Visual Studio Code 中打开集成终端。</span><span class="sxs-lookup"><span data-stu-id="5ec75-121">Open the Integrated Terminal from Visual Studio Code by typing <kbd>CTRL</kbd>+<kbd>\\`</kbd> (backtick).</span></span> <span data-ttu-id="5ec75-122">也可以在主菜单中依次选择“视图” > “集成终端”。</span><span class="sxs-lookup"><span data-stu-id="5ec75-122">Alternatively, you can select **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="5ec75-123">在终端窗口中，键入“`dotnet new console`”。</span><span class="sxs-lookup"><span data-stu-id="5ec75-123">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="5ec75-124">这会在已编写“Hello World”简单程序的文件夹中创建 `Program.cs` 文件，以及 `HelloWorld.csproj` C# 项目文件。</span><span class="sxs-lookup"><span data-stu-id="5ec75-124">This creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

  ![dotnet new 命令](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="5ec75-126">解析生成资产：</span><span class="sxs-lookup"><span data-stu-id="5ec75-126">Resolve the build assets:</span></span>

    * <span data-ttu-id="5ec75-127">对于 .NET Core 1.1，键入“`dotnet restore`”。</span><span class="sxs-lookup"><span data-stu-id="5ec75-127">For **.NET Core 1.1**, type `dotnet restore`.</span></span> <span data-ttu-id="5ec75-128">运行 `dotnet restore` 后，便有权访问生成项目所需的 .NET Core 包。</span><span class="sxs-lookup"><span data-stu-id="5ec75-128">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

   ![dotnet restore 命令](media/with-visual-studio-code/dotnetrestore.png)

    * <span data-ttu-id="5ec75-130">对于 .NET Core 2.0，这一步是可选的。</span><span class="sxs-lookup"><span data-stu-id="5ec75-130">For **.NET Core 2.0**, this step is optional.</span></span> <span data-ttu-id="5ec75-131">`dotnet restore` 命令在新项目创建时自动执行。</span><span class="sxs-lookup"><span data-stu-id="5ec75-131">The `dotnet restore` command executes automatically when a new project is created.</span></span>

4. <span data-ttu-id="5ec75-132">运行“Hello World”程序：</span><span class="sxs-lookup"><span data-stu-id="5ec75-132">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="5ec75-133">键入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="5ec75-133">Type `dotnet run`.</span></span> 

  ![dotnet run 命令](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="5ec75-135">还可以观看简短的视频教程，以获取更多关于在 [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core)、[macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 或 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) 上进行安装的帮助。</span><span class="sxs-lookup"><span data-stu-id="5ec75-135">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="5ec75-136">调试</span><span class="sxs-lookup"><span data-stu-id="5ec75-136">Debug</span></span>
1. <span data-ttu-id="5ec75-137">单击打开 *Program.cs*。</span><span class="sxs-lookup"><span data-stu-id="5ec75-137">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="5ec75-138">在 Visual Studio Code 中首次打开 C# 文件时，将在编辑器中加载 [OmniSharp](http://www.omnisharp.net/)。</span><span class="sxs-lookup"><span data-stu-id="5ec75-138">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) will load in the editor.</span></span>

  ![打开 Program.cs 文件](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="5ec75-140">Visual Studio Code 会提示添加缺少的资产，以生成和调试应用。</span><span class="sxs-lookup"><span data-stu-id="5ec75-140">Visual Studio Code will prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="5ec75-141">选择**“是”**。</span><span class="sxs-lookup"><span data-stu-id="5ec75-141">Select **Yes**.</span></span> 

  ![提示添加缺少的资产](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="5ec75-143">若要打开调试视图，请单击左侧菜单上的“调试”图标。</span><span class="sxs-lookup"><span data-stu-id="5ec75-143">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

  ![打开“调试”选项卡](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="5ec75-145">找到窗格最上面的绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="5ec75-145">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="5ec75-146">请确保已选择旁边下拉列表中的“`.NET Core Launch (console)`”。</span><span class="sxs-lookup"><span data-stu-id="5ec75-146">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

  ![选择 .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="5ec75-148">单击第 9 行旁边的**编辑器边距**（编辑器中行号左侧的空间），为项目添加断点。</span><span class="sxs-lookup"><span data-stu-id="5ec75-148">Add a breakpoint to your project by clicking on the **editor margin** (the space on the left of the line numbers in the editor) next to line 9.</span></span>

  ![设置断点](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="5ec75-150">按 <kbd>F5</kbd> 或选择绿色箭头启动调试。</span><span class="sxs-lookup"><span data-stu-id="5ec75-150">Select <kbd>F5</kbd> or the green arrow to start debugging.</span></span> <span data-ttu-id="5ec75-151">在到达你在上一步中设置的断点时，调试器会停止执行程序。</span><span class="sxs-lookup"><span data-stu-id="5ec75-151">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="5ec75-152">调试时，可以在左上角的窗格中查看本地变量，也可以使用调试控制台进行查看。</span><span class="sxs-lookup"><span data-stu-id="5ec75-152">While debugging you can view your local variables in the top left pane or use the debug console.</span></span>

  ![运行和调试](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="5ec75-154">选择最上面的绿色箭头以继续调试，或选择最上面的红色方块以停止调试。</span><span class="sxs-lookup"><span data-stu-id="5ec75-154">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="5ec75-155">若要详细了解如何使用 OmniSharp 在 Visual Studio Code 中进行 .NET Core 调试，以及相关的疑难解答提示，请参阅[有关设置 .NET Core 调试器的说明](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec75-155">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ec75-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ec75-156">See also</span></span>
<span data-ttu-id="5ec75-157">[设置 Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span><span class="sxs-lookup"><span data-stu-id="5ec75-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
[<span data-ttu-id="5ec75-158">在 Visual Studio Code 中进行调试</span><span class="sxs-lookup"><span data-stu-id="5ec75-158">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)

