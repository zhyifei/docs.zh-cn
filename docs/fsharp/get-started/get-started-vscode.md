---
title: 开始使用F#在 Visual Studio Code
description: 了解如何使用F#使用 Visual Studio Code 和 Ionide 插件套件。
ms.date: 12/23/2018
ms.openlocfilehash: 3e526d33a8b52e3c1241ed861d5ceb37eac10451
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57846566"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="a46b5-103">开始使用F#在 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a46b5-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="a46b5-104">您可以编写F#中[Visual Studio Code](https://code.visualstudio.com)与[Ionide 插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)获取 IntelliSense 和基本代码更完美的跨平台的轻型集成开发环境 (IDE) 体验重构。</span><span class="sxs-lookup"><span data-stu-id="a46b5-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="a46b5-105">请访问[Ionide.io](http://ionide.io)若要了解有关该插件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a46b5-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="a46b5-106">若要开始，请确保已[F#和正确安装 Ionide 插件](install-fsharp.md#install-f-with-visual-studio-code)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="a46b5-107">Ionide 将生成.NET FrameworkF#项目，不 dotnet core，可以跨平台兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="a46b5-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="a46b5-108">如果在上运行**Linux**或**OSX**，若要开始更简单的方法是使用[命令行工具](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command line tools](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="a46b5-109">使用 Ionide 创建第一个项目</span><span class="sxs-lookup"><span data-stu-id="a46b5-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="a46b5-110">若要创建一个新F#项目中，打开 Visual Studio Code （可将其命名任意） 的新文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a46b5-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="a46b5-111">接下来，打开命令面板 (**视图 > 命令面板**) 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="a46b5-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="a46b5-112">这由[伪造](https://github.com/fsharp-editing/Forge)项目。</span><span class="sxs-lookup"><span data-stu-id="a46b5-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="a46b5-113">如果没有看到模板选项，请尝试通过运行以下命令在命令面板中刷新模板： `>F#: Refresh Project Templates`。</span><span class="sxs-lookup"><span data-stu-id="a46b5-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="a46b5-114">选择"F#:新建项目"通过命中**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a46b5-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="a46b5-115">这会转到下一步，即用于选择项目模板。</span><span class="sxs-lookup"><span data-stu-id="a46b5-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="a46b5-116">选取`classlib`模板，然后点击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a46b5-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="a46b5-117">接下来，选择一个目录来创建的项目中。</span><span class="sxs-lookup"><span data-stu-id="a46b5-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="a46b5-118">如果将其留空，则使用当前目录。</span><span class="sxs-lookup"><span data-stu-id="a46b5-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="a46b5-119">最后，在最后一步中的为项目命名。</span><span class="sxs-lookup"><span data-stu-id="a46b5-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="a46b5-120">F#使用[Pascal 大小写](http://c2.com/cgi/wiki?PascalCase)项目名称。</span><span class="sxs-lookup"><span data-stu-id="a46b5-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="a46b5-121">本文使用`ClassLibraryDemo`作为名称。</span><span class="sxs-lookup"><span data-stu-id="a46b5-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="a46b5-122">已输入所需为你的项目的名称后, 命中**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a46b5-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="a46b5-123">如果您遵循上一步，你会获得 Visual Studio 代码上的工作区的左侧具有以下出现：</span><span class="sxs-lookup"><span data-stu-id="a46b5-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="a46b5-124">F#项目本身，其下方`ClassLibraryDemo`文件夹。</span><span class="sxs-lookup"><span data-stu-id="a46b5-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="a46b5-125">添加通过包的正确的目录结构[ `Paket` ](https://fsprojects.github.io/Paket/)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="a46b5-126">跨平台生成的脚本[ `FAKE` ](https://fsharp.github.io/FAKE/)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="a46b5-127">`paket.exe`可以提取包，并为您解决依赖项的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="a46b5-128">一个`.gitignore`文件如果想要将此项目添加到基于 Git 的源代码管理。</span><span class="sxs-lookup"><span data-stu-id="a46b5-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="a46b5-129">编写一些代码</span><span class="sxs-lookup"><span data-stu-id="a46b5-129">Writing some code</span></span>

<span data-ttu-id="a46b5-130">打开*ClassLibraryDemo*文件夹。</span><span class="sxs-lookup"><span data-stu-id="a46b5-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="a46b5-131">您应看到以下文件：</span><span class="sxs-lookup"><span data-stu-id="a46b5-131">You should see the following files:</span></span>

1. <span data-ttu-id="a46b5-132">`ClassLibraryDemo.fs`F#与定义的类的实现文件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="a46b5-133">`ClassLibraryDemo.fsproj`F#用于生成此项目的项目文件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="a46b5-134">`Script.fsx`F#将源的文件加载的脚本文件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="a46b5-135">`paket.references`指定项目依赖项的 paket 依存文件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="a46b5-136">打开`Script.fsx`，并在它的末尾添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="a46b5-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="a46b5-137">此函数将一个单词转换到的窗体[Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="a46b5-138">下一步是评估它使用F#交互式 (FSI)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="a46b5-139">突出显示整个函数 （它应为长达 11 行）。</span><span class="sxs-lookup"><span data-stu-id="a46b5-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="a46b5-140">一旦它被突出显示，保存**Alt**密钥并点击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a46b5-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="a46b5-141">您会注意到，下面的弹出窗口，它应显示类似如下：</span><span class="sxs-lookup"><span data-stu-id="a46b5-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![示例中的F#交互通过 Ionide 输出](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="a46b5-143">这做三件事：</span><span class="sxs-lookup"><span data-stu-id="a46b5-143">This did three things:</span></span>

1. <span data-ttu-id="a46b5-144">它启动了 FSI 进程。</span><span class="sxs-lookup"><span data-stu-id="a46b5-144">It started the FSI process.</span></span>
2. <span data-ttu-id="a46b5-145">它通过金融服务业进程发送您突出显示的代码。</span><span class="sxs-lookup"><span data-stu-id="a46b5-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="a46b5-146">FSI 过程计算通过发送的代码。</span><span class="sxs-lookup"><span data-stu-id="a46b5-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="a46b5-147">因为您通过发送[函数](../language-reference/functions/index.md)，现在可以调用该函数使用 FSI ！</span><span class="sxs-lookup"><span data-stu-id="a46b5-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="a46b5-148">在交互式窗口中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="a46b5-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="a46b5-149">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="a46b5-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="a46b5-150">现在，让我们尝试使用作为第一个字母元音。</span><span class="sxs-lookup"><span data-stu-id="a46b5-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="a46b5-151">输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a46b5-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="a46b5-152">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="a46b5-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="a46b5-153">该函数似乎按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="a46b5-153">The function appears to be working as expected.</span></span> <span data-ttu-id="a46b5-154">恭喜，你只需编写您的第一个F#函数在 Visual Studio Code，并使用 FSI 计算它 ！</span><span class="sxs-lookup"><span data-stu-id="a46b5-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="a46b5-155">您可能已经注意到，FSI 中的行结尾`;;`。</span><span class="sxs-lookup"><span data-stu-id="a46b5-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="a46b5-156">这是因为 FSI 可让你可以输入多行。</span><span class="sxs-lookup"><span data-stu-id="a46b5-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="a46b5-157">`;;`结束时，可让金融服务业知道何时完成代码。</span><span class="sxs-lookup"><span data-stu-id="a46b5-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="a46b5-158">解释代码</span><span class="sxs-lookup"><span data-stu-id="a46b5-158">Explaining the code</span></span>

<span data-ttu-id="a46b5-159">如果您不确定代码实际如何操作，下面是的分步说明。</span><span class="sxs-lookup"><span data-stu-id="a46b5-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="a46b5-160">如您所见，`toPigLatin`是一个函数，它接受作为其输入一个单词，并将其转换为该单词的 Pig Latin 表示形式。</span><span class="sxs-lookup"><span data-stu-id="a46b5-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="a46b5-161">此规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="a46b5-161">The rules for this are as follows:</span></span>

<span data-ttu-id="a46b5-162">如果在 word 中的第一个字符以元音开头，添加到单词结尾"yay"。</span><span class="sxs-lookup"><span data-stu-id="a46b5-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="a46b5-163">如果它不以元音开头，将该第一个字符移动到单词结尾，并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="a46b5-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="a46b5-164">您可能已经注意到 FSI 中的以下：</span><span class="sxs-lookup"><span data-stu-id="a46b5-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="a46b5-165">这表明`toPigLatin`是一个函数，采用`string`作为输入 (称为`word`)，并返回另一个`string`。</span><span class="sxs-lookup"><span data-stu-id="a46b5-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="a46b5-166">这被称为[函数的类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/)，一个基本的F#，是了解的关键F#代码。</span><span class="sxs-lookup"><span data-stu-id="a46b5-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="a46b5-167">此外会发现这样如果您将鼠标悬停在 Visual Studio Code 中的函数。</span><span class="sxs-lookup"><span data-stu-id="a46b5-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="a46b5-168">在函数正文中，您会注意到两个不同的部分：</span><span class="sxs-lookup"><span data-stu-id="a46b5-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="a46b5-169">内部函数，称为`isVowel`，，它确定如果给定的字符 (`c`) 通过检查与一个通过提供的模式匹配为元音[模式匹配](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="a46b5-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="a46b5-170">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md)表达式，用以检查是否第一个字符为元音的元素，并返回值的所有输入字符构造基于 if 的第一个字符是元音还是失败：</span><span class="sxs-lookup"><span data-stu-id="a46b5-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="a46b5-171">流`toPigLatin`因此：</span><span class="sxs-lookup"><span data-stu-id="a46b5-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="a46b5-172">检查输入的单词的第一个字符是否元音。</span><span class="sxs-lookup"><span data-stu-id="a46b5-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="a46b5-173">如果是，将"yay"附加到单词结尾。</span><span class="sxs-lookup"><span data-stu-id="a46b5-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="a46b5-174">否则为将该第一个字符移动到单词结尾并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="a46b5-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="a46b5-175">还有一的最后一件事要注意这： 没有从与许多其他语言有不同的函数返回没有显式指令。</span><span class="sxs-lookup"><span data-stu-id="a46b5-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="a46b5-176">这是因为F#是基于表达式的函数的正文中的最后一个表达式，返回值。</span><span class="sxs-lookup"><span data-stu-id="a46b5-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="a46b5-177">因为`if..then..else`本身是一个表达式，正文`then`块或正文`else`块将根据输入值返回。</span><span class="sxs-lookup"><span data-stu-id="a46b5-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="a46b5-178">将脚本代码移动到实现文件</span><span class="sxs-lookup"><span data-stu-id="a46b5-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="a46b5-179">在本文中前面几节演示了常见的第一步，在编写F#代码： 编写初始函数并使用 FSI 以交互方式执行它。</span><span class="sxs-lookup"><span data-stu-id="a46b5-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="a46b5-180">这称为 REPL 驱动的开发，其中[REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)代表"读取-评估-打印循环"。</span><span class="sxs-lookup"><span data-stu-id="a46b5-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="a46b5-181">它是实验功能，直到您看到的内容使用的好办法。</span><span class="sxs-lookup"><span data-stu-id="a46b5-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="a46b5-182">REPL 驱动开发的下一步是将移动到的工作代码F#实现文件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="a46b5-183">然后可以通过编译F#为可执行程序集的编译器。</span><span class="sxs-lookup"><span data-stu-id="a46b5-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="a46b5-184">若要开始，请打开`ClassLibraryDemo.fs`。</span><span class="sxs-lookup"><span data-stu-id="a46b5-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="a46b5-185">您会注意到，一些代码中已存在。</span><span class="sxs-lookup"><span data-stu-id="a46b5-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="a46b5-186">请继续并删除类定义中，但请务必选中[ `namespace` ](../language-reference/namespaces.md)声明在顶部。</span><span class="sxs-lookup"><span data-stu-id="a46b5-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="a46b5-187">接下来，创建一个新[ `module` ](../language-reference/modules.md)调用`PigLatin`并复制`toPigLatin`函数导入到其这种情况下：</span><span class="sxs-lookup"><span data-stu-id="a46b5-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="a46b5-188">接下来，打开`Script.fsx`文件，并删除整个`toPigLatin`函数，但请务必在文件中保留以下两行：</span><span class="sxs-lookup"><span data-stu-id="a46b5-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```
<span data-ttu-id="a46b5-189">选择这两个行文本，然后按 Alt + Enter 可在 FSI 中执行这些行。</span><span class="sxs-lookup"><span data-stu-id="a46b5-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="a46b5-190">这些将将 Pig Latin 库的内容加载到 FSI 过程并`open``ClassLibraryDemo`命名空间，以便您具有对功能的访问。</span><span class="sxs-lookup"><span data-stu-id="a46b5-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="a46b5-191">接下来，在 FSI 窗口中，调用与函数`PigLatin`前面定义的模块：</span><span class="sxs-lookup"><span data-stu-id="a46b5-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="a46b5-192">成功！</span><span class="sxs-lookup"><span data-stu-id="a46b5-192">Success!</span></span> <span data-ttu-id="a46b5-193">如前面一样，但现在从加载获得相同的结果F#实现文件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="a46b5-194">此处的主要区别在于F#源代码文件编译到可以不只是在 FSI 中任意位置，执行的程序集。</span><span class="sxs-lookup"><span data-stu-id="a46b5-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="a46b5-195">总结</span><span class="sxs-lookup"><span data-stu-id="a46b5-195">Summary</span></span>

<span data-ttu-id="a46b5-196">在本文中，你已了解：</span><span class="sxs-lookup"><span data-stu-id="a46b5-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="a46b5-197">如何设置 Visual Studio Code 中通过 Ionide。</span><span class="sxs-lookup"><span data-stu-id="a46b5-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="a46b5-198">如何创建你的第一个F#通过 Ionide 项目。</span><span class="sxs-lookup"><span data-stu-id="a46b5-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="a46b5-199">如何使用F#脚本编写您的第一个F#函数，在 Ionide 和 FSI 然后执行它。</span><span class="sxs-lookup"><span data-stu-id="a46b5-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="a46b5-200">如何迁移您的脚本代码与F#源，然后从 FSI 调用该代码。</span><span class="sxs-lookup"><span data-stu-id="a46b5-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="a46b5-201">您现在能够编写更多F#使用 Visual Studio Code 和 Ionide 代码。</span><span class="sxs-lookup"><span data-stu-id="a46b5-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a46b5-202">疑难解答</span><span class="sxs-lookup"><span data-stu-id="a46b5-202">Troubleshooting</span></span>

<span data-ttu-id="a46b5-203">下面是几种方法可以对某些可能会遇到的问题进行故障排除：</span><span class="sxs-lookup"><span data-stu-id="a46b5-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="a46b5-204">若要获取代码编辑功能 Ionide，在F#文件需要保存到磁盘，以及在 Visual Studio Code 工作区中处于打开状态的文件夹内。</span><span class="sxs-lookup"><span data-stu-id="a46b5-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="a46b5-205">如果已对系统所做的更改，或使用打开的 Visual Studio Code 安装 Ionide 必备组件，请重新启动 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="a46b5-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="a46b5-206">检查是否可以使用F#编译器和F#交互式从命令行，而无需完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="a46b5-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="a46b5-207">就可以通过键入`fsc`有关的命令行中F#编译器，并`fsi`或`fsharpi`视觉对象F#分别 Windows 和 Mac/Linux 上的 Mono 上的工具。</span><span class="sxs-lookup"><span data-stu-id="a46b5-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="a46b5-208">如果在项目目录中有无效字符，Ionide 可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="a46b5-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="a46b5-209">如果出现这种情况，重命名你的项目目录。</span><span class="sxs-lookup"><span data-stu-id="a46b5-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="a46b5-210">如果使用无 Ionide 命令，检查你[Visual Studio Code 的键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)看到如果你正在通过意外覆盖它们。</span><span class="sxs-lookup"><span data-stu-id="a46b5-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="a46b5-211">如果你的计算机上将中断 Ionide 和以上均不是已修复问题，请尝试删除`ionide-fsharp`目录在计算机上重新安装该插件套件。</span><span class="sxs-lookup"><span data-stu-id="a46b5-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="a46b5-212">Ionide 是一个开放源代码项目的成员由生成和维护F#社区。</span><span class="sxs-lookup"><span data-stu-id="a46b5-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="a46b5-213">请报告问题并随意在参与[Ionide VSCode:FSharp GitHub 存储库](https://github.com/ionide/ionide-vscode-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="a46b5-214">如果您有报告的问题，请按照[获取的日志报告的问题时要使用的说明](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="a46b5-215">您还可以要求从 Ionide 开发人员的更多帮助和F#中的社区[Ionide Gitter 通道](https://gitter.im/ionide/ionide-project)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a46b5-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a46b5-216">Next steps</span></span>

<span data-ttu-id="a46b5-217">若要详细了解F#和功能的语言，请查看[概览F# ](../tour.md)。</span><span class="sxs-lookup"><span data-stu-id="a46b5-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
