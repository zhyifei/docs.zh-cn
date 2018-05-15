---
title: 如何：在代码中模拟鼠标和键盘事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: cdb37fe549ebfbcdb5a0c5b6008a1922fdbf471b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="fcebc-102">如何：在代码中模拟鼠标和键盘事件</span><span class="sxs-lookup"><span data-stu-id="fcebc-102">How to: Simulate Mouse and Keyboard Events in Code</span></span>
<span data-ttu-id="fcebc-103">Windows 窗体提供多个选项，用于以编程方式模拟鼠标和键盘输入。</span><span class="sxs-lookup"><span data-stu-id="fcebc-103">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="fcebc-104">本主题将简要阐述这些选项。</span><span class="sxs-lookup"><span data-stu-id="fcebc-104">This topic provides an overview of these options.</span></span>  
  
## <a name="simulating-mouse-input"></a><span data-ttu-id="fcebc-105">模拟鼠标输入</span><span class="sxs-lookup"><span data-stu-id="fcebc-105">Simulating Mouse Input</span></span>  
 <span data-ttu-id="fcebc-106">模拟鼠标事件的最佳方法是调用 `On`*EventName* 方法，引发要模拟的鼠标事件。</span><span class="sxs-lookup"><span data-stu-id="fcebc-106">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="fcebc-107">此选项通常只在自定义控件和窗体内可用，因为引发事件的方法受到保护且只能在控件或窗体内访问。</span><span class="sxs-lookup"><span data-stu-id="fcebc-107">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="fcebc-108">例如，以下步骤说明了如何在代码中模拟单击鼠标右键按钮的操作。</span><span class="sxs-lookup"><span data-stu-id="fcebc-108">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>  
  
#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="fcebc-109">若要以编程方式单击鼠标右键按钮</span><span class="sxs-lookup"><span data-stu-id="fcebc-109">To programmatically click the right mouse button</span></span>  
  
1.  <span data-ttu-id="fcebc-110">创建 <xref:System.Windows.Forms.MouseEventArgs>，其 <xref:System.Windows.Forms.MouseEventArgs.Button%2A> 属性设置为 <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> 值。</span><span class="sxs-lookup"><span data-stu-id="fcebc-110">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>  
  
2.  <span data-ttu-id="fcebc-111">调用 <xref:System.Windows.Forms.Control.OnMouseClick%2A> 方法，其中参数为此 <xref:System.Windows.Forms.MouseEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="fcebc-111">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>  
  
 <span data-ttu-id="fcebc-112">有关自定义控件的详细信息，请参阅[设计时开发 Windows 窗体控件](../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="fcebc-112">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span>  
  
 <span data-ttu-id="fcebc-113">还可使用其他方法模拟鼠标输入。</span><span class="sxs-lookup"><span data-stu-id="fcebc-113">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="fcebc-114">例如，可以编程方式设置表示状态（通常通过鼠标输入设置）的控件属性（如 <xref:System.Windows.Forms.CheckBox.Checked%2A> 控件的 <xref:System.Windows.Forms.CheckBox> 属性），也可以直接调用连接到要模拟的事件的委托。</span><span class="sxs-lookup"><span data-stu-id="fcebc-114">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>  
  
## <a name="simulating-keyboard-input"></a><span data-ttu-id="fcebc-115">模拟键盘输入</span><span class="sxs-lookup"><span data-stu-id="fcebc-115">Simulating Keyboard Input</span></span>  
 <span data-ttu-id="fcebc-116">除了可通过上面讨论的鼠标输入策略来模拟键盘输入，Windows 窗体还提供了 <xref:System.Windows.Forms.SendKeys> 类，可将击键发送到活动的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcebc-116">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="fcebc-117">如果你的应用程序旨在用于全球各种键盘，使用 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 可能会产生不可预知的结果，应当避免。</span><span class="sxs-lookup"><span data-stu-id="fcebc-117">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcebc-118"><xref:System.Windows.Forms.SendKeys> 类已更新为 .NET Framework 3.0，从而可用于在 Windows Vista 上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcebc-118">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="fcebc-119">Windows Vista 增强的安全性（称为用户帐户控件或 UAC）可避免以前的实现按预期运行。</span><span class="sxs-lookup"><span data-stu-id="fcebc-119">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>  
>   
>  <span data-ttu-id="fcebc-120"><xref:System.Windows.Forms.SendKeys> 类容易遭受某些开发人员不得不解决的计时问题。</span><span class="sxs-lookup"><span data-stu-id="fcebc-120">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="fcebc-121">更新后的实现仍然容易遇到计时问题，但速度稍微快一些，并且可能需要更改解决方法。</span><span class="sxs-lookup"><span data-stu-id="fcebc-121">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="fcebc-122"><xref:System.Windows.Forms.SendKeys> 类先尝试使用以前的实现，失败后再使用新的实现。</span><span class="sxs-lookup"><span data-stu-id="fcebc-122">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="fcebc-123">因此， <xref:System.Windows.Forms.SendKeys> 类在不同操作系统上的运行方式可能不同。</span><span class="sxs-lookup"><span data-stu-id="fcebc-123">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="fcebc-124">此外，当 <xref:System.Windows.Forms.SendKeys> 类使用新的实现时， <xref:System.Windows.Forms.SendKeys.SendWait%2A> 方法不会等到消息被处理后才将其发送至其他进程。</span><span class="sxs-lookup"><span data-stu-id="fcebc-124">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>  
>   
>  <span data-ttu-id="fcebc-125">如果如论使用何种操作系统，你的应用程序均依赖于一致的行为，则可通过将以下应用程序设置添加至 app.config 文件强制执行 <xref:System.Windows.Forms.SendKeys> 类以使用新的实现。</span><span class="sxs-lookup"><span data-stu-id="fcebc-125">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>  
>   
>  `<appSettings>`  
>   
>  `<add key="SendKeys" value="SendInput"/>`  
>   
>  `</appSettings>`  
>   
>  <span data-ttu-id="fcebc-126">若要强制执行 <xref:System.Windows.Forms.SendKeys> 类以使用以前的实现，请改用 `"JournalHook"` 值。</span><span class="sxs-lookup"><span data-stu-id="fcebc-126">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>  
  
#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="fcebc-127">若要将击键发送到相同的应用程序</span><span class="sxs-lookup"><span data-stu-id="fcebc-127">To send a keystroke to the same application</span></span>  
  
1.  <span data-ttu-id="fcebc-128">调用 <xref:System.Windows.Forms.SendKeys.Send%2A> 类或 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 类的 <xref:System.Windows.Forms.SendKeys> 方法。</span><span class="sxs-lookup"><span data-stu-id="fcebc-128">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="fcebc-129">指定的击键将由应用程序的活动控件接收。</span><span class="sxs-lookup"><span data-stu-id="fcebc-129">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="fcebc-130">下面的代码示例使用 <xref:System.Windows.Forms.SendKeys.Send%2A> 模拟用户双击窗体表面时按 ENTER 键的操作。</span><span class="sxs-lookup"><span data-stu-id="fcebc-130">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="fcebc-131">此示例假定 <xref:System.Windows.Forms.Form> 具有一个选项卡索引为 0 的 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="fcebc-131">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]  
  
#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="fcebc-132">若要将击键发送到不同的应用程序</span><span class="sxs-lookup"><span data-stu-id="fcebc-132">To send a keystroke to a different application</span></span>  
  
1.  <span data-ttu-id="fcebc-133">激活将接收击键的应用程序窗口，然后调用 <xref:System.Windows.Forms.SendKeys.Send%2A> 或 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fcebc-133">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="fcebc-134">由于托管的方法均不会激活其他应用程序，所以必须使用本机 Windows 方法将焦点强制设置到其他应用程序上。</span><span class="sxs-lookup"><span data-stu-id="fcebc-134">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="fcebc-135">下面的代码示例使用平台调用来调用 `FindWindow` 和 `SetForegroundWindow` 方法以激活计算器应用程序窗口，然后调用 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 向计算器应用程序发出一系列计算。</span><span class="sxs-lookup"><span data-stu-id="fcebc-135">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fcebc-136">可查找计算器应用程序的 `FindWindow` 调用的正确参数因 Windows 版本而异。</span><span class="sxs-lookup"><span data-stu-id="fcebc-136">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="fcebc-137">下面的代码查找 [!INCLUDE[win7](../../../includes/win7-md.md)]上的计算器应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcebc-137">The following code finds the Calculator application on [!INCLUDE[win7](../../../includes/win7-md.md)].</span></span> <span data-ttu-id="fcebc-138">在 [!INCLUDE[windowsver](../../../includes/windowsver-md.md)]上，将第一个参数更改为“SciCalc”。</span><span class="sxs-lookup"><span data-stu-id="fcebc-138">On [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], change the first parameter to "SciCalc".</span></span> <span data-ttu-id="fcebc-139">可使用 Spy++ 工具（Visual Studio 附带）确定正确的参数。</span><span class="sxs-lookup"><span data-stu-id="fcebc-139">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="fcebc-140">示例</span><span class="sxs-lookup"><span data-stu-id="fcebc-140">Example</span></span>  
 <span data-ttu-id="fcebc-141">以下代码示例显示上述代码示例的完整应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcebc-141">The following code example is the complete application for the previous code examples.</span></span>  
  
 [!code-cpp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fcebc-142">编译代码</span><span class="sxs-lookup"><span data-stu-id="fcebc-142">Compiling the Code</span></span>  
 <span data-ttu-id="fcebc-143">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fcebc-143">This example requires:</span></span>  
  
-   <span data-ttu-id="fcebc-144">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fcebc-144">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fcebc-145">为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="fcebc-145">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fcebc-146">你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。</span><span class="sxs-lookup"><span data-stu-id="fcebc-146">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="fcebc-147">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="fcebc-147">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcebc-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcebc-148">See Also</span></span>  
 [<span data-ttu-id="fcebc-149">Windows 窗体中的用户输入</span><span class="sxs-lookup"><span data-stu-id="fcebc-149">User Input in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-in-windows-forms.md)
