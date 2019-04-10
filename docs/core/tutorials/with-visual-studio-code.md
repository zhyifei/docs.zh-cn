---
title: C# 和 Visual Studio Code 入门
description: 了解如何使用 Visual Studio Code 创建和调试首个 C# .NET Core 应用。
author: kendrahavens
ms.date: 12/05/2018
ms.custom: seodec18
ms.openlocfilehash: d91427197662d61c1c3ffc242de9b1128b81b9c6
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890548"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="d0165-103">C# 和 Visual Studio Code 入门</span><span class="sxs-lookup"><span data-stu-id="d0165-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="d0165-104">.NET Core 提供了快速运行的模块化平台，用于创建在 Windows、Linux 和 macOS 上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0165-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="d0165-105">带 C# 扩展的 Visual Studio Code 提供功能强大的编辑体验，完全支持 C# IntelliSense（智能代码填充）和调试。</span><span class="sxs-lookup"><span data-stu-id="d0165-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0165-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="d0165-106">Prerequisites</span></span>

1. <span data-ttu-id="d0165-107">安装 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="d0165-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="d0165-108">获取 [.NET Core SDK](https://www.microsoft.com/net/download/core)。</span><span class="sxs-lookup"><span data-stu-id="d0165-108">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="d0165-109">安装 Visual Studio Code 的 [C# 扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="d0165-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="d0165-110">若要详细了解如何在 Visual Studio Code 上安装扩展，请访问 [VS Code 扩展市场](https://code.visualstudio.com/docs/editor/extension-gallery)。</span><span class="sxs-lookup"><span data-stu-id="d0165-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="d0165-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="d0165-111">Hello World</span></span>

<span data-ttu-id="d0165-112">让我们从 .NET Core 上的一个简单“Hello World”程序入手：</span><span class="sxs-lookup"><span data-stu-id="d0165-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="d0165-113">打开项目：</span><span class="sxs-lookup"><span data-stu-id="d0165-113">Open a project:</span></span>

    * <span data-ttu-id="d0165-114">打开 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="d0165-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="d0165-115">依次单击左侧菜单上的“资源管理器”图标和 **“打开文件夹”**。</span><span class="sxs-lookup"><span data-stu-id="d0165-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="d0165-116">从主菜单中选择“文件” > “打开文件夹”，打开要在其中放置 C# 项目的文件夹，然后单击“选择文件夹”。</span><span class="sxs-lookup"><span data-stu-id="d0165-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="d0165-117">在我们的示例中，为项目创建名为“HelloWorld”的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0165-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![Visual Studio Code“打开文件夹”](media/with-visual-studio-code/vs-code-open-folder.png)

2. <span data-ttu-id="d0165-119">初始化 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="d0165-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="d0165-120">通过从主菜单中选择“视图” > “集成终端”，从 Visual Studio Code 中打开集成终端。</span><span class="sxs-lookup"><span data-stu-id="d0165-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="d0165-121">在终端窗口中，键入“`dotnet new console`”。</span><span class="sxs-lookup"><span data-stu-id="d0165-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="d0165-122">此命令在已编写“Hello World”简单程序的文件夹中创建 `Program.cs` 文件，以及 `HelloWorld.csproj` C# 项目文件。</span><span class="sxs-lookup"><span data-stu-id="d0165-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![dotnet new 命令](media/with-visual-studio-code/dotnet-new-command.png)

3. <span data-ttu-id="d0165-124">解析生成资产：</span><span class="sxs-lookup"><span data-stu-id="d0165-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="d0165-125">对于 .NET Core 1.x，键入 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="d0165-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="d0165-126">运行 `dotnet restore` 后，便有权访问生成项目所需的 .NET Core 包。</span><span class="sxs-lookup"><span data-stu-id="d0165-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![dotnet restore 命令](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="d0165-128">运行“Hello World”程序：</span><span class="sxs-lookup"><span data-stu-id="d0165-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="d0165-129">键入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="d0165-129">Type `dotnet run`.</span></span>

      ![dotnet run 命令](media/with-visual-studio-code/dotnet-run-command.png)

<span data-ttu-id="d0165-131">还可以观看简短的视频教程，以获取更多关于在 [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core)、[macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 或 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) 上进行安装的帮助。</span><span class="sxs-lookup"><span data-stu-id="d0165-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="d0165-132">调试</span><span class="sxs-lookup"><span data-stu-id="d0165-132">Debug</span></span>

1. <span data-ttu-id="d0165-133">单击打开 *Program.cs*。</span><span class="sxs-lookup"><span data-stu-id="d0165-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="d0165-134">在 Visual Studio Code 中首次打开 C# 文件时，会在编辑器中加载 [OmniSharp](https://www.omnisharp.net/)。</span><span class="sxs-lookup"><span data-stu-id="d0165-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![打开 Program.cs 文件](media/with-visual-studio-code/open-program-cs.png)

2. <span data-ttu-id="d0165-136">Visual Studio Code 会提示添加缺少的资产，以生成和调试应用。</span><span class="sxs-lookup"><span data-stu-id="d0165-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="d0165-137">选择 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="d0165-137">Select **Yes**.</span></span>

    ![提示添加缺少的资产](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="d0165-139">若要打开调试视图，请单击左侧菜单上的“调试”图标。</span><span class="sxs-lookup"><span data-stu-id="d0165-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![在 Visual Studio Code 中打开“调试”选项卡](media/with-visual-studio-code/open-debug-tab.png)

4. <span data-ttu-id="d0165-141">找到窗格最上面的绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="d0165-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="d0165-142">请确保已选择旁边下拉列表中的“`.NET Core Launch (console)`”。</span><span class="sxs-lookup"><span data-stu-id="d0165-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![在 Visual Studio Code 中选择“.NET Core”](media/with-visual-studio-code/select-net-core.png)

5. <span data-ttu-id="d0165-144">单击第 9 行旁边的编辑器边距（编辑器中行号左侧的空间）或者将文本光标移动到编辑器中的第 9 行并按 <kbd>F9</kbd>，为项目添加断点。</span><span class="sxs-lookup"><span data-stu-id="d0165-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![设置断点](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. <span data-ttu-id="d0165-146">要开始调试，请选择 <kbd>F5</kbd> 或绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="d0165-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="d0165-147">在到达你在上一步中设置的断点时，调试器会停止执行程序。</span><span class="sxs-lookup"><span data-stu-id="d0165-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="d0165-148">调试时，可以在左上角的窗格中查看局部变量，也可以使用调试控制台进行查看。</span><span class="sxs-lookup"><span data-stu-id="d0165-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

7. <span data-ttu-id="d0165-149">选择最上面的蓝色箭头以继续调试，或选择最上面的红色方块以停止调试。</span><span class="sxs-lookup"><span data-stu-id="d0165-149">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![在 Visual Studio Code 中运行并调试](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="d0165-151">若要详细了解如何使用 OmniSharp 在 Visual Studio Code 中进行 .NET Core 调试，以及相关的疑难解答提示，请参阅[有关设置 .NET Core 调试器的说明](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。</span><span class="sxs-lookup"><span data-stu-id="d0165-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="d0165-152">添加类</span><span class="sxs-lookup"><span data-stu-id="d0165-152">Add a class</span></span>

1. <span data-ttu-id="d0165-153">若要添加一个新类，请右键单击 VSCode Explorer 并选择“新文件”。</span><span class="sxs-lookup"><span data-stu-id="d0165-153">To add a new class right-click in the VSCode Explorer and select **New File**.</span></span> <span data-ttu-id="d0165-154">此操作会将新文件添加到在 VSCode 中打开的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d0165-154">This adds a new file to the folder you have open in VSCode.</span></span>
2. <span data-ttu-id="d0165-155">将文件命名为 `MyClass.cs`。</span><span class="sxs-lookup"><span data-stu-id="d0165-155">Name your file `MyClass.cs`.</span></span> <span data-ttu-id="d0165-156">必须在末尾使用 `.cs` 扩展名保存它，以便将其识别为 csharp 文件。</span><span class="sxs-lookup"><span data-stu-id="d0165-156">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
3. <span data-ttu-id="d0165-157">添加下面的代码，以创建第一个类。</span><span class="sxs-lookup"><span data-stu-id="d0165-157">Add the code below to create your first class.</span></span> <span data-ttu-id="d0165-158">确保包括正确的命名空间，以便可以从 `Program.cs` 文件引用它。</span><span class="sxs-lookup"><span data-stu-id="d0165-158">Make sure to include the correct namespace so you can reference it from your `Program.cs` file.</span></span>
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

4. <span data-ttu-id="d0165-159">通过添加下面的代码，从 `Program.cs` 中的主要方法调用新类。</span><span class="sxs-lookup"><span data-stu-id="d0165-159">Call your new class from your main method in `Program.cs` by adding the code below.</span></span>

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            MyClass c1 = new MyClass();
            Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
        }
    }
}
```

5. <span data-ttu-id="d0165-160">保存更改并再次运行程序。</span><span class="sxs-lookup"><span data-stu-id="d0165-160">Save your changes and run your program again.</span></span> <span data-ttu-id="d0165-161">新消息应显示追加的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0165-161">The new message should appear with the appended string.</span></span>
```console
> dotnet run
Hello World! Happy coding!
```

## <a name="faq"></a><span data-ttu-id="d0165-162">FAQ</span><span class="sxs-lookup"><span data-stu-id="d0165-162">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="d0165-163">缺少在 Visual Studio Code 中生成和调试 C# 所需的资产。</span><span class="sxs-lookup"><span data-stu-id="d0165-163">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="d0165-164">调试器显示“无配置”。</span><span class="sxs-lookup"><span data-stu-id="d0165-164">My debugger says "No Configuration."</span></span>

<span data-ttu-id="d0165-165">Visual Studio Code C# 扩展可生成用于生成和调试的资产。</span><span class="sxs-lookup"><span data-stu-id="d0165-165">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="d0165-166">首次打开 C# 项目时，Visual Studio Code 会提示用户生成这些资产。</span><span class="sxs-lookup"><span data-stu-id="d0165-166">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="d0165-167">如果当时并未生成这些资产，仍可以通过打开命令面板（“视图”>“命令面板”）并键入“>.NET：生成用于生成和调试的资产”来运行此命令。</span><span class="sxs-lookup"><span data-stu-id="d0165-167">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="d0165-168">选择此方法可生成所需的 .vscode、launch.json 和 tasks.jsonn 配置文件。</span><span class="sxs-lookup"><span data-stu-id="d0165-168">Selecting this generates the .vscode, launch.json, and tasks.json configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0165-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0165-169">See also</span></span>

- [<span data-ttu-id="d0165-170">设置 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d0165-170">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="d0165-171">在 Visual Studio Code 中进行调试</span><span class="sxs-lookup"><span data-stu-id="d0165-171">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
