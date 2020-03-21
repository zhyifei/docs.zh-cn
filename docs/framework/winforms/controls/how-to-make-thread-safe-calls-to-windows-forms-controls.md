---
title: 对控件进行线程安全调用
ms.date: 02/19/2019
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: 365b1acb693b9ff2be603a3e659ed8d846a7696a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141999"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="8ff0b-102">如何：对 Windows 窗体控件进行线程安全调用</span><span class="sxs-lookup"><span data-stu-id="8ff0b-102">How to: Make thread-safe calls to Windows Forms controls</span></span>

<span data-ttu-id="8ff0b-103">多线程可以提高 Windows 窗体应用的性能，但访问 Windows 窗体控件本质上并不安全线程。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-103">Multithreading can improve the performance of Windows Forms apps, but access to Windows Forms controls isn't inherently thread-safe.</span></span> <span data-ttu-id="8ff0b-104">多线程可能会将代码暴露给非常严重和复杂的错误。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-104">Multithreading can expose your code to very serious and complex bugs.</span></span> <span data-ttu-id="8ff0b-105">操作控件的两个或多个线程可能会强制控件进入不一致状态，并导致争用条件、死锁以及冻结或挂起。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-105">Two or more threads manipulating a control can force the control into an inconsistent state and lead to race conditions, deadlocks, and freezes or hangs.</span></span> <span data-ttu-id="8ff0b-106">如果在应用中实现多线程读取，请确保以线程安全的方式调用交叉线程控件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-106">If you implement multithreading in your app, be sure to call cross-thread controls in a thread-safe way.</span></span> <span data-ttu-id="8ff0b-107">有关详细信息，请参阅[托管线程最佳实践](../../../standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-107">For more information, see [Managed threading best practices](../../../standard/threading/managed-threading-best-practices.md).</span></span>

<span data-ttu-id="8ff0b-108">有两种方法可以从未创建该控件的线程安全地调用 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-108">There are two ways to safely call a Windows Forms control from a thread that didn't create that control.</span></span> <span data-ttu-id="8ff0b-109">可以使用 方法<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>调用在主线程中创建的委托，而主线程又调用控件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-109">You can use the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method to call a delegate created in the main thread, which in turn calls the control.</span></span> <span data-ttu-id="8ff0b-110">或者，可以实现 一<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>个 ，它使用事件驱动的模型将后台线程中完成的工作与报告结果分开。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-110">Or, you can implement a <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, which uses an event-driven model to separate work done in the background thread from reporting on the results.</span></span>

## <a name="unsafe-cross-thread-calls"></a><span data-ttu-id="8ff0b-111">不安全的交叉线程调用</span><span class="sxs-lookup"><span data-stu-id="8ff0b-111">Unsafe cross-thread calls</span></span>

<span data-ttu-id="8ff0b-112">直接从未创建控件的线程调用控件是不安全的。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-112">It's unsafe to call a control directly from a thread that didn't create it.</span></span> <span data-ttu-id="8ff0b-113">以下代码段说明了对控件的<xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>不安全调用。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-113">The following code snippet illustrates an unsafe call to the <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control.</span></span> <span data-ttu-id="8ff0b-114">事件`Button1_Click`处理程序创建一个新`WriteTextUnsafe`线程，该线程直接设置主线程的属性。 <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8ff0b-114">The `Button1_Click` event handler creates a new `WriteTextUnsafe` thread, which sets the main thread's <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> property directly.</span></span>

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

<span data-ttu-id="8ff0b-115">Visual Studio 调试器通过引发消息中的 调用<xref:System.InvalidOperationException>来检测这些不安全的线程调用，**跨线程操作无效。控件""从创建该线程以外的线程访问。**</span><span class="sxs-lookup"><span data-stu-id="8ff0b-115">The Visual Studio debugger detects these unsafe thread calls by raising an <xref:System.InvalidOperationException> with the message, **Cross-thread operation not valid. Control "" accessed from a thread other than the thread it was created on.**</span></span> <span data-ttu-id="8ff0b-116">在<xref:System.InvalidOperationException>Visual Studio 调试期间，始终发生不安全的交叉线程调用，并且可能在应用运行时发生。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-116">The <xref:System.InvalidOperationException> always occurs for unsafe cross-thread calls during Visual Studio debugging, and may occur at app runtime.</span></span> <span data-ttu-id="8ff0b-117">应修复此问题，但可以通过将<xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType>属性设置为`false`来禁用异常。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-117">You should fix the issue, but you can disable the exception by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> property to `false`.</span></span>

## <a name="safe-cross-thread-calls"></a><span data-ttu-id="8ff0b-118">安全交叉线程调用</span><span class="sxs-lookup"><span data-stu-id="8ff0b-118">Safe cross-thread calls</span></span>

<span data-ttu-id="8ff0b-119">以下代码示例演示了从未创建该控件的线程安全地调用 Windows 窗体控件的两种方法：</span><span class="sxs-lookup"><span data-stu-id="8ff0b-119">The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:</span></span>

1. <span data-ttu-id="8ff0b-120">方法<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>，它从主线程调用委托来调用控件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-120">The <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method, which calls a delegate from the main thread to call the control.</span></span>
2. <span data-ttu-id="8ff0b-121">提供<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>事件驱动模型的组件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-121">A <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which offers an event-driven model.</span></span>

<span data-ttu-id="8ff0b-122">在这两个示例中，后台线程休眠一秒钟以模拟该线程中正在完成的工作。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-122">In both examples, the background thread sleeps for one second to simulate work being done in that thread.</span></span>

<span data-ttu-id="8ff0b-123">可以从 C# 或 Visual Basic 命令行生成和运行这些示例为 .NET 框架应用。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-123">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="8ff0b-124">有关详细信息，请参阅使用[csc.exe 的命令行构建](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[命令行（可视基本）中的生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-124">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="8ff0b-125">从 .NET Core 3.0 开始，您还可以从具有 .NET 核心 Windows 窗体*\<文件夹名称>.csproj*项目文件的文件夹中生成并运行 Windows .NET Core 应用示例。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-125">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-use-the-invoke-method-with-a-delegate"></a><span data-ttu-id="8ff0b-126">示例：使用具有委托的 Invoke 方法</span><span class="sxs-lookup"><span data-stu-id="8ff0b-126">Example: Use the Invoke method with a delegate</span></span>

<span data-ttu-id="8ff0b-127">下面的示例演示了用于确保对 Windows 窗体控件进行线程安全调用的模式。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-127">The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control.</span></span> <span data-ttu-id="8ff0b-128">它查询该<xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>属性，该属性将控件的创建线程 ID 与调用线程 ID 进行比较。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-128">It queries the <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> property, which compares the control's creating thread ID to the calling thread ID.</span></span> <span data-ttu-id="8ff0b-129">如果线程指示相同，它将直接调用控件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-129">If the thread IDs are the same, it calls the control directly.</span></span> <span data-ttu-id="8ff0b-130">如果线程指示不同，它将使用主线程的委托调用<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType>方法，从而对控件进行实际调用。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-130">If the thread IDs are different, it calls the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> method with a delegate from the main thread, which makes the actual call to the control.</span></span>

<span data-ttu-id="8ff0b-131">启用`SafeCallDelegate`设置<xref:System.Windows.Forms.TextBox>控件的属性<xref:System.Windows.Forms.TextBox.Text%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-131">The `SafeCallDelegate` enables setting the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8ff0b-132">方法`WriteTextSafe`查询<xref:System.Windows.Forms.Control.InvokeRequired%2A>。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-132">The `WriteTextSafe` method queries <xref:System.Windows.Forms.Control.InvokeRequired%2A>.</span></span> <span data-ttu-id="8ff0b-133">如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>返回`true` `WriteTextSafe` ，则`SafeCallDelegate`将<xref:System.Windows.Forms.Control.Invoke%2A>传递给 方法以对控件进行实际调用。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-133">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, `WriteTextSafe` passes the `SafeCallDelegate` to the <xref:System.Windows.Forms.Control.Invoke%2A> method to make the actual call to the control.</span></span> <span data-ttu-id="8ff0b-134">如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>返回`false` `WriteTextSafe` ，则<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>直接设置 。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-134">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, `WriteTextSafe` sets the <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directly.</span></span> <span data-ttu-id="8ff0b-135">事件`Button1_Click`处理程序创建新线程并运行方法`WriteTextSafe`。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-135">The `Button1_Click` event handler creates the new thread and runs the `WriteTextSafe` method.</span></span>

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a><span data-ttu-id="8ff0b-136">示例：使用后台辅助角色事件处理程序</span><span class="sxs-lookup"><span data-stu-id="8ff0b-136">Example: Use a BackgroundWorker event handler</span></span>

<span data-ttu-id="8ff0b-137">实现多线程的一种简单方法是使用<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>组件，该组件使用事件驱动的模型。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-137">An easy way to implement multithreading is with the <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which uses an event-driven model.</span></span> <span data-ttu-id="8ff0b-138">后台线程运行事件<xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>，该事件不与主线程交互。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-138">The background thread runs the <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> event, which doesn't interact with the main thread.</span></span> <span data-ttu-id="8ff0b-139">主线程运行 和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType><xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>事件处理程序，可以调用主线程的控件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-139">The main thread runs the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> event handlers, which can call the main thread's controls.</span></span>

<span data-ttu-id="8ff0b-140">要使用 进行<xref:System.ComponentModel.BackgroundWorker>线程安全调用，请在后台线程中创建一个方法来执行该工作，并将其绑定到<xref:System.ComponentModel.BackgroundWorker.DoWork>事件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-140">To make a thread-safe call by using <xref:System.ComponentModel.BackgroundWorker>, create a method in the background thread to do the work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event.</span></span> <span data-ttu-id="8ff0b-141">在主线程中创建另一种方法以报告后台工作的结果，并将其绑定到<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>或<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-141">Create another method in the main thread to report the results of the background work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> or <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span> <span data-ttu-id="8ff0b-142">要启动后台线程，请调用<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-142">To start the background thread, call <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="8ff0b-143">该示例使用<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序设置<xref:System.Windows.Forms.TextBox>控件的属性。 <xref:System.Windows.Forms.TextBox.Text%2A></span><span class="sxs-lookup"><span data-stu-id="8ff0b-143">The example uses the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler to set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8ff0b-144">有关使用事件的示例，<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>请参阅<xref:System.ComponentModel.BackgroundWorker>。</span><span class="sxs-lookup"><span data-stu-id="8ff0b-144">For an example using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span>

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="8ff0b-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ff0b-145">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="8ff0b-146">操作方式：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="8ff0b-146">How to: Run an operation in the background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="8ff0b-147">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="8ff0b-147">How to: Implement a form that uses a background operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="8ff0b-148">使用 .NET 框架开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="8ff0b-148">Develop custom Windows Forms controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
