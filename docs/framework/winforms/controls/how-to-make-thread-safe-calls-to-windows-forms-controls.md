---
title: 如何：对 Windows 窗体控件进行线程安全调用
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
ms.openlocfilehash: 78ad7b16d5220972a61848c0c80cd884afa842d9
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928620"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="440eb-102">如何：对 Windows 窗体控件进行线程安全调用</span><span class="sxs-lookup"><span data-stu-id="440eb-102">How to: Make thread-safe calls to Windows Forms controls</span></span>

<span data-ttu-id="440eb-103">多线程处理可以提高 Windows 窗体应用的性能，但对 Windows 窗体控件的访问本质上不是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="440eb-103">Multithreading can improve the performance of Windows Forms apps, but access to Windows Forms controls isn't inherently thread-safe.</span></span> <span data-ttu-id="440eb-104">多线程处理可以将你的代码公开给非常严重且复杂的 bug。</span><span class="sxs-lookup"><span data-stu-id="440eb-104">Multithreading can expose your code to very serious and complex bugs.</span></span> <span data-ttu-id="440eb-105">处理控件的两个或多个线程可能会强制控件处于不一致状态并导致争用情况、死锁和冻结或挂起。</span><span class="sxs-lookup"><span data-stu-id="440eb-105">Two or more threads manipulating a control can force the control into an inconsistent state and lead to race conditions, deadlocks, and freezes or hangs.</span></span> <span data-ttu-id="440eb-106">如果在应用程序中实现多线程处理，请确保以线程安全的方式调用跨线程控件。</span><span class="sxs-lookup"><span data-stu-id="440eb-106">If you implement multithreading in your app, be sure to call cross-thread controls in a thread-safe way.</span></span> <span data-ttu-id="440eb-107">有关详细信息，请参阅[托管线程处理最佳做法](../../../standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="440eb-107">For more information, see [Managed threading best practices](../../../standard/threading/managed-threading-best-practices.md).</span></span> 

<span data-ttu-id="440eb-108">可以通过两种方法从未创建该控件的线程安全调用 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="440eb-108">There are two ways to safely call a Windows Forms control from a thread that didn't create that control.</span></span> <span data-ttu-id="440eb-109">您可以使用<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>方法调用在主线程中创建的委托，该委托又调用控件。</span><span class="sxs-lookup"><span data-stu-id="440eb-109">You can use the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method to call a delegate created in the main thread, which in turn calls the control.</span></span> <span data-ttu-id="440eb-110">或者，你可以实现<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>，它使用事件驱动模型将后台线程中完成的工作与报表上的结果进行分隔。</span><span class="sxs-lookup"><span data-stu-id="440eb-110">Or, you can implement a <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, which uses an event-driven model to separate work done in the background thread from reporting on the results.</span></span> 

## <a name="unsafe-cross-thread-calls"></a><span data-ttu-id="440eb-111">不安全的跨线程调用</span><span class="sxs-lookup"><span data-stu-id="440eb-111">Unsafe cross-thread calls</span></span>

<span data-ttu-id="440eb-112">直接从未创建控件的线程调用控件是不安全的。</span><span class="sxs-lookup"><span data-stu-id="440eb-112">It's unsafe to call a control directly from a thread that didn't create it.</span></span> <span data-ttu-id="440eb-113">下面的代码段演示了对<xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>控件的不安全调用。</span><span class="sxs-lookup"><span data-stu-id="440eb-113">The following code snippet illustrates an unsafe call to the <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control.</span></span> <span data-ttu-id="440eb-114">事件处理程序创建一个新`WriteTextUnsafe`线程，该线程直接设置主线程<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>的属性。 `Button1_Click`</span><span class="sxs-lookup"><span data-stu-id="440eb-114">The `Button1_Click` event handler creates a new `WriteTextUnsafe` thread, which sets the main thread's <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> property directly.</span></span> 

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

<span data-ttu-id="440eb-115">Visual Studio 调试器通过引发<xref:System.InvalidOperationException>消息（跨线程操作无效） **来检测这些不安全的线程调用。控件 "" 从创建它的线程之外的其他线程访问。**</span><span class="sxs-lookup"><span data-stu-id="440eb-115">The Visual Studio debugger detects these unsafe thread calls by raising an <xref:System.InvalidOperationException> with the message, **Cross-thread operation not valid. Control "" accessed from a thread other than the thread it was created on.**</span></span> <span data-ttu-id="440eb-116">在 Visual Studio 调试过程中，对于不安全的跨线程调用始终出现，在应用运行时可能会发生。<xref:System.InvalidOperationException></span><span class="sxs-lookup"><span data-stu-id="440eb-116">The <xref:System.InvalidOperationException> always occurs for unsafe cross-thread calls during Visual Studio debugging, and may occur at app runtime.</span></span> <span data-ttu-id="440eb-117">你应修复此问题，但你可以通过将<xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType>属性设置为来`false`禁用异常。</span><span class="sxs-lookup"><span data-stu-id="440eb-117">You should fix the issue, but you can disable the exception by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> property to `false`.</span></span>

## <a name="safe-cross-thread-calls"></a><span data-ttu-id="440eb-118">安全的跨线程调用</span><span class="sxs-lookup"><span data-stu-id="440eb-118">Safe cross-thread calls</span></span> 

<span data-ttu-id="440eb-119">下面的代码示例演示了两种从未创建 Windows 窗体控件的线程安全调用的方法：</span><span class="sxs-lookup"><span data-stu-id="440eb-119">The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:</span></span> 

1. <span data-ttu-id="440eb-120"><xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>方法，它从主线程调用委托以调用控件。</span><span class="sxs-lookup"><span data-stu-id="440eb-120">The <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method, which calls a delegate from the main thread to call the control.</span></span> 
2. <span data-ttu-id="440eb-121">一个<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>组件，它提供事件驱动模型。</span><span class="sxs-lookup"><span data-stu-id="440eb-121">A <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which offers an event-driven model.</span></span> 

<span data-ttu-id="440eb-122">在这两个示例中，后台线程休眠一秒钟，以模拟在该线程中完成的工作。</span><span class="sxs-lookup"><span data-stu-id="440eb-122">In both examples, the background thread sleeps for one second to simulate work being done in that thread.</span></span> 

<span data-ttu-id="440eb-123">你可以从C#或 Visual Basic 命令行 .NET Framework 应用生成并运行这些示例。</span><span class="sxs-lookup"><span data-stu-id="440eb-123">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="440eb-124">有关详细信息，请参阅[通过 csc 生成命令行](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[从命令行生成（Visual Basic）](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="440eb-124">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="440eb-125">从.NET Core 3.0 开始，你还可以生成并运行示例作为 Windows.NET Core 应用程序从具有.NET Core Windows 窗体的文件夹 *\<文件夹名称>.csproj* 项目文件。</span><span class="sxs-lookup"><span data-stu-id="440eb-125">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-use-the-invoke-method-with-a-delegate"></a><span data-ttu-id="440eb-126">示例：将 Invoke 方法与委托一起使用</span><span class="sxs-lookup"><span data-stu-id="440eb-126">Example: Use the Invoke method with a delegate</span></span>

<span data-ttu-id="440eb-127">下面的示例演示了一种用于确保对 Windows 窗体控件进行线程安全调用的模式。</span><span class="sxs-lookup"><span data-stu-id="440eb-127">The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control.</span></span> <span data-ttu-id="440eb-128">它查询<xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>属性，该属性将控件的创建线程 id 与调用线程 id 进行比较。</span><span class="sxs-lookup"><span data-stu-id="440eb-128">It queries the <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> property, which compares the control's creating thread ID to the calling thread ID.</span></span> <span data-ttu-id="440eb-129">如果线程 Id 相同，则它会直接调用控件。</span><span class="sxs-lookup"><span data-stu-id="440eb-129">If the thread IDs are the same, it calls the control directly.</span></span> <span data-ttu-id="440eb-130">如果线程 id 不同，则使用主线程中<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType>的委托调用方法，这将对控件进行实际调用。</span><span class="sxs-lookup"><span data-stu-id="440eb-130">If the thread IDs are different, it calls the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> method with a delegate from the main thread, which makes the actual call to the control.</span></span>

<span data-ttu-id="440eb-131">允许设置控件的<xref:System.Windows.Forms.TextBox.Text%2A>属性。 <xref:System.Windows.Forms.TextBox> `SafeCallDelegate`</span><span class="sxs-lookup"><span data-stu-id="440eb-131">The `SafeCallDelegate` enables setting the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="440eb-132">`WriteTextSafe`方法查询<xref:System.Windows.Forms.Control.InvokeRequired%2A>。</span><span class="sxs-lookup"><span data-stu-id="440eb-132">The `WriteTextSafe` method queries <xref:System.Windows.Forms.Control.InvokeRequired%2A>.</span></span> <span data-ttu-id="440eb-133">如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>返回`true` ，`WriteTextSafe`则将传递`SafeCallDelegate`给方法以对控件进行实际调用。<xref:System.Windows.Forms.Control.Invoke%2A></span><span class="sxs-lookup"><span data-stu-id="440eb-133">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, `WriteTextSafe` passes the `SafeCallDelegate` to the <xref:System.Windows.Forms.Control.Invoke%2A> method to make the actual call to the control.</span></span> <span data-ttu-id="440eb-134">如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>返回`false`，则`WriteTextSafe`直接设置。 <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="440eb-134">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, `WriteTextSafe` sets the <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directly.</span></span> <span data-ttu-id="440eb-135">事件处理程序创建新线程并`WriteTextSafe`运行方法。 `Button1_Click`</span><span class="sxs-lookup"><span data-stu-id="440eb-135">The `Button1_Click` event handler creates the new thread and runs the `WriteTextSafe` method.</span></span> 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a><span data-ttu-id="440eb-136">示例：使用 BackgroundWorker 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="440eb-136">Example: Use a BackgroundWorker event handler</span></span>

<span data-ttu-id="440eb-137">实现多线程处理的一种简单方法<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>是使用组件，该组件使用事件驱动模型。</span><span class="sxs-lookup"><span data-stu-id="440eb-137">An easy way to implement multithreading is with the <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which uses an event-driven model.</span></span> <span data-ttu-id="440eb-138">后台线程运行<xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>不与主线程交互的事件。</span><span class="sxs-lookup"><span data-stu-id="440eb-138">The background thread runs the <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> event, which doesn't interact with the main thread.</span></span> <span data-ttu-id="440eb-139">主线程运行<xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType>和<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>事件处理程序，这些处理程序可以调用主线程的控件。</span><span class="sxs-lookup"><span data-stu-id="440eb-139">The main thread runs the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> event handlers, which can call the main thread's controls.</span></span>

<span data-ttu-id="440eb-140">若要通过使用<xref:System.ComponentModel.BackgroundWorker>进行线程安全调用，请在后台线程中创建方法来完成工作，并将其绑定<xref:System.ComponentModel.BackgroundWorker.DoWork>到事件。</span><span class="sxs-lookup"><span data-stu-id="440eb-140">To make a thread-safe call by using <xref:System.ComponentModel.BackgroundWorker>, create a method in the background thread to do the work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event.</span></span> <span data-ttu-id="440eb-141">在主线程中创建另一个方法来报告后台工作的结果，并将其绑定到<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>或<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="440eb-141">Create another method in the main thread to report the results of the background work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> or <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span> <span data-ttu-id="440eb-142">若要启动后台线程，请<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>调用。</span><span class="sxs-lookup"><span data-stu-id="440eb-142">To start the background thread, call <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>.</span></span> 

<span data-ttu-id="440eb-143">该示例使用<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序<xref:System.Windows.Forms.TextBox>设置控件的<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="440eb-143">The example uses the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler to set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="440eb-144">有关使用<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件的示例，请参见<xref:System.ComponentModel.BackgroundWorker>。</span><span class="sxs-lookup"><span data-stu-id="440eb-144">For an example using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span> 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="440eb-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="440eb-145">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="440eb-146">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="440eb-146">How to: Run an operation in the background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="440eb-147">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="440eb-147">How to: Implement a form that uses a background operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="440eb-148">利用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="440eb-148">Develop custom Windows Forms controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
