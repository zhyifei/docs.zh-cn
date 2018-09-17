---
title: C# 和 Visual Studio Code 入门 - C# 指南
description: 了解如何使用 Visual Studio Code 创建和调试首个 C# .NET Core 应用。
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: 321edcebdea141b7290fa57b47c8d9fc91d3521c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668218"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="4e8af-103">C# 和 Visual Studio Code 入门</span><span class="sxs-lookup"><span data-stu-id="4e8af-103">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="4e8af-104">.NET Core 提供了快速运行的模块化平台，用于创建在 Windows、Linux 和 macOS 上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e8af-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="4e8af-105">带 C# 扩展的 Visual Studio Code 提供功能强大的编辑体验，完全支持 C# IntelliSense（智能代码填充）和调试。</span><span class="sxs-lookup"><span data-stu-id="4e8af-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e8af-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="4e8af-106">Prerequisites</span></span>

1. <span data-ttu-id="4e8af-107">安装 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="4e8af-108">获取 [.NET Core SDK](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-108">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="4e8af-109">安装 Visual Studio Code 的 [C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="4e8af-110">若要详细了解如何在 Visual Studio Code 上安装扩展，请访问 [VS Code 扩展市场](https://code.visualstudio.com/docs/editor/extension-gallery)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="4e8af-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="4e8af-111">Hello World</span></span>

<span data-ttu-id="4e8af-112">让我们从 .NET Core 上的一个简单“Hello World”程序入手：</span><span class="sxs-lookup"><span data-stu-id="4e8af-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="4e8af-113">打开项目：</span><span class="sxs-lookup"><span data-stu-id="4e8af-113">Open a project:</span></span>

    * <span data-ttu-id="4e8af-114">打开 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="4e8af-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="4e8af-115">依次单击左侧菜单上的“资源管理器”图标和 **“打开文件夹”**。</span><span class="sxs-lookup"><span data-stu-id="4e8af-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="4e8af-116">从主菜单中选择“文件” > “打开文件夹”，打开要在其中放置 C# 项目的文件夹，然后单击“选择文件夹”。</span><span class="sxs-lookup"><span data-stu-id="4e8af-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="4e8af-117">在我们的示例中，为项目创建名为“HelloWorld”的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4e8af-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="4e8af-119">初始化 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="4e8af-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="4e8af-120">通过从主菜单中选择“视图” > “集成终端”，从 Visual Studio Code 中打开集成终端。</span><span class="sxs-lookup"><span data-stu-id="4e8af-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="4e8af-121">在终端窗口中，键入“`dotnet new console`”。</span><span class="sxs-lookup"><span data-stu-id="4e8af-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="4e8af-122">此命令在已编写“Hello World”简单程序的文件夹中创建 `Program.cs` 文件，以及 `HelloWorld.csproj` C# 项目文件。</span><span class="sxs-lookup"><span data-stu-id="4e8af-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![dotnet new 命令](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="4e8af-124">解析生成资产：</span><span class="sxs-lookup"><span data-stu-id="4e8af-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="4e8af-125">对于 .NET Core 1.x，键入 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="4e8af-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="4e8af-126">运行 `dotnet restore` 后，便有权访问生成项目所需的 .NET Core 包。</span><span class="sxs-lookup"><span data-stu-id="4e8af-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![dotnet restore 命令](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="4e8af-128">运行“Hello World”程序：</span><span class="sxs-lookup"><span data-stu-id="4e8af-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="4e8af-129">键入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="4e8af-129">Type `dotnet run`.</span></span>

      ![dotnet run 命令](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="4e8af-131">还可以观看简短的视频教程，以获取更多关于在 [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core)、[macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 或 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) 上进行安装的帮助。</span><span class="sxs-lookup"><span data-stu-id="4e8af-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="4e8af-132">调试</span><span class="sxs-lookup"><span data-stu-id="4e8af-132">Debug</span></span>

1. <span data-ttu-id="4e8af-133">单击打开 *Program.cs*。</span><span class="sxs-lookup"><span data-stu-id="4e8af-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="4e8af-134">在 Visual Studio Code 中首次打开 C# 文件时，会在编辑器中加载 [OmniSharp](http://www.omnisharp.net/)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![打开 Program.cs 文件](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="4e8af-136">Visual Studio Code 会提示添加缺少的资产，以生成和调试应用。</span><span class="sxs-lookup"><span data-stu-id="4e8af-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="4e8af-137">选择 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="4e8af-137">Select **Yes**.</span></span>

    ![提示添加缺少的资产](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="4e8af-139">若要打开调试视图，请单击左侧菜单上的“调试”图标。</span><span class="sxs-lookup"><span data-stu-id="4e8af-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![打开“调试”选项卡](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="4e8af-141">找到窗格最上面的绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="4e8af-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="4e8af-142">请确保已选择旁边下拉列表中的“`.NET Core Launch (console)`”。</span><span class="sxs-lookup"><span data-stu-id="4e8af-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![选择 .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="4e8af-144">单击第 9 行旁边的编辑器边距（编辑器中行号左侧的空间）或者将文本光标移动到编辑器中的第 9 行并按 <kbd>F9</kbd>，为项目添加断点。</span><span class="sxs-lookup"><span data-stu-id="4e8af-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![设置断点](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="4e8af-146">要开始调试，请选择 <kbd>F5</kbd> 或绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="4e8af-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="4e8af-147">在到达你在上一步中设置的断点时，调试器会停止执行程序。</span><span class="sxs-lookup"><span data-stu-id="4e8af-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="4e8af-148">调试时，可以在左上角的窗格中查看局部变量，也可以使用调试控制台进行查看。</span><span class="sxs-lookup"><span data-stu-id="4e8af-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![运行和调试](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="4e8af-150">选择最上面的绿色箭头以继续调试，或选择最上面的红色方块以停止调试。</span><span class="sxs-lookup"><span data-stu-id="4e8af-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP]
> <span data-ttu-id="4e8af-151">若要详细了解如何使用 OmniSharp 在 Visual Studio Code 中进行 .NET Core 调试，以及相关的疑难解答提示，请参阅[有关设置 .NET Core 调试器的说明](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="faq"></a><span data-ttu-id="4e8af-152">FAQ</span><span class="sxs-lookup"><span data-stu-id="4e8af-152">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="4e8af-153">缺少在 Visual Studio Code 中生成和调试 C# 所需的资产。</span><span class="sxs-lookup"><span data-stu-id="4e8af-153">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="4e8af-154">调试器显示“无配置”。</span><span class="sxs-lookup"><span data-stu-id="4e8af-154">My debugger says "No Configuration."</span></span>

<span data-ttu-id="4e8af-155">Visual Studio Code C# 扩展可生成用于生成和调试的资产。</span><span class="sxs-lookup"><span data-stu-id="4e8af-155">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="4e8af-156">首次打开 C# 项目时，Visual Studio Code 会提示用户生成这些资产。</span><span class="sxs-lookup"><span data-stu-id="4e8af-156">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="4e8af-157">如果当时并未生成这些资产，仍可以通过打开命令面板（“视图”>“命令面板”）并键入“>.NET: Generate Assets for Build and Debug”来运行此命令。</span><span class="sxs-lookup"><span data-stu-id="4e8af-157">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="4e8af-158">选择此方法可生成所需的 .vscode、launch.json 和 tasks.jsonn 配置文件。</span><span class="sxs-lookup"><span data-stu-id="4e8af-158">Selecting this generates the .vscode, launch.json, and tasks.json configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e8af-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e8af-159">See also</span></span>

* [<span data-ttu-id="4e8af-160">设置 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4e8af-160">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
* [<span data-ttu-id="4e8af-161">在 Visual Studio Code 中进行调试</span><span class="sxs-lookup"><span data-stu-id="4e8af-161">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
