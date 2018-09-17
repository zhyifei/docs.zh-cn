---
title: 使用 Visual Studio 2017 生成 .NET Core Visual Basic Hello World 应用程序
description: 了解如何使用 Visual Studio 2017 生成简单的 Visual Basic .NET Core 控制台应用程序。
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: d6b58e491b2857f83fe9b2e55ed35630c42b79ed
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45596515"
---
# <a name="build-a-visual-basic-hello-world-application-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="2bf2b-103">使用 Visual Studio 2017 生成 Visual Basic .NET Core Hello World 应用程序</span><span class="sxs-lookup"><span data-stu-id="2bf2b-103">Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="2bf2b-104">本主题分步介绍了如何使用 Visual Studio 2017 生成、调试和发布简单的 Visual Basic .NET Core 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-104">This topic provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using Visual Basic in Visual Studio 2017.</span></span> <span data-ttu-id="2bf2b-105">Visual Studio 2017 提供了功能全面的开发环境，可用于生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-105">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="2bf2b-106">只要应用程序没有平台专属依赖项，应用程序就可以在 .NET Core 的任何目标平台上和安装了 .NET Core 的任何系统上运行。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-106">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bf2b-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="2bf2b-107">Prerequisites</span></span>

<span data-ttu-id="2bf2b-108">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-108">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="2bf2b-109">可以使用 .NET Core 2.0 开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-109">You can develop your app with .NET Core 2.0.</span></span>

<span data-ttu-id="2bf2b-110">有关详细信息，请参阅 [Windows 上 .NET Core 的先决条件](../../core/windows-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-110">For more information, see [Prerequisites for .NET Core on Windows](../../core/windows-prerequisites.md).</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="2bf2b-111">简单的“Hello World”应用程序</span><span class="sxs-lookup"><span data-stu-id="2bf2b-111">A simple Hello World application</span></span>

<span data-ttu-id="2bf2b-112">首先创建简单的“Hello World”控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-112">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="2bf2b-113">请执行这些步骤：</span><span class="sxs-lookup"><span data-stu-id="2bf2b-113">Follow these steps:</span></span>

1. <span data-ttu-id="2bf2b-114">启动 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-114">Launch Visual Studio 2017.</span></span> <span data-ttu-id="2bf2b-115">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="2bf2b-116">在“新项目”\*对话框中，依次选择“Visual Basic”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-116">In the *New Project*\* dialog, select the **Visual Basic** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="2bf2b-117">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-117">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="2bf2b-118">在“名称”文本框中，键入“HelloWorld”。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-118">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="2bf2b-119">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-119">Select the **OK** button.</span></span>

   ![选择了“控制台应用”的“新建项目”对话框](./media/vb-with-visual-studio/new-project.png)
   
1. <span data-ttu-id="2bf2b-121">Visual Studio 使用模板创建项目。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-121">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="2bf2b-122">Visual Basic .NET Core 控制台应用程序模板自动定义类 `Program`，其中包含一个需要将 <xref:System.String> 数组用作参数的方法 `Main`。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-122">The Visual Basic Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="2bf2b-123">`Main` 是应用程序入口点，同时也是在应用程序启动时由运行时自动调用的方法。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-123">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="2bf2b-124">*args* 数组中包含在应用程序启动时提供的所有命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-124">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio 和新建的 HelloWorld 项目](./media/vb-with-visual-studio/devenv.png)

   <span data-ttu-id="2bf2b-126">用于创建简单的“Hello World”应用程序的模板。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-126">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="2bf2b-127">它通过调用 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 方法在控制台窗口中</span><span class="sxs-lookup"><span data-stu-id="2bf2b-127">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="2bf2b-128">显示文本字符串“Hello World!”。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-128">in the console window.</span></span> <span data-ttu-id="2bf2b-129">现在，选择工具栏上含绿色箭头的“HelloWorld”按钮，可以在调试模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-129">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="2bf2b-130">如果这样操作，控制台窗口只在较短的时间内可见，然后就会关闭。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-130">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="2bf2b-131">这是因为在执行 `Main` 方法中的单个语句后，`Main` 方法和应用程序将立即终止。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-131">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="2bf2b-132">若要在应用程序关闭控制台窗口前将其暂停，请在调用 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 方法后立即添加下列代码：</span><span class="sxs-lookup"><span data-stu-id="2bf2b-132">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method:</span></span>

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   <span data-ttu-id="2bf2b-133">此代码会提示用户按任意键，然后在用户按键前暂停程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-133">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="2bf2b-134">在菜单栏中，选择“生成” > “生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-134">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="2bf2b-135">这会将程序编译成一种中间语言 (IL)，然后由实时 (JIT) 编译器转换成二进制代码。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-135">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="2bf2b-136">选择工具栏上含绿色箭头的“HelloWorld”按钮，从而运行程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-136">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![控制台窗口，其中显示 Hello World Press any key to continue](./media/with-visual-studio/helloworld1.png)

1. <span data-ttu-id="2bf2b-138">按任意键关闭控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-138">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="2bf2b-139">改进“Hello World”应用程序</span><span class="sxs-lookup"><span data-stu-id="2bf2b-139">Enhancing the Hello World application</span></span>

<span data-ttu-id="2bf2b-140">将应用程序改进为提示用户输入名字，并将它与日期和时间一起显示。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-140">Enhance your application to prompt the user for his or her name and to display it along with the date and time.</span></span> <span data-ttu-id="2bf2b-141">若要修改和测试程序，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2bf2b-141">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="2bf2b-142">在代码窗口中，在 `Sub Main(args As String())` 代码行后面的左括号和第一个右括号之间，输入以下 Visual Basic 代码：</span><span class="sxs-lookup"><span data-stu-id="2bf2b-142">Enter the following Visual Basic code in the code window immediately after the opening bracket that follows the `Sub Main(args As String())` line and before the first closing bracket:</span></span>

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="2bf2b-143">此代码替换现有的 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>、<xref:System.Console.Write%2A?displayProperty=nameWithType> 和 <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> 语句。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-143">This code replaces the existing <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType>, and <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> statements.</span></span>

   ![更新了 Main 方法的 Visual Studio Program 文件](./media/vb-with-visual-studio/codewindow.png)

   <span data-ttu-id="2bf2b-145">此代码在控制台中显示“What is your name?”，</span><span class="sxs-lookup"><span data-stu-id="2bf2b-145">This code displays "What is your name?"</span></span> <span data-ttu-id="2bf2b-146">然后等待用户输入字符串并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-146">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="2bf2b-147">它将此字符串存储到名为 `name` 的变量中。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-147">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="2bf2b-148">它还会检索 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性的值（其中包含当前的本地时间），并将此值赋给 `currentDate` 变量。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `currentDate`.</span></span> <span data-ttu-id="2bf2b-149">最后，使用[内插字符串](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)在控制台窗口中显示这些值。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-149">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="2bf2b-150">依次选择 **“生成”** > **“生成解决方案”**，编译此程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-150">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="2bf2b-151">选择工具栏上的绿色箭头、按 F5 或选择“调试” > “启动调试”菜单项，在 Visual Studio 的调试模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-151">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="2bf2b-152">出现提示时，输入名称并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-152">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![控制台窗口，含已修改程序的输出](./media/with-visual-studio/helloworld2.png)

1. <span data-ttu-id="2bf2b-154">按任意键关闭控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-154">Press any key to close the console window.</span></span>

<span data-ttu-id="2bf2b-155">现已创建并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-155">You've created and run your application.</span></span> <span data-ttu-id="2bf2b-156">若要开发专业应用程序，仍需要执行一些其他步骤，才可发布应用程序：</span><span class="sxs-lookup"><span data-stu-id="2bf2b-156">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="2bf2b-157">有关调试应用程序的信息，请参阅[使用 Visual Studio 2017 调试 C# Hello World 应用程序](debugging-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-157">For information on debugging your application, see [Debugging your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="2bf2b-158">若要了解如何开发和发布可发行版应用程序，请参阅[使用 Visual Studio 2017 发布 C# Hello World 应用程序](publishing-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-158">For information on developing and publishing a distributable version of your application, see [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

<!--
## Related topics

Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017. For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).

You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor. For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md). -->
