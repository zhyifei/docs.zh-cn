---
title: '要开始使用 Visual Studio 代码中的 F #'
description: '了解如何使用 F # 使用 Visual Studio Code 和 Ionide 插件套件。'
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2018
ms.locfileid: "34728623"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="5b997-103">要开始使用 Visual Studio 代码中的 F #</span><span class="sxs-lookup"><span data-stu-id="5b997-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="5b997-104">你可以编写 F # [Visual Studio Code](https://code.visualstudio.com)与[Ionide 插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)，若要获取与 IntelliSense 和基本代码的极佳跨平台的轻型集成开发环境 (IDE) 体验重构。</span><span class="sxs-lookup"><span data-stu-id="5b997-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="5b997-105">请访问[Ionide.io](http://ionide.io)若要了解有关该插件套件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b997-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b997-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="5b997-106">Prerequisites</span></span>

<span data-ttu-id="5b997-107">你必须具有[安装 git](https://git-scm.com/download)并在你的路径，以使上可用的项目模板中 Ionide 使用。</span><span class="sxs-lookup"><span data-stu-id="5b997-107">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span> <span data-ttu-id="5b997-108">你可以验证它正确安装了，通过键入`git --version`在命令提示符处并按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5b997-108">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="5b997-109">macOS</span><span class="sxs-lookup"><span data-stu-id="5b997-109">macOS</span></span>](#tab/macos)

<span data-ttu-id="5b997-110">Ionide 使用[Mono](http://www.mono-project.com)。</span><span class="sxs-lookup"><span data-stu-id="5b997-110">Ionide uses [Mono](http://www.mono-project.com).</span></span> <span data-ttu-id="5b997-111">在 macOS 上安装 Mono 的最简单方法是通过 Homebrew。</span><span class="sxs-lookup"><span data-stu-id="5b997-111">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="5b997-112">只需在你的终端键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5b997-112">Simply type the following into your terminal:</span></span>

```
brew install mono
```

<span data-ttu-id="5b997-113">你还必须安装[.NET 核心 SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="5b997-113">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="5b997-114">Linux</span><span class="sxs-lookup"><span data-stu-id="5b997-114">Linux</span></span>](#tab/linux)

<span data-ttu-id="5b997-115">在 Linux 上 Ionide 还使用[Mono](https://www.mono-project.com)。</span><span class="sxs-lookup"><span data-stu-id="5b997-115">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="5b997-116">如果要在 Debian 或 Ubuntu 上，你可以使用以下各项：</span><span class="sxs-lookup"><span data-stu-id="5b997-116">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="5b997-117">你还必须安装[.NET 核心 SDK](https://www.microsoft.com/net/download)。</span><span class="sxs-lookup"><span data-stu-id="5b997-117">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="5b997-118">Windows</span><span class="sxs-lookup"><span data-stu-id="5b997-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="5b997-119">如果你在 Windows 上，你必须[使用 F # 支持安装 Visual Studio](get-started-visual-studio.md#installing-f)。</span><span class="sxs-lookup"><span data-stu-id="5b997-119">If you're on Windows, you must [install Visual Studio with F# support](get-started-visual-studio.md#installing-f).</span></span> <span data-ttu-id="5b997-120">这将安装所有必需的组件来编写、 编译和执行 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="5b997-120">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="5b997-121">你还必须安装[.NET 核心 SDK](https://www.microsoft.com/net/download/)。</span><span class="sxs-lookup"><span data-stu-id="5b997-121">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="5b997-122">安装 Visual Studio Code 和 Ionide 插件</span><span class="sxs-lookup"><span data-stu-id="5b997-122">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="5b997-123">你可以安装从 Visual Studio Code [code.visualstudio.com](https://code.visualstudio.com)网站。</span><span class="sxs-lookup"><span data-stu-id="5b997-123">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span>

<span data-ttu-id="5b997-124">接下来，请单击扩展图标和"Ionide"搜索:</span><span class="sxs-lookup"><span data-stu-id="5b997-124">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="5b997-125">F # 中，Visual Studio Code 中支持所需的唯一插件[Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="5b997-125">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="5b997-126">但是，你还可以安装[Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)获取[虚设](https://fsharp.github.io/FAKE/)支持和[Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)获取[Paket](https://fsprojects.github.io/Paket/)支持。</span><span class="sxs-lookup"><span data-stu-id="5b997-126">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="5b997-127">但是，伪造 Paket 以及其他 F # 社区工具来生成项目并管理依赖项，分别。</span><span class="sxs-lookup"><span data-stu-id="5b997-127">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="5b997-128">使用 Ionide 创建第一个项目</span><span class="sxs-lookup"><span data-stu-id="5b997-128">Creating your first project with Ionide</span></span>

<span data-ttu-id="5b997-129">若要创建新的 F # 项目，打开 （你可以将其任意命名） 的新文件夹中的 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="5b997-129">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="5b997-130">接下来，打开命令调色板 (**视图 > 命令调色板**) 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="5b997-130">Next, open the command pallette (**View > Command Pallette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="5b997-131">这由提供支持[伪造](https://github.com/fsharp-editing/Forge)项目。</span><span class="sxs-lookup"><span data-stu-id="5b997-131">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
<span data-ttu-id="5b997-132">如果你未看到模板选项，请尝试通过在命令控制板中运行以下命令刷新模板： `>F#: Refresh Project Templates`。</span><span class="sxs-lookup"><span data-stu-id="5b997-132">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="5b997-133">选择"F #:: 新项目"通过点击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5b997-133">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="5b997-134">将你转到下一步，即对于选择的项目模板。</span><span class="sxs-lookup"><span data-stu-id="5b997-134">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="5b997-135">选取`classlib`模板和命中**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5b997-135">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="5b997-136">接下来，选择一个目录来创建的项目中。</span><span class="sxs-lookup"><span data-stu-id="5b997-136">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="5b997-137">如果你将其留空，则使用当前目录。</span><span class="sxs-lookup"><span data-stu-id="5b997-137">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="5b997-138">最后，命名你的项目中的最后一步。</span><span class="sxs-lookup"><span data-stu-id="5b997-138">Finally, name your project in the final step.</span></span> <span data-ttu-id="5b997-139">F # 使用[Pascal case](http://c2.com/cgi/wiki?PascalCase)项目名称。</span><span class="sxs-lookup"><span data-stu-id="5b997-139">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="5b997-140">本文章将使用`ClassLibraryDemo`作为名称。</span><span class="sxs-lookup"><span data-stu-id="5b997-140">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="5b997-141">已输入所需为你的项目的名称后, 命中**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5b997-141">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="5b997-142">如果您遵循上一步，你会获得 Visual Studio 代码上的工作区的左侧显示替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="5b997-142">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="5b997-143">F # 项目本身，底层`ClassLibraryDemo`文件夹。</span><span class="sxs-lookup"><span data-stu-id="5b997-143">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="5b997-144">添加通过包的正确的目录结构[ `Paket` ](https://fsprojects.github.io/Paket/)。</span><span class="sxs-lookup"><span data-stu-id="5b997-144">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="5b997-145">跨平台生成脚本[ `FAKE` ](https://fsharp.github.io/FAKE/)。</span><span class="sxs-lookup"><span data-stu-id="5b997-145">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="5b997-146">`paket.exe`可以提取包并为你解决依赖项的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="5b997-146">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="5b997-147">A`.gitignore`文件如果你想要将此项目添加到基于 Git 的源控制。</span><span class="sxs-lookup"><span data-stu-id="5b997-147">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="5b997-148">编写一些代码</span><span class="sxs-lookup"><span data-stu-id="5b997-148">Writing some code</span></span>

<span data-ttu-id="5b997-149">打开*ClassLibraryDemo*文件夹。</span><span class="sxs-lookup"><span data-stu-id="5b997-149">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="5b997-150">你应看到以下文件：</span><span class="sxs-lookup"><span data-stu-id="5b997-150">You should see the following files:</span></span>

1. <span data-ttu-id="5b997-151">`ClassLibraryDemo.fs`定义的类具有的 F # 实现文件。</span><span class="sxs-lookup"><span data-stu-id="5b997-151">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="5b997-152">`ClassLibraryDemo.fsproj`用于生成此项目的 F # 项目文件。</span><span class="sxs-lookup"><span data-stu-id="5b997-152">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="5b997-153">`Script.fsx`加载的源文件的 F # 脚本文件。</span><span class="sxs-lookup"><span data-stu-id="5b997-153">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="5b997-154">`paket.references`指定项目依赖项的 Paket 文件。</span><span class="sxs-lookup"><span data-stu-id="5b997-154">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="5b997-155">打开`Script.fsx`，并在末尾添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5b997-155">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="5b997-156">此函数将一个单词转换为一种形式的[Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)。</span><span class="sxs-lookup"><span data-stu-id="5b997-156">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="5b997-157">下一步是评估使用 F # 交互式 (FSI)。</span><span class="sxs-lookup"><span data-stu-id="5b997-157">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="5b997-158">突出显示整个函数 （它应为长达 11 行）。</span><span class="sxs-lookup"><span data-stu-id="5b997-158">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="5b997-159">一旦将突出显示，保存**Alt**密钥并点击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="5b997-159">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="5b997-160">你会注意到下面，弹出一个窗口，并且它应显示类似如下内容：</span><span class="sxs-lookup"><span data-stu-id="5b997-160">You'll notice a window pop up below, and it should show something like this:</span></span>

![与 Ionide F # Interactive 输出的示例](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="5b997-162">这未三项操作：</span><span class="sxs-lookup"><span data-stu-id="5b997-162">This did three things:</span></span>

1. <span data-ttu-id="5b997-163">它启动了 FSI 进程。</span><span class="sxs-lookup"><span data-stu-id="5b997-163">It started the FSI process.</span></span>
2. <span data-ttu-id="5b997-164">它通过 FSI 过程发送您突出显示的代码。</span><span class="sxs-lookup"><span data-stu-id="5b997-164">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="5b997-165">FSI 过程评估通过发送的代码。</span><span class="sxs-lookup"><span data-stu-id="5b997-165">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="5b997-166">因为通过发送[函数](../language-reference/functions/index.md)，现在，您可以调用该函数使用 FSI ！</span><span class="sxs-lookup"><span data-stu-id="5b997-166">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="5b997-167">在交互式窗口中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="5b997-167">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="5b997-168">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="5b997-168">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="5b997-169">现在，让我们以作为第一个字母元音并重试。</span><span class="sxs-lookup"><span data-stu-id="5b997-169">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="5b997-170">输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5b997-170">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="5b997-171">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="5b997-171">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="5b997-172">该函数似乎按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="5b997-172">The function appears to be working as expected.</span></span> <span data-ttu-id="5b997-173">祝贺你，你只需在 Visual Studio 代码中编写 F # 第一个函数，因此它使用评估 FSI ！</span><span class="sxs-lookup"><span data-stu-id="5b997-173">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="5b997-174">你可能已经注意到，用来终止 FSI 中行`;;`。</span><span class="sxs-lookup"><span data-stu-id="5b997-174">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="5b997-175">这是因为 FSI 可以输入多行。</span><span class="sxs-lookup"><span data-stu-id="5b997-175">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="5b997-176">`;;`末尾允许 FSI 知道完成代码。</span><span class="sxs-lookup"><span data-stu-id="5b997-176">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="5b997-177">说明代码</span><span class="sxs-lookup"><span data-stu-id="5b997-177">Explaining the code</span></span>

<span data-ttu-id="5b997-178">如果你不确定的代码实际如何操作，以下是分步向导。</span><span class="sxs-lookup"><span data-stu-id="5b997-178">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="5b997-179">如你所见，`toPigLatin`是一个函数，它接受将单词设置为其输入，并将其转换为该单词的 Pig Latin 表示形式。</span><span class="sxs-lookup"><span data-stu-id="5b997-179">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="5b997-180">此规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b997-180">The rules for this are as follows:</span></span>

<span data-ttu-id="5b997-181">如果在 word 中的第一个字符以元音开头，添加到单词末尾的"yay"。</span><span class="sxs-lookup"><span data-stu-id="5b997-181">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="5b997-182">如果它不会开始元音，移到单词末尾的第一个字符，并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="5b997-182">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="5b997-183">你可能已经注意到 FSI 中的以下：</span><span class="sxs-lookup"><span data-stu-id="5b997-183">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="5b997-184">这表明`toPigLatin`是采用一个函数`string`作为输入 (调用`word`)，并返回另一个`string`。</span><span class="sxs-lookup"><span data-stu-id="5b997-184">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="5b997-185">这称为[函数类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/)，F # 的关键在于了解 F # 代码的基础部分。</span><span class="sxs-lookup"><span data-stu-id="5b997-185">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="5b997-186">如果将鼠标悬停在 Visual Studio 代码中的函数，将还会发现此情况。</span><span class="sxs-lookup"><span data-stu-id="5b997-186">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="5b997-187">在函数正文中，你会注意到两个不同的部分：</span><span class="sxs-lookup"><span data-stu-id="5b997-187">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="5b997-188">内部函数调用`isVowel`，如果给定的字符，它确定 (`c`) 元音方法是检查如果它通过提供的模式之一匹配的[模式匹配](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="5b997-188">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="5b997-189">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md)检查是否第一个字符为元音的元素，并基于 if 的第一个字符构造外的输入字符的返回值的表达式是元音还是失败：</span><span class="sxs-lookup"><span data-stu-id="5b997-189">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="5b997-190">流`toPigLatin`因此它也是：</span><span class="sxs-lookup"><span data-stu-id="5b997-190">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="5b997-191">检查输入的单词的第一个字符是否元音。</span><span class="sxs-lookup"><span data-stu-id="5b997-191">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="5b997-192">如果是，附加到单词末尾的"yay"。</span><span class="sxs-lookup"><span data-stu-id="5b997-192">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="5b997-193">否则为移动到单词末尾的第一个字符并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="5b997-193">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="5b997-194">没有最后一件要有关此注意的事情： 没有返回从函数，不同于很多其他语言有无显式指令。</span><span class="sxs-lookup"><span data-stu-id="5b997-194">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="5b997-195">这是因为 F # 是基于表达式的和的函数体中的最后一个表达式是返回值。</span><span class="sxs-lookup"><span data-stu-id="5b997-195">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="5b997-196">因为`if..then..else`本身是一个表达式，正文`then`块或正文`else`块将根据输入的值返回。</span><span class="sxs-lookup"><span data-stu-id="5b997-196">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="5b997-197">将你的脚本代码移动到实现文件</span><span class="sxs-lookup"><span data-stu-id="5b997-197">Moving your script code into the implementation file</span></span>

<span data-ttu-id="5b997-198">在本文前面部分所示编写 F # 代码的常见第一步： 编写初始函数，然后以交互方式使用 FSI 执行它。</span><span class="sxs-lookup"><span data-stu-id="5b997-198">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="5b997-199">这称为 REPL 驱动开发，其中[REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)代表"读取-计算-打印循环"。</span><span class="sxs-lookup"><span data-stu-id="5b997-199">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="5b997-200">它是在将某产品投入使用之前，尝试使用功能的好方法。</span><span class="sxs-lookup"><span data-stu-id="5b997-200">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="5b997-201">REPL 驱动的开发的下一步是将运行的代码移到 F # 实现文件。</span><span class="sxs-lookup"><span data-stu-id="5b997-201">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="5b997-202">它可以然后编译器编译的 F # 到可执行的程序集中。</span><span class="sxs-lookup"><span data-stu-id="5b997-202">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="5b997-203">若要开始，打开`ClassLibraryDemo.fs`。</span><span class="sxs-lookup"><span data-stu-id="5b997-203">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="5b997-204">你会注意到某些代码已在存在。</span><span class="sxs-lookup"><span data-stu-id="5b997-204">You'll notice that some code is already in there.</span></span> <span data-ttu-id="5b997-205">请继续并删除类定义中，但请确保让[ `namespace` ](../language-reference/namespaces.md)顶部的声明。</span><span class="sxs-lookup"><span data-stu-id="5b997-205">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="5b997-206">接下来，创建一个新[ `module` ](../language-reference/modules.md)调用`PigLatin`和复制`toPigLatin`函数导入到它在这种：</span><span class="sxs-lookup"><span data-stu-id="5b997-206">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="5b997-207">接下来，打开`Script.fsx`再次，文件并删除整个`toPigLatin`起作用，但请确保在文件中保留以下两行：</span><span class="sxs-lookup"><span data-stu-id="5b997-207">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="5b997-208">FSI 编写脚本来加载需要的第一行`ClassLibraryDemo.fs`。</span><span class="sxs-lookup"><span data-stu-id="5b997-208">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span> <span data-ttu-id="5b997-209">第二行是一种便于： 省略它是可选的但你将需要键入`open ClassLibraryDemo`FSI 窗口如果你想要使中`ToPigLatin`纳入范围的模块。</span><span class="sxs-lookup"><span data-stu-id="5b997-209">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="5b997-210">接下来，在 FSI 窗口中，调用具有的函数`PigLatin`前面定义的模块：</span><span class="sxs-lookup"><span data-stu-id="5b997-210">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="5b997-211">成功！</span><span class="sxs-lookup"><span data-stu-id="5b997-211">Success!</span></span> <span data-ttu-id="5b997-212">获取与之前相同的结果，但现在从 F # 实现文件加载。</span><span class="sxs-lookup"><span data-stu-id="5b997-212">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="5b997-213">此处的主要区别是，将 F # 源代码文件编译成可以不只是在 FSI 中任意位置，执行的程序集。</span><span class="sxs-lookup"><span data-stu-id="5b997-213">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="5b997-214">总结</span><span class="sxs-lookup"><span data-stu-id="5b997-214">Summary</span></span>

<span data-ttu-id="5b997-215">在本文中，你已了解：</span><span class="sxs-lookup"><span data-stu-id="5b997-215">In this article, you've learned:</span></span>

1. <span data-ttu-id="5b997-216">如何设置与 Ionide 的 Visual Studio 代码。</span><span class="sxs-lookup"><span data-stu-id="5b997-216">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="5b997-217">如何使用 Ionide 创建第一个 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="5b997-217">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="5b997-218">如何使用 F # 脚本在 Ionide 中编写 F # 第一个函数，则在 FSI 中执行它。</span><span class="sxs-lookup"><span data-stu-id="5b997-218">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="5b997-219">如何将你的脚本代码迁移到 F # 源代码，然后从 FSI 调用该代码。</span><span class="sxs-lookup"><span data-stu-id="5b997-219">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="5b997-220">你现在正在配备编写更多的 F # 代码使用 Visual Studio Code 和 Ionide。</span><span class="sxs-lookup"><span data-stu-id="5b997-220">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5b997-221">疑难解答</span><span class="sxs-lookup"><span data-stu-id="5b997-221">Troubleshooting</span></span>

<span data-ttu-id="5b997-222">以下是可解决可能会遇到某些问题的几个方法：</span><span class="sxs-lookup"><span data-stu-id="5b997-222">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="5b997-223">若要获取的代码编辑功能 Ionide，F # 文件需要保存到磁盘，以及在 Visual Studio Code 工作区中处于打开状态的文件夹内。</span><span class="sxs-lookup"><span data-stu-id="5b997-223">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="5b997-224">如果你对系统进行更改或使用打开的 Visual Studio Code 安装 Ionide 系统必备组件，重新启动 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="5b997-224">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="5b997-225">检查可使用 F # 编译器和 F # interactive 中没有的完全限定路径的命令行。</span><span class="sxs-lookup"><span data-stu-id="5b997-225">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="5b997-226">你可以通过键入来实现`fsc`F # 编译器的命令行中和`fsi`或`fsharpi`Visual F # 工具在 Windows 和 Mac/Linux 上的 Mono 上分别。</span><span class="sxs-lookup"><span data-stu-id="5b997-226">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="5b997-227">如果你已在你项目目录中的无效字符，Ionide 可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="5b997-227">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="5b997-228">如果出现这种情况，重命名你的项目目录。</span><span class="sxs-lookup"><span data-stu-id="5b997-228">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="5b997-229">如果使用无 Ionide 命令，请检查你[Visual Studio Code 键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)若要查看如果你要重写这些意外。</span><span class="sxs-lookup"><span data-stu-id="5b997-229">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="5b997-230">如果在您的计算机上中断 Ionide 和上述任何具有固定你的问题，请尝试删除`ionide-fsharp`目录在你的计算机上，然后重新安装的插件套件。</span><span class="sxs-lookup"><span data-stu-id="5b997-230">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="5b997-231">Ionide 是开放源代码项目生成和维护由 F # 社区的成员。</span><span class="sxs-lookup"><span data-stu-id="5b997-231">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="5b997-232">请报告问题并随意在参与[Ionide VSCode: FSharp GitHub 存储库](https://github.com/ionide/ionide-vscode-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="5b997-232">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="5b997-233">如果你有报告的问题，请遵循[获取日志报告问题时要使用的说明](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)。</span><span class="sxs-lookup"><span data-stu-id="5b997-233">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="5b997-234">你还可以请求更多帮助从 Ionide 开发人员和 F # 中的社区[Ionide Gitter 通道](https://gitter.im/ionide/ionide-project)。</span><span class="sxs-lookup"><span data-stu-id="5b997-234">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b997-235">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5b997-235">Next steps</span></span>

<span data-ttu-id="5b997-236">若要了解有关 F # 和语言的功能的详细信息，请查看[教程的 F #](../tour.md)。</span><span class="sxs-lookup"><span data-stu-id="5b997-236">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
