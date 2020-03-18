---
title: 在 Visual Studio 中使用 .NET Core 创建 Hello World 应用程序
description: 了解如何使用 Visual Studio 在 C# 或 Visual Basic 中创建第一个 .NET Core 控制台应用程序。
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713999"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="6a2db-103">教程：在 Visual Studio 2019 中创建第一个 .NET Core 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="6a2db-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="6a2db-104">本文将逐步介绍如何在 Visual Studio 2019 中创建和运行 Hello World .NET Core 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a2db-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="6a2db-105">通常使用 Hello World 应用程序向初学者介绍新的编程语言。</span><span class="sxs-lookup"><span data-stu-id="6a2db-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="6a2db-106">此程序只在屏幕上显示短语“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="6a2db-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="6a2db-107">。</span><span class="sxs-lookup"><span data-stu-id="6a2db-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a2db-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="6a2db-108">Prerequisites</span></span>

- <span data-ttu-id="6a2db-109">安装了具有“.NET Core 跨平台开发”  工作负载的 [Visual Studio 2019 版本 16.4 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="6a2db-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="6a2db-110">选择此工作负载时，将自动安装 .NET Core 3.1 SDK。</span><span class="sxs-lookup"><span data-stu-id="6a2db-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="6a2db-111">有关详细信息，请参阅[安装 .NET Core SDK](../install/sdk.md?pivots=os-windows) 一文中的[在 Visual Studio 中安装](../install/sdk.md?pivots=os-windows#install-with-visual-studio)部分。</span><span class="sxs-lookup"><span data-stu-id="6a2db-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="6a2db-112">创建应用</span><span class="sxs-lookup"><span data-stu-id="6a2db-112">Create the app</span></span>

<span data-ttu-id="6a2db-113">以下说明创建一个简单的 Hello World 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="6a2db-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="6a2db-114">C#</span><span class="sxs-lookup"><span data-stu-id="6a2db-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="6a2db-115">打开 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="6a2db-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="6a2db-116">创建一个名为“HelloWorld”的新 C# .NET Core 控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="6a2db-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="6a2db-117">在“开始”窗口上，选择“创建新项目”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-117">On the start window, choose **Create a new project**.</span></span>

      ![在 Visual Studio“启动”窗口选择“创建新项目”按钮](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="6a2db-119">在“创建新项目”  页面，在搜索框中输入“控制台”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="6a2db-120">接下来，从“语言”列表中选择“C#”  ，然后从“平台”列表中选择“所有平台”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="6a2db-121">选择“控制台应用 (.NET Core)”  模板，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![使用所选筛选器创建新项目窗口](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="6a2db-123">如果看不到 .NET Core 模板，则可能缺少安装所需的工作负载。</span><span class="sxs-lookup"><span data-stu-id="6a2db-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="6a2db-124">在“找不到所需内容?”  消息下，选择“安装更多工具和功能”  链接。</span><span class="sxs-lookup"><span data-stu-id="6a2db-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="6a2db-125">Visual Studio 安装程序随即打开。</span><span class="sxs-lookup"><span data-stu-id="6a2db-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="6a2db-126">确保安装了“.NET Core 跨平台开发”  工作负载。</span><span class="sxs-lookup"><span data-stu-id="6a2db-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="6a2db-127">在“配置新项目”  页面，在“项目名称”  框中输入“HelloWorld”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="6a2db-128">然后，选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-128">Then, choose **Create**.</span></span>

      ![为新项目窗口配置“项目名称”、“位置”和“解决方案名称”字段](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="6a2db-130">C# .NET Core 控制台应用程序模板会自动定义类 `Program` 和一个需要将 <xref:System.String> 数组用作自变量的方法 `Main`。</span><span class="sxs-lookup"><span data-stu-id="6a2db-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="6a2db-131">`Main` 是应用程序入口点，同时也是在应用程序启动时由运行时自动调用的方法。</span><span class="sxs-lookup"><span data-stu-id="6a2db-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="6a2db-132">*args* 数组中包含在应用程序启动时提供的所有命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="6a2db-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio 和新建的 HelloWorld 项目](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[<span data-ttu-id="6a2db-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a2db-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="6a2db-135">打开 Visual Studio 2019。</span><span class="sxs-lookup"><span data-stu-id="6a2db-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="6a2db-136">创建一个名为“HelloWorld”的新 Visual Basic .NET Core 控制台应用项目。</span><span class="sxs-lookup"><span data-stu-id="6a2db-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="6a2db-137">在“开始”窗口上，选择“创建新项目”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-137">On the start window, choose **Create a new project**.</span></span>

      ![在 Visual Studio“启动”窗口选择“创建新项目”按钮](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="6a2db-139">在“创建新项目”  页面，在搜索框中输入“控制台”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="6a2db-140">接下来，从“语言”列表中选择“Visual Basic”  ，然后从“平台”列表中选择“所有平台”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="6a2db-141">选择“控制台应用 (.NET Core)”  模板，然后选择“下一步”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![为“控制台应用(.NET Framework)”选择 Visual Basic 模板](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="6a2db-143">如果看不到 .NET Core 模板，则可能缺少安装所需的工作负载。</span><span class="sxs-lookup"><span data-stu-id="6a2db-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="6a2db-144">在“找不到所需内容?”  消息下，选择“安装更多工具和功能”  链接。</span><span class="sxs-lookup"><span data-stu-id="6a2db-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="6a2db-145">Visual Studio 安装程序随即打开。</span><span class="sxs-lookup"><span data-stu-id="6a2db-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="6a2db-146">确保安装了“.NET Core 跨平台开发”  工作负载。</span><span class="sxs-lookup"><span data-stu-id="6a2db-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="6a2db-147">在“配置新项目”  页面，在“项目名称”  框中输入“HelloWorld”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="6a2db-148">然后，选择“创建”  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="6a2db-149">.NET Core 控制台应用程序模板会自动定义类 `Program` 和一个需要将 <xref:System.String> 数组用作自变量的方法 `Main`。</span><span class="sxs-lookup"><span data-stu-id="6a2db-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="6a2db-150">`Main` 是应用程序入口点，同时也是在应用程序启动时由运行时自动调用的方法。</span><span class="sxs-lookup"><span data-stu-id="6a2db-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="6a2db-151">`args` 参数中包含在应用程序启动时提供的所有命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="6a2db-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio 和新建的 HelloWorld 项目](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="6a2db-153">用于创建简单的“Hello World”应用程序的模板。</span><span class="sxs-lookup"><span data-stu-id="6a2db-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="6a2db-154">它通过调用 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 方法在控制台窗口中</span><span class="sxs-lookup"><span data-stu-id="6a2db-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="6a2db-155">显示文本字符串“Hello World!”。</span><span class="sxs-lookup"><span data-stu-id="6a2db-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="6a2db-156">运行应用</span><span class="sxs-lookup"><span data-stu-id="6a2db-156">Run the app</span></span>

1. <span data-ttu-id="6a2db-157">若要运行程序，请在工具栏上选择“HelloWorld”  ，或按 F5  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![已选择“HelloWorld 运行”按钮的 Visual Studio 工具栏](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="6a2db-159">此时将打开在屏幕上显示文本“Hello World!”</span><span class="sxs-lookup"><span data-stu-id="6a2db-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="6a2db-160">并附带一些 Visual Studio 调试信息的控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="6a2db-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![控制台窗口，其中显示 Hello World Press any key to continue](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="6a2db-162">按任意键关闭控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="6a2db-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="6a2db-163">增强应用</span><span class="sxs-lookup"><span data-stu-id="6a2db-163">Enhance the app</span></span>

<span data-ttu-id="6a2db-164">改进应用程序，提示用户输入名字，并将其与日期和时间一同显示。</span><span class="sxs-lookup"><span data-stu-id="6a2db-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="6a2db-165">以下说明再次修改并运行应用：</span><span class="sxs-lookup"><span data-stu-id="6a2db-165">The following instructions modify and run the app again:</span></span>

# <a name="c"></a>[<span data-ttu-id="6a2db-166">C#</span><span class="sxs-lookup"><span data-stu-id="6a2db-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="6a2db-167">将 `Main` 方法的内容（当前只是调用 `Console.WriteLine` 的行）替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="6a2db-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="6a2db-168">此代码在控制台中显示“What is your name?”，</span><span class="sxs-lookup"><span data-stu-id="6a2db-168">This code displays "What is your name?"</span></span> <span data-ttu-id="6a2db-169">然后等待用户输入字符串并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="6a2db-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="6a2db-170">它将此字符串存储到名为 `name` 的变量中。</span><span class="sxs-lookup"><span data-stu-id="6a2db-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="6a2db-171">它还会检索 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性的值（其中包含当前的本地时间），并将此值赋给 `date` 变量。</span><span class="sxs-lookup"><span data-stu-id="6a2db-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="6a2db-172">最后，使用[内插字符串](../../csharp/language-reference/tokens/interpolated.md)在控制台窗口中显示这些值。</span><span class="sxs-lookup"><span data-stu-id="6a2db-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="6a2db-173">依次选择 **“生成”**  >  **“生成解决方案”** ，编译此程序。</span><span class="sxs-lookup"><span data-stu-id="6a2db-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="6a2db-174">若要运行程序，请在工具栏上选择“HelloWorld”  ，或按 F5  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="6a2db-175">出现提示时，输入名称并按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="6a2db-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![控制台窗口，含已修改程序的输出](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="6a2db-177">按任意键关闭控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="6a2db-177">Press any key to close the console window.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="6a2db-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a2db-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="6a2db-179">将 `Main` 方法的内容（当前只是调用 `Console.WriteLine` 的行）替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="6a2db-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="6a2db-180">此代码在控制台中显示“What is your name?”，</span><span class="sxs-lookup"><span data-stu-id="6a2db-180">This code displays "What is your name?"</span></span> <span data-ttu-id="6a2db-181">然后等待用户输入字符串并按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="6a2db-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="6a2db-182">它将此字符串存储到名为 `name` 的变量中。</span><span class="sxs-lookup"><span data-stu-id="6a2db-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="6a2db-183">它还会检索 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性的值（其中包含当前的本地时间），并将此值赋给 `date` 变量。</span><span class="sxs-lookup"><span data-stu-id="6a2db-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="6a2db-184">最后，使用[内插字符串](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)在控制台窗口中显示这些值。</span><span class="sxs-lookup"><span data-stu-id="6a2db-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="6a2db-185">依次选择 **“生成”**  >  **“生成解决方案”** ，编译此程序。</span><span class="sxs-lookup"><span data-stu-id="6a2db-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="6a2db-186">若要运行程序，请在工具栏上选择“HelloWorld”  ，或按 F5  。</span><span class="sxs-lookup"><span data-stu-id="6a2db-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="6a2db-187">出现提示时，输入名称并按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="6a2db-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![控制台窗口，含已修改程序的输出](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="6a2db-189">按任意键关闭控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="6a2db-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="6a2db-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6a2db-190">Next steps</span></span>

<span data-ttu-id="6a2db-191">在本文中，你已创建并运行第一个 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a2db-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="6a2db-192">下一步，调试应用。</span><span class="sxs-lookup"><span data-stu-id="6a2db-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6a2db-193">在 Visual Studio 中调试 .NET Core Hello World 应用程序</span><span class="sxs-lookup"><span data-stu-id="6a2db-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
