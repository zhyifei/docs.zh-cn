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
ms.openlocfilehash: 3211df1f0e585780039471b80b5b913613ad9bbd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913791"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="8bef1-102">如何：对 Windows 窗体控件进行线程安全调用</span><span class="sxs-lookup"><span data-stu-id="8bef1-102">How to: Make thread-safe calls to Windows Forms controls</span></span>

<span data-ttu-id="8bef1-103">多线程处理可以提高性能的 Windows 窗体应用程序，但对 Windows 窗体控件的访问不是本质上是线程安全。</span><span class="sxs-lookup"><span data-stu-id="8bef1-103">Multithreading can improve the performance of Windows Forms apps, but access to Windows Forms controls isn't inherently thread-safe.</span></span> <span data-ttu-id="8bef1-104">多线程处理可以公开你的代码非常严重且复杂的 bug。</span><span class="sxs-lookup"><span data-stu-id="8bef1-104">Multithreading can expose your code to very serious and complex bugs.</span></span> <span data-ttu-id="8bef1-105">操作控件的两个或多个线程可以迫使该控件处于不一致的状态，并会导致争用条件、 死锁，并冻结或挂起。</span><span class="sxs-lookup"><span data-stu-id="8bef1-105">Two or more threads manipulating a control can force the control into an inconsistent state and lead to race conditions, deadlocks, and freezes or hangs.</span></span> <span data-ttu-id="8bef1-106">如果你实现多线程处理在应用中，请确保以线程安全的方式调用跨线程控件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-106">If you implement multithreading in your app, be sure to call cross-thread controls in a thread-safe way.</span></span> <span data-ttu-id="8bef1-107">有关详细信息，请参阅[托管线程处理最佳做法](../../../standard/threading/managed-threading-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="8bef1-107">For more information, see [Managed threading best practices](../../../standard/threading/managed-threading-best-practices.md).</span></span> 

<span data-ttu-id="8bef1-108">有两种方法来安全地从并未创建该控件的线程调用的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-108">There are two ways to safely call a Windows Forms control from a thread that didn't create that control.</span></span> <span data-ttu-id="8bef1-109">可以使用<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>方法来调用在主线程，这又会调用该控件中创建一个委托。</span><span class="sxs-lookup"><span data-stu-id="8bef1-109">You can use the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method to call a delegate created in the main thread, which in turn calls the control.</span></span> <span data-ttu-id="8bef1-110">或者，可以实现<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>，它使用一个事件驱动的模型将报告结果中的后台线程完成工作。</span><span class="sxs-lookup"><span data-stu-id="8bef1-110">Or, you can implement a <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, which uses an event-driven model to separate work done in the background thread from reporting on the results.</span></span> 

## <a name="unsafe-cross-thread-calls"></a><span data-ttu-id="8bef1-111">不安全的跨线程调用</span><span class="sxs-lookup"><span data-stu-id="8bef1-111">Unsafe cross-thread calls</span></span>

<span data-ttu-id="8bef1-112">它是不安全，若要直接从没有创建它的线程调用控件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-112">It's unsafe to call a control directly from a thread that didn't create it.</span></span> <span data-ttu-id="8bef1-113">下面的代码段说明了对的不安全调用<xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>控件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-113">The following code snippet illustrates an unsafe call to the <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control.</span></span> <span data-ttu-id="8bef1-114">`Button1_Click`事件处理程序创建一个新`WriteTextUnsafe`线程，设置主线程的<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>直接属性。</span><span class="sxs-lookup"><span data-stu-id="8bef1-114">The `Button1_Click` event handler creates a new `WriteTextUnsafe` thread, which sets the main thread's <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> property directly.</span></span> 

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

<span data-ttu-id="8bef1-115">Visual Studio 调试器检测到这些不安全的线程调用，通过引发<xref:System.InvalidOperationException>消息，**跨线程操作无效。控制""从其创建的线程以外的线程访问。**</span><span class="sxs-lookup"><span data-stu-id="8bef1-115">The Visual Studio debugger detects these unsafe thread calls by raising an <xref:System.InvalidOperationException> with the message, **Cross-thread operation not valid. Control "" accessed from a thread other than the thread it was created on.**</span></span> <span data-ttu-id="8bef1-116"><xref:System.InvalidOperationException>始终不安全的跨线程调用 Visual Studio 在调试期间，发生并且可能会出现在应用运行时。</span><span class="sxs-lookup"><span data-stu-id="8bef1-116">The <xref:System.InvalidOperationException> always occurs for unsafe cross-thread calls during Visual Studio debugging, and may occur at app runtime.</span></span> <span data-ttu-id="8bef1-117">可修复此问题，但你可以通过设置禁用异常<xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="8bef1-117">You should fix the issue, but you can disable the exception by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> property to `false`.</span></span>

## <a name="safe-cross-thread-calls"></a><span data-ttu-id="8bef1-118">安全的跨线程调用</span><span class="sxs-lookup"><span data-stu-id="8bef1-118">Safe cross-thread calls</span></span> 

<span data-ttu-id="8bef1-119">下面的代码示例演示两种方式安全地从没有创建它的线程调用的 Windows 窗体控件：</span><span class="sxs-lookup"><span data-stu-id="8bef1-119">The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:</span></span> 
1. <span data-ttu-id="8bef1-120"><xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>方法，从主线程调用控件调用委托。</span><span class="sxs-lookup"><span data-stu-id="8bef1-120">The <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method, which calls a delegate from the main thread to call the control.</span></span> 
2. <span data-ttu-id="8bef1-121">一个<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>组件，提供了一个事件驱动模型。</span><span class="sxs-lookup"><span data-stu-id="8bef1-121">A <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which offers an event-driven model.</span></span> 

<span data-ttu-id="8bef1-122">在这两个示例中，后台线程处于睡眠状态一秒以模拟该线程中正在进行的工作。</span><span class="sxs-lookup"><span data-stu-id="8bef1-122">In both examples, the background thread sleeps for one second to simulate work being done in that thread.</span></span> 

<span data-ttu-id="8bef1-123">您可以生成并运行这些示例作为从.NET Framework 应用程序C#或 Visual Basic 命令行。</span><span class="sxs-lookup"><span data-stu-id="8bef1-123">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="8bef1-124">有关详细信息，请参阅[命令行上使用 csc.exe 生成](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[中的命令行 (Visual Basic 中) 生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="8bef1-124">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="8bef1-125">从.NET Core 3.0 开始，你还可以生成并运行示例作为 Windows.NET Core 应用程序从具有.NET Core Windows 窗体的文件夹 *\<文件夹名称>.csproj* 项目文件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-125">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-use-the-invoke-method-with-a-delegate"></a><span data-ttu-id="8bef1-126">示例:使用 Invoke 方法和委托</span><span class="sxs-lookup"><span data-stu-id="8bef1-126">Example: Use the Invoke method with a delegate</span></span>

<span data-ttu-id="8bef1-127">下面的示例演示了用于确保对 Windows 窗体控件的线程安全调用的模式。</span><span class="sxs-lookup"><span data-stu-id="8bef1-127">The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control.</span></span> <span data-ttu-id="8bef1-128">它会查询<xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>属性，将该控件进行比较的创建线程 ID 以调用线程 id。</span><span class="sxs-lookup"><span data-stu-id="8bef1-128">It queries the <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> property, which compares the control's creating thread ID to the calling thread ID.</span></span> <span data-ttu-id="8bef1-129">如果线程 Id 是相同的则会直接调用控件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-129">If the thread IDs are the same, it calls the control directly.</span></span> <span data-ttu-id="8bef1-130">如果线程 Id 不相同，则会调用<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType>从主线程，这使得对控件的实际调用的委托的方法。</span><span class="sxs-lookup"><span data-stu-id="8bef1-130">If the thread IDs are different, it calls the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> method with a delegate from the main thread, which makes the actual call to the control.</span></span>

<span data-ttu-id="8bef1-131">`SafeCallDelegate`允许设定<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8bef1-131">The `SafeCallDelegate` enables setting the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8bef1-132">`WriteTextSafe`方法查询<xref:System.Windows.Forms.Control.InvokeRequired%2A>。</span><span class="sxs-lookup"><span data-stu-id="8bef1-132">The `WriteTextSafe` method queries <xref:System.Windows.Forms.Control.InvokeRequired%2A>.</span></span> <span data-ttu-id="8bef1-133">如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>将返回`true`，`WriteTextSafe`传递`SafeCallDelegate`到<xref:System.Windows.Forms.Control.Invoke%2A>进行实际调用控件的方法。</span><span class="sxs-lookup"><span data-stu-id="8bef1-133">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, `WriteTextSafe` passes the `SafeCallDelegate` to the <xref:System.Windows.Forms.Control.Invoke%2A> method to make the actual call to the control.</span></span> <span data-ttu-id="8bef1-134">如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>将返回`false`，`WriteTextSafe`设置<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>直接。</span><span class="sxs-lookup"><span data-stu-id="8bef1-134">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, `WriteTextSafe` sets the <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directly.</span></span> <span data-ttu-id="8bef1-135">`Button1_Click`事件处理程序将创建新线程并运行`WriteTextSafe`方法。</span><span class="sxs-lookup"><span data-stu-id="8bef1-135">The `Button1_Click` event handler creates the new thread and runs the `WriteTextSafe` method.</span></span> 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a><span data-ttu-id="8bef1-136">示例:使用 BackgroundWorker 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="8bef1-136">Example: Use a BackgroundWorker event handler</span></span>

<span data-ttu-id="8bef1-137">方便地实现多线程是使用<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>组件，使用事件驱动模型。</span><span class="sxs-lookup"><span data-stu-id="8bef1-137">An easy way to implement multithreading is with the <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which uses an event-driven model.</span></span> <span data-ttu-id="8bef1-138">后台线程运行<xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>事件，不与主线程进行交互。</span><span class="sxs-lookup"><span data-stu-id="8bef1-138">The background thread runs the <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> event, which doesn't interact with the main thread.</span></span> <span data-ttu-id="8bef1-139">主线程运行<xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType>和<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>事件处理程序，可以调用主线程的控件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-139">The main thread runs the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> event handlers, which can call the main thread's controls.</span></span>

<span data-ttu-id="8bef1-140">若要通过使用调用线程安全<xref:System.ComponentModel.BackgroundWorker>，在后台线程来执行工作，创建一种方法，并将其绑定到<xref:System.ComponentModel.BackgroundWorker.DoWork>事件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-140">To make a thread-safe call by using <xref:System.ComponentModel.BackgroundWorker>, create a method in the background thread to do the work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event.</span></span> <span data-ttu-id="8bef1-141">在主线程来报告后台工作，结果中创建另一种方法并将其绑定到<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>或<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="8bef1-141">Create another method in the main thread to report the results of the background work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> or <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span> <span data-ttu-id="8bef1-142">若要启动后台线程，请调用<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8bef1-142">To start the background thread, call <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>.</span></span> 

<span data-ttu-id="8bef1-143">该示例使用<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序设置<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8bef1-143">The example uses the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler to set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8bef1-144">有关使用示例<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>事件，请参阅<xref:System.ComponentModel.BackgroundWorker>。</span><span class="sxs-lookup"><span data-stu-id="8bef1-144">For an example using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span> 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="8bef1-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bef1-145">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="8bef1-146">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="8bef1-146">How to: Run an operation in the background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="8bef1-147">如何：实现使用后台操作的窗体</span><span class="sxs-lookup"><span data-stu-id="8bef1-147">How to: Implement a form that uses a background operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="8bef1-148">开发自定义 Windows 窗体控件与.NET Framework</span><span class="sxs-lookup"><span data-stu-id="8bef1-148">Develop custom Windows Forms controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
