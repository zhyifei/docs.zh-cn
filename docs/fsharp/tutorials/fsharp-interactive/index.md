---
title: F# Interactive (fsi.exe) 参考
description: '了解如何 F # Interactive (fsi.exe) 用于在控制台以交互方式运行 F # 代码或执行 F # 脚本。'
ms.date: 05/16/2016
ms.openlocfilehash: b16ebcfe361ef50c7c7ba8510f01f6704e62ce3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564869"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="9e5e3-103">使用 F# 进行交互式编程</span><span class="sxs-lookup"><span data-stu-id="9e5e3-103">Interactive Programming with F#</span></span> #

> [!NOTE]
<span data-ttu-id="9e5e3-104">本文目前仅介绍适用于 Windows 的体验。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-104">This article currently describes the experience for Windows only.</span></span>  <span data-ttu-id="9e5e3-105">它将被重写。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-105">It will be rewritten.</span></span>

> [!NOTE]
<span data-ttu-id="9e5e3-106">API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-106">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="9e5e3-107">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-107">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="9e5e3-108">F# Interactive (fsi.exe) 用于在控制台以交互方式运行 F# 代码，或执行 F# 脚本。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-108">F# Interactive (fsi.exe) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="9e5e3-109">换句话说，F# Interactive 对 F# 语言执行 REPL（读取、计算、打印循环）。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-109">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="9e5e3-110">若要从控制台运行 F# Interactive，请运行 fsi.exe。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-110">To run F# Interactive from the console, run fsi.exe.</span></span>  <span data-ttu-id="9e5e3-111">你可以找到 fsi.exe 中的"c:\Program 文件 (x86) \Microsoft SDKs\F#\<版本 > \Framework\<版本 >\"。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-111">You will find fsi.exe in "c:\Program Files (x86)\Microsoft SDKs\F#\<version>\Framework\<version>\".</span></span> <span data-ttu-id="9e5e3-112">有关可用命令行选项的信息，请参阅 [F# Interactive 选项](../../language-reference/fsharp-interactive-options.md)。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-112">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

<span data-ttu-id="9e5e3-113">若要通过 Visual Studio 运行 F# Interactive，可以单击标记为“F# Interactive”的相应工具栏按钮，或使用组合键 **Ctrl+Alt+F**。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-113">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="9e5e3-114">执行此操作将打开交互式窗口，该窗口是运行 F# Interactive 会话的工具窗口。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-114">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="9e5e3-115">还可以选择一些希望在交互式窗口中运行的代码，然后点击组合键 **ALT+ENTER**。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-115">You can also select some code that you want to run in the interactive window and hit the key combination **ALT+ENTER**.</span></span> <span data-ttu-id="9e5e3-116">F# Interactive 在标记为“F# Interactive”的工具窗口中启动。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-116">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="9e5e3-117">当您使用此组合键时，请确保焦点位于编辑器窗口内。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-117">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="9e5e3-118">无论您使用的是控制台还是 Visual Studio，都会出现命令提示符，并且解释器会等待您输入代码。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-118">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="9e5e3-119">你可以像在代码文件中一样输入代码。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-119">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="9e5e3-120">若要编译和执行代码，请输入两个分号 (**;;**) 以终止一行或几行输入。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-120">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="9e5e3-121">F# Interactive 试图编译代码，如果成功，它将执行代码并打印其所编译类型和值的签名。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-121">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="9e5e3-122">如果发生错误，解释器将打印错误消息。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-122">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="9e5e3-123">在同一个会话中输入的代码可以访问之前输入的任何构造，以便你可以生成程序。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-123">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="9e5e3-124">工具窗口中的大容量缓存允许你在需要时将代码复制到文件中。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-124">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="9e5e3-125">当在 Visual Studio 中运行时，F# Interactive 将独立于你的项目运行，因此，你不能在 F# Interactive 中使用在项目中定义的构造，除非你将函数的代码复制到交互式窗口中。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-125">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="9e5e3-126">如果打开的项目引用了某些库，可以通过“解决方案资源管理器”在 F# Interactive 中引用这些库。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-126">If you have a project open that references some libraries, you can reference these in F# Interactive through **Solution Explorer**.</span></span> <span data-ttu-id="9e5e3-127">若要在 F# Interactive 中引用库，请展开“引用”节点，打开库的快捷菜单，然后选择“发送至 F# Interactive”。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-127">To reference a library in F# Interactive, expand the **References** node, open the shortcut menu for the library, and choose **Send to F# Interactive**.</span></span>

<span data-ttu-id="9e5e3-128">你可以通过调整设置控制 F# Interactive 命令行自变量（选项）。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-128">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="9e5e3-129">在“工具”菜单上，选择“选项...”，然后展开“F# 工具”。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-129">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="9e5e3-130">可以更改的两种设置是 F# Interactive 选项和“64 位F# Interactive”，只有在 64 位计算机上运行 F# Interactive 时，更改才有意义。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-130">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="9e5e3-131">此设置确定是否需要运行 fsi.exe 或 fsianycpu.exe 的专用 64 位版本，它使用计算机体系结构确定是作为 32 位还是 64 位进程来运行。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-131">This setting determines whether you want to run the dedicated 64-bit version of fsi.exe or fsianycpu.exe, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>


## <a name="scripting-with-f"></a><span data-ttu-id="9e5e3-132">使用 F# 编写脚本</span><span class="sxs-lookup"><span data-stu-id="9e5e3-132">Scripting with F#</span></span> #
<span data-ttu-id="9e5e3-133">脚本使用 **.fsx** 或 **.fsscript** 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-133">Scripts use the file extension **.fsx** or **.fsscript**.</span></span> <span data-ttu-id="9e5e3-134">可以不编译源代码再运行编译的程序集，而仅运行 **fsi.exe** 并指定 F# 源代码脚本的文件名，F# Interactive 会实时读取并执行代码。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-134">Instead of compiling source code and then later running the compiled assembly, you can just run **fsi.exe** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span>


## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a><span data-ttu-id="9e5e3-135">交互式、脚本编写和编译环境之间的差异</span><span class="sxs-lookup"><span data-stu-id="9e5e3-135">Differences Between the Interactive, Scripting and Compiled Environments</span></span>
<span data-ttu-id="9e5e3-136">在 F# Interactive 中编译代码时，无论是以交互方式运行还是直接运行脚本，都会定义 **INTERACTIVE** 符号。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-136">When you are compiling code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="9e5e3-137">在编译器中编译代码时，将定义 **COMPILED** 符号。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-137">When you are compiling code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="9e5e3-138">因此，如果编译模式和交互模式下的代码不同，你可以使用预处理器指令进行条件编译以确定使用哪种模式。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-138">Thus, if code needs to be different in compiled and interactive modes, you can use preprocessor directives for conditional compilation to determine which to use.</span></span>

<span data-ttu-id="9e5e3-139">当在 F# Interactive 中执行脚本时，某些指令可用，而在编译器中执行时，这些指令却不可用。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-139">Some directives are available when you are executing scripts in F# Interactive that are not available when you are executing the compiler.</span></span> <span data-ttu-id="9e5e3-140">下表总结了使用 F# Interactive 时可用的指令。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-140">The following table summarizes directives that are available when you are using F# Interactive.</span></span>

|<span data-ttu-id="9e5e3-141">指令</span><span class="sxs-lookup"><span data-stu-id="9e5e3-141">Directive</span></span>|<span data-ttu-id="9e5e3-142">描述</span><span class="sxs-lookup"><span data-stu-id="9e5e3-142">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="9e5e3-143">**#help**</span><span class="sxs-lookup"><span data-stu-id="9e5e3-143">**#help**</span></span>|<span data-ttu-id="9e5e3-144">显示有关可用指令的信息。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-144">Displays information about available directives.</span></span>|
|<span data-ttu-id="9e5e3-145">**#I**</span><span class="sxs-lookup"><span data-stu-id="9e5e3-145">**#I**</span></span>|<span data-ttu-id="9e5e3-146">指定程序集搜索路径并用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-146">Specifies an assembly search path in quotation marks.</span></span>|
|<span data-ttu-id="9e5e3-147">**#load**</span><span class="sxs-lookup"><span data-stu-id="9e5e3-147">**#load**</span></span>|<span data-ttu-id="9e5e3-148">读取、编译并运行源文件。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-148">Reads a source file, compiles it, and runs it.</span></span>|
|<span data-ttu-id="9e5e3-149">**#quit**</span><span class="sxs-lookup"><span data-stu-id="9e5e3-149">**#quit**</span></span>|<span data-ttu-id="9e5e3-150">终止 F# Interactive 会话。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-150">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="9e5e3-151">**#r**</span><span class="sxs-lookup"><span data-stu-id="9e5e3-151">**#r**</span></span>|<span data-ttu-id="9e5e3-152">引用程序集。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-152">References an assembly.</span></span>|
|<span data-ttu-id="9e5e3-153">**#time ["on"&#124;"off"]**</span><span class="sxs-lookup"><span data-stu-id="9e5e3-153">**#time ["on"&#124;"off"]**</span></span>|<span data-ttu-id="9e5e3-154">单独使用 **#time** 时，可在是否显示性能信息之间切换。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-154">By itself, **#time** toggles whether to display performance information.</span></span> <span data-ttu-id="9e5e3-155">启用后，F# Interactive 将测量实际时间、CPU 时间，以及所解释并执行的代码的每个部分的垃圾回收信息。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-155">When it is enabled, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="9e5e3-156">当在 F# Interactive 中指定文件或路径时，应指定字符串文本。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-156">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="9e5e3-157">因此，文件和路径必须用引号引起来，也可以使用常见的转义符。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-157">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="9e5e3-158">此外，你还可以使用 @ 字符，此时 F# Interactive 会将包含路径的字符串解释为原义字符串。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-158">Also, you can use the @ character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="9e5e3-159">这会导致 F# Interactive 忽略转义符。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-159">This causes F# Interactive to ignore any escape characters.</span></span>

<span data-ttu-id="9e5e3-160">编译模式与交互模式的其中一个区别是访问命令行自变量的方法。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-160">One of the differences between compiled and interactive mode is the way you access command line arguments.</span></span> <span data-ttu-id="9e5e3-161">在编译模式下，使用 **System.Environment.GetCommandLineArgs**。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-161">In compiled mode, use **System.Environment.GetCommandLineArgs**.</span></span> <span data-ttu-id="9e5e3-162">在脚本中，使用 **fsi.CommandLineArgs**。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-162">In scripts, use **fsi.CommandLineArgs**.</span></span>

<span data-ttu-id="9e5e3-163">下面的代码说明如何创建可读取脚本中命令行自变量的函数，并演示如何从脚本引用另一个程序集。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-163">The following code illustrates how to create a function that reads the command line arguments in a script and also demonstrates how to reference another assembly from a script.</span></span> <span data-ttu-id="9e5e3-164">第一个代码文件 **MyAssembly.fs** 是所引用程序集的代码。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-164">The first code file, **MyAssembly.fs**, is the code for the assembly being referenced.</span></span> <span data-ttu-id="9e5e3-165">使用命令行 **fsc-a MyAssembly.fs** 编译此文件，然后使用命令行 **fsi --exec file1.fsx** test 以脚本执行第二个文件</span><span class="sxs-lookup"><span data-stu-id="9e5e3-165">Compile this file with the command line: **fsc -a MyAssembly.fs** and then execute the second file as a script with the command line: **fsi --exec file1.fsx** test</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="9e5e3-166">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e5e3-166">The output is as follows:</span></span>

```
Command line arguments: 
file1.fsx
test
90
```

## <a name="related-topics"></a><span data-ttu-id="9e5e3-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="9e5e3-167">Related Topics</span></span>

|<span data-ttu-id="9e5e3-168">标题</span><span class="sxs-lookup"><span data-stu-id="9e5e3-168">Title</span></span>|<span data-ttu-id="9e5e3-169">描述</span><span class="sxs-lookup"><span data-stu-id="9e5e3-169">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="9e5e3-170">F# Interactive 选项</span><span class="sxs-lookup"><span data-stu-id="9e5e3-170">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="9e5e3-171">描述的 F # Interactive，命令行语法和选项 fsi.exe。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-171">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
|[<span data-ttu-id="9e5e3-172">F# Interactive 库参考</span><span class="sxs-lookup"><span data-stu-id="9e5e3-172">F# Interactive Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|<span data-ttu-id="9e5e3-173">描述在 F# Interactive 中执行代码时可用的库功能。</span><span class="sxs-lookup"><span data-stu-id="9e5e3-173">Describes library functionality available when executing code in F# interactive.</span></span>|
