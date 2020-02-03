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
ms.openlocfilehash: 101457ab2a02b8de49d06c354ca307e07b690ba2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736161"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>如何：对 Windows 窗体控件进行线程安全调用

多线程处理可以提高 Windows 窗体应用的性能，但对 Windows 窗体控件的访问本质上不是线程安全的。 多线程处理可以将你的代码公开给非常严重且复杂的 bug。 处理控件的两个或多个线程可能会强制控件处于不一致状态并导致争用情况、死锁和冻结或挂起。 如果在应用程序中实现多线程处理，请确保以线程安全的方式调用跨线程控件。 有关详细信息，请参阅[托管线程处理最佳做法](../../../standard/threading/managed-threading-best-practices.md)。 

可以通过两种方法从未创建该控件的线程安全调用 Windows 窗体控件。 您可以使用 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> 方法调用在主线程中创建的委托，该委托又调用控件。 或者，您可以实现一个 <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>，该使用事件驱动模型将后台线程中完成的工作与报表上的结果进行分隔。 

## <a name="unsafe-cross-thread-calls"></a>不安全的跨线程调用

直接从未创建控件的线程调用控件是不安全的。 下面的代码段演示对 <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> 控件的不安全调用。 `Button1_Click` 事件处理程序创建一个新的 `WriteTextUnsafe` 线程，该线程直接设置主线程的 <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> 属性。 

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

Visual Studio 调试器通过使用消息引发 <xref:System.InvalidOperationException> 来检测这些不安全线程调用，**跨线程操作无效。控件 "" 从创建它的线程之外的其他线程访问。** 在 Visual Studio 调试过程中，<xref:System.InvalidOperationException> 始终对不安全的跨线程调用发生，并且可能会在应用运行时发生。 应修复此问题，但可以通过将 <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> 属性设置为 `false`来禁用异常。

## <a name="safe-cross-thread-calls"></a>安全的跨线程调用 

下面的代码示例演示了两种从未创建 Windows 窗体控件的线程安全调用的方法： 

1. <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> 方法，该方法从主线程调用委托以调用控件。 
2. 一个 <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> 组件，该组件提供事件驱动模型。 

在这两个示例中，后台线程休眠一秒钟，以模拟在该线程中完成的工作。 

你可以从C#或 Visual Basic 命令行 .NET Framework 应用生成并运行这些示例。 有关详细信息，请参阅[通过 csc 生成命令行](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[从命令行生成（Visual Basic）](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。 

从 .NET Core 3.0 开始，还可以从具有 .NET Core Windows 窗体 *\<文件夹名称 > .csproj*项目文件的文件夹生成并运行示例作为 Windows .net core 应用。 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>示例：对委托使用 Invoke 方法

下面的示例演示了一种用于确保对 Windows 窗体控件进行线程安全调用的模式。 它将查询 <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> 属性，该属性将控件的创建线程 ID 与调用线程 ID 进行比较。 如果线程 Id 相同，则它会直接调用控件。 如果线程 Id 不同，它将使用主线程中的委托调用 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> 方法，这将对控件进行实际调用。

`SafeCallDelegate` 允许设置 <xref:System.Windows.Forms.TextBox> 控件的 <xref:System.Windows.Forms.TextBox.Text%2A> 属性。 `WriteTextSafe` 方法 <xref:System.Windows.Forms.Control.InvokeRequired%2A>查询。 如果 <xref:System.Windows.Forms.Control.InvokeRequired%2A> 返回 `true`，`WriteTextSafe` 会将 `SafeCallDelegate` 传递到 <xref:System.Windows.Forms.Control.Invoke%2A> 方法，以对控件进行实际调用。 如果 <xref:System.Windows.Forms.Control.InvokeRequired%2A> 返回 `false`，`WriteTextSafe` 将直接设置 <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>。 `Button1_Click` 事件处理程序将创建新线程并运行 `WriteTextSafe` 方法。 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>示例：使用 BackgroundWorker 事件处理程序

实现多线程处理的一种简单方法是使用 <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> 组件，该组件使用事件驱动模型。 后台线程运行不与主线程交互的 <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> 事件。 主线程运行 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> 和 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> 事件处理程序，这些处理程序可调用主线程的控件。

若要通过使用 <xref:System.ComponentModel.BackgroundWorker>进行线程安全调用，请在后台线程中创建一个方法来完成工作，并将其绑定到 <xref:System.ComponentModel.BackgroundWorker.DoWork> 事件。 在主线程中创建另一个方法来报告后台工作的结果，并将其绑定到 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 或 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件。 若要启动后台线程，请调用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>。 

该示例使用 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 事件处理程序来设置 <xref:System.Windows.Forms.TextBox> 控件的 <xref:System.Windows.Forms.TextBox.Text%2A> 属性。 有关使用 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 事件的示例，请参阅 <xref:System.ComponentModel.BackgroundWorker>。 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>另请参阅

- <xref:System.ComponentModel.BackgroundWorker>
- [如何：在后台运行操作](how-to-run-an-operation-in-the-background.md)
- [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)
- [利用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
