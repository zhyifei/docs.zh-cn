---
title: 使用 Visual Studio 2017 生成 .NET Core C# Hello World 应用程序
description: 了解如何使用 Visual Studio 2017 生成简单的 C# .NET Core 控制台应用程序。
author: BillWagner
ms.author: wiwagn
ms.date: 09/13/2017
ms.custom: vs-dotnet
ms.openlocfilehash: 031c0a433391fbe4cdd40f6ce648f476787baf48
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003017"
---
# <a name="build-a-c-hello-world-application-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="5221b-103">使用 Visual Studio 2017 生成 C# .NET Core Hello World 应用程序</span><span class="sxs-lookup"><span data-stu-id="5221b-103">Build a C# Hello World application with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="5221b-104">本主题分步介绍了如何使用 Visual Studio 2017 生成、调试和发布简单的 C# .NET Core 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-104">This topic provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="5221b-105">Visual Studio 2017 提供了功能全面的开发环境，可用于生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-105">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="5221b-106">只要应用程序没有平台专属依赖项，应用程序就可以在 .NET Core 的任何目标平台上和安装了 .NET Core 的任何系统上运行。</span><span class="sxs-lookup"><span data-stu-id="5221b-106">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5221b-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="5221b-107">Prerequisites</span></span>

<span data-ttu-id="5221b-108">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)。</span><span class="sxs-lookup"><span data-stu-id="5221b-108">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="5221b-109">可以使用 .NET Core 1.1 或 .NET Core 2.0 开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-109">You can develop your app with either .NET Core 1.1 or .NET Core 2.0.</span></span>

<span data-ttu-id="5221b-110">有关详细信息，请参阅 [Windows 上 .NET Core 的先决条件](../../core/windows-prerequisites.md)主题。</span><span class="sxs-lookup"><span data-stu-id="5221b-110">For more information, see the [Prerequisites for .NET Core on Windows](../../core/windows-prerequisites.md) topic.</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="5221b-111">简单的“Hello World”应用程序</span><span class="sxs-lookup"><span data-stu-id="5221b-111">A simple Hello World application</span></span>

<span data-ttu-id="5221b-112">首先创建简单的“Hello World”控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-112">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="5221b-113">请执行这些步骤：</span><span class="sxs-lookup"><span data-stu-id="5221b-113">Follow these steps:</span></span>

1. <span data-ttu-id="5221b-114">启动 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="5221b-114">Launch Visual Studio 2017.</span></span> <span data-ttu-id="5221b-115">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="5221b-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="5221b-116">在“新项目”\*对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="5221b-116">In the *New Project*\* dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="5221b-117">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="5221b-117">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="5221b-118">在“名称”文本框中，键入“HelloWorld”。</span><span class="sxs-lookup"><span data-stu-id="5221b-118">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="5221b-119">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="5221b-119">Select the **OK** button.</span></span>

   ![选择了“控制台应用”的“新建项目”对话框](./media/with-visual-studio/newproject.png)
   
1. <span data-ttu-id="5221b-121">Visual Studio 使用模板创建项目。</span><span class="sxs-lookup"><span data-stu-id="5221b-121">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="5221b-122">C# .NET Core 控制台应用程序模板会自动定义类 `Program` 和一个需要将 <xref:System.String> 数组用作自变量的方法 `Main`。</span><span class="sxs-lookup"><span data-stu-id="5221b-122">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="5221b-123">`Main` 是应用程序入口点，同时也是在应用程序启动时由运行时自动调用的方法。</span><span class="sxs-lookup"><span data-stu-id="5221b-123">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="5221b-124">*args* 数组中包含在应用程序启动时提供的所有命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="5221b-124">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio 和新建的 HelloWorld 项目](./media/with-visual-studio/devenv.png)

   <span data-ttu-id="5221b-126">用于创建简单的“Hello World”应用程序的模板。</span><span class="sxs-lookup"><span data-stu-id="5221b-126">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="5221b-127">它通过调用 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 方法在控制台窗口中</span><span class="sxs-lookup"><span data-stu-id="5221b-127">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="5221b-128">显示文本字符串“Hello World!”。</span><span class="sxs-lookup"><span data-stu-id="5221b-128">in the console window.</span></span> <span data-ttu-id="5221b-129">现在，选择工具栏上含绿色箭头的“HelloWorld”按钮，可以在调试模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-129">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="5221b-130">如果这样操作，控制台窗口只在较短的时间内可见，然后就会关闭。</span><span class="sxs-lookup"><span data-stu-id="5221b-130">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="5221b-131">这是因为在执行 `Main` 方法中的单个语句后，`Main` 方法和应用程序将立即终止。</span><span class="sxs-lookup"><span data-stu-id="5221b-131">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="5221b-132">若要在应用程序关闭控制台窗口前将其暂停，请在调用 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 方法后立即添加下列代码：</span><span class="sxs-lookup"><span data-stu-id="5221b-132">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method:</span></span>

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```
   <span data-ttu-id="5221b-133">此代码会提示用户按任意键，然后在用户按键前暂停程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-133">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="5221b-134">在菜单栏中，选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="5221b-134">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="5221b-135">这会将程序编译成一种中间语言 (IL)，然后由实时 (JIT) 编译器转换成二进制代码。</span><span class="sxs-lookup"><span data-stu-id="5221b-135">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="5221b-136">选择工具栏上含绿色箭头的“HelloWorld”按钮，从而运行程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-136">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![控制台窗口，其中显示 Hello World Press any key to continue](./media/with-visual-studio/helloworld1.png)

1. <span data-ttu-id="5221b-138">按任意键关闭控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="5221b-138">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="5221b-139">改进“Hello World”应用程序</span><span class="sxs-lookup"><span data-stu-id="5221b-139">Enhancing the Hello World application</span></span>

<span data-ttu-id="5221b-140">改进应用程序，提示用户输入名字，并将其与日期和时间一同显示。</span><span class="sxs-lookup"><span data-stu-id="5221b-140">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="5221b-141">若要修改和测试程序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5221b-141">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="5221b-142">在代码窗口中，在 `static void Main(string[] args)` 代码行后面的左括号和第一个右括号之间，输入以下 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="5221b-142">Enter the following C# code in the code window immediately after the opening bracket that follows the `static void Main(string[] args)` line and before the first closing bracket:</span></span>

   [!code-csharp[GettingStarted#1](../../../samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="5221b-143">此代码替换现有的 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>、<xref:System.Console.Write%2A?displayProperty=nameWithType> 和 <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> 语句。</span><span class="sxs-lookup"><span data-stu-id="5221b-143">This code replaces the existing <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType>, and <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> statements.</span></span>

   ![Visual Studio Program c-sharp 文件，含更新后 Main 方法](./media/with-visual-studio/codewindow.png)

   <span data-ttu-id="5221b-145">此代码在控制台中显示“What is your name?”，</span><span class="sxs-lookup"><span data-stu-id="5221b-145">This code displays "What is your name?"</span></span> <span data-ttu-id="5221b-146">然后等待用户输入字符串并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="5221b-146">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="5221b-147">它将此字符串存储到名为 `name` 的变量中。</span><span class="sxs-lookup"><span data-stu-id="5221b-147">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="5221b-148">它还会检索 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性的值（其中包含当前的本地时间），并将此值赋给 `date` 变量。</span><span class="sxs-lookup"><span data-stu-id="5221b-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="5221b-149">最后，使用[内插字符串](../../csharp/language-reference/tokens/interpolated.md)在控制台窗口中显示这些值。</span><span class="sxs-lookup"><span data-stu-id="5221b-149">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="5221b-150">依次选择 **“生成”** > **“生成解决方案”**，编译此程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-150">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="5221b-151">选择工具栏上的绿色箭头、按 F5 或选择“调试” > “启动调试”菜单项，在 Visual Studio 的调试模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-151">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="5221b-152">出现提示时，输入名称并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="5221b-152">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![控制台窗口，含已修改程序的输出](./media/with-visual-studio/helloworld2.png)

1. <span data-ttu-id="5221b-154">按任意键关闭控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="5221b-154">Press any key to close the console window.</span></span>

<span data-ttu-id="5221b-155">现已创建并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-155">You've created and run your application.</span></span> <span data-ttu-id="5221b-156">若要开发专业应用程序，仍需要执行一些其他步骤，才可发布应用程序：</span><span class="sxs-lookup"><span data-stu-id="5221b-156">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="5221b-157">有关调试应用程序的信息，请参阅[使用 Visual Studio 2017 调试 C# Hello World 应用程序](debugging-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="5221b-157">For information on debugging your application, see [Debugging your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="5221b-158">若要了解如何开发和发布可发行版应用程序，请参阅[使用 Visual Studio 2017 发布 C# Hello World 应用程序](publishing-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="5221b-158">For information on developing and publishing a distributable version of your application, see [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5221b-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="5221b-159">Related topics</span></span>

<span data-ttu-id="5221b-160">还可以使用 Visual Studio 2017 生成 .NET Core 类库，而不是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="5221b-160">Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017.</span></span> <span data-ttu-id="5221b-161">有关分步说明，请参阅[使用 Visual Studio 2017 生成 C# .NET Core 类库](library-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="5221b-161">For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).</span></span>

<span data-ttu-id="5221b-162">还可以使用 [Visual Studio Code](https://code.visualstudio.com/)（可供下载的代码编辑器）开发在 Mac、Linux 和 Windows 上运行的 .NET Core 控制台应用。</span><span class="sxs-lookup"><span data-stu-id="5221b-162">You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor.</span></span> <span data-ttu-id="5221b-163">有关分步教程，请参阅 [Visual Studio Code 入门](with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="5221b-163">For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md).</span></span>
