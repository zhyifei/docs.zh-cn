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
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>如何：对 Windows 窗体控件进行线程安全调用

多线程可以提高 Windows 窗体应用的性能，但访问 Windows 窗体控件本质上并不安全线程。 多线程可能会将代码暴露给非常严重和复杂的错误。 操作控件的两个或多个线程可能会强制控件进入不一致状态，并导致争用条件、死锁以及冻结或挂起。 如果在应用中实现多线程读取，请确保以线程安全的方式调用交叉线程控件。 有关详细信息，请参阅[托管线程最佳实践](../../../standard/threading/managed-threading-best-practices.md)。

有两种方法可以从未创建该控件的线程安全地调用 Windows 窗体控件。 可以使用 方法<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>调用在主线程中创建的委托，而主线程又调用控件。 或者，可以实现 一<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>个 ，它使用事件驱动的模型将后台线程中完成的工作与报告结果分开。

## <a name="unsafe-cross-thread-calls"></a>不安全的交叉线程调用

直接从未创建控件的线程调用控件是不安全的。 以下代码段说明了对控件的<xref:System.Windows.Forms.TextBox?displayProperty=nameWithType>不安全调用。 事件`Button1_Click`处理程序创建一个新`WriteTextUnsafe`线程，该线程直接设置主线程的属性。 <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>

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

Visual Studio 调试器通过引发消息中的 调用<xref:System.InvalidOperationException>来检测这些不安全的线程调用，**跨线程操作无效。控件""从创建该线程以外的线程访问。** 在<xref:System.InvalidOperationException>Visual Studio 调试期间，始终发生不安全的交叉线程调用，并且可能在应用运行时发生。 应修复此问题，但可以通过将<xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType>属性设置为`false`来禁用异常。

## <a name="safe-cross-thread-calls"></a>安全交叉线程调用

以下代码示例演示了从未创建该控件的线程安全地调用 Windows 窗体控件的两种方法：

1. 方法<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>，它从主线程调用委托来调用控件。
2. 提供<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>事件驱动模型的组件。

在这两个示例中，后台线程休眠一秒钟以模拟该线程中正在完成的工作。

可以从 C# 或 Visual Basic 命令行生成和运行这些示例为 .NET 框架应用。 有关详细信息，请参阅使用[csc.exe 的命令行构建](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[命令行（可视基本）中的生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。

从 .NET Core 3.0 开始，您还可以从具有 .NET 核心 Windows 窗体*\<文件夹名称>.csproj*项目文件的文件夹中生成并运行 Windows .NET Core 应用示例。

## <a name="example-use-the-invoke-method-with-a-delegate"></a>示例：使用具有委托的 Invoke 方法

下面的示例演示了用于确保对 Windows 窗体控件进行线程安全调用的模式。 它查询该<xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName>属性，该属性将控件的创建线程 ID 与调用线程 ID 进行比较。 如果线程指示相同，它将直接调用控件。 如果线程指示不同，它将使用主线程的委托调用<xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType>方法，从而对控件进行实际调用。

启用`SafeCallDelegate`设置<xref:System.Windows.Forms.TextBox>控件的属性<xref:System.Windows.Forms.TextBox.Text%2A>。 方法`WriteTextSafe`查询<xref:System.Windows.Forms.Control.InvokeRequired%2A>。 如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>返回`true` `WriteTextSafe` ，则`SafeCallDelegate`将<xref:System.Windows.Forms.Control.Invoke%2A>传递给 方法以对控件进行实际调用。 如果<xref:System.Windows.Forms.Control.InvokeRequired%2A>返回`false` `WriteTextSafe` ，则<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType>直接设置 。 事件`Button1_Click`处理程序创建新线程并运行方法`WriteTextSafe`。

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>示例：使用后台辅助角色事件处理程序

实现多线程的一种简单方法是使用<xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>组件，该组件使用事件驱动的模型。 后台线程运行事件<xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType>，该事件不与主线程交互。 主线程运行 和<xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType><xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType>事件处理程序，可以调用主线程的控件。

要使用 进行<xref:System.ComponentModel.BackgroundWorker>线程安全调用，请在后台线程中创建一个方法来执行该工作，并将其绑定到<xref:System.ComponentModel.BackgroundWorker.DoWork>事件。 在主线程中创建另一种方法以报告后台工作的结果，并将其绑定到<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>或<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件。 要启动后台线程，请调用<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>。

该示例使用<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>事件处理程序设置<xref:System.Windows.Forms.TextBox>控件的属性。 <xref:System.Windows.Forms.TextBox.Text%2A> 有关使用事件的示例，<xref:System.ComponentModel.BackgroundWorker.ProgressChanged>请参阅<xref:System.ComponentModel.BackgroundWorker>。

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>另请参阅

- <xref:System.ComponentModel.BackgroundWorker>
- [操作方式：在后台运行操作](how-to-run-an-operation-in-the-background.md)
- [如何：实现使用后台操作的窗体](how-to-implement-a-form-that-uses-a-background-operation.md)
- [使用 .NET 框架开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
