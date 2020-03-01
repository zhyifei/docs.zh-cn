---
title: 使用 Visual Studio 调试 Hello World .NET Core 应用程序
description: 了解如何使用 Visual Studio 调试用 C# 或 Visual Basic 编写的 Hello World 应用程序。
ms.date: 12/05/2019
ms.custom: vs-dotnet
ms.openlocfilehash: b2ee1401fc89f990c5f930d80d1a510a117e63a0
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156668"
---
# <a name="debug-your-c-or-visual-basic-net-core-hello-world-application-using-visual-studio"></a><span data-ttu-id="69746-103">使用 Visual Studio 调试 C# 或 Visual Basic .NET Core Hello World 应用程序</span><span class="sxs-lookup"><span data-stu-id="69746-103">Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio</span></span>

<span data-ttu-id="69746-104">至此，已按照[使用 Visual Studio 2019 创建第一个 .NET Core 控制台应用程序](with-visual-studio.md)中的步骤操作，创建和运行简单的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="69746-104">So far, you've followed the steps in [Create your first .NET Core console application in Visual Studio 2019](with-visual-studio.md) to create and run a simple console application.</span></span> <span data-ttu-id="69746-105">编写和编译应用程序后，可以开始进行测试。</span><span class="sxs-lookup"><span data-stu-id="69746-105">Once you've written and compiled your application, you can begin testing it.</span></span> <span data-ttu-id="69746-106">Visual Studio 提供一整套调试工具，方便你在排除应用程序故障时使用。</span><span class="sxs-lookup"><span data-stu-id="69746-106">Visual Studio includes a comprehensive set of debugging tools that you can use to troubleshoot your application.</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="69746-107">“调试”生成配置</span><span class="sxs-lookup"><span data-stu-id="69746-107">Debug build configuration</span></span>

<span data-ttu-id="69746-108">“调试”  和“发布”  是 Visual Studio 的两种默认生成配置。</span><span class="sxs-lookup"><span data-stu-id="69746-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="69746-109">当前的生成配置显示在工具栏上。</span><span class="sxs-lookup"><span data-stu-id="69746-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="69746-110">下面的工具栏图像显示 Visual Studio 配置为编译应用的“调试”版本：</span><span class="sxs-lookup"><span data-stu-id="69746-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![突出显示“调试”的 Visual Studio 工具栏](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="69746-112">首先运行应用的“调试”版本。</span><span class="sxs-lookup"><span data-stu-id="69746-112">Begin by running the Debug version of your app.</span></span> <span data-ttu-id="69746-113">“调试”生成配置会禁用大多数编译器优化，并在生成过程中提供更丰富的信息。</span><span class="sxs-lookup"><span data-stu-id="69746-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="69746-114">设置断点</span><span class="sxs-lookup"><span data-stu-id="69746-114">Set a breakpoint</span></span>

<span data-ttu-id="69746-115">运行程序，并尝试一些调试功能：</span><span class="sxs-lookup"><span data-stu-id="69746-115">Run your program and try a few debugging features:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="69746-116">C#</span><span class="sxs-lookup"><span data-stu-id="69746-116">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="69746-117">通过在读取 `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` 的行上单击代码窗口的左边距来设置该行的断点  。</span><span class="sxs-lookup"><span data-stu-id="69746-117">Set a *breakpoint* on the line that reads `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="69746-118">也可以通过将插入符号置于代码行中，然后按 F9  或从菜单栏中选择“调试”   > “切换断点”  来设置断点。</span><span class="sxs-lookup"><span data-stu-id="69746-118">You can also set a breakpoint by placing the caret in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="69746-119">断点会在执行包含断点的代码行之前  暂时中断执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="69746-119">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="69746-120">如下图所示，Visual Studio 通过突出显示此代码行，并在其左侧边缘显示红色圆圈来指明该行设置了断点。</span><span class="sxs-lookup"><span data-stu-id="69746-120">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![设置断点后的 Visual Studio 程序窗口](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="69746-122">选择工具栏上含绿色箭头的“HelloWorld”  按钮、按 F5  或选择“调试”   > “启动调试”  ，在“调试”模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="69746-122">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing **F5**, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="69746-123">当程序提示输入名称时，在控制台窗口中输入字符串，然后按 Enter  。</span><span class="sxs-lookup"><span data-stu-id="69746-123">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="69746-124">到达断点时，程序停止执行，然后执行 `Console.WriteLine` 方法。</span><span class="sxs-lookup"><span data-stu-id="69746-124">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="69746-125">“局部变量”  窗口显示当前正在执行的方法中定义的变量值。</span><span class="sxs-lookup"><span data-stu-id="69746-125">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio 中断点的屏幕截图](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="69746-127">在“即时”  窗口中，可以与正在调试的应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="69746-127">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="69746-128">可以通过交互方式更改变量值，看看这样会对程序产生哪些影响。</span><span class="sxs-lookup"><span data-stu-id="69746-128">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="69746-129">如果“即时”  窗口不可见，请选择“调试”   > “Windows”   > “即时”  来显示它。</span><span class="sxs-lookup"><span data-stu-id="69746-129">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="69746-130">在“即时”  窗口中输入 `name = "Gracie"`，然后按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="69746-130">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="69746-131">在“即时”  窗口中输入 `date = DateTime.Parse("11/16/2019 5:25 PM")`，然后按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="69746-131">Enter `date = DateTime.Parse("11/16/2019 5:25 PM")` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="69746-132">“即时”  窗口显示字符串变量的值和 <xref:System.DateTime> 值的属性。</span><span class="sxs-lookup"><span data-stu-id="69746-132">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="69746-133">此外，“局部变量”  窗口中也会更新变量值。</span><span class="sxs-lookup"><span data-stu-id="69746-133">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Visual Studio 2019 中的“局部变量”和“即时”窗口](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="69746-135">选择工具栏中的“继续”  按钮，或选择“调试”   > “继续”  ，继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="69746-135">Continue program execution by selecting the **Continue** button in the toolbar or by selecting **Debug** > **Continue**.</span></span> <span data-ttu-id="69746-136">控制台窗口中显示的值对应于在“即时”  窗口中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="69746-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![显示输入值的控制台窗口](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="69746-138">按任意键，退出应用程序并停止调试。</span><span class="sxs-lookup"><span data-stu-id="69746-138">Press any key to exit the application and stop debugging.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="69746-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69746-139">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="69746-140">通过在读取 `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")` 的行上单击代码窗口的左边距来设置该行的断点  。</span><span class="sxs-lookup"><span data-stu-id="69746-140">Set a *breakpoint* on the line that reads `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")` by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="69746-141">也可以通过将插入符号置于所需的行中，然后从菜单栏中选择“调试”   > “切换断点”  来设置断点。</span><span class="sxs-lookup"><span data-stu-id="69746-141">You can also set a breakpoint by placing the caret on the desired line and then choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="69746-142">断点会在执行包含断点的代码行之前  暂时中断执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="69746-142">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="69746-143">如下图所示，Visual Studio 通过突出显示此代码行，并在其左侧边缘显示红色圆圈来指明这行设置了断点。</span><span class="sxs-lookup"><span data-stu-id="69746-143">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![设置断点后的 Visual Studio 程序窗口](./media/debugging-with-visual-studio/vb/set-breakpoint-in-editor.png)

1. <span data-ttu-id="69746-145">选择工具栏上含绿色箭头的“HelloWorld”  按钮、按 F5  或选择“调试”   > “启动调试”  ，在“调试”模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="69746-145">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing **F5**, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="69746-146">当程序提示输入名称时，在控制台窗口中输入字符串，然后按 Enter  。</span><span class="sxs-lookup"><span data-stu-id="69746-146">Enter a string in the console window when the program prompts for a name and press **Enter**.</span></span>

1. <span data-ttu-id="69746-147">到达断点时，程序停止执行，然后执行 `Console.WriteLine` 方法。</span><span class="sxs-lookup"><span data-stu-id="69746-147">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="69746-148">“局部变量”  窗口显示当前正在执行的方法中定义的变量值。</span><span class="sxs-lookup"><span data-stu-id="69746-148">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

1. <span data-ttu-id="69746-149">在“即时”  窗口中，可以与正在调试的应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="69746-149">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="69746-150">可以通过交互方式更改变量值，看看这样会对程序产生哪些影响。</span><span class="sxs-lookup"><span data-stu-id="69746-150">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="69746-151">如果“即时”  窗口不可见，请选择“调试”   > “Windows”   > “即时”  来显示它。</span><span class="sxs-lookup"><span data-stu-id="69746-151">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="69746-152">在“即时”  窗口中输入 `name = "Gracie"`，然后按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="69746-152">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="69746-153">在“即时”  窗口中输入 `date = DateTime.Parse("11/16/2019 5:25 PM")`，然后按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="69746-153">Enter `date = DateTime.Parse("11/16/2019 5:25 PM")` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="69746-154">“局部变量”  窗口中会更新变量值。</span><span class="sxs-lookup"><span data-stu-id="69746-154">The values of the variables are updated in the **Locals** window.</span></span>

1. <span data-ttu-id="69746-155">选择工具栏中的“继续”  按钮，或选择“调试”   > “继续”  菜单项，继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="69746-155">Continue program execution by selecting the **Continue** button in the toolbar or by selecting the **Debug** > **Continue** menu item.</span></span> <span data-ttu-id="69746-156">控制台窗口中显示的值对应于在“即时”  窗口中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="69746-156">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![显示输入值的控制台窗口](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="69746-158">按任意键，退出应用程序并停止调试。</span><span class="sxs-lookup"><span data-stu-id="69746-158">Press any key to exit the application and stop debugging.</span></span>

---

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="69746-159">设置条件断点</span><span class="sxs-lookup"><span data-stu-id="69746-159">Set a conditional breakpoint</span></span>

<span data-ttu-id="69746-160">程序显示用户输入的字符串。</span><span class="sxs-lookup"><span data-stu-id="69746-160">Your program displays the string that the user enters.</span></span> <span data-ttu-id="69746-161">如果用户没有输入任何内容，情况又如何呢？</span><span class="sxs-lookup"><span data-stu-id="69746-161">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="69746-162">可使用名为“条件断点”  的实用调试功能来测试这种情况，该功能可在满足一个或多个条件时中断程序执行。</span><span class="sxs-lookup"><span data-stu-id="69746-162">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="69746-163">若要设置条件断点，并测试用户无法输入字符串时的情况如何，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="69746-163">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

# <a name="c"></a>[<span data-ttu-id="69746-164">C#</span><span class="sxs-lookup"><span data-stu-id="69746-164">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="69746-165">右键单击表示断点的红点。</span><span class="sxs-lookup"><span data-stu-id="69746-165">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="69746-166">在上下文菜单中，选择“条件”  ，打开“断点设置”  对话框。</span><span class="sxs-lookup"><span data-stu-id="69746-166">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="69746-167">选择“条件”  框（如果尚未选择）。</span><span class="sxs-lookup"><span data-stu-id="69746-167">Check the box for **Conditions** if it's not already selected.</span></span>

   ![显示断点设置面板的编辑器 - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="69746-169">对于“条件表达式”  ，将“e.g. x == 5”替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="69746-169">For the **Conditional Expression**, replace "e.g. x == 5" with the following:</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="69746-170">要测试的代码条件是 `String.IsNullOrEmpty(name)` 方法调用是否为 `true`，因为 `name` 尚未分配有值或值为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="69746-170">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because `name` has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="69746-171">与条件表达式不同，你还可以指定命中次数  ，这样程序就会在语句的执行次数达到指定值时中断执行；也可以指定筛选条件  ，这样就可以根据诸如线程标识符、进程名称或线程名称之类的属性来中断程序执行。</span><span class="sxs-lookup"><span data-stu-id="69746-171">Instead of a conditional expression, you can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="69746-172">选择“关闭”  以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="69746-172">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="69746-173">通过按 F5  调试来启动程序。</span><span class="sxs-lookup"><span data-stu-id="69746-173">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="69746-174">在控制台窗口中，在看到输入名称的提示时按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="69746-174">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="69746-175">由于符合指定的条件（`name` 为 `null` 或 <xref:System.String.Empty?displayProperty=nameWithType>），因此程序在到达断点时以及在 `Console.WriteLine` 方法执行前停止执行。</span><span class="sxs-lookup"><span data-stu-id="69746-175">Because the condition you specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="69746-176">选择“局部变量”  窗口，其中显示当前正在执行的方法的局部变量值。</span><span class="sxs-lookup"><span data-stu-id="69746-176">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="69746-177">在这种情况下，`Main` 是当前正在执行的方法。</span><span class="sxs-lookup"><span data-stu-id="69746-177">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="69746-178">请注意，`name` 变量的值为 `""` 或 <xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="69746-178">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="69746-179">在“即时”  窗口中输入下面的语句并按 Enter  ，确认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="69746-179">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="69746-180">结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="69746-180">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ![在执行语句后返回值 true 的即时窗口 - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="69746-182">选择工具栏上的“继续”  按钮，继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="69746-182">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="69746-183">按任意键，关闭控制台窗口并停止调试。</span><span class="sxs-lookup"><span data-stu-id="69746-183">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="69746-184">单击代码窗口左侧边缘上的点，或选中该代码行，选择“调试”>“切换断点”  ，从而清除断点。</span><span class="sxs-lookup"><span data-stu-id="69746-184">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="69746-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69746-185">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="69746-186">右键单击表示断点的红点。</span><span class="sxs-lookup"><span data-stu-id="69746-186">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="69746-187">在上下文菜单中，选择“条件”  ，打开“断点设置”  对话框。</span><span class="sxs-lookup"><span data-stu-id="69746-187">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="69746-188">选中“条件”  对应的框。</span><span class="sxs-lookup"><span data-stu-id="69746-188">Check the box for **Conditions**.</span></span>

   ![显示断点设置面板的编辑器 - Visual Basic](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. <span data-ttu-id="69746-190">对于“条件表达式”  ，将“e.g. x = 5”替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="69746-190">For the **Conditional Expression** replace "e.g. x = 5" with the following:</span></span>

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="69746-191">要测试的代码条件是 `String.IsNullOrEmpty(name)` 方法调用是否为 `true`，因为 `name` 尚未分配有值或值为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="69746-191">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because `name` has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="69746-192">与条件表达式不同，你还可以指定命中次数  ，这样程序就会在语句的执行次数达到指定值时中断执行；也可以指定筛选条件  ，这样就可以根据诸如线程标识符、进程名称或线程名称之类的属性来中断程序执行。</span><span class="sxs-lookup"><span data-stu-id="69746-192">Instead of a conditional expression, you can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="69746-193">选择“关闭”  以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="69746-193">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="69746-194">通过按 F5  调试来启动程序。</span><span class="sxs-lookup"><span data-stu-id="69746-194">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="69746-195">在控制台窗口中，在看到输入名称的提示时按 Enter  键。</span><span class="sxs-lookup"><span data-stu-id="69746-195">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="69746-196">由于符合指定的条件（`name` 为 `null` 或 <xref:System.String.Empty?displayProperty=nameWithType>），因此程序在到达断点时以及在 `Console.WriteLine` 方法执行前停止执行。</span><span class="sxs-lookup"><span data-stu-id="69746-196">Because the condition you specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="69746-197">选择“局部变量”  窗口，其中显示当前正在执行的方法的局部变量值。</span><span class="sxs-lookup"><span data-stu-id="69746-197">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="69746-198">在这种情况下，`Main` 是当前正在执行的方法。</span><span class="sxs-lookup"><span data-stu-id="69746-198">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="69746-199">请注意，`name` 变量的值为 `""` 或 <xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="69746-199">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="69746-200">在“即时”  窗口中输入下面的语句并按 Enter  ，确认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="69746-200">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="69746-201">结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="69746-201">The result is `true`.</span></span>

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   ![在执行语句后返回值 true 的即时窗口 - Visual Basic](./media/debugging-with-visual-studio/vb/immediate-window-output.png)

1. <span data-ttu-id="69746-203">选择工具栏上的“继续”  按钮，继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="69746-203">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="69746-204">按任意键，关闭控制台窗口并停止调试。</span><span class="sxs-lookup"><span data-stu-id="69746-204">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="69746-205">单击代码窗口左侧边缘上的点，或选中该行，选择“调试”>“切换断点”  菜单项，从而清除断点。</span><span class="sxs-lookup"><span data-stu-id="69746-205">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing the **Debug > Toggle Breakpoint** menu item with the row selected.</span></span>

---
## <a name="step-through-a-program"></a><span data-ttu-id="69746-206">单步执行程序</span><span class="sxs-lookup"><span data-stu-id="69746-206">Step through a program</span></span>

<span data-ttu-id="69746-207">使用 Visual Studio，还可以单步执行程序，并监视其执行情况。</span><span class="sxs-lookup"><span data-stu-id="69746-207">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="69746-208">通常可以设置断点，并使用此功能单步执行程序流，尽管是一小部分程序代码。</span><span class="sxs-lookup"><span data-stu-id="69746-208">Ordinarily, you'd set a breakpoint and use this feature to follow program flow through a small part of your program code.</span></span> <span data-ttu-id="69746-209">因为程序很小，因此可以单步执行整个程序：</span><span class="sxs-lookup"><span data-stu-id="69746-209">Since your program is small, you can step through the entire program:</span></span>

# <a name="c"></a>[<span data-ttu-id="69746-210">C#</span><span class="sxs-lookup"><span data-stu-id="69746-210">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="69746-211">在菜单栏上，选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-211">On the menu bar, choose **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-212">Visual Studio 会在要执行的下一行旁边突出显示一个箭头。</span><span class="sxs-lookup"><span data-stu-id="69746-212">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 单步执行方法 - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="69746-214">此时，“局部变量”  窗口显示程序只定义了一个变量，即 `args`。</span><span class="sxs-lookup"><span data-stu-id="69746-214">At this point, the **Locals** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="69746-215">由于尚未向程序传递任何命令行自变量，因此它的值是一个空字符串数组。</span><span class="sxs-lookup"><span data-stu-id="69746-215">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="69746-216">此外，Visual Studio 还打开了一个空白控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="69746-216">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="69746-217">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-217">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-218">Visual Studio 现在突出显示要执行的下一行。</span><span class="sxs-lookup"><span data-stu-id="69746-218">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="69746-219">如图所示，从上一语句执行到该行代码花费了不到 1 毫秒的时间。</span><span class="sxs-lookup"><span data-stu-id="69746-219">As the image shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="69746-220">`args` 仍然是唯一声明的变量，控制台窗口仍为空白。</span><span class="sxs-lookup"><span data-stu-id="69746-220">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 单步执行方法源 - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

1. <span data-ttu-id="69746-222">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-222">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-223">Visual Studio 突出显示包含 `name` 变量赋值的语句。</span><span class="sxs-lookup"><span data-stu-id="69746-223">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="69746-224">“局部变量”  窗口显示 `name` 为 `null`，控制台窗口显示字符串“What is your name?”。</span><span class="sxs-lookup"><span data-stu-id="69746-224">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="69746-225">在控制台窗口中输入字符串，然后按 Enter  ，从而响应提示。</span><span class="sxs-lookup"><span data-stu-id="69746-225">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="69746-226">控制台无响应，输入的字符串未显示在控制台窗口中，但 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法将捕获输入。</span><span class="sxs-lookup"><span data-stu-id="69746-226">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="69746-227">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-227">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-228">Visual Studio 突出显示包含 `date` 变量赋值的语句。</span><span class="sxs-lookup"><span data-stu-id="69746-228">Visual Studio highlights the statement that includes the `date` variable assignment.</span></span> <span data-ttu-id="69746-229">“局部变量”  窗口显示 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="69746-229">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="69746-230">控制台窗口还显示在提示符处输入的字符串。</span><span class="sxs-lookup"><span data-stu-id="69746-230">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="69746-231">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-231">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-232">“局部变量”  窗口显示通过 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性赋值后的 `date` 变量值。</span><span class="sxs-lookup"><span data-stu-id="69746-232">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="69746-233">控制台窗口保持不变。</span><span class="sxs-lookup"><span data-stu-id="69746-233">The console window is unchanged.</span></span>

1. <span data-ttu-id="69746-234">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-234">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-235">Visual Studio 调用 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="69746-235">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="69746-236">控制台窗口会显示格式化的字符串。</span><span class="sxs-lookup"><span data-stu-id="69746-236">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="69746-237">选择“调试”   > “跳出”  ，或按 Shift  +F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-237">Select **Debug** > **Step Out** or press **Shift**+**F11**.</span></span> <span data-ttu-id="69746-238">这将停止单步执行。</span><span class="sxs-lookup"><span data-stu-id="69746-238">This stops step-by-step execution.</span></span> <span data-ttu-id="69746-239">控制台窗口会显示一条消息，并等待用户按任意键。</span><span class="sxs-lookup"><span data-stu-id="69746-239">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="69746-240">按任意键，关闭控制台窗口并停止调试。</span><span class="sxs-lookup"><span data-stu-id="69746-240">Press any key to close the console window and stop debugging.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="69746-241">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69746-241">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="69746-242">在菜单栏上，选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-242">On the menu bar, choose **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-243">Visual Studio 会在要执行的下一行旁边突出显示一个箭头。</span><span class="sxs-lookup"><span data-stu-id="69746-243">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 单步执行方法 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="69746-245">此时，“局部变量”  窗口显示程序只定义了一个变量，即 `args`。</span><span class="sxs-lookup"><span data-stu-id="69746-245">At this point, the **Locals** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="69746-246">由于尚未向程序传递任何命令行自变量，因此它的值是一个空字符串数组。</span><span class="sxs-lookup"><span data-stu-id="69746-246">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="69746-247">此外，Visual Studio 还打开了一个空白控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="69746-247">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="69746-248">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-248">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-249">Visual Studio 现在突出显示要执行的下一行。</span><span class="sxs-lookup"><span data-stu-id="69746-249">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="69746-250">如图所示，从上一语句执行到这行代码花费了不到 1 毫秒的时间。</span><span class="sxs-lookup"><span data-stu-id="69746-250">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="69746-251">`args` 仍然是唯一声明的变量，控制台窗口仍为空白。</span><span class="sxs-lookup"><span data-stu-id="69746-251">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 单步执行方法源 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="69746-253">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-253">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-254">Visual Studio 突出显示包含 `name` 变量赋值的语句。</span><span class="sxs-lookup"><span data-stu-id="69746-254">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="69746-255">“局部变量”  窗口显示 `name` 为 `Nothing`，控制台窗口显示字符串“What is your name?”。</span><span class="sxs-lookup"><span data-stu-id="69746-255">The **Locals** window shows that `name` is `Nothing`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="69746-256">在控制台窗口中输入字符串，然后按 Enter  ，从而响应提示。</span><span class="sxs-lookup"><span data-stu-id="69746-256">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="69746-257">控制台无响应，输入的字符串未显示在控制台窗口中，但 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法将捕获输入。</span><span class="sxs-lookup"><span data-stu-id="69746-257">The console is unresponsive, and the string you enter isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="69746-258">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-258">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-259">Visual Studio 突出显示包含 `currentDate` 变量赋值的语句。</span><span class="sxs-lookup"><span data-stu-id="69746-259">Visual Studio highlights the statement that includes the `currentDate` variable assignment.</span></span> <span data-ttu-id="69746-260">“局部变量”  窗口显示 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="69746-260">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="69746-261">控制台窗口还显示你在看到控制台输入提示后输入的字符串。</span><span class="sxs-lookup"><span data-stu-id="69746-261">The console window also displays the string entered when the console prompted for input.</span></span>

1. <span data-ttu-id="69746-262">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-262">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-263">控制台窗口保持不变。</span><span class="sxs-lookup"><span data-stu-id="69746-263">The console window is unchanged.</span></span>

1. <span data-ttu-id="69746-264">选择“调试”   > “单步执行”  ，或按 F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-264">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="69746-265">Visual Studio 调用 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="69746-265">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="69746-266">控制台窗口会显示格式化的字符串。</span><span class="sxs-lookup"><span data-stu-id="69746-266">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="69746-267">选择“调试”   > “跳出”  ，或按 Shift  +F11  。</span><span class="sxs-lookup"><span data-stu-id="69746-267">Select **Debug** > **Step Out** or press **Shift**+**F11**.</span></span> <span data-ttu-id="69746-268">这将停止单步执行。</span><span class="sxs-lookup"><span data-stu-id="69746-268">This stops step-by-step execution.</span></span> <span data-ttu-id="69746-269">控制台窗口会显示一条消息，并等待用户按任意键。</span><span class="sxs-lookup"><span data-stu-id="69746-269">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="69746-270">按任意键，关闭控制台窗口并停止调试。</span><span class="sxs-lookup"><span data-stu-id="69746-270">Press any key to close the console window and stop debugging.</span></span>

---

## <a name="build-a-release-version"></a><span data-ttu-id="69746-271">生成“发布”版本</span><span class="sxs-lookup"><span data-stu-id="69746-271">Build a Release version</span></span>

<span data-ttu-id="69746-272">测试应用程序的“调试”版本后，还应该编译并测试“发布”版本。</span><span class="sxs-lookup"><span data-stu-id="69746-272">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="69746-273">发布版本包含编译器优化，有时可能会对应用程序的行为产生不良影响。</span><span class="sxs-lookup"><span data-stu-id="69746-273">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="69746-274">例如，旨在提升性能的编译器优化可能会在多线程应用程序中创建争用条件。</span><span class="sxs-lookup"><span data-stu-id="69746-274">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="69746-275">若要生成和测试控制台应用程序的发布版本，请将工具栏上的生成配置从“调试”  更改为“发布”  。</span><span class="sxs-lookup"><span data-stu-id="69746-275">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![默认 Visual Studio 工具栏，其中突出显示调试](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="69746-277">按 F5  或选择“生成”  菜单中的“生成解决方案”  后，Visual Studio 会编译应用程序的“发布”版本。</span><span class="sxs-lookup"><span data-stu-id="69746-277">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="69746-278">可像测试“调试”版本一样测试“发布”版本。</span><span class="sxs-lookup"><span data-stu-id="69746-278">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69746-279">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69746-279">Next steps</span></span>

<span data-ttu-id="69746-280">调试完应用程序后，下一步是发布应用程序的可部署版本。</span><span class="sxs-lookup"><span data-stu-id="69746-280">Once you've debugged your application, the next step is to publish a deployable version of the app.</span></span> <span data-ttu-id="69746-281">若要了解如何执行此操作，请参阅[使用 Visual Studio 发布 .NET Core Hello World 应用程序](publishing-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="69746-281">For information on how to do this, see [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>
