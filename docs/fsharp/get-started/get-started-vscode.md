---
title: '在 Visual Studio Code 中的 F # 入门'
description: '了解如何使用 F # 与 Visual Studio Code 和 Ionide 插件套件。'
ms.date: 05/28/2018
ms.openlocfilehash: e962be2796cf0d6eb90d459730659e492f864716
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192663"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="33925-103">在 Visual Studio Code 中的 F # 入门</span><span class="sxs-lookup"><span data-stu-id="33925-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="33925-104">您可以编写 F # [Visual Studio Code](https://code.visualstudio.com)与[Ionide 插件](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)获取 IntelliSense 和基本代码更完美的跨平台的轻型集成开发环境 (IDE) 体验重构。</span><span class="sxs-lookup"><span data-stu-id="33925-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="33925-105">请访问[Ionide.io](http://ionide.io)若要了解有关该插件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="33925-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="33925-106">若要开始，请确保已[F # 和 Ionide 插件正确安装](install-fsharp.md#install-f-with-visual-studio-code)。</span><span class="sxs-lookup"><span data-stu-id="33925-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="33925-107">使用 Ionide 创建第一个项目</span><span class="sxs-lookup"><span data-stu-id="33925-107">Creating your first project with Ionide</span></span>

<span data-ttu-id="33925-108">若要创建一个新的 F # 项目，请在 （可将其命名任意） 的新文件夹中打开 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="33925-108">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="33925-109">接下来，打开命令面板 (**视图 > 命令面板**) 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="33925-109">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="33925-110">这由[伪造](https://github.com/fsharp-editing/Forge)项目。</span><span class="sxs-lookup"><span data-stu-id="33925-110">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
<span data-ttu-id="33925-111">如果没有看到模板选项，请尝试通过运行以下命令在命令面板中刷新模板： `>F#: Refresh Project Templates`。</span><span class="sxs-lookup"><span data-stu-id="33925-111">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="33925-112">通过点击来选择"F #:: 新建项目" **Enter**。</span><span class="sxs-lookup"><span data-stu-id="33925-112">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="33925-113">这会转到下一步，即用于选择项目模板。</span><span class="sxs-lookup"><span data-stu-id="33925-113">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="33925-114">选取`classlib`模板，然后点击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="33925-114">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="33925-115">接下来，选择一个目录来创建的项目中。</span><span class="sxs-lookup"><span data-stu-id="33925-115">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="33925-116">如果将其留空，则使用当前目录。</span><span class="sxs-lookup"><span data-stu-id="33925-116">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="33925-117">最后，在最后一步中的为项目命名。</span><span class="sxs-lookup"><span data-stu-id="33925-117">Finally, name your project in the final step.</span></span> <span data-ttu-id="33925-118">使用 F # [Pascal 大小写](http://c2.com/cgi/wiki?PascalCase)项目名称。</span><span class="sxs-lookup"><span data-stu-id="33925-118">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="33925-119">本文使用`ClassLibraryDemo`作为名称。</span><span class="sxs-lookup"><span data-stu-id="33925-119">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="33925-120">已输入所需为你的项目的名称后, 命中**Enter**。</span><span class="sxs-lookup"><span data-stu-id="33925-120">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="33925-121">如果您遵循上一步，你会获得 Visual Studio 代码上的工作区的左侧具有以下出现：</span><span class="sxs-lookup"><span data-stu-id="33925-121">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="33925-122">F # 项目本身，其下方`ClassLibraryDemo`文件夹。</span><span class="sxs-lookup"><span data-stu-id="33925-122">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="33925-123">添加通过包的正确的目录结构[ `Paket` ](https://fsprojects.github.io/Paket/)。</span><span class="sxs-lookup"><span data-stu-id="33925-123">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="33925-124">跨平台生成的脚本[ `FAKE` ](https://fsharp.github.io/FAKE/)。</span><span class="sxs-lookup"><span data-stu-id="33925-124">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="33925-125">`paket.exe`可以提取包，并为您解决依赖项的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="33925-125">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="33925-126">一个`.gitignore`文件如果想要将此项目添加到基于 Git 的源代码管理。</span><span class="sxs-lookup"><span data-stu-id="33925-126">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="33925-127">编写一些代码</span><span class="sxs-lookup"><span data-stu-id="33925-127">Writing some code</span></span>

<span data-ttu-id="33925-128">打开*ClassLibraryDemo*文件夹。</span><span class="sxs-lookup"><span data-stu-id="33925-128">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="33925-129">您应看到以下文件：</span><span class="sxs-lookup"><span data-stu-id="33925-129">You should see the following files:</span></span>

1. <span data-ttu-id="33925-130">`ClassLibraryDemo.fs`F # 实现文件与定义的类。</span><span class="sxs-lookup"><span data-stu-id="33925-130">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="33925-131">`ClassLibraryDemo.fsproj`用于生成此项目的 F # 项目文件。</span><span class="sxs-lookup"><span data-stu-id="33925-131">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="33925-132">`Script.fsx`加载的源文件的 F # 脚本文件。</span><span class="sxs-lookup"><span data-stu-id="33925-132">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="33925-133">`paket.references`指定项目依赖项的 paket 依存文件。</span><span class="sxs-lookup"><span data-stu-id="33925-133">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="33925-134">打开`Script.fsx`，并在它的末尾添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="33925-134">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="33925-135">此函数将一个单词转换到的窗体[Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)。</span><span class="sxs-lookup"><span data-stu-id="33925-135">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="33925-136">下一步是对其使用 F # 交互式 (FSI) 进行评估。</span><span class="sxs-lookup"><span data-stu-id="33925-136">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="33925-137">突出显示整个函数 （它应为长达 11 行）。</span><span class="sxs-lookup"><span data-stu-id="33925-137">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="33925-138">一旦它被突出显示，保存**Alt**密钥并点击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="33925-138">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="33925-139">您会注意到，下面的弹出窗口，它应显示类似如下：</span><span class="sxs-lookup"><span data-stu-id="33925-139">You'll notice a window pop up below, and it should show something like this:</span></span>

![通过 Ionide F # Interactive 输出的示例](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="33925-141">这做三件事：</span><span class="sxs-lookup"><span data-stu-id="33925-141">This did three things:</span></span>

1. <span data-ttu-id="33925-142">它启动了 FSI 进程。</span><span class="sxs-lookup"><span data-stu-id="33925-142">It started the FSI process.</span></span>
2. <span data-ttu-id="33925-143">它通过金融服务业进程发送您突出显示的代码。</span><span class="sxs-lookup"><span data-stu-id="33925-143">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="33925-144">FSI 过程计算通过发送的代码。</span><span class="sxs-lookup"><span data-stu-id="33925-144">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="33925-145">因为您通过发送[函数](../language-reference/functions/index.md)，现在可以调用该函数使用 FSI ！</span><span class="sxs-lookup"><span data-stu-id="33925-145">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="33925-146">在交互式窗口中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="33925-146">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="33925-147">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="33925-147">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="33925-148">现在，让我们尝试使用作为第一个字母元音。</span><span class="sxs-lookup"><span data-stu-id="33925-148">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="33925-149">输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="33925-149">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="33925-150">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="33925-150">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="33925-151">该函数似乎按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="33925-151">The function appears to be working as expected.</span></span> <span data-ttu-id="33925-152">祝贺你，只需在 Visual Studio Code 中编写第一个 F # 函数和计算使用 FSI ！</span><span class="sxs-lookup"><span data-stu-id="33925-152">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="33925-153">您可能已经注意到，FSI 中的行结尾`;;`。</span><span class="sxs-lookup"><span data-stu-id="33925-153">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="33925-154">这是因为 FSI 可让你可以输入多行。</span><span class="sxs-lookup"><span data-stu-id="33925-154">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="33925-155">`;;`结束时，可让金融服务业知道何时完成代码。</span><span class="sxs-lookup"><span data-stu-id="33925-155">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="33925-156">解释代码</span><span class="sxs-lookup"><span data-stu-id="33925-156">Explaining the code</span></span>

<span data-ttu-id="33925-157">如果您不确定代码实际如何操作，下面是的分步说明。</span><span class="sxs-lookup"><span data-stu-id="33925-157">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="33925-158">如您所见，`toPigLatin`是一个函数，它接受作为其输入一个单词，并将其转换为该单词的 Pig Latin 表示形式。</span><span class="sxs-lookup"><span data-stu-id="33925-158">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="33925-159">此规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="33925-159">The rules for this are as follows:</span></span>

<span data-ttu-id="33925-160">如果在 word 中的第一个字符以元音开头，添加到单词结尾"yay"。</span><span class="sxs-lookup"><span data-stu-id="33925-160">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="33925-161">如果它不以元音开头，将该第一个字符移动到单词结尾，并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="33925-161">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="33925-162">您可能已经注意到 FSI 中的以下：</span><span class="sxs-lookup"><span data-stu-id="33925-162">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="33925-163">这表明`toPigLatin`是一个函数，采用`string`作为输入 (称为`word`)，并返回另一个`string`。</span><span class="sxs-lookup"><span data-stu-id="33925-163">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="33925-164">这称为[函数的类型签名](https://fsharpforfunandprofit.com/posts/function-signatures/)，F # 的是了解 F # 代码的关键的基本部分。</span><span class="sxs-lookup"><span data-stu-id="33925-164">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="33925-165">此外会发现这样如果您将鼠标悬停在 Visual Studio Code 中的函数。</span><span class="sxs-lookup"><span data-stu-id="33925-165">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="33925-166">在函数正文中，您会注意到两个不同的部分：</span><span class="sxs-lookup"><span data-stu-id="33925-166">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="33925-167">内部函数，称为`isVowel`，，它确定如果给定的字符 (`c`) 通过检查与一个通过提供的模式匹配为元音[模式匹配](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="33925-167">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="33925-168">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md)表达式，用以检查是否第一个字符为元音的元素，并返回值的所有输入字符构造基于 if 的第一个字符是元音还是失败：</span><span class="sxs-lookup"><span data-stu-id="33925-168">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="33925-169">流`toPigLatin`因此：</span><span class="sxs-lookup"><span data-stu-id="33925-169">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="33925-170">检查输入的单词的第一个字符是否元音。</span><span class="sxs-lookup"><span data-stu-id="33925-170">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="33925-171">如果是，将"yay"附加到单词结尾。</span><span class="sxs-lookup"><span data-stu-id="33925-171">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="33925-172">否则为将该第一个字符移动到单词结尾并将"在"添加到它。</span><span class="sxs-lookup"><span data-stu-id="33925-172">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="33925-173">还有一的最后一件事要注意这： 没有从与许多其他语言有不同的函数返回没有显式指令。</span><span class="sxs-lookup"><span data-stu-id="33925-173">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="33925-174">这是因为 F # 是基于表达式和函数的正文中的最后一个表达式是返回值。</span><span class="sxs-lookup"><span data-stu-id="33925-174">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="33925-175">因为`if..then..else`本身是一个表达式，正文`then`块或正文`else`块将根据输入值返回。</span><span class="sxs-lookup"><span data-stu-id="33925-175">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="33925-176">将脚本代码移动到实现文件</span><span class="sxs-lookup"><span data-stu-id="33925-176">Moving your script code into the implementation file</span></span>

<span data-ttu-id="33925-177">在本文中前面部分所示编写 F # 代码的常见第一步： 编写初始函数并使用 FSI 以交互方式执行它。</span><span class="sxs-lookup"><span data-stu-id="33925-177">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="33925-178">这称为 REPL 驱动的开发，其中[REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)代表"读取-评估-打印循环"。</span><span class="sxs-lookup"><span data-stu-id="33925-178">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="33925-179">它是实验功能，直到您看到的内容使用的好办法。</span><span class="sxs-lookup"><span data-stu-id="33925-179">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="33925-180">REPL 驱动开发的下一步是将工作代码移动到 F # 实现文件。</span><span class="sxs-lookup"><span data-stu-id="33925-180">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="33925-181">它然后，可编译的 F # 编译器为可执行程序集。</span><span class="sxs-lookup"><span data-stu-id="33925-181">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="33925-182">若要开始，请打开`ClassLibraryDemo.fs`。</span><span class="sxs-lookup"><span data-stu-id="33925-182">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="33925-183">您会注意到，一些代码中已存在。</span><span class="sxs-lookup"><span data-stu-id="33925-183">You'll notice that some code is already in there.</span></span> <span data-ttu-id="33925-184">请继续并删除类定义中，但请务必选中[ `namespace` ](../language-reference/namespaces.md)声明在顶部。</span><span class="sxs-lookup"><span data-stu-id="33925-184">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="33925-185">接下来，创建一个新[ `module` ](../language-reference/modules.md)调用`PigLatin`并复制`toPigLatin`函数导入到其这种情况下：</span><span class="sxs-lookup"><span data-stu-id="33925-185">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="33925-186">接下来，打开`Script.fsx`文件，并删除整个`toPigLatin`函数，但请务必在文件中保留以下两行：</span><span class="sxs-lookup"><span data-stu-id="33925-186">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="33925-187">第一行所需的脚本加载 FSI `ClassLibraryDemo.fs`。</span><span class="sxs-lookup"><span data-stu-id="33925-187">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span> <span data-ttu-id="33925-188">第二行是一种便于： 省略它是可选的但您将需要键入`open ClassLibraryDemo`如果你想要使程序 FSI 窗口中`ToPigLatin`纳入作用域的模块。</span><span class="sxs-lookup"><span data-stu-id="33925-188">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="33925-189">接下来，在 FSI 窗口中，调用与函数`PigLatin`前面定义的模块：</span><span class="sxs-lookup"><span data-stu-id="33925-189">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="33925-190">成功！</span><span class="sxs-lookup"><span data-stu-id="33925-190">Success!</span></span> <span data-ttu-id="33925-191">获取与之前相同的结果，但现在从 F # 实现文件中加载。</span><span class="sxs-lookup"><span data-stu-id="33925-191">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="33925-192">此处的主要区别是，F # 源代码文件编译到可以不只是在 FSI 中任意位置，执行的程序集。</span><span class="sxs-lookup"><span data-stu-id="33925-192">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="33925-193">总结</span><span class="sxs-lookup"><span data-stu-id="33925-193">Summary</span></span>

<span data-ttu-id="33925-194">在本文中，你已了解：</span><span class="sxs-lookup"><span data-stu-id="33925-194">In this article, you've learned:</span></span>

1. <span data-ttu-id="33925-195">如何设置 Visual Studio Code 中通过 Ionide。</span><span class="sxs-lookup"><span data-stu-id="33925-195">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="33925-196">如何使用 Ionide 创建第一个 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="33925-196">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="33925-197">如何使用 F # 脚本编写第一个 F # 函数中 Ionide 并执行在 FSI 中。</span><span class="sxs-lookup"><span data-stu-id="33925-197">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="33925-198">如何将脚本代码迁移到 F # 源代码，然后从 FSI 调用该代码。</span><span class="sxs-lookup"><span data-stu-id="33925-198">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="33925-199">您现在能够编写更多 F # 代码使用 Visual Studio Code 和 Ionide。</span><span class="sxs-lookup"><span data-stu-id="33925-199">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="33925-200">疑难解答</span><span class="sxs-lookup"><span data-stu-id="33925-200">Troubleshooting</span></span>

<span data-ttu-id="33925-201">下面是几种方法可以对某些可能会遇到的问题进行故障排除：</span><span class="sxs-lookup"><span data-stu-id="33925-201">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="33925-202">若要获取代码编辑功能 Ionide，F # 文件需要保存到磁盘，以及在 Visual Studio Code 工作区中处于打开状态的文件夹内。</span><span class="sxs-lookup"><span data-stu-id="33925-202">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="33925-203">如果已对系统所做的更改，或使用打开的 Visual Studio Code 安装 Ionide 必备组件，请重新启动 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="33925-203">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="33925-204">检查，可以使用 F # 编译器和 F # interactive 从命令行，而无需完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="33925-204">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="33925-205">就可以通过键入`fsc`F # 编译器的命令行中和`fsi`或`fsharpi`Visual F # 工具在 Windows 和 Mac/Linux 上的 Mono 上分别。</span><span class="sxs-lookup"><span data-stu-id="33925-205">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="33925-206">如果在项目目录中有无效字符，Ionide 可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="33925-206">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="33925-207">如果出现这种情况，重命名你的项目目录。</span><span class="sxs-lookup"><span data-stu-id="33925-207">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="33925-208">如果使用无 Ionide 命令，检查你[Visual Studio Code 的键绑定](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts)看到如果你正在通过意外覆盖它们。</span><span class="sxs-lookup"><span data-stu-id="33925-208">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="33925-209">如果你的计算机上将中断 Ionide 和以上均不是已修复问题，请尝试删除`ionide-fsharp`目录在计算机上重新安装该插件套件。</span><span class="sxs-lookup"><span data-stu-id="33925-209">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="33925-210">Ionide 是由 F # 社区成员处生成和维护的开放源代码项目。</span><span class="sxs-lookup"><span data-stu-id="33925-210">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="33925-211">请报告问题并随意在参与[Ionide VSCode: FSharp GitHub 存储库](https://github.com/ionide/ionide-vscode-fsharp)。</span><span class="sxs-lookup"><span data-stu-id="33925-211">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="33925-212">如果您有报告的问题，请按照[获取的日志报告的问题时要使用的说明](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)。</span><span class="sxs-lookup"><span data-stu-id="33925-212">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="33925-213">此外可以通过 Ionide 开发人员和 F # 社区中的询问有关进一步的帮助[Ionide Gitter 通道](https://gitter.im/ionide/ionide-project)。</span><span class="sxs-lookup"><span data-stu-id="33925-213">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="33925-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="33925-214">Next steps</span></span>

<span data-ttu-id="33925-215">若要了解有关 F # 和语言的功能的详细信息，请查看[F # 教程](../tour.md)。</span><span class="sxs-lookup"><span data-stu-id="33925-215">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
