---
title: Visual Studio Code 中的F#入门
description: 了解如何与 Visual Studio Code F#和 ionide 入门插件套件一起使用。
ms.date: 12/23/2018
ms.openlocfilehash: baaa87207122cfe314972aee5dfaf8a41de2c394
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629977"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="67338-103">Visual Studio Code 中的F#入门</span><span class="sxs-lookup"><span data-stu-id="67338-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="67338-104">你可以使用F# [ionide 入门插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)编写[Visual Studio Code](https://code.visualstudio.com) , 通过 IntelliSense 和基本代码重构获取强大的跨平台、轻型集成开发环境 (IDE) 体验。</span><span class="sxs-lookup"><span data-stu-id="67338-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="67338-105">请访问[Ionide.io](http://ionide.io) , 了解有关该插件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="67338-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="67338-106">若要开始, 请确保已[ F#正确安装和 ionide 入门插件](install-fsharp.md#install-f-with-visual-studio-code)。</span><span class="sxs-lookup"><span data-stu-id="67338-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="67338-107">Ionide 入门将生成 .NET Framework F#项目, 而不是 dotnet core, 这可能会造成跨平台兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="67338-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="67338-108">如果在**Linux**或**OSX**上运行, 一种更简单的入门方法是使用[命令行工具](get-started-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="67338-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command-line tools](get-started-command-line.md).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="67338-109">用 Ionide 入门创建您的第一个项目</span><span class="sxs-lookup"><span data-stu-id="67338-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="67338-110">若要创建新F#项目, 请在新文件夹中打开 Visual Studio Code (可将其命名为任何所需的名称)。</span><span class="sxs-lookup"><span data-stu-id="67338-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="67338-111">接下来, 打开命令面板 (**查看 > 命令面板**) 并键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="67338-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="67338-112">这由[伪造](https://github.com/fsharp-editing/Forge)项目提供支持。</span><span class="sxs-lookup"><span data-stu-id="67338-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="67338-113">如果看不到模板选项, 请在命令面板中运行以下命令来尝试刷新模板: `>F#: Refresh Project Templates`。</span><span class="sxs-lookup"><span data-stu-id="67338-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="67338-114">选择 "F#:新项目 ", 按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="67338-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="67338-115">这会转到下一步, 即选择项目模板。</span><span class="sxs-lookup"><span data-stu-id="67338-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="67338-116">选取模板并按**Enter。** `classlib`</span><span class="sxs-lookup"><span data-stu-id="67338-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="67338-117">接下来, 选择要在其中创建项目的目录。</span><span class="sxs-lookup"><span data-stu-id="67338-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="67338-118">如果将其留空, 它将使用当前目录。</span><span class="sxs-lookup"><span data-stu-id="67338-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="67338-119">最后, 在最后一个步骤中将项目命名为。</span><span class="sxs-lookup"><span data-stu-id="67338-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="67338-120">F#对项目名称使用[Pascal 大小写](http://c2.com/cgi/wiki?PascalCase)。</span><span class="sxs-lookup"><span data-stu-id="67338-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="67338-121">本文使用`ClassLibraryDemo`作为名称。</span><span class="sxs-lookup"><span data-stu-id="67338-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="67338-122">输入要用于项目的名称后, 按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="67338-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="67338-123">如果执行了上一步, 应会看到左侧的 "Visual Studio Code" 工作区显示如下:</span><span class="sxs-lookup"><span data-stu-id="67338-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="67338-124">F#项目本身, 位于文件夹的`ClassLibraryDemo`下方。</span><span class="sxs-lookup"><span data-stu-id="67338-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="67338-125">用于通过[`Paket`](https://fsprojects.github.io/Paket/)添加包的正确目录结构。</span><span class="sxs-lookup"><span data-stu-id="67338-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="67338-126">使用[`FAKE`](https://fsharp.github.io/FAKE/)的跨平台生成脚本。</span><span class="sxs-lookup"><span data-stu-id="67338-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="67338-127">可`paket.exe`执行的可提取包和解析依赖项的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="67338-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="67338-128">如果`.gitignore`要将此项目添加到基于 Git 的源代码管理, 则为文件。</span><span class="sxs-lookup"><span data-stu-id="67338-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="67338-129">编写一些代码</span><span class="sxs-lookup"><span data-stu-id="67338-129">Writing some code</span></span>

<span data-ttu-id="67338-130">打开*ClassLibraryDemo*文件夹。</span><span class="sxs-lookup"><span data-stu-id="67338-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="67338-131">应会看到以下文件:</span><span class="sxs-lookup"><span data-stu-id="67338-131">You should see the following files:</span></span>

1. <span data-ttu-id="67338-132">`ClassLibraryDemo.fs`, 具有F#定义了类的实现文件。</span><span class="sxs-lookup"><span data-stu-id="67338-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="67338-133">`ClassLibraryDemo.fsproj`, 用于F#生成此项目的项目文件。</span><span class="sxs-lookup"><span data-stu-id="67338-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="67338-134">`Script.fsx`, 加载F#源文件的脚本文件。</span><span class="sxs-lookup"><span data-stu-id="67338-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="67338-135">`paket.references`, 用于指定项目依赖项的 Paket 文件。</span><span class="sxs-lookup"><span data-stu-id="67338-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="67338-136">打开`Script.fsx`, 并在它的末尾添加以下代码:</span><span class="sxs-lookup"><span data-stu-id="67338-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="67338-137">此函数将字转换为[Pig 拉丁](https://en.wikipedia.org/wiki/Pig_Latin)形式的单词。</span><span class="sxs-lookup"><span data-stu-id="67338-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="67338-138">下一步是使用F#交互式 (fsi.exe) 对其进行评估。</span><span class="sxs-lookup"><span data-stu-id="67338-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="67338-139">突出显示整个函数 (长度应为11行)。</span><span class="sxs-lookup"><span data-stu-id="67338-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="67338-140">突出显示后, 请按住**Alt**键, 然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="67338-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="67338-141">你会注意到下面的窗口弹出窗口, 它应显示如下所示的内容:</span><span class="sxs-lookup"><span data-stu-id="67338-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ionide 入门的F#交互式输出示例](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="67338-143">这三个方面:</span><span class="sxs-lookup"><span data-stu-id="67338-143">This did three things:</span></span>

1. <span data-ttu-id="67338-144">它启动了 FSI.EXE 进程。</span><span class="sxs-lookup"><span data-stu-id="67338-144">It started the FSI process.</span></span>
2. <span data-ttu-id="67338-145">它发送了你在 FSI.EXE 过程中突出显示的代码。</span><span class="sxs-lookup"><span data-stu-id="67338-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="67338-146">FSI.EXE 进程对你发送的代码进行评估。</span><span class="sxs-lookup"><span data-stu-id="67338-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="67338-147">由于发送的内容是一个[函数](../language-reference/functions/index.md), 因此你现在可以使用 fsi.exe 调用该函数!</span><span class="sxs-lookup"><span data-stu-id="67338-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="67338-148">在交互窗口中, 键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="67338-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="67338-149">你应看到以下结果:</span><span class="sxs-lookup"><span data-stu-id="67338-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="67338-150">现在, 让我们尝试使用元音作为第一个字母。</span><span class="sxs-lookup"><span data-stu-id="67338-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="67338-151">输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="67338-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="67338-152">你应看到以下结果:</span><span class="sxs-lookup"><span data-stu-id="67338-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="67338-153">函数看起来像预期那样工作。</span><span class="sxs-lookup"><span data-stu-id="67338-153">The function appears to be working as expected.</span></span> <span data-ttu-id="67338-154">恭喜, 你只是在 Visual Studio Code F#编写了第一个函数, 并在 fsi.exe 中对其进行了评估!</span><span class="sxs-lookup"><span data-stu-id="67338-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="67338-155">正如您可能已经注意到的, FSI.EXE 中的行`;;`以结尾。</span><span class="sxs-lookup"><span data-stu-id="67338-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="67338-156">这是因为 FSI.EXE 允许输入多个行。</span><span class="sxs-lookup"><span data-stu-id="67338-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="67338-157">结束`;;`时, fsi.exe 知道代码的完成时间。</span><span class="sxs-lookup"><span data-stu-id="67338-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="67338-158">解释代码</span><span class="sxs-lookup"><span data-stu-id="67338-158">Explaining the code</span></span>

<span data-ttu-id="67338-159">如果你不确定代码实际执行的操作, 以下是一个循序渐进的步骤。</span><span class="sxs-lookup"><span data-stu-id="67338-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="67338-160">正如您所看到`toPigLatin`的, 它是一个将单词作为其输入并将其转换为 Pig 的单词的表示形式的函数。</span><span class="sxs-lookup"><span data-stu-id="67338-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="67338-161">此操作的规则如下所示:</span><span class="sxs-lookup"><span data-stu-id="67338-161">The rules for this are as follows:</span></span>

<span data-ttu-id="67338-162">如果单词中的第一个字符以元音开头, 则将 "yay" 添加到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="67338-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="67338-163">如果它不以元音开头, 请将第一个字符移动到单词末尾, 并向其添加 "ay"。</span><span class="sxs-lookup"><span data-stu-id="67338-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="67338-164">您可能已注意到 FSI.EXE 中的以下内容:</span><span class="sxs-lookup"><span data-stu-id="67338-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="67338-165">这表明`toPigLatin`函数`string`作为输入 (称为`word`), 并返回另一个`string`。</span><span class="sxs-lookup"><span data-stu-id="67338-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="67338-166">这称为[函数的类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/), 这是理解F# F#代码的关键部分。</span><span class="sxs-lookup"><span data-stu-id="67338-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="67338-167">如果将鼠标悬停在 Visual Studio Code 的函数上, 也会注意到这一点。</span><span class="sxs-lookup"><span data-stu-id="67338-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="67338-168">在函数体中, 你会注意到两个不同的部分:</span><span class="sxs-lookup"><span data-stu-id="67338-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="67338-169">一个名`isVowel`为的内部函数, 通过检查给定字符 (`c`) 是否通过[模式匹配](../language-reference/pattern-matching.md)与提供的模式之一匹配来确定是否为元音:</span><span class="sxs-lookup"><span data-stu-id="67338-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="67338-170">一个[`if..then..else`](../language-reference/conditional-expressions-if-then-else.md)表达式, 用于检查第一个字符是否为元音, 并根据第一个字符是否为元音, 从输入字符中构造返回值:</span><span class="sxs-lookup"><span data-stu-id="67338-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="67338-171">这样的流`toPigLatin`就是:</span><span class="sxs-lookup"><span data-stu-id="67338-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="67338-172">检查输入词的第一个字符是否为元音。</span><span class="sxs-lookup"><span data-stu-id="67338-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="67338-173">如果是, 请将 "yay" 附加到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="67338-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="67338-174">否则, 将第一个字符移动到单词末尾, 并向其添加 "ay"。</span><span class="sxs-lookup"><span data-stu-id="67338-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="67338-175">最后要注意的一点是: 没有从函数返回的显式说明, 这不同于其他许多语言。</span><span class="sxs-lookup"><span data-stu-id="67338-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="67338-176">这是因为F#基于表达式, 而函数主体中的最后一个表达式是返回值。</span><span class="sxs-lookup"><span data-stu-id="67338-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="67338-177">由于`if..then..else`本身是一个表达式, 因此将根据输入`then`值返回块体`else`或块体。</span><span class="sxs-lookup"><span data-stu-id="67338-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="67338-178">将脚本代码移到实现文件中</span><span class="sxs-lookup"><span data-stu-id="67338-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="67338-179">本文前面的部分演示了编写F#代码的常见第一步: 编写一个初始函数并使用 fsi.exe 以交互方式执行该函数。</span><span class="sxs-lookup"><span data-stu-id="67338-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="67338-180">这称为 "复制驱动开发", 其中, "[复制](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)" 代表 "读取-评估-打印循环"。</span><span class="sxs-lookup"><span data-stu-id="67338-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="67338-181">这是一种非常好的方法, 可让你体验功能。</span><span class="sxs-lookup"><span data-stu-id="67338-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="67338-182">复制驱动开发的下一步是将工作代码移到F#实现文件中。</span><span class="sxs-lookup"><span data-stu-id="67338-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="67338-183">然后, F#编译器可以将它编译为可执行的程序集。</span><span class="sxs-lookup"><span data-stu-id="67338-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="67338-184">若要开始, `ClassLibraryDemo.fs`请打开。</span><span class="sxs-lookup"><span data-stu-id="67338-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="67338-185">你会注意到, 其中已存在某些代码。</span><span class="sxs-lookup"><span data-stu-id="67338-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="67338-186">继续并删除类定义, 但请确保将[`namespace`](../language-reference/namespaces.md)声明保留在顶部。</span><span class="sxs-lookup"><span data-stu-id="67338-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="67338-187">接下来, 创建一个[`module`](../language-reference/modules.md)名`PigLatin`为的新`toPigLatin` , 并将函数复制到其中:</span><span class="sxs-lookup"><span data-stu-id="67338-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="67338-188">接下来, 再次`Script.fsx`打开该文件并删除整个`toPigLatin`函数, 但请确保在该文件中保留以下两行:</span><span class="sxs-lookup"><span data-stu-id="67338-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="67338-189">选择两行文本, 并按 Alt + Enter 在 FSI.EXE 中执行这些行。</span><span class="sxs-lookup"><span data-stu-id="67338-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="67338-190">这会将 Pig 拉丁语库的内容加载到 fsi.exe 进程和`open` `ClassLibraryDemo`命名空间, 以便您可以访问该功能。</span><span class="sxs-lookup"><span data-stu-id="67338-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="67338-191">接下来, 在 fsi.exe 窗口中, 调用函数, 该`PigLatin`函数包含之前定义的模块:</span><span class="sxs-lookup"><span data-stu-id="67338-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="67338-192">成功！</span><span class="sxs-lookup"><span data-stu-id="67338-192">Success!</span></span> <span data-ttu-id="67338-193">您将获得与以前相同的结果, 但现在是F#从实现文件加载的。</span><span class="sxs-lookup"><span data-stu-id="67338-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="67338-194">此处的主要差别在于, F#源文件编译成可在任意位置执行的程序集, 而不只是在 fsi.exe 中执行。</span><span class="sxs-lookup"><span data-stu-id="67338-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="67338-195">总结</span><span class="sxs-lookup"><span data-stu-id="67338-195">Summary</span></span>

<span data-ttu-id="67338-196">本文介绍了以下内容:</span><span class="sxs-lookup"><span data-stu-id="67338-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="67338-197">如何设置 Ionide 入门 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="67338-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="67338-198">如何创建具有 Ionide 入门的F#第一个项目。</span><span class="sxs-lookup"><span data-stu-id="67338-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="67338-199">如何使用F#脚本编写 ionide 入门中的第F#一个函数, 然后在 fsi.exe 中执行它。</span><span class="sxs-lookup"><span data-stu-id="67338-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="67338-200">如何将脚本代码迁移到F#源, 然后从 fsi.exe 调用该代码。</span><span class="sxs-lookup"><span data-stu-id="67338-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="67338-201">现在, 你可以使用 Visual Studio Code 和 Ionide 入门F#编写更多的代码。</span><span class="sxs-lookup"><span data-stu-id="67338-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="67338-202">疑难解答</span><span class="sxs-lookup"><span data-stu-id="67338-202">Troubleshooting</span></span>

<span data-ttu-id="67338-203">可以通过以下几种方法来解决你可能遇到的某些问题:</span><span class="sxs-lookup"><span data-stu-id="67338-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="67338-204">若要获取 Ionide 入门的代码编辑功能, 需要F#将文件保存到磁盘, 并保存在 Visual Studio Code 工作区中打开的文件夹内。</span><span class="sxs-lookup"><span data-stu-id="67338-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="67338-205">如果已对系统进行了更改或安装了 Visual Studio Code 的 Ionide 入门必备组件, 请 Visual Studio Code 重新启动。</span><span class="sxs-lookup"><span data-stu-id="67338-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="67338-206">检查是否可以从命令行F#使用编译器F#和交互式路径, 而无需使用完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="67338-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="67338-207">为此, 你可以在`fsc`命令行中键入F#编译器, `fsi`或`fsharpi`在 Windows 上的 Visual F# tools 和 Mac/Linux 上分别键入。</span><span class="sxs-lookup"><span data-stu-id="67338-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="67338-208">如果项目目录中包含无效字符, 则 Ionide 入门可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="67338-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="67338-209">如果出现这种情况, 请重命名项目目录。</span><span class="sxs-lookup"><span data-stu-id="67338-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="67338-210">如果 Ionide 入门命令均不起作用, 请检查你的[Visual Studio Code 键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts), 以确定你是否会意外地替代它们。</span><span class="sxs-lookup"><span data-stu-id="67338-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="67338-211">如果计算机上的 ionide 入门中断, 并且上述任何内容都不能解决问题, 请尝试删除`ionide-fsharp`计算机上的目录, 并重新安装插件套件。</span><span class="sxs-lookup"><span data-stu-id="67338-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="67338-212">Ionide 入门是由F#社区成员构建和维护的开源项目。</span><span class="sxs-lookup"><span data-stu-id="67338-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="67338-213">请在[ionide 入门-VSCode 上报告问题并随意参与:Fsharp.core GitHub 存储](https://github.com/ionide/ionide-vscode-fsharp)库。</span><span class="sxs-lookup"><span data-stu-id="67338-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="67338-214">如果你有要报告的问题, 请按照[说明来获取报告问题时要使用的日志](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)。</span><span class="sxs-lookup"><span data-stu-id="67338-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="67338-215">你还可以在[Ionide 入门 Gitter 通道](https://gitter.im/ionide/ionide-project)中请求 ionide 入门开发人员F#和社区提供进一步的帮助。</span><span class="sxs-lookup"><span data-stu-id="67338-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="67338-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="67338-216">Next steps</span></span>

<span data-ttu-id="67338-217">若要了解有关F#语言的详细信息, 请参阅[的F#教程](../tour.md)。</span><span class="sxs-lookup"><span data-stu-id="67338-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
