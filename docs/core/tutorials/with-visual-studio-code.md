---
title: C# 和 Visual Studio Code 入门
description: 了解如何使用 Visual Studio Code 创建和调试首个 C# .NET Core 应用。
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506869"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="bb3ee-103">C# 和 Visual Studio Code 入门</span><span class="sxs-lookup"><span data-stu-id="bb3ee-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="bb3ee-104">.NET Core 提供了快速运行的模块化平台，用于创建在 Windows、Linux 和 macOS 上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="bb3ee-105">带 C# 扩展的 Visual Studio Code 提供功能强大的编辑体验，完全支持 C# IntelliSense（智能代码填充）和调试。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb3ee-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="bb3ee-106">Prerequisites</span></span>

1. <span data-ttu-id="bb3ee-107">安装 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="bb3ee-108">获取 [.NET Core SDK](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="bb3ee-109">安装 Visual Studio Code 的 [C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="bb3ee-110">若要详细了解如何在 Visual Studio Code 上安装扩展，请访问 [VS Code 扩展市场](https://code.visualstudio.com/docs/editor/extension-gallery)。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="bb3ee-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="bb3ee-111">Hello World</span></span>

<span data-ttu-id="bb3ee-112">从 .NET Core 上的一个简单“Hello World”程序入手：</span><span class="sxs-lookup"><span data-stu-id="bb3ee-112">Get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="bb3ee-113">打开项目：</span><span class="sxs-lookup"><span data-stu-id="bb3ee-113">Open a project:</span></span>

    - <span data-ttu-id="bb3ee-114">打开 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="bb3ee-115">从主菜单中选择“文件” > “打开文件夹”   。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-115">Select **File** > **Open Folder** from the main menu.</span></span>
    - <span data-ttu-id="bb3ee-116">创建一个名为“HelloWorld”的文件夹，然后单击“选择文件夹”   。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-116">Create a folder named *HelloWorld*, and click **Select Folder**.</span></span> <span data-ttu-id="bb3ee-117">默认情况下，文件夹名称将是项目名称和命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-117">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="bb3ee-118">稍后将在本教程中添加代码，假定项目命名空间为 `HelloWorld`。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-118">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="bb3ee-119">初始化 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="bb3ee-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="bb3ee-120">通过从主菜单中选择“视图” > “终端”，从 Visual Studio Code 中打开终端   。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-120">Open the Terminal from Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>
    - <span data-ttu-id="bb3ee-121">在终端窗口中，键入 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-121">In the terminal window, enter `dotnet new console`.</span></span>

      <span data-ttu-id="bb3ee-122">此命令在已编写“Hello World”简单程序的文件夹中创建“Program.cs”文件，以及名为“HelloWorld.csproj”的 C# 项目文件   。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![dotnet new 命令](media/with-visual-studio-code/dotnet-new-command.png)

1. <span data-ttu-id="bb3ee-124">运行“Hello World”程序：</span><span class="sxs-lookup"><span data-stu-id="bb3ee-124">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="bb3ee-125">在终端窗口中，输入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-125">In the terminal window, enter `dotnet run`.</span></span>

      ![dotnet run 命令](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a><span data-ttu-id="bb3ee-127">调试</span><span class="sxs-lookup"><span data-stu-id="bb3ee-127">Debug</span></span>

1. <span data-ttu-id="bb3ee-128">单击打开 *Program.cs*。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-128">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="bb3ee-129">在 Visual Studio Code 中首次打开 C# 文件时，会在编辑器中加载 [OmniSharp](https://www.omnisharp.net/)。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-129">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![打开 Program.cs 文件](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="bb3ee-131">Visual Studio Code 会提示添加缺少的资产，以生成和调试应用。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-131">Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="bb3ee-132">选择 **“是”** 。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-132">Select **Yes**.</span></span>

    ![提示添加缺少的资产](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="bb3ee-134">若要打开调试视图，请单击左侧菜单上的“调试”图标。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-134">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![在 Visual Studio Code 中打开“调试”选项卡](media/with-visual-studio-code/open-debug-tab.png)

1. <span data-ttu-id="bb3ee-136">找到窗格最上面的绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-136">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="bb3ee-137">请确保已选择旁边下拉列表中的“.NET Core Launch (控制台)”  。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-137">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![在 Visual Studio Code 中选择“.NET Core”](media/with-visual-studio-code/select-net-core.png)

1. <span data-ttu-id="bb3ee-139">单击第 9 行旁边的编辑器边距  （编辑器中行号左侧的空间）或者将文本光标移动到编辑器中的第 9 行并按 <kbd>F9</kbd>，为项目添加断点。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-139">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![设置断点](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. <span data-ttu-id="bb3ee-141">请按 <kbd>F5</kbd> 或选择绿色箭头启动调试。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-141">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="bb3ee-142">在到达你在上一步中设置的断点时，调试器会停止执行程序。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-142">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="bb3ee-143">调试时，可以在左上角的窗格中查看局部变量，也可以使用调试控制台进行查看。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-143">While debugging, you can view your local variables in the top-left pane or use the debug console.</span></span>

1. <span data-ttu-id="bb3ee-144">选择最上面的蓝色箭头以继续调试，或选择最上面的红色方块以停止调试。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-144">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![在 Visual Studio Code 中运行并调试](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="bb3ee-146">若要详细了解如何使用 OmniSharp 在 Visual Studio Code 中进行 .NET Core 调试，以及相关的疑难解答提示，请参阅[有关设置 .NET Core 调试器的说明](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-146">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="bb3ee-147">添加类</span><span class="sxs-lookup"><span data-stu-id="bb3ee-147">Add a class</span></span>

1. <span data-ttu-id="bb3ee-148">若要添加一个新类，请右键单击 Program.cs 下方的 VSCode Explorer 并选择“新建文件”   。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-148">To add a new class, right-click in the VSCode Explorer below *Program.cs* and select **New File**.</span></span> <span data-ttu-id="bb3ee-149">此操作会将新文件添加到在 VSCode 中打开的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-149">This adds a new file to the folder you have open in VSCode.</span></span>
1. <span data-ttu-id="bb3ee-150">将文件命名为 MyClass.cs  。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-150">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="bb3ee-151">必须在末尾使用 `.cs` 扩展名保存它，以便将其识别为 csharp 文件。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-151">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
1. <span data-ttu-id="bb3ee-152">添加下面的代码，以创建第一个类。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-152">Add the following code to create your first class.</span></span>

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

1. <span data-ttu-id="bb3ee-153">通过将 Program.cs 中的代码替换为以下代码，从 `Main` 方法调用新类  ：</span><span class="sxs-lookup"><span data-stu-id="bb3ee-153">Call your new class from your `Main` method by replacing the code in *Program.cs* with the following code:</span></span>

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

1. <span data-ttu-id="bb3ee-154">保存更改。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-154">Save your changes.</span></span>

1. <span data-ttu-id="bb3ee-155">再次运行程序。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-155">Run the program again.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="bb3ee-156">新消息会显示追加的字符串。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-156">The new message appears with the appended string.</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="bb3ee-157">FAQ</span><span class="sxs-lookup"><span data-stu-id="bb3ee-157">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="bb3ee-158">缺少在 Visual Studio Code 中生成和调试 C# 所需的资产。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-158">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="bb3ee-159">调试器显示“无配置”。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-159">My debugger says "No Configuration."</span></span>

<span data-ttu-id="bb3ee-160">Visual Studio Code C# 扩展可生成用于生成和调试的资产。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-160">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="bb3ee-161">首次打开 C# 项目时，Visual Studio Code 会提示用户生成这些资产。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-161">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="bb3ee-162">如果当时并未生成这些资产，仍可以通过打开命令面板（“视图”>“命令面板”  ）并键入“>.NET：生成用于生成和调试的资产”来运行此命令。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-162">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="bb3ee-163">选择此方法可生成所需的 .vscode、launch.json 和 tasks.jsonn 配置文件    。</span><span class="sxs-lookup"><span data-stu-id="bb3ee-163">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb3ee-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb3ee-164">See also</span></span>

- [<span data-ttu-id="bb3ee-165">设置 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bb3ee-165">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="bb3ee-166">在 Visual Studio Code 中进行调试</span><span class="sxs-lookup"><span data-stu-id="bb3ee-166">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
