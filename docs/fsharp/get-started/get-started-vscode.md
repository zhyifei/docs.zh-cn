---
title: Visual Studio Code 中的 F# 入门
description: 了解如何与 Visual Studio Code F#和 ionide 入门插件套件一起使用。
ms.date: 12/23/2018
ms.openlocfilehash: 2802438144eb2352c3abeeccfc126b16c6a87d8f
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204910"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="80475-103">Visual Studio Code 中的 F# 入门</span><span class="sxs-lookup"><span data-stu-id="80475-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="80475-104">你可以使用F# [ionide 入门插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)编写[Visual Studio Code](https://code.visualstudio.com) ，通过 IntelliSense 和代码重构获取强大的跨平台、轻型集成开发环境（IDE）体验。</span><span class="sxs-lookup"><span data-stu-id="80475-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and code refactorings.</span></span> <span data-ttu-id="80475-105">请访问[Ionide.io](http://ionide.io) ，了解有关该插件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="80475-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="80475-106">若要开始，请确保已[ F#正确安装和 ionide 入门插件](install-fsharp.md#install-f-with-visual-studio-code)。</span><span class="sxs-lookup"><span data-stu-id="80475-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="create-your-first-project-with-ionide"></a><span data-ttu-id="80475-107">通过 Ionide 入门创建第一个项目</span><span class="sxs-lookup"><span data-stu-id="80475-107">Create your first project with Ionide</span></span>

<span data-ttu-id="80475-108">若要创建新F#项目，请打开命令行并使用 .NET Core CLI 创建新项目：</span><span class="sxs-lookup"><span data-stu-id="80475-108">To create a new F# project, open a command line and create a new project with the .NET Core CLI:</span></span>

```dotnetcli
dotnet new console -lang F# -o FirstIonideProject
```

<span data-ttu-id="80475-109">完成后，将目录更改为该项目并打开 Visual Studio Code：</span><span class="sxs-lookup"><span data-stu-id="80475-109">Once it completes, change directory to the project and open Visual Studio Code:</span></span>

```console
cd FirstIonideProject
code .
```

<span data-ttu-id="80475-110">在 Visual Studio Code 上加载项目后，你应看到窗口F#左侧的解决方案资源管理器窗格处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="80475-110">After the project loads on Visual Studio Code, you should see the F# Solution Explorer pane on the left-hand side of your window open.</span></span> <span data-ttu-id="80475-111">这意味着 Ionide 入门已成功加载您刚刚创建的项目。</span><span class="sxs-lookup"><span data-stu-id="80475-111">This means Ionide has successfully loaded the project you just created.</span></span> <span data-ttu-id="80475-112">您可以在此时间点之前在编辑器中编写代码，但一旦发生这种情况，就会完成加载。</span><span class="sxs-lookup"><span data-stu-id="80475-112">You can write code in the editor before this point in time, but once this happens, everything has finished loading.</span></span>

## <a name="configure-f-interactive"></a><span data-ttu-id="80475-113">配置F#交互式</span><span class="sxs-lookup"><span data-stu-id="80475-113">Configure F# interactive</span></span>

<span data-ttu-id="80475-114">首先，请确保 .NET Core 脚本是您的默认脚本环境：</span><span class="sxs-lookup"><span data-stu-id="80475-114">First, ensure that .NET Core scripting is your default scripting environment:</span></span>

1. <span data-ttu-id="80475-115">打开 Visual Studio Code 设置（**代码** > **首选项** > **设置**）。</span><span class="sxs-lookup"><span data-stu-id="80475-115">Open the Visual Studio Code settings (**Code** > **Preferences** > **Settings**).</span></span>
1. <span data-ttu-id="80475-116">搜索术语 **F# "脚本**"。</span><span class="sxs-lookup"><span data-stu-id="80475-116">Search for the term **F# Script**.</span></span>
1. <span data-ttu-id="80475-117">单击 " **fsharp.core：使用 SDK 脚本**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="80475-117">Click the checkbox that says **FSharp: use SDK scripts**.</span></span>

<span data-ttu-id="80475-118">目前这是必需的，因为在基于 .NET Framework 的脚本中，某些旧行为不能用于 .NET Core 脚本，Ionide 入门目前正在努力实现这种向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="80475-118">This is currently necessary due to some legacy behaviors in .NET Framework-based scripting that don't work with .NET Core scripting, and Ionide is currently striving for that backwards compatibility.</span></span> <span data-ttu-id="80475-119">未来，.NET Core 脚本将成为默认值。</span><span class="sxs-lookup"><span data-stu-id="80475-119">In the future, .NET Core scripting will become the default.</span></span>

### <a name="write-your-first-script"></a><span data-ttu-id="80475-120">编写您的第一个脚本</span><span class="sxs-lookup"><span data-stu-id="80475-120">Write your first script</span></span>

<span data-ttu-id="80475-121">将 Visual Studio Code 配置为使用 .NET Core 脚本后，请导航到 Visual Studio Code 中的资源管理器视图，并创建新文件。</span><span class="sxs-lookup"><span data-stu-id="80475-121">Once you've configured Visual Studio Code to use .NET Core scripting, navigate to the Explorer view in Visual Studio Code and create a new file.</span></span> <span data-ttu-id="80475-122">将其命名为*MyFirstScript. .fsx*。</span><span class="sxs-lookup"><span data-stu-id="80475-122">Name it *MyFirstScript.fsx*.</span></span>

<span data-ttu-id="80475-123">现在，将以下代码添加到其中：</span><span class="sxs-lookup"><span data-stu-id="80475-123">Now add the following code to it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="80475-124">此函数将字转换为[Pig 拉丁](https://en.wikipedia.org/wiki/Pig_Latin)形式的单词。</span><span class="sxs-lookup"><span data-stu-id="80475-124">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="80475-125">下一步是使用F#交互式（fsi.exe）对其进行评估。</span><span class="sxs-lookup"><span data-stu-id="80475-125">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="80475-126">突出显示整个函数（长度应为11行）。</span><span class="sxs-lookup"><span data-stu-id="80475-126">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="80475-127">突出显示后，请按住**Alt**键，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="80475-127">Once it's highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="80475-128">你会注意到，屏幕底部会弹出一个终端窗口，其外观应如下所示：</span><span class="sxs-lookup"><span data-stu-id="80475-128">You'll notice a terminal window pop up on the bottom of the screen, and it should look similar to this:</span></span>

![Ionide 入门的F#交互式输出示例](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="80475-130">这三个方面：</span><span class="sxs-lookup"><span data-stu-id="80475-130">This did three things:</span></span>

1. <span data-ttu-id="80475-131">它启动了 FSI.EXE 进程。</span><span class="sxs-lookup"><span data-stu-id="80475-131">It started the FSI process.</span></span>
2. <span data-ttu-id="80475-132">它发送了你在 FSI.EXE 过程中突出显示的代码。</span><span class="sxs-lookup"><span data-stu-id="80475-132">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="80475-133">FSI.EXE 进程对你发送的代码进行评估。</span><span class="sxs-lookup"><span data-stu-id="80475-133">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="80475-134">由于发送的内容是一个[函数](../language-reference/functions/index.md)，因此你现在可以使用 fsi.exe 调用该函数！</span><span class="sxs-lookup"><span data-stu-id="80475-134">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="80475-135">在交互窗口中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="80475-135">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="80475-136">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="80475-136">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="80475-137">现在，让我们尝试使用元音作为第一个字母。</span><span class="sxs-lookup"><span data-stu-id="80475-137">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="80475-138">输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="80475-138">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="80475-139">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="80475-139">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="80475-140">函数看起来像预期那样工作。</span><span class="sxs-lookup"><span data-stu-id="80475-140">The function appears to be working as expected.</span></span> <span data-ttu-id="80475-141">恭喜，你只是在 Visual Studio Code F#编写了第一个函数，并在 fsi.exe 中对其进行了评估！</span><span class="sxs-lookup"><span data-stu-id="80475-141">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="80475-142">正如您可能已经注意到的，FSI.EXE 中的行是 `;;`终止的。</span><span class="sxs-lookup"><span data-stu-id="80475-142">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="80475-143">这是因为 FSI.EXE 允许输入多个行。</span><span class="sxs-lookup"><span data-stu-id="80475-143">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="80475-144">末尾的 `;;` 使 FSI.EXE 知道代码的完成时间。</span><span class="sxs-lookup"><span data-stu-id="80475-144">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="80475-145">解释代码</span><span class="sxs-lookup"><span data-stu-id="80475-145">Explaining the code</span></span>

<span data-ttu-id="80475-146">如果你不确定代码实际执行的操作，以下是一个循序渐进的步骤。</span><span class="sxs-lookup"><span data-stu-id="80475-146">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="80475-147">正如您所看到的，`toPigLatin` 是采用单词作为其输入的函数，并将其转换为该单词的 Pig 表示形式。</span><span class="sxs-lookup"><span data-stu-id="80475-147">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="80475-148">此操作的规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="80475-148">The rules for this are as follows:</span></span>

<span data-ttu-id="80475-149">如果单词中的第一个字符以元音开头，则将 "yay" 添加到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="80475-149">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="80475-150">如果它不以元音开头，请将第一个字符移动到单词末尾，并向其添加 "ay"。</span><span class="sxs-lookup"><span data-stu-id="80475-150">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="80475-151">您可能已注意到 FSI.EXE 中的以下内容：</span><span class="sxs-lookup"><span data-stu-id="80475-151">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="80475-152">这表明 `toPigLatin` 是作为输入（称为 `word`）的 `string` 函数，返回另一个 `string`。</span><span class="sxs-lookup"><span data-stu-id="80475-152">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="80475-153">这称为[函数的类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/)，这是理解F# F#代码的关键部分。</span><span class="sxs-lookup"><span data-stu-id="80475-153">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="80475-154">如果将鼠标悬停在 Visual Studio Code 的函数上，也会注意到这一点。</span><span class="sxs-lookup"><span data-stu-id="80475-154">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="80475-155">在函数体中，你会注意到两个不同的部分：</span><span class="sxs-lookup"><span data-stu-id="80475-155">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="80475-156">称为 `isVowel`的内部函数，通过检查是否将给定字符（`c`）与通过[模式匹配](../language-reference/pattern-matching.md)提供的其中一种模式相匹配来确定是否为元音：</span><span class="sxs-lookup"><span data-stu-id="80475-156">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="80475-157">一个[`if..then..else`](../language-reference/conditional-expressions-if-then-else.md)表达式，用于检查第一个字符是否为元音，并根据第一个字符是否为元音，从输入字符中构造返回值：</span><span class="sxs-lookup"><span data-stu-id="80475-157">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="80475-158">因此，`toPigLatin` 的流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="80475-158">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="80475-159">检查输入词的第一个字符是否为元音。</span><span class="sxs-lookup"><span data-stu-id="80475-159">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="80475-160">如果是，请将 "yay" 附加到单词的结尾。</span><span class="sxs-lookup"><span data-stu-id="80475-160">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="80475-161">否则，将第一个字符移动到单词末尾，并向其添加 "ay"。</span><span class="sxs-lookup"><span data-stu-id="80475-161">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="80475-162">最后要注意的一点是：没有从函数返回的显式说明，这不同于其他许多语言。</span><span class="sxs-lookup"><span data-stu-id="80475-162">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="80475-163">这是因为F#基于表达式，而函数主体中的最后一个表达式是返回值。</span><span class="sxs-lookup"><span data-stu-id="80475-163">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="80475-164">由于 `if..then..else` 本身是一个表达式，将根据输入值返回 `then` 块的主体或 `else` 块的正文。</span><span class="sxs-lookup"><span data-stu-id="80475-164">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a><span data-ttu-id="80475-165">将控制台应用程序转换为 Pig 拉丁语生成器</span><span class="sxs-lookup"><span data-stu-id="80475-165">Turn the console app into a Pig Latin generator</span></span>

<span data-ttu-id="80475-166">本文前面的部分演示了编写F#代码的常见第一步：编写一个初始函数并使用 fsi.exe 以交互方式执行该函数。</span><span class="sxs-lookup"><span data-stu-id="80475-166">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="80475-167">这称为 "复制驱动开发"，其中，"[复制](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)" 代表 "读取-评估-打印循环"。</span><span class="sxs-lookup"><span data-stu-id="80475-167">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="80475-168">这是一种非常好的方法，可让你体验功能。</span><span class="sxs-lookup"><span data-stu-id="80475-168">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="80475-169">复制驱动开发的下一步是将工作代码移到F#实现文件中。</span><span class="sxs-lookup"><span data-stu-id="80475-169">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="80475-170">然后， F#编译器可以将它编译为可执行的程序集。</span><span class="sxs-lookup"><span data-stu-id="80475-170">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="80475-171">若要开始，请打开先前用 .NET Core CLI 创建的*程序. fs*文件。</span><span class="sxs-lookup"><span data-stu-id="80475-171">To begin, open the *Program.fs* file that you created earlier with the .NET Core CLI.</span></span> <span data-ttu-id="80475-172">你会注意到，其中已存在某些代码。</span><span class="sxs-lookup"><span data-stu-id="80475-172">You'll notice that some code is already in there.</span></span>

<span data-ttu-id="80475-173">接下来，创建一个名为 `PigLatin` 的新[`module`](../language-reference/modules.md) ，并将前面创建的 `toPigLatin` 函数复制到其中：</span><span class="sxs-lookup"><span data-stu-id="80475-173">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function you created earlier into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="80475-174">此模块应位于 `main` 函数的上方和 `open System` 声明的下方。</span><span class="sxs-lookup"><span data-stu-id="80475-174">This module should be above the `main` function and below the `open System` declaration.</span></span> <span data-ttu-id="80475-175">声明的顺序很重要F#，因此在文件中调用函数之前，需要先定义函数。</span><span class="sxs-lookup"><span data-stu-id="80475-175">Order of declarations matters in F#, so you'll need to define the function before you call it in a file.</span></span>

<span data-ttu-id="80475-176">现在，在 `main` 函数中，对参数调用 Pig 拉丁语生成器函数：</span><span class="sxs-lookup"><span data-stu-id="80475-176">Now, in the `main` function, call your Pig Latin generator function on the arguments:</span></span>

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn "%s in Pig Latin is: %s" name newName

    0
```

<span data-ttu-id="80475-177">现在，你可以从命令行运行控制台应用：</span><span class="sxs-lookup"><span data-stu-id="80475-177">Now you can run your console app from the command line:</span></span>

```console
dotnet run apple banana
```

<span data-ttu-id="80475-178">您将看到，它输出的结果与您的脚本文件的结果相同，但这一次是正在运行的程序！</span><span class="sxs-lookup"><span data-stu-id="80475-178">And you'll see that it outputs the same result as your script file, but this time as a running program!</span></span>

## <a name="troubleshooting-ionide"></a><span data-ttu-id="80475-179">Ionide 入门故障排除</span><span class="sxs-lookup"><span data-stu-id="80475-179">Troubleshooting Ionide</span></span>

<span data-ttu-id="80475-180">可以通过以下几种方法来解决你可能遇到的某些问题：</span><span class="sxs-lookup"><span data-stu-id="80475-180">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="80475-181">若要获取 Ionide 入门的代码编辑功能，需要F#将文件保存到磁盘，并保存在 Visual Studio Code 工作区中打开的文件夹内。</span><span class="sxs-lookup"><span data-stu-id="80475-181">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
1. <span data-ttu-id="80475-182">如果已对系统进行了更改或安装了 Visual Studio Code 的 Ionide 入门必备组件，请 Visual Studio Code 重新启动。</span><span class="sxs-lookup"><span data-stu-id="80475-182">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
1. <span data-ttu-id="80475-183">如果项目目录中包含无效字符，则 Ionide 入门可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="80475-183">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="80475-184">如果出现这种情况，请重命名项目目录。</span><span class="sxs-lookup"><span data-stu-id="80475-184">Rename your project directories if this is the case.</span></span>
1. <span data-ttu-id="80475-185">如果 Ionide 入门命令均不起作用，请检查你的[Visual Studio Code 键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)，以确定你是否会意外地替代它们。</span><span class="sxs-lookup"><span data-stu-id="80475-185">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
1. <span data-ttu-id="80475-186">如果计算机上的 Ionide 入门中断，并且上述任何内容都不能解决问题，请尝试删除计算机上的 `ionide-fsharp` 目录，并重新安装插件套件。</span><span class="sxs-lookup"><span data-stu-id="80475-186">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>
1. <span data-ttu-id="80475-187">如果未能加载项目（ F#解决方案资源管理器将显示这种情况），请右键单击该项目，然后单击 "**查看详细信息**" 以获取更多诊断信息。</span><span class="sxs-lookup"><span data-stu-id="80475-187">If a project failed to load (the F# Solution Explorer will show this), right-click on that project and click **See details** to get more diagnostic info.</span></span>

<span data-ttu-id="80475-188">Ionide 入门是由F#社区成员构建和维护的开源项目。</span><span class="sxs-lookup"><span data-stu-id="80475-188">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="80475-189">请在[ionide 入门-vscode-Fsharp.core GitHub 存储库](https://github.com/ionide/ionide-vscode-fsharp)上报告问题，并将其提供给你。</span><span class="sxs-lookup"><span data-stu-id="80475-189">Please report issues and feel free to contribute at the [ionide-vscode-fsharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="80475-190">你还可以在[Ionide 入门 Gitter 通道](https://gitter.im/ionide/ionide-project)中请求 ionide 入门开发人员F#和社区提供进一步的帮助。</span><span class="sxs-lookup"><span data-stu-id="80475-190">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="80475-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="80475-191">Next steps</span></span>

<span data-ttu-id="80475-192">若要了解有关F#语言的详细信息，请参阅[的F#教程](../tour.md)。</span><span class="sxs-lookup"><span data-stu-id="80475-192">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
