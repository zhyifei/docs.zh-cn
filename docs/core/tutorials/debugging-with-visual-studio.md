---
title: "使用 Visual Studio 2017 调试 C# Hello World 应用程序"
description: "了解如何使用 Visual Studio 2017 调试用 C# 编写的 Hello World 应用程序。"
keywords: ".NET Core, .NET Core 控制台应用程序, .NET Core 调试"
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
ms.openlocfilehash: 6fbebf69b2772b4159841d13068e7b95a39bea92
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="debug-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="cd4ed-104">使用 Visual Studio 2017 调试 Hello World 应用程序</span><span class="sxs-lookup"><span data-stu-id="cd4ed-104">Debug your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="cd4ed-105">至此，已按照[使用 Visual Studio 2017 生成 C# .NET Core Hello World 应用程序](.\with-visual-studio.md)或[使用 Visual Studio 2017 生成 Visual Basic .NET Core Hello World 用用程序](vb-with-visual-studio.md)中的步骤操作，创建和运行简单的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-105">So far, you've followed the steps in [Build a C# Hello World Application with .NET Core in Visual Studio 2017](.\with-visual-studio.md) or [Build a Visual Basic Hello World Application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md) to create and run a simple console application.</span></span> <span data-ttu-id="cd4ed-106">编写和编译应用程序后，可以开始进行测试。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-106">Once you've written and compiled your application, you can begin testing it.</span></span> <span data-ttu-id="cd4ed-107">Visual Studio 提供一整套调试工具，方便你在测试和排除应用程序故障时使用。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-107">Visual Studio includes a comprehensive set of debugging tools that you can use when testing and troubleshooting your application.</span></span>

## <a name="debugging-in-debug-mode"></a><span data-ttu-id="cd4ed-108">在调试模式下调试</span><span class="sxs-lookup"><span data-stu-id="cd4ed-108">Debugging in Debug mode</span></span>

<span data-ttu-id="cd4ed-109">“调试”和“发布”是 Visual Studio 的两种默认生成配置。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-109">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="cd4ed-110">当前的生成配置显示在工具栏上。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-110">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="cd4ed-111">下面的工具栏图像显示 Visual Studio 配置为在“调试”模式下编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-111">The following toolbar image shows that Visual Studio is configured to compile your application in **Debug** mode.</span></span>

   ![Visual Studio 工具栏](./media/debugging-with-visual-studio/toolbar1.png)

<span data-ttu-id="cd4ed-113">一开始应始终在调试模式下测试程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-113">You should always begin by testing your program in Debug mode.</span></span> <span data-ttu-id="cd4ed-114">调试模式会禁用大多数编译器优化，并在生成过程中提供更丰富的信息。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-114">Debug mode turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="setting-a-breakpoint"></a><span data-ttu-id="cd4ed-115">设置断点</span><span class="sxs-lookup"><span data-stu-id="cd4ed-115">Setting a breakpoint</span></span>

<span data-ttu-id="cd4ed-116">在调试模式下运行程序，并尝试一些调试功能：</span><span class="sxs-lookup"><span data-stu-id="cd4ed-116">Run your program in Debug mode and try a few debugging features:</span></span>

1. <span data-ttu-id="cd4ed-117">断点会在执行包含断点的代码行之前暂时中断执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-117">A *breakpoint* temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="cd4ed-118">C#</span><span class="sxs-lookup"><span data-stu-id="cd4ed-118">C#</span></span>](#tab/csharp)
   <span data-ttu-id="cd4ed-119">若要在 `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` 一行上设置断点，可单击该行上代码窗口的左侧边缘，或选中该行，选择“调试” > “切换断点”菜单项。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-119">Set a breakpoint on the line that reads `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` by clicking in the left margin of the code window on that line or by choosing the **Debug** > **Toggle Breakpoint** menu item with the line selected.</span></span> <span data-ttu-id="cd4ed-120">如下图所示，Visual Studio 通过突出显示此代码行，并在其左侧边缘显示红色圆圈来指明这行设置了断点。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-120">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![设置断点后的 Visual Studio 程序窗口](./media/debugging-with-visual-studio/setbreakpoint.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="cd4ed-122">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd4ed-122">Visual Basic</span></span>](#tab/visual-basic)
   <span data-ttu-id="cd4ed-123">若要在 `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` 一行上设置断点，可单击该行上代码窗口的左侧边缘，或选中该行，选择“调试” > “切换断点”菜单项。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-123">Set a breakpoint on the line that reads `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` by clicking in the left margin of the code window on that line or by choosing the **Debug** > **Toggle Breakpoint** menu item with the line selected.</span></span> <span data-ttu-id="cd4ed-124">如下图所示，Visual Studio 通过突出显示此代码行，并在其左侧边缘显示红色圆圈来指明这行设置了断点。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-124">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   <a name="visual-studio-program-window-with-breakpoint-setmediadebugging-with-visual-studiovb-setbreakpointpng"></a>![设置断点后的 Visual Studio 程序窗口](./media/debugging-with-visual-studio/vb-setbreakpoint.png)
---

1. <span data-ttu-id="cd4ed-126">选择工具栏上含绿色箭头的“HelloWorld”按钮、按 F5 或选择“调试” > “启动调试”，在调试模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-126">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing F5, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="cd4ed-127">当程序提示输入名称时，在控制台窗口中输入字符串，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-127">Enter a string in the console window when the program prompts for a name and press Enter.</span></span>

1. <span data-ttu-id="cd4ed-128">到达断点时，程序停止执行，然后执行 `Console.WriteLine` 方法。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-128">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="cd4ed-129">“自动”窗口显示当前代码行周围使用的变量值。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-129">The **Autos** window displays the values of variables that are used around the current line.</span></span> <span data-ttu-id="cd4ed-130">“局部变量”窗口（可以通过单击“局部变量”选项卡查看）显示当前正在执行的方法中定义的变量值。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-130">The **Locals** window (which you can view by clicking the **Locals** tab) displays the values of variables that are defined in the currently executing method.</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="cd4ed-131">C#</span><span class="sxs-lookup"><span data-stu-id="cd4ed-131">C#</span></span>](#tab/csharp)
   ![Visual Studio 应用程序窗口](./media/debugging-with-visual-studio/break.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="cd4ed-133">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd4ed-133">Visual Basic</span></span>](#tab/visual-basic)
   <a name="visual-studio-application-windowmediadebugging-with-visual-studiovb-breakpng"></a>![Visual Studio 应用程序窗口](./media/debugging-with-visual-studio/vb-break.png)
---

1. <span data-ttu-id="cd4ed-135">可更改变量值，查看这样会对程序产生哪些影响。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-135">You can change the value of the variables to see how it affects your program.</span></span> <span data-ttu-id="cd4ed-136">如果“即时窗口”不可见，请选择“调试” > “Windows” > “即时”菜单项来显示它。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-136">If the **Immediate Window** is not visible, display it by choosing the **Debug** > **Windows** > **Immediate** menu item.</span></span> <span data-ttu-id="cd4ed-137">在“即时窗口”中，可以与正在调试的应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-137">The **Immediate Window** lets you interact with the application you're debugging.</span></span>

1. <span data-ttu-id="cd4ed-138">可以交互方式更改变量的值。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-138">You can interactively change the values of variables.</span></span> <span data-ttu-id="cd4ed-139">在“即时窗口”中输入 `name = "Gracie"`，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-139">Enter `name = "Gracie"` in the **Immediate Window** and press the Enter key.</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="cd4ed-140">C#</span><span class="sxs-lookup"><span data-stu-id="cd4ed-140">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="cd4ed-141">在“即时窗口”中输入 `date = new DateTime(2016,11,01,11,59,00)`，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-141">Enter `date = new DateTime(2016,11,01,11,59,00)` in the **Immediate Window** and press the Enter key.</span></span>

   <span data-ttu-id="cd4ed-142">“即时窗口”窗口显示字符串变量的值和 <xref:System.DateTime> 值的属性。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-142">The **Immediate Window** displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="cd4ed-143">此外，**“自动”**和**“局部变量”**窗口中也会更新变量值。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-143">In addition, the value of the variables is updated in the **Autos** and **Locals** windows.</span></span>

   ![自动窗口和即时窗口](./media/debugging-with-visual-studio/autosimmediate.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="cd4ed-145">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd4ed-145">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="cd4ed-146">在“即时窗口”中输入 `currentDate = new DateTime(2016,11,01,11,59,00)`，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-146">Enter `currentDate = new DateTime(2016,11,01,11,59,00)` in the **Immediate Window** and press the Enter key.</span></span>

<!-- The **Immediate Window** displays the value of the string variable and the properties of the <xref:System.DateTime> value. In addition, the value of the variables is updated in the **Autos** and **Locals** windows.

   ![Autos window and Immediate Window](./media/debugging-with-visual-studio/vb-autosimmediate.png)
-->
---

1. <span data-ttu-id="cd4ed-147">选择工具栏中的“继续”按钮，或选择“调试” > “继续”菜单项，继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-147">Continue program execution by selecting the **Continue** button in the toolbar or by selecting the **Debug** > **Continue** menu item.</span></span> <span data-ttu-id="cd4ed-148">控制台窗口中显示的值对应于在“即时窗口”中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-148">The values displayed in the console window correspond to the changes you made in the **Immediate Window**.</span></span>

   ![控制台窗口，在“What is your name?”提示下显示键入的值 Jack，后跟“Hello Gracie on 11/1/2016 at 11:59am”](./media/debugging-with-visual-studio/changed.png)

1. <span data-ttu-id="cd4ed-150">按任意键，退出应用程序并结束调试模式。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-150">Press any key to exit the application and end Debug mode.</span></span>

## <a name="setting-a-conditional-breakpoint"></a><span data-ttu-id="cd4ed-151">设置条件断点</span><span class="sxs-lookup"><span data-stu-id="cd4ed-151">Setting a conditional breakpoint</span></span>

<span data-ttu-id="cd4ed-152">程序显示用户输入的字符串。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-152">Your program displays the string that the user enters.</span></span> <span data-ttu-id="cd4ed-153">如果用户没有输入任何内容，情况又如何呢？</span><span class="sxs-lookup"><span data-stu-id="cd4ed-153">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="cd4ed-154">可使用实用的调试功能“条件断点”来测试这种情况，该功能可在满足一个或多个条件时中断程序执行。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-154">You can test this with a useful debugging feature, the *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="cd4ed-155">若要设置条件断点，并测试用户无法输入字符串时的情况如何，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cd4ed-155">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="cd4ed-156">C#</span><span class="sxs-lookup"><span data-stu-id="cd4ed-156">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="cd4ed-157">右键单击表示断点的红点。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-157">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="cd4ed-158">在上下文菜单中，选择“条件”，打开“断点设置”对话框。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-158">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="cd4ed-159">选中“条件”对应的框。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-159">Check the box for **Conditions**.</span></span>

   ![断点设置面板](./media/debugging-with-visual-studio/breakpointsettings.png)

1. <span data-ttu-id="cd4ed-161">对于“条件表达式”，将“e.g. x == 5”替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="cd4ed-161">For the **Conditional Expression** replace "e.g. x == 5" with the following:</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="cd4ed-162">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd4ed-162">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="cd4ed-163">右键单击表示断点的红点。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-163">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="cd4ed-164">在上下文菜单中，选择“条件”，打开“断点设置”对话框。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-164">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="cd4ed-165">选中“条件”对应的框。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-165">Check the box for **Conditions**.</span></span>

   ![断点设置面板](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. <span data-ttu-id="cd4ed-167">对于“条件表达式”，将“e.g. x = 5”替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="cd4ed-167">For the **Conditional Expression** replace "e.g. x = 5" with the following:</span></span>

   ```vb
   String.IsNullOrEmpty(name)
   ```
---

   <span data-ttu-id="cd4ed-168">要测试的代码条件是 `String.IsNullOrEmpty(name)` 方法调用是否为 `true`，因为 name 尚未分配有值或值为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-168">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because *name* has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="cd4ed-169">还可以指定命中次数，这样程序就会在语句的执行次数达到指定值时中断执行；也可以指定筛选条件，这样就可以根据诸如线程标识符、进程名称或线程名称之类的属性来中断程序执行。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-169">You can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="cd4ed-170">选择“关闭”按钮，关闭此对话框。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-170">Select the **Close** button to close the dialog.</span></span>

1. <span data-ttu-id="cd4ed-171">在调试模式下运行程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-171">Run the program in Debug mode.</span></span>

1. <span data-ttu-id="cd4ed-172">在控制台窗口中，在看到输入名称的提示时按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-172">In the console window, press the Enter key when prompted to enter your name.</span></span>

1. <span data-ttu-id="cd4ed-173">由于符合我们指定的条件（`name` 为 `null` 或 <xref:System.String.Empty?displayProperty=nameWithType>），因此程序在到达断点时以及在 `Console.WriteLine` 方法执行前停止执行。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-173">Because the condition we specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="cd4ed-174">选择“局部变量”窗口，其中显示当前正在执行的方法（在此程序中为 `Main` 方法）的局部变量值。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-174">Select the **Locals** window, which shows the values of variables that are local to the currently executing method, which is the `Main` method in your program.</span></span> <span data-ttu-id="cd4ed-175">请注意，`name` 变量的值为 `""` 或 <xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-175">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="cd4ed-176">C#</span><span class="sxs-lookup"><span data-stu-id="cd4ed-176">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="cd4ed-177">在“即时窗口”中输入下面的语句，确认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-177">Confirm the value is an empty string by entering the following statement in the **Immediate Window**.</span></span> <span data-ttu-id="cd4ed-178">结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-178">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ![即时窗口，执行语句后返回值 true](./media/debugging-with-visual-studio/emptystring.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="cd4ed-180">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd4ed-180">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="cd4ed-181">在“即时窗口”中输入下面的语句，确认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-181">Confirm the value is an empty string by entering the following statement in the **Immediate Window**.</span></span> <span data-ttu-id="cd4ed-182">结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-182">The result is `true`.</span></span>

   ```vb
   ? String.IsNullOrEmpty(name)
   ```
  ![即时窗口，执行语句后返回值 true](./media/debugging-with-visual-studio/vb-emptystring.png)
---

1. <span data-ttu-id="cd4ed-184">选择工具栏上的“继续”按钮，继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-184">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="cd4ed-185">按任意键，关闭控制台窗口并退出调试模式。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-185">Press any key to close the console window and exit Debug mode.</span></span>

1. <span data-ttu-id="cd4ed-186">单击代码窗口左侧边缘上的点，或选中该行，选择“调试”>“切换断点”菜单项，从而清除断点。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-186">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing the **Debug > Toggle Breakpoint** menu item with the row selected.</span></span>

---
## <a name="stepping-through-a-program"></a><span data-ttu-id="cd4ed-187">单步执行程序</span><span class="sxs-lookup"><span data-stu-id="cd4ed-187">Stepping through a program</span></span>

<span data-ttu-id="cd4ed-188">使用 Visual Studio，还可以单步执行程序，并监视其执行情况。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-188">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="cd4ed-189">通常可以设置断点，并使用此功能单步执行程序流，尽管是一小部分程序代码。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-189">Ordinarily, you'd set a breakpoint and use this feature to follow program flow though a small part of your program code.</span></span> <span data-ttu-id="cd4ed-190">因为程序很小，因此可以通过执行以下操作来单步执行整个程序：</span><span class="sxs-lookup"><span data-stu-id="cd4ed-190">Since your program is small, you can step through the entire program by doing the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="cd4ed-191">C#</span><span class="sxs-lookup"><span data-stu-id="cd4ed-191">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="cd4ed-192">在菜单栏上，选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-192">On the menu bar, choose **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-193">Visual Studio 会在要执行的下一行旁边突出显示一个箭头。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-193">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 窗口](./media/debugging-with-visual-studio/stepinto1.png)

   <span data-ttu-id="cd4ed-195">此时，“自动”窗口显示程序只定义了一个变量，即 `args`。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-195">At this point, the **Autos** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="cd4ed-196">由于尚未向程序传递任何命令行自变量，因此它的值是一个空字符串数组。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-196">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="cd4ed-197">此外，Visual Studio 还打开了一个空白控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-197">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="cd4ed-198">选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-198">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-199">Visual Studio 现在突出显示要执行的下一行。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-199">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="cd4ed-200">如图所示，从上一语句执行到这行代码花费了不到 1 毫秒的时间。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-200">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="cd4ed-201">`args` 仍然是唯一声明的变量，控制台窗口仍为空白。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-201">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 窗口](./media/debugging-with-visual-studio/stepinto2.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="cd4ed-203">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd4ed-203">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="cd4ed-204">在菜单栏上，选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-204">On the menu bar, choose **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-205">Visual Studio 会在要执行的下一行旁边突出显示一个箭头。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-205">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 窗口](./media/debugging-with-visual-studio/vb-stepinto1.png)

   <span data-ttu-id="cd4ed-207">此时，由于还没有向程序传递任何命令行参数，因此“自动”窗口显示 `args` 变量的值是一组空字符串。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-207">At this point, because you haven't passed any command-line arguments to the program, the **Autos** window shows that the value of the `args` variable is an empty string array.</span></span> <span data-ttu-id="cd4ed-208">此外，Visual Studio 还打开了一个空白控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-208">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="cd4ed-209">选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-209">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-210">Visual Studio 现在突出显示要执行的下一行。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-210">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="cd4ed-211">如图所示，从上一语句执行到这行代码花费了不到 1 毫秒的时间。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-211">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="cd4ed-212">`args` 仍然是唯一声明的变量，控制台窗口仍为空白。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-212">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 窗口](./media/debugging-with-visual-studio/vb-stepinto2.png)
---

1. <span data-ttu-id="cd4ed-214">选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-214">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-215">Visual Studio 突出显示包含 `name` 变量赋值的语句。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-215">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="cd4ed-216">“自动”窗口显示 `name` 为 `null`（在 C# 中）或 `Nothing`（在 Visual Basic 中），控制台窗口显示字符串“What is your name?”。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-216">The **Autos** window shows that `name` is `null` (in C#) or `Nothing` (in Visual Basic), and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="cd4ed-217">在控制台窗口中输入字符串，然后按 Enter，从而响应提示。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-217">Respond to the prompt by entering a string in the console window and pressing Enter.</span></span> <span data-ttu-id="cd4ed-218">控制台无响应，输入的字符串未显示在控制台窗口中，但 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法将捕获输入。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-218">The console is unresponsive, and the string you enter isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="cd4ed-219">选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-219">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-220">Visual Studio 突出显示包含 `date`（在 C# 中）或 `currentDate`（在 Visual Basic 中）变量赋值的语句。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-220">Visual Studio highlights the statement that includes the `date` (in C#) or `currentDate` (in Visual Basic) variable assignment.</span></span> <span data-ttu-id="cd4ed-221">“自动”窗口显示 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性值以及 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-221">The **Autos** window shows the <xref:System.DateTime.Now?displayProperty=nameWithType> property value and the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cd4ed-222">控制台窗口还显示你在看到控制台输入提示后输入的字符串。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-222">The console window also displays the string entered when the console prompted for input.</span></span>

1. <span data-ttu-id="cd4ed-223">选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-223">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-224">“自动”窗口显示通过 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性赋值后的 `date` 变量值。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-224">The **Autos** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="cd4ed-225">控制台窗口保持不变。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-225">The console window is unchanged.</span></span>

1. <span data-ttu-id="cd4ed-226">选择“调试” > “单步执行”，或按 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-226">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="cd4ed-227">Visual Studio 调用 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-227">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cd4ed-228">“自动”窗口显示 `date`（或 `currentDate`）和 `name` 变量的值，控制台窗口显示格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-228">The values of the `date` (or `currentDate`) and `name` variables appear in the **Autos** window, and the console window displays the formatted string.</span></span>

1. <span data-ttu-id="cd4ed-229">选择“调试” > “跳出”，或按 Shift 和 F11 键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-229">Select **Debug** > **Step Out** or press Shift and the F11 key.</span></span> <span data-ttu-id="cd4ed-230">这将停止单步执行。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-230">This stops step-by-step execution.</span></span> <span data-ttu-id="cd4ed-231">控制台窗口会显示一条消息，并等待用户按任意键。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-231">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="cd4ed-232">按任意键，关闭控制台窗口并退出调试模式。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-232">Press any key to close the console window and exit Debug mode.</span></span>

## <a name="building-a-release-version"></a><span data-ttu-id="cd4ed-233">生成发布版本</span><span class="sxs-lookup"><span data-stu-id="cd4ed-233">Building a Release version</span></span>

<span data-ttu-id="cd4ed-234">测试应用程序的调试版本后，还应该编译并测试发布版本。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-234">Once you've tested the Debug build of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="cd4ed-235">发布版本包含编译器优化，有时可能会对应用程序的行为产生不良影响。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-235">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="cd4ed-236">例如，旨在提升性能的编译器优化可能会在异步或多线程应用程序中创建争用条件。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-236">For example, compiler optimizations that are designed to improve performance can create race conditions in asynchronous or multithreaded applications.</span></span>

<span data-ttu-id="cd4ed-237">若要生成和测试控制台应用程序的发布版本，请将工具栏上的生成配置从“调试”更改为“发布”。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-237">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![Image](./media/debugging-with-visual-studio/toolbar2.png)

<span data-ttu-id="cd4ed-239">按 F5 或选择“生成”菜单中的“生成解决方案”后，Visual Studio 会编译控制台应用程序的发布版本。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-239">When you press F5 or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of your console application.</span></span> <span data-ttu-id="cd4ed-240">可像测试应用程序的调试版本一样测试发布版本。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-240">You can test it as you did the Debug version of the application.</span></span>

<span data-ttu-id="cd4ed-241">调试完应用程序后，下一步是发布应用程序的可部署版本。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-241">Once you've finished debugging your application, the next step is to publish a deployable version of your application.</span></span> <span data-ttu-id="cd4ed-242">若要了解如何执行此操作，请参阅[使用 Visual Studio 2017 发布 Hello World 应用程序](./publishing-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4ed-242">For information on how to do this, see [Publish the Hello World application with Visual Studio 2017](./publishing-with-visual-studio.md).</span></span>
