---
title: "F # 在 Visual Studio 代码中使用 Ionide 入门"
description: "了解如何使用 F # 使用 Visual Studio Code 和 Ionide 插件套件。"
keywords: "visual f #、 f # 中，函数编程，.NET 中，Visual Studio Code，vscode Ionide"
author: cartermp
ms.author: phcart
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 49775139-082e-442f-b5a2-dd402399b5d2
ms.openlocfilehash: 336316eaf474f4c10d63657f178ce4a336ad7a54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="getting-started-with-f-in-visual-studio-code-with-ionide"></a><span data-ttu-id="63ecb-104">F # 在 Visual Studio 代码中使用 Ionide 入门</span><span class="sxs-lookup"><span data-stu-id="63ecb-104">Getting Started with F# in Visual Studio Code with Ionide</span></span>

<span data-ttu-id="63ecb-105">你可以编写 F # [Visual Studio Code](https://code.visualstudio.com)与[Ionide 插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)，若要获取与 IntelliSense 和基本代码重构更完美的跨平台的轻型 IDE 体验。</span><span class="sxs-lookup"><span data-stu-id="63ecb-105">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight IDE experience with IntelliSense and basic code refactorings.</span></span>  <span data-ttu-id="63ecb-106">请访问[Ionide.io](http://ionide.io)若要了解有关该插件套件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="63ecb-106">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63ecb-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="63ecb-107">Prerequisites</span></span>

<span data-ttu-id="63ecb-108">F # 4.0 或更高版本必须为使用 Ionide 你计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="63ecb-108">F# 4.0 or higher must be installed on your machine to use Ionide.</span></span>

<span data-ttu-id="63ecb-109">你还必须拥有[安装 git](https://git-scm.com/download)并在你的路径，以使上可用的项目模板中 Ionide 使用。</span><span class="sxs-lookup"><span data-stu-id="63ecb-109">You must also have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span>  <span data-ttu-id="63ecb-110">你可以验证它正确安装了，通过键入`git`命令 prompt.and 按在**Enter**。</span><span class="sxs-lookup"><span data-stu-id="63ecb-110">You can verify that it is installed correctly by typing `git` at a command prompt.and pressing **Enter**.</span></span>

### <a name="windows"></a><span data-ttu-id="63ecb-111">Windows</span><span class="sxs-lookup"><span data-stu-id="63ecb-111">Windows</span></span>

<span data-ttu-id="63ecb-112">如果你在 Windows 上，则必须安装 F # 的两个选项。</span><span class="sxs-lookup"><span data-stu-id="63ecb-112">If you're on Windows, you have two options for installing F#.</span></span>

<span data-ttu-id="63ecb-113">如果你已安装 Visual Studio，并且没有 F #，则可以[安装 Visual F # 工具](get-started-visual-studio.md#installing-f)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-113">If you've already installed Visual Studio and don't have F#, you can [Install the Visual F# Tools](get-started-visual-studio.md#installing-f).</span></span>  <span data-ttu-id="63ecb-114">这将安装所有必需的组件来编写、 编译和执行 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="63ecb-114">This will install all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="63ecb-115">如果你不想安装 Visual Studio，请按照以下说明：</span><span class="sxs-lookup"><span data-stu-id="63ecb-115">If you prefer not to install Visual Studio, use the following instructions:</span></span>

1. <span data-ttu-id="63ecb-116">安装[.NET Framework 4.5 或更高版本](https://www.microsoft.com/en-US/download/details.aspx?id=30653)如果你正在运行 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="63ecb-116">Install [.NET Framework 4.5 or higher](https://www.microsoft.com/en-US/download/details.aspx?id=30653) if you're running Windows 7.</span></span>  <span data-ttu-id="63ecb-117">如果你使用的 Windows 8 或更高版本，你不需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="63ecb-117">If you're using Windows 8 or higher, you do not need to do this.</span></span>

2. <span data-ttu-id="63ecb-118">为您的操作系统中安装 Windows SDK:</span><span class="sxs-lookup"><span data-stu-id="63ecb-118">Install the Windows SDK for your OS:</span></span>

    * [<span data-ttu-id="63ecb-119">Windows 10 SDK</span><span class="sxs-lookup"><span data-stu-id="63ecb-119">Windows 10 SDK</span></span>](https://dev.windows.com/en-US/downloads/windows-10-sdk)
    * [<span data-ttu-id="63ecb-120">Windows 8.1 SDK</span><span class="sxs-lookup"><span data-stu-id="63ecb-120">Windows 8.1 SDK</span></span>](http://msdn.microsoft.com/windows/desktop/bg162891)
    * [<span data-ttu-id="63ecb-121">Windows 8 SDK</span><span class="sxs-lookup"><span data-stu-id="63ecb-121">Windows 8 SDK</span></span>](http://msdn.microsoft.com/windows/hardware/hh852363.aspx)
    * [<span data-ttu-id="63ecb-122">Windows 7 SDK</span><span class="sxs-lookup"><span data-stu-id="63ecb-122">Windows 7 SDK</span></span>](http://www.microsoft.com/download/details.aspx?id=8279)

3. <span data-ttu-id="63ecb-123">安装[Microsoft Build 工具 2015年](https://www.microsoft.com/en-us/download/details.aspx?id=48159)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-123">Install the [Microsoft Build Tools 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48159).</span></span>  <span data-ttu-id="63ecb-124">你可能还需要安装[Microsoft 生成工具 2013年](https://www.microsoft.com/en-us/download/details.aspx?id=40760)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-124">You may also need to install [Microsoft Build Tools 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40760).</span></span>

4. <span data-ttu-id="63ecb-125">安装[Visual F # 工具](https://www.microsoft.com/en-us/download/details.aspx?id=48179)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-125">Install the [Visual F# Tools](https://www.microsoft.com/en-us/download/details.aspx?id=48179).</span></span>

<span data-ttu-id="63ecb-126">在 64 位 Windows 上的编译器和工具位于此处：</span><span class="sxs-lookup"><span data-stu-id="63ecb-126">On 64-bit Windows, the compiler and tools are located here:</span></span>

```
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

<span data-ttu-id="63ecb-127">在 32 位 Windows 上的编译器工具位于此处：</span><span class="sxs-lookup"><span data-stu-id="63ecb-127">On 32-bit Windows, the compiler tools are located here:</span></span>

```
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

<span data-ttu-id="63ecb-128">Ionide 会自动检测的编译器和工具，但如果不是，由于某种原因 （例如，Visual F # 工具已安装到其他目录），也可以手动添加包含的文件夹 (`...\Microsoft SDKs\F#\4.0`) 到你的路径。</span><span class="sxs-lookup"><span data-stu-id="63ecb-128">Ionide automatically detects the compiler and tools, but if it doesn't for some reason (for example, the Visual F# Tools were installed to a different directory), you can manually add the containing folder (`...\Microsoft SDKs\F#\4.0`) to your PATH.</span></span>

### <a name="macos"></a><span data-ttu-id="63ecb-129">macOS</span><span class="sxs-lookup"><span data-stu-id="63ecb-129">macOS</span></span>

<span data-ttu-id="63ecb-130">在 macOS，Ionide 使用[Mono](http://www.mono-project.com)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-130">On macOS, Ionide uses [Mono](http://www.mono-project.com).</span></span>  <span data-ttu-id="63ecb-131">在 macOS 上安装 Mono 的最简单方法是通过 Homebrew。</span><span class="sxs-lookup"><span data-stu-id="63ecb-131">The easiest way to install Mono on macOS is via Homebrew.</span></span>  <span data-ttu-id="63ecb-132">只需在你的终端键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="63ecb-132">Simply type the following into your terminal:</span></span>

```
brew install mono
```

### <a name="linux"></a><span data-ttu-id="63ecb-133">Linux</span><span class="sxs-lookup"><span data-stu-id="63ecb-133">Linux</span></span>

<span data-ttu-id="63ecb-134">在 Linux 上 Ionide 还使用[Mono](http://www.mono-project.com)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-134">On Linux, Ionide also uses [Mono](http://www.mono-project.com).</span></span>  <span data-ttu-id="63ecb-135">如果要在 Debian 或 Ubuntu 上，你可以使用以下各项：</span><span class="sxs-lookup"><span data-stu-id="63ecb-135">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="63ecb-136">安装 Visual Studio Code 和 Ionide 插件</span><span class="sxs-lookup"><span data-stu-id="63ecb-136">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="63ecb-137">你可以安装从 Visual Studio Code [code.visualstudio.com](https://code.visualstudio.com)网站。</span><span class="sxs-lookup"><span data-stu-id="63ecb-137">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span>  <span data-ttu-id="63ecb-138">之后，有两种方法可以找到 Ionide 插件：</span><span class="sxs-lookup"><span data-stu-id="63ecb-138">After that, there are two ways to find the Ionide plugin:</span></span>

1. <span data-ttu-id="63ecb-139">使用命令控制板 (Ctrl + Shift + P 在 Windows 上，⌘ + Shift + P 在 macOS，在 Linux 上的 Ctrl + Shift + P 上)，并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="63ecb-139">Use the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

    ```
    >ext install Ionide
    ```

2. <span data-ttu-id="63ecb-140">单击扩展图标并搜索"Ionide":</span><span class="sxs-lookup"><span data-stu-id="63ecb-140">Click the Extensions icon and search for "Ionide":</span></span>

    ![](media/getting-started-vscode/vscode-ext.png)

<span data-ttu-id="63ecb-141">F # 中，Visual Studio Code 中支持所需的唯一插件[Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-141">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>  <span data-ttu-id="63ecb-142">但是，你还可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)和，以获取[虚设](http://fsharp.github.io/FAKE/)支持和[Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[Paket](https://fsprojects.github.io/Paket/)支持。</span><span class="sxs-lookup"><span data-stu-id="63ecb-142">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) and to get [FAKE](http://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span>  <span data-ttu-id="63ecb-143">但是，伪造 Paket 以及其他 F # 社区工具来生成项目并分别管理依赖关系。</span><span class="sxs-lookup"><span data-stu-id="63ecb-143">FAKE and Paket are additonal F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="63ecb-144">使用 Ionide 创建第一个项目</span><span class="sxs-lookup"><span data-stu-id="63ecb-144">Creating your first project with Ionide</span></span>

<span data-ttu-id="63ecb-145">若要创建新的 F # 项目，打开 （你可以将其任意命名） 的新文件夹中的 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="63ecb-145">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

![](media/getting-started-vscode/vscode-open-dir.png)

<span data-ttu-id="63ecb-146">接下来，打开命令控制板 (Ctrl + Shift + P 在 Windows 上，⌘ + Shift + P 在 macOS，在 Linux 上的 Ctrl + Shift + P 上)，然后键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="63ecb-146">Next, open the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

```
>f#: New Project
```

<span data-ttu-id="63ecb-147">这由提供支持[伪造](https://github.com/fsharp-editing/Forge)项目。</span><span class="sxs-lookup"><span data-stu-id="63ecb-147">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>  <span data-ttu-id="63ecb-148">将显示如下所示的内容：</span><span class="sxs-lookup"><span data-stu-id="63ecb-148">You should see something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
<span data-ttu-id="63ecb-149">如果你看不到更高版本，请尝试通过在命令控制板中运行以下命令刷新模板： `>F#: Refresh Project Templates`。</span><span class="sxs-lookup"><span data-stu-id="63ecb-149">If you don't see the above, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="63ecb-150">选择"F #:: 新项目"通过点击**Enter**，会将你转到此步骤：</span><span class="sxs-lookup"><span data-stu-id="63ecb-150">Select "F#: New Project" by hitting **Enter**, which will take you to this step:</span></span>

![](media/getting-started-vscode/vscode-proj-type.png)

<span data-ttu-id="63ecb-151">这将选择用于特定类型的项目模板。</span><span class="sxs-lookup"><span data-stu-id="63ecb-151">This will select a template for a specific type of project.</span></span>  <span data-ttu-id="63ecb-152">如有相当多的选项在这里， [FsLab](http://fslab.org)数据科学的模板或[Suave](https://suave.io) Web 编程的模板。</span><span class="sxs-lookup"><span data-stu-id="63ecb-152">There are quite a few options here, such as an [FsLab](http://fslab.org) template for Data Science or [Suave](https://suave.io) template for Web Programming.</span></span>  <span data-ttu-id="63ecb-153">本文章将使用`classlib`模板，因此突出显示，并按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="63ecb-153">This article uses the `classlib` template, so highlight that and hit **Enter**.</span></span>  <span data-ttu-id="63ecb-154">然后将访问以下步骤：</span><span class="sxs-lookup"><span data-stu-id="63ecb-154">You will then reach the following step:</span></span>

![](media/getting-started-vscode/vscode-new-dir.png)

<span data-ttu-id="63ecb-155">这样就可以在不同的目录，如果你愿意创建项目。</span><span class="sxs-lookup"><span data-stu-id="63ecb-155">This lets you create the project in a different directory, if you like.</span></span>  <span data-ttu-id="63ecb-156">将其留空现在。</span><span class="sxs-lookup"><span data-stu-id="63ecb-156">Leave it blank for now.</span></span>  <span data-ttu-id="63ecb-157">它将在当前目录中创建项目。</span><span class="sxs-lookup"><span data-stu-id="63ecb-157">It will create the project in the current directory.</span></span>  <span data-ttu-id="63ecb-158">一旦你按**Enter**，就会达到以下步骤：</span><span class="sxs-lookup"><span data-stu-id="63ecb-158">Once you press **Enter**, you will reach the following step:</span></span>

![](media/getting-started-vscode/vscode-proj-name.png)

<span data-ttu-id="63ecb-159">这样，你将你的项目。</span><span class="sxs-lookup"><span data-stu-id="63ecb-159">This lets you name your project.</span></span>  <span data-ttu-id="63ecb-160">F # 使用[Pascal case](http://c2.com/cgi/wiki?PascalCase)项目名称。</span><span class="sxs-lookup"><span data-stu-id="63ecb-160">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span>  <span data-ttu-id="63ecb-161">本文章将使用`ClassLibraryDemo`作为名称。</span><span class="sxs-lookup"><span data-stu-id="63ecb-161">This article uses `ClassLibraryDemo` as the name.</span></span>  <span data-ttu-id="63ecb-162">已输入所需为你的项目的名称后, 命中**Enter**。</span><span class="sxs-lookup"><span data-stu-id="63ecb-162">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="63ecb-163">如果您遵循了前面的步骤步骤，你会获得 Visual Studio 代码工作区在左侧以如下所示：</span><span class="sxs-lookup"><span data-stu-id="63ecb-163">If you followed the previous step steps, you should get the Visual Studio Code Workspace on the left-hand side to look something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

<span data-ttu-id="63ecb-164">此模板生成的几种方法，你将找到有用：</span><span class="sxs-lookup"><span data-stu-id="63ecb-164">This template generates a few things you'll find useful:</span></span>

1. <span data-ttu-id="63ecb-165">F # 项目本身，底层`ClassLibraryDemo`文件夹。</span><span class="sxs-lookup"><span data-stu-id="63ecb-165">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="63ecb-166">添加通过包的正确的目录结构[ `Paket` ](http://fsprojects.github.io/Paket/)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-166">The correct directory structure for adding packages via [`Paket`](http://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="63ecb-167">跨平台生成脚本[ `FAKE` ](http://fsharp.github.io/FAKE/)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-167">A cross-platform build script with [`FAKE`](http://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="63ecb-168">`paket.exe`可以提取包并为你解决依赖项的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="63ecb-168">The `paket.exe` executable which can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="63ecb-169">A`.gitignore`文件如果你想要将此项目添加到基于 Git 的源控制。</span><span class="sxs-lookup"><span data-stu-id="63ecb-169">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="63ecb-170">编写一些代码</span><span class="sxs-lookup"><span data-stu-id="63ecb-170">Writing some code</span></span>

<span data-ttu-id="63ecb-171">打开*ClassLibraryDemo*文件夹。</span><span class="sxs-lookup"><span data-stu-id="63ecb-171">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="63ecb-172">你应看到以下文件：</span><span class="sxs-lookup"><span data-stu-id="63ecb-172">You should see the following files:</span></span>

1. <span data-ttu-id="63ecb-173">`ClassLibraryDemo.fs`定义的类具有的 F # 实现文件。</span><span class="sxs-lookup"><span data-stu-id="63ecb-173">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="63ecb-174">`CassLibraryDemo.fsproj`用于生成此项目的 F # 项目文件。</span><span class="sxs-lookup"><span data-stu-id="63ecb-174">`CassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="63ecb-175">`Script.fsx`一个 F # 脚本文件，其中加载的源文件。</span><span class="sxs-lookup"><span data-stu-id="63ecb-175">`Script.fsx`, an F# script file which loads the source file.</span></span>
4. <span data-ttu-id="63ecb-176">`paket.references`它指定项目依赖项的 Paket 文件。</span><span class="sxs-lookup"><span data-stu-id="63ecb-176">`paket.references`, a Paket file which specifies the project dependencies.</span></span>

<span data-ttu-id="63ecb-177">打开`Script.fsx`，并在末尾添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="63ecb-177">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="63ecb-178">此函数将一个单词转换为一种形式的[Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-178">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span>  <span data-ttu-id="63ecb-179">下一步是评估使用 F # 交互式 (FSI)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-179">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="63ecb-180">突出显示整个函数 （它应为长达 11 行）。</span><span class="sxs-lookup"><span data-stu-id="63ecb-180">Highlight the entire function (it should be 11 lines long).</span></span>  <span data-ttu-id="63ecb-181">一旦将突出显示，保存**Alt**密钥并点击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="63ecb-181">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span>  <span data-ttu-id="63ecb-182">你会注意到下面，弹出一个窗口，并且它应显示类似如下内容：</span><span class="sxs-lookup"><span data-stu-id="63ecb-182">You'll notice a window pop up below, and it should show something like this:</span></span>

![](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="63ecb-183">这未三项操作：</span><span class="sxs-lookup"><span data-stu-id="63ecb-183">This did three things:</span></span>

1. <span data-ttu-id="63ecb-184">它启动了 FSI 进程。</span><span class="sxs-lookup"><span data-stu-id="63ecb-184">It started the FSI process.</span></span>
2. <span data-ttu-id="63ecb-185">它通过 FSI 过程发送您突出显示的代码。</span><span class="sxs-lookup"><span data-stu-id="63ecb-185">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="63ecb-186">FSI 过程评估通过发送的代码。</span><span class="sxs-lookup"><span data-stu-id="63ecb-186">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="63ecb-187">因为通过发送[函数](../language-reference/functions/index.md)，现在，您可以调用该函数使用 FSI ！</span><span class="sxs-lookup"><span data-stu-id="63ecb-187">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span>  <span data-ttu-id="63ecb-188">在交互式窗口中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="63ecb-188">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="63ecb-189">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="63ecb-189">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="63ecb-190">现在，让我们以作为第一个字母元音并重试。</span><span class="sxs-lookup"><span data-stu-id="63ecb-190">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="63ecb-191">输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="63ecb-191">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="63ecb-192">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="63ecb-192">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="63ecb-193">该函数似乎按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="63ecb-193">The function appears to be working as expected.</span></span>  <span data-ttu-id="63ecb-194">祝贺你，你只需在 Visual Studio 代码中编写 F # 第一个函数，因此它使用评估 FSI ！</span><span class="sxs-lookup"><span data-stu-id="63ecb-194">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="63ecb-195">你可能已经注意到，用来终止 FSI 中行`;;`。</span><span class="sxs-lookup"><span data-stu-id="63ecb-195">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span>  <span data-ttu-id="63ecb-196">这是因为 FSI 可以输入多行。</span><span class="sxs-lookup"><span data-stu-id="63ecb-196">This is because FSI allows you to enter multiple lines.</span></span>  <span data-ttu-id="63ecb-197">`;;`末尾允许 FSI 知道完成代码。</span><span class="sxs-lookup"><span data-stu-id="63ecb-197">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="63ecb-198">说明代码</span><span class="sxs-lookup"><span data-stu-id="63ecb-198">Explaining the code</span></span>

<span data-ttu-id="63ecb-199">如果你不确定的代码实际如何操作，以下是分步向导。</span><span class="sxs-lookup"><span data-stu-id="63ecb-199">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="63ecb-200">如你所见，`toPigLatin`是一个函数以捕获将单词设置为其输入，并将其转换为该单词的 Pig Latin 表示形式。</span><span class="sxs-lookup"><span data-stu-id="63ecb-200">As you can see, `toPigLatin` is a function which takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span>  <span data-ttu-id="63ecb-201">此规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="63ecb-201">The rules for this are as follows:</span></span>

<span data-ttu-id="63ecb-202">如果在 word 中的第一个字符以元音开头，添加到单词末尾的"yay"。</span><span class="sxs-lookup"><span data-stu-id="63ecb-202">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span>  <span data-ttu-id="63ecb-203">如果它不会开始元音，移到单词末尾的第一个字符，并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="63ecb-203">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="63ecb-204">你可能已经注意到 FSI 中的以下：</span><span class="sxs-lookup"><span data-stu-id="63ecb-204">You may have noticed the following in FSI:</span></span>

```
val toPigLatin : word:string -> string
```

<span data-ttu-id="63ecb-205">这表明`toPigLatin`是一个函数中采用`string`作为输入 (调用`word`)，并返回另一个`string`。</span><span class="sxs-lookup"><span data-stu-id="63ecb-205">This states that `toPigLatin` is a function which takes in a `string` as input (called `word`), and returns another `string`.</span></span>  <span data-ttu-id="63ecb-206">这称为[函数类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/)，F # 的关键在于了解 F # 代码的基础部分。</span><span class="sxs-lookup"><span data-stu-id="63ecb-206">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span>  <span data-ttu-id="63ecb-207">如果将鼠标悬停在 Visual Studio 代码中的函数，将还会发现此情况。</span><span class="sxs-lookup"><span data-stu-id="63ecb-207">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="63ecb-208">在函数正文中，你会注意到两个不同的部分：</span><span class="sxs-lookup"><span data-stu-id="63ecb-208">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="63ecb-209">内部函数调用`isVowel`，它确定如果给定的字符 (`c`) 元音方法是检查如果它通过提供的模式之一匹配的[模式匹配](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="63ecb-209">An inner function, called `isVowel`, which determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="63ecb-210">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md)基于 if 的第一个字符的检查，如果第一个字符为元音的元素，并构造外的输入字符的返回值的表达式是元音还是失败：</span><span class="sxs-lookup"><span data-stu-id="63ecb-210">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression which checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="63ecb-211">流`toPigLatin`因此它也是：</span><span class="sxs-lookup"><span data-stu-id="63ecb-211">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="63ecb-212">检查输入的单词的第一个字符是否元音。</span><span class="sxs-lookup"><span data-stu-id="63ecb-212">Check if the first character of the input word is a vowel.</span></span>  <span data-ttu-id="63ecb-213">如果是，附加到单词末尾的"yay"。</span><span class="sxs-lookup"><span data-stu-id="63ecb-213">If it is, attach "yay" to the end of the word.</span></span>  <span data-ttu-id="63ecb-214">否则为移动到单词末尾的第一个字符并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="63ecb-214">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="63ecb-215">没有最后一件要有关此注意的事情： 没有返回从函数，不同于很多其他语言有无显式指令。</span><span class="sxs-lookup"><span data-stu-id="63ecb-215">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span>  <span data-ttu-id="63ecb-216">这是因为 F # 是基于表达式的和的函数体中的最后一个表达式是返回值。</span><span class="sxs-lookup"><span data-stu-id="63ecb-216">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span>  <span data-ttu-id="63ecb-217">因为`if..then..else`本身是一个表达式，正文`then`块或正文`else`块将根据输入的值返回。</span><span class="sxs-lookup"><span data-stu-id="63ecb-217">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="63ecb-218">将你的脚本代码移动到实现文件</span><span class="sxs-lookup"><span data-stu-id="63ecb-218">Moving your script code into the implementation file</span></span>

<span data-ttu-id="63ecb-219">在本文前面部分所示编写 F # 代码的常见第一步： 编写初始函数，然后以交互方式使用 FSI 执行它。</span><span class="sxs-lookup"><span data-stu-id="63ecb-219">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span>  <span data-ttu-id="63ecb-220">这称为 REPL 驱动的开发，REPL 其中代表"读取-计算-打印循环"。</span><span class="sxs-lookup"><span data-stu-id="63ecb-220">This is known as REPL-driven development, where REPL stands for "Read-Evaluate-Print Loop".</span></span>  <span data-ttu-id="63ecb-221">它是在将某产品投入使用之前，尝试使用功能的好方法。</span><span class="sxs-lookup"><span data-stu-id="63ecb-221">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="63ecb-222">REPL 驱动的开发的下一步是将运行的代码移到 F # 实现文件。</span><span class="sxs-lookup"><span data-stu-id="63ecb-222">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span>  <span data-ttu-id="63ecb-223">它可以然后编译器编译的 F # 成可执行程序集。</span><span class="sxs-lookup"><span data-stu-id="63ecb-223">It can then be compiled by the F# compiler into an assembly which can be executed.</span></span>

<span data-ttu-id="63ecb-224">若要开始，打开`ClassLibraryDemo.fs`。</span><span class="sxs-lookup"><span data-stu-id="63ecb-224">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="63ecb-225">你会注意到某些代码已在存在。</span><span class="sxs-lookup"><span data-stu-id="63ecb-225">You'll notice that some code is already in there.</span></span>  <span data-ttu-id="63ecb-226">请继续并删除类定义中，但请确保让[ `namespace` ](../language-reference/namespaces.md)顶部的声明。</span><span class="sxs-lookup"><span data-stu-id="63ecb-226">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="63ecb-227">接下来，创建一个新[ `module` ](../language-reference/modules.md)调用`PigLatin`和复制`toPigLatin`函数导入到它在这种：</span><span class="sxs-lookup"><span data-stu-id="63ecb-227">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="63ecb-228">这是如果你还想要从 C# 或 Visual Basic 项目中调用你的代码，你可以组织在 F # 代码中，函数和常用的方法的各种方法之一。</span><span class="sxs-lookup"><span data-stu-id="63ecb-228">This is one of the many ways you can organize functions in F# code, and a common approach if you also want to call your code from C# or Visual Basic projects.</span></span>

<span data-ttu-id="63ecb-229">接下来，打开`Script.fsx`再次，文件并删除整个`toPigLatin`起作用，但请确保在文件中保留以下两行：</span><span class="sxs-lookup"><span data-stu-id="63ecb-229">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="63ecb-230">FSI 编写脚本来加载需要的第一行`ClassLibraryDemo.fs`。</span><span class="sxs-lookup"><span data-stu-id="63ecb-230">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="63ecb-231">第二行是一种便于： 省略它是可选的但你将需要键入`open ClassLibraryDemo`FSI 窗口如果你想要使中`ToPigLatin`纳入范围的模块。</span><span class="sxs-lookup"><span data-stu-id="63ecb-231">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="63ecb-232">接下来，在 FSI 窗口中，调用具有的函数`PigLatin`前面定义的模块：</span><span class="sxs-lookup"><span data-stu-id="63ecb-232">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="63ecb-233">成功！</span><span class="sxs-lookup"><span data-stu-id="63ecb-233">Success!</span></span>  <span data-ttu-id="63ecb-234">获取与之前相同的结果，但现在从 F # 实现文件加载。</span><span class="sxs-lookup"><span data-stu-id="63ecb-234">You get the same results as before, but now loaded from an F# implementation file.</span></span>  <span data-ttu-id="63ecb-235">此处的主要差别在于 F # 源代码文件被编译到的任何位置，就可以不只是在 FSI 中执行程序集。</span><span class="sxs-lookup"><span data-stu-id="63ecb-235">The major difference here is that F# source files are compiled into assemblies which can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="63ecb-236">摘要</span><span class="sxs-lookup"><span data-stu-id="63ecb-236">Summary</span></span>

<span data-ttu-id="63ecb-237">在本文中，你已了解：</span><span class="sxs-lookup"><span data-stu-id="63ecb-237">In this article, you've learned:</span></span>

1. <span data-ttu-id="63ecb-238">如何设置与 Ionide 的 Visual Studio 代码。</span><span class="sxs-lookup"><span data-stu-id="63ecb-238">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="63ecb-239">如何使用 Ionide 创建第一个 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="63ecb-239">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="63ecb-240">如何使用 F # 脚本在 Ionide 中编写 F # 第一个函数，则在 FSI 中执行它。</span><span class="sxs-lookup"><span data-stu-id="63ecb-240">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="63ecb-241">如何将你的脚本代码迁移到 F # 源代码，然后从 FSI 调用该代码。</span><span class="sxs-lookup"><span data-stu-id="63ecb-241">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="63ecb-242">你现在正在配备编写更多的 F # 代码使用 Visual Studio Code 和 Ionide。</span><span class="sxs-lookup"><span data-stu-id="63ecb-242">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="63ecb-243">疑难解答</span><span class="sxs-lookup"><span data-stu-id="63ecb-243">Troubleshooting</span></span>

<span data-ttu-id="63ecb-244">以下是可解决可能会遇到某些问题的几个方法：</span><span class="sxs-lookup"><span data-stu-id="63ecb-244">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="63ecb-245">若要获取的代码编辑功能 Ionide，F # 文件需要保存到磁盘，以及在 Visual Studio Code 工作区中处于打开状态的文件夹内。</span><span class="sxs-lookup"><span data-stu-id="63ecb-245">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="63ecb-246">如果你对系统进行更改或使用打开的 Visual Studio Code 安装 Ionide 系统必备组件，重新启动 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="63ecb-246">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="63ecb-247">检查可使用 F # 编译器和 F # interactive 中没有的完全限定路径的命令行。</span><span class="sxs-lookup"><span data-stu-id="63ecb-247">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span>  <span data-ttu-id="63ecb-248">你可以通过键入来实现`fsc`F # 编译器的命令行中和`fsi`或`fsharpi`Visual F # 工具在 Windows 和 Mac/Linux 上的 Mono 上分别。</span><span class="sxs-lookup"><span data-stu-id="63ecb-248">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="63ecb-249">如果你已在你项目目录中的无效字符，Ionide 可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="63ecb-249">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="63ecb-250">如果出现这种情况，重命名你的项目目录。</span><span class="sxs-lookup"><span data-stu-id="63ecb-250">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="63ecb-251">如果使用无 Ionide 命令，请检查你[Visual Studio Code 键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)若要查看如果你要重写这些意外。</span><span class="sxs-lookup"><span data-stu-id="63ecb-251">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="63ecb-252">如果在您的计算机上中断 Ionide 和上述任何具有固定你的问题，请尝试删除`ionide-fsharp`目录在你的计算机上，然后重新安装的插件套件。</span><span class="sxs-lookup"><span data-stu-id="63ecb-252">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="63ecb-253">Ionide 是开放源代码项目生成和维护由 F # 社区的成员。</span><span class="sxs-lookup"><span data-stu-id="63ecb-253">Ionide is an open source project built and maintained by members of the F# community.</span></span>  <span data-ttu-id="63ecb-254">请报告问题并随意在参与[Ionide VSCode: FSharp GitHub 存储库](https://github.com/ionide/ionide-vscode-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-254">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="63ecb-255">如果你有报告的问题，请遵循[获取日志报告问题时要使用的说明](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-255">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="63ecb-256">你还可以请求更多帮助从 Ionide 开发人员和 F # 中的社区[Ionide Gitter 通道](https://gitter.im/ionide/ionide-project)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-256">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="63ecb-257">后续步骤</span><span class="sxs-lookup"><span data-stu-id="63ecb-257">Next steps</span></span>

<span data-ttu-id="63ecb-258">若要了解有关 F # 和语言的功能的详细信息，请查看[教程的 F #](../tour.md)。</span><span class="sxs-lookup"><span data-stu-id="63ecb-258">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="63ecb-259">请参阅</span><span class="sxs-lookup"><span data-stu-id="63ecb-259">See also</span></span>

[<span data-ttu-id="63ecb-260">F# 教程</span><span class="sxs-lookup"><span data-stu-id="63ecb-260">Tour of F#</span></span>](../tour.md)

[<span data-ttu-id="63ecb-261">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="63ecb-261">F# Language Reference</span></span>](../language-reference/index.md)

[<span data-ttu-id="63ecb-262">函数</span><span class="sxs-lookup"><span data-stu-id="63ecb-262">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="63ecb-263">模块</span><span class="sxs-lookup"><span data-stu-id="63ecb-263">Modules</span></span>](../language-reference/modules.md)

[<span data-ttu-id="63ecb-264">命名空间</span><span class="sxs-lookup"><span data-stu-id="63ecb-264">Namespaces</span></span>](../language-reference/namespaces.md)

[<span data-ttu-id="63ecb-265">Ionide VSCode: FSharp</span><span class="sxs-lookup"><span data-stu-id="63ecb-265">Ionide-VSCode: FSharp</span></span>](https://github.com/ionide/ionide-vscode-fsharp)
