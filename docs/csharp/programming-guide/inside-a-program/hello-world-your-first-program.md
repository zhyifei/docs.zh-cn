---
title: Hello World -- 您的第一个程序（C# 编程指南）
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 90f0ec6b88a2822cb3429948681c76c70f3d3f18
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45593037"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="d07ca-102">Hello World -- 您的第一个程序（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d07ca-102">Hello World -- Your First Program (C# Programming Guide)</span></span>
<span data-ttu-id="d07ca-103">以下过程创建传统“Hello World!”程序的 C#</span><span class="sxs-lookup"><span data-stu-id="d07ca-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="d07ca-104">版本。</span><span class="sxs-lookup"><span data-stu-id="d07ca-104">program.</span></span> <span data-ttu-id="d07ca-105">该程序显示字符串 `Hello World!`</span><span class="sxs-lookup"><span data-stu-id="d07ca-105">The program displays the string `Hello World!`</span></span>  
  
 <span data-ttu-id="d07ca-106">有关介绍性概念的更多示例，请参阅 [Visual C# 和 Visual Basic 入门](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="d07ca-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="d07ca-107">创建并运行控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d07ca-107">To create and run a console application</span></span>  
  
1.  <span data-ttu-id="d07ca-108">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d07ca-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d07ca-109">在菜单栏上，依次选择“文件” 、“新建” 、“项目” 。</span><span class="sxs-lookup"><span data-stu-id="d07ca-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="d07ca-110">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="d07ca-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d07ca-111">依次展开“已安装”、“模板”、“Visual C#”，然后选择“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="d07ca-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="d07ca-112">在“名称”框中，指定项目名称，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="d07ca-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="d07ca-113">新项目将出现在“解决方案资源管理器”中。</span><span class="sxs-lookup"><span data-stu-id="d07ca-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="d07ca-114">如果 Program.cs 未在“代码编辑器”中打开，则在“解决方案资源管理器”中打开“Program.cs”的快捷菜单，然后选择“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="d07ca-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="d07ca-115">将 Program.cs 的内容替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="d07ca-115">Replace the contents of Program.cs with the following code.</span></span>  
  
     [!code-csharp[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  <span data-ttu-id="d07ca-116">选择 F5 键运行该项目。</span><span class="sxs-lookup"><span data-stu-id="d07ca-116">Choose the F5 key to run the project.</span></span> <span data-ttu-id="d07ca-117">将显示包含行 `Hello World!` 的命令提示符窗口</span><span class="sxs-lookup"><span data-stu-id="d07ca-117">A Command Prompt window appears that contains the line `Hello World!`</span></span>  
  
 <span data-ttu-id="d07ca-118">接下来，将检查此程序的重要部分。</span><span class="sxs-lookup"><span data-stu-id="d07ca-118">Next, the important parts of this program are examined.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="d07ca-119">注释</span><span class="sxs-lookup"><span data-stu-id="d07ca-119">Comments</span></span>  
 <span data-ttu-id="d07ca-120">第一行包含一条注释。</span><span class="sxs-lookup"><span data-stu-id="d07ca-120">The first line contains a comment.</span></span> <span data-ttu-id="d07ca-121">字符 `//` 将该行的其余内容转换为一条注释。</span><span class="sxs-lookup"><span data-stu-id="d07ca-121">The characters `//` convert the rest of the line to a comment.</span></span>  
  
 [!code-csharp[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 <span data-ttu-id="d07ca-122">还可以通过将文本块置于 `/*` 和 `*/` 字符之间，禁止对其的注释。</span><span class="sxs-lookup"><span data-stu-id="d07ca-122">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="d07ca-123">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="d07ca-123">This is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## <a name="main-method"></a><span data-ttu-id="d07ca-124">Main 方法</span><span class="sxs-lookup"><span data-stu-id="d07ca-124">Main Method</span></span>  
 <span data-ttu-id="d07ca-125">C# 控制台应用程序必须包含 `Main` 方法，控件在其中开始和结束。</span><span class="sxs-lookup"><span data-stu-id="d07ca-125">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="d07ca-126">在 `Main` 方法中，可以创建对象并执行其他方法。</span><span class="sxs-lookup"><span data-stu-id="d07ca-126">The `Main` method is where you create objects and execute other methods.</span></span>  
  
 <span data-ttu-id="d07ca-127">`Main` 方法是驻留在类或结构中的[静态](../../../csharp/language-reference/keywords/static.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d07ca-127">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="d07ca-128">在上一个“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="d07ca-128">In the previous "Hello World!"</span></span> <span data-ttu-id="d07ca-129">示例中，该方法驻留在名为 `Hello` 的类中。</span><span class="sxs-lookup"><span data-stu-id="d07ca-129">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="d07ca-130">可以通过以下方式之一来声明 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="d07ca-130">You can declare the `Main` method in one of the following ways:</span></span>  
  
-   <span data-ttu-id="d07ca-131">它可返回 `void`。</span><span class="sxs-lookup"><span data-stu-id="d07ca-131">It can return `void`.</span></span>  
  
     [!code-csharp[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   <span data-ttu-id="d07ca-132">还可以返回一个整数。</span><span class="sxs-lookup"><span data-stu-id="d07ca-132">It can also return an integer.</span></span>  
  
     [!code-csharp[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   <span data-ttu-id="d07ca-133">无论使用哪种返回类型，它都可以带有参数。</span><span class="sxs-lookup"><span data-stu-id="d07ca-133">With either of the return types, it can take arguments.</span></span>  
  
     [!code-csharp[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     <span data-ttu-id="d07ca-134">或</span><span class="sxs-lookup"><span data-stu-id="d07ca-134">-or-</span></span>  
  
     [!code-csharp[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 <span data-ttu-id="d07ca-135">`Main` 方法中定义的参数 `args` 是一个 `string` 类型的数组，该数组包含用于调用该程序的命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="d07ca-135">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="d07ca-136">与 C++ 不同的是该数组不包括可执行 (exe) 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d07ca-136">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>  
  
 <span data-ttu-id="d07ca-137">若要深入了解如何使用命令行参数，请参阅 [Main() 和命令行参数](../../../csharp/programming-guide/main-and-command-args/index.md)与[如何：使用命令行创建和使用程序集](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)中的示例。</span><span class="sxs-lookup"><span data-stu-id="d07ca-137">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
 <span data-ttu-id="d07ca-138">在调试模式下运行程序时，对 `Main` 方法末尾处 <xref:System.Console.ReadKey%2A> 的调用可以防止在有可能读取输出内容之前控制台窗口关闭，具体方法是按 F5 键。</span><span class="sxs-lookup"><span data-stu-id="d07ca-138">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>  
  
## <a name="input-and-output"></a><span data-ttu-id="d07ca-139">输入和输出</span><span class="sxs-lookup"><span data-stu-id="d07ca-139">Input and Output</span></span>  
 <span data-ttu-id="d07ca-140">C# 程序通常使用由 .NET Framework 的运行时库提供的输入/输出服务。</span><span class="sxs-lookup"><span data-stu-id="d07ca-140">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="d07ca-141">语句 `System.Console.WriteLine("Hello World!");` 使用 <xref:System.Console.WriteLine%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="d07ca-141">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="d07ca-142">这是运行时库中 <xref:System.Console> 类的输出方法之一。</span><span class="sxs-lookup"><span data-stu-id="d07ca-142">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="d07ca-143">该方法将在标准输出流中显示其字符串参数，后接新行。</span><span class="sxs-lookup"><span data-stu-id="d07ca-143">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="d07ca-144">其他 <xref:System.Console> 方法可用于不同的输入和输出操作。</span><span class="sxs-lookup"><span data-stu-id="d07ca-144">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="d07ca-145">如果程序开头包含 `using System;` 指令，则可以直接使用 <xref:System> 类和方法，而不必进行完全限定。</span><span class="sxs-lookup"><span data-stu-id="d07ca-145">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="d07ca-146">例如，可以调用 `Console.WriteLine`，而非 `System.Console.WriteLine`：</span><span class="sxs-lookup"><span data-stu-id="d07ca-146">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-csharp[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 <span data-ttu-id="d07ca-147">有关输入/输出方法的详细信息，请参阅 <xref:System.IO>。</span><span class="sxs-lookup"><span data-stu-id="d07ca-147">For more information about input/output methods, see <xref:System.IO>.</span></span>  
  
## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="d07ca-148">命令行编译和执行</span><span class="sxs-lookup"><span data-stu-id="d07ca-148">Command-Line Compilation and Execution</span></span>  
 <span data-ttu-id="d07ca-149">通过使用命令行</span><span class="sxs-lookup"><span data-stu-id="d07ca-149">You can compile the "Hello World!"</span></span> <span data-ttu-id="d07ca-150">而非 Visual Studio 集成开发环境 (IDE)，可以编译“Hello World!”程序。</span><span class="sxs-lookup"><span data-stu-id="d07ca-150">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="d07ca-151">从命令提示符中编译并运行</span><span class="sxs-lookup"><span data-stu-id="d07ca-151">To compile and run from a command prompt</span></span>  
  
1.  <span data-ttu-id="d07ca-152">将上一过程的代码粘贴到任何文本编辑器中，然后将该文件保存为文本文件。</span><span class="sxs-lookup"><span data-stu-id="d07ca-152">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="d07ca-153">为 `Hello.cs` 文件命名。</span><span class="sxs-lookup"><span data-stu-id="d07ca-153">Name the file `Hello.cs`.</span></span> <span data-ttu-id="d07ca-154">C# 源代码文件使用 `.cs` 扩展。</span><span class="sxs-lookup"><span data-stu-id="d07ca-154">C# source code files use the extension `.cs`.</span></span>  
  
2.  <span data-ttu-id="d07ca-155">执行以下任一步骤以打开命令提示符窗口：</span><span class="sxs-lookup"><span data-stu-id="d07ca-155">Perform one of the following steps to open a command-prompt window:</span></span>  
  
    -   <span data-ttu-id="d07ca-156">在 Windows 10 的“开始”菜单上，搜索 `Developer Command Prompt`，然后点击或选择“VS 2017 开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="d07ca-156">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="d07ca-157">将出现“开发人员命令提示”窗口。</span><span class="sxs-lookup"><span data-stu-id="d07ca-157">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="d07ca-158">在 Windows 7 中，打开“启动”菜单，展开当前版本的 Visual Studio 的文件夹，打开“Visual Studio Tools”快捷菜单，然后选择“VS 2017 开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="d07ca-158">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="d07ca-159">将出现“开发人员命令提示”窗口。</span><span class="sxs-lookup"><span data-stu-id="d07ca-159">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="d07ca-160">从标准命令提示符窗口启用命令行生成。</span><span class="sxs-lookup"><span data-stu-id="d07ca-160">Enable command-line builds from a standard Command Prompt window.</span></span>  
  
         <span data-ttu-id="d07ca-161">请参阅[如何：为 Visual Studio 命令行设置环境变量](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="d07ca-161">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>  
  
3.  <span data-ttu-id="d07ca-162">在命令提示窗口中，导航到包含 `Hello.cs` 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d07ca-162">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>  
  
4.  <span data-ttu-id="d07ca-163">输入以下命令以编译 `Hello.cs`。</span><span class="sxs-lookup"><span data-stu-id="d07ca-163">Enter the following command to compile `Hello.cs`.</span></span>  
  
     `csc Hello.cs`  
  
     <span data-ttu-id="d07ca-164">如果程序不存在编译错误，系统将创建名为 `Hello.exe` 的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="d07ca-164">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>  
  
5.  <span data-ttu-id="d07ca-165">在命令提示窗口中，输入以下命令以运行该程序：</span><span class="sxs-lookup"><span data-stu-id="d07ca-165">In the command-prompt window, enter the following command to run the program:</span></span>  
  
     `Hello`  
  
 <span data-ttu-id="d07ca-166">有关 C# 编译器及其选项的详细信息，请参阅 [C# 编译器选项](../../../csharp/language-reference/compiler-options/index.md)。</span><span class="sxs-lookup"><span data-stu-id="d07ca-166">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d07ca-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="d07ca-167">See Also</span></span>

- [<span data-ttu-id="d07ca-168">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d07ca-168">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d07ca-169">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="d07ca-169">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
- [<span data-ttu-id="d07ca-170">字符串</span><span class="sxs-lookup"><span data-stu-id="d07ca-170">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
- [<span data-ttu-id="d07ca-171">\<paveover>C# 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="d07ca-171">\<paveover>C# Sample Applications</span></span>](https://msdn.microsoft.com/library/9a9d7aaa-51d3-4224-b564-95409b0f3e15)  
- [<span data-ttu-id="d07ca-172">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d07ca-172">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d07ca-173">Main() 和命令行参数</span><span class="sxs-lookup"><span data-stu-id="d07ca-173">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [<span data-ttu-id="d07ca-174">Visual C# 和 Visual Basic 入门</span><span class="sxs-lookup"><span data-stu-id="d07ca-174">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
