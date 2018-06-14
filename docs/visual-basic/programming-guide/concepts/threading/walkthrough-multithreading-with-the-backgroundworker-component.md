---
title: 多线程处理 BackgroundWorker 组件 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
ms.openlocfilehash: 07700aa526866729f1ba1a8d846f22ce333c356d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654286"
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>演练： 利用 BackgroundWorker 组件 (Visual Basic) 的多线程处理
本演练演示如何创建在文本文件中搜索单词出现次数的多线程 Windows 窗体应用程序。 演示内容包括：  
  
-   使用可由 <xref:System.ComponentModel.BackgroundWorker> 组件调用的方法定义类。  
  
-   处理 <xref:System.ComponentModel.BackgroundWorker> 组件引发的事件。  
  
-   启动 <xref:System.ComponentModel.BackgroundWorker> 组件运行方法。  
  
-   实现停止 <xref:System.ComponentModel.BackgroundWorker> 组件的 `Cancel` 按钮。  
  
### <a name="to-create-the-user-interface"></a>创建用户界面  
  
1.  打开新的 Visual Basic Windows 窗体应用程序项目，并创建名为窗体`Form1`。  
  
2.  向 `Form1` 中添加两个按钮和四个文本框。  
  
3.  按下表所示命名对象。  
  
    |对象|属性|设置|  
    |------------|--------------|-------------|  
    |第一个按钮|`Name`, `Text`|启动，启动|  
    |第二个按钮|`Name`, `Text`|取消，取消|  
    |第一个文本框|`Name`, `Text`|SourceFile，""|  
    |第二个文本框|`Name`, `Text`|CompareString，""|  
    |第三个文本框|`Name`, `Text`|WordsCounted，"0"|  
    |第四个文本框|`Name`, `Text`|LinesCounted，"0"|  
  
4.  在每个文本框旁添加一个标签。 为每个标签设置 `Text` 属性，如下表所示。  
  
    |对象|属性|设置|  
    |------------|--------------|-------------|  
    |第一个标签|`Text`|源文件|  
    |第二个标签|`Text`|比较字符串|  
    |第三个标签|`Text`|匹配的单词|  
    |第四个标签|`Text`|行计数|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>创建 BackgroundWorker 组件并订阅其事件  
  
1.  从“工具箱”的“组件”部分，将 <xref:System.ComponentModel.BackgroundWorker> 组件添加到窗体。 它将出现在窗体的组件栏中。  
  
2.  设置 BackgroundWorker1 对象的以下属性。  
  
    |属性|设置|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>定义将在单独线程上运行的方法  
  
1.  在“项目”菜单中，选择“添加类”以将类添加到项目。 随即出现“添加新项”对话框。  
  
2.  从模板窗口选择“类”，然后在名称字段中输入 `Words.vb`。  
  
3.  单击 **添加**。 随即出现 `Words` 类。  
  
4.  将下面的代码添加到 `Words` 类中:  
  
    ```vb  
    Public Class Words  
        ' Object to store the current state, for passing to the caller.  
        Public Class CurrentState  
            Public LinesCounted As Integer  
            Public WordsMatched As Integer  
        End Class  
  
        Public SourceFile As String  
        Public CompareString As String  
        Private WordCount As Integer = 0  
        Private LinesCounted As Integer = 0  
  
        Public Sub CountWords(  
            ByVal worker As System.ComponentModel.BackgroundWorker,  
            ByVal e As System.ComponentModel.DoWorkEventArgs  
        )  
            ' Initialize the variables.  
            Dim state As New CurrentState  
            Dim line = ""  
            Dim elapsedTime = 20  
            Dim lastReportDateTime = Now  
  
            If CompareString Is Nothing OrElse  
               CompareString = System.String.Empty Then  
  
               Throw New Exception("CompareString not specified.")  
            End If  
  
            Using myStream As New System.IO.StreamReader(SourceFile)  
  
                ' Process lines while there are lines remaining in the file.  
                Do While Not myStream.EndOfStream  
                    If worker.CancellationPending Then  
                        e.Cancel = True  
                        Exit Do  
                    Else  
                        line = myStream.ReadLine  
                        WordCount += CountInString(line, CompareString)  
                        LinesCounted += 1  
  
                        ' Raise an event so the form can monitor progress.  
                        If Now > lastReportDateTime.AddMilliseconds(elapsedTime) Then  
                            state.LinesCounted = LinesCounted  
                            state.WordsMatched = WordCount  
                            worker.ReportProgress(0, state)  
                            lastReportDateTime = Now  
                        End If  
  
                        ' Uncomment for testing.  
                        'System.Threading.Thread.Sleep(5)  
                    End If  
                Loop  
  
                ' Report the final count values.  
                state.LinesCounted = LinesCounted  
                state.WordsMatched = WordCount  
                worker.ReportProgress(0, state)  
            End Using  
        End Sub  
  
        Private Function CountInString(  
            ByVal SourceString As String,  
            ByVal CompareString As String  
        ) As Integer  
            ' This function counts the number of times  
            ' a word is found in a line.  
            If SourceString Is Nothing Then  
                Return 0  
            End If  
  
            Dim EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString)  
  
            ' To count all occurrences of the string, even within words, remove  
            ' both instances of "\b".  
            Dim regex As New System.Text.RegularExpressions.Regex(  
                "\b" + EscapedCompareString + "\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase)  
  
            Dim matches As System.Text.RegularExpressions.MatchCollection  
            matches = regex.Matches(SourceString)  
            Return matches.Count  
        End Function  
    End Class  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a>处理线程中的事件  
  
-   将以下事件处理程序添加到主窗体：  
  
    ```vb  
    Private Sub BackgroundWorker1_RunWorkerCompleted(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
      ) Handles BackgroundWorker1.RunWorkerCompleted  
  
        ' This event handler is called when the background thread finishes.  
        ' This method runs on the main thread.  
        If e.Error IsNot Nothing Then  
            MessageBox.Show("Error: " & e.Error.Message)  
        ElseIf e.Cancelled Then  
            MessageBox.Show("Word counting canceled.")  
        Else  
            MessageBox.Show("Finished counting words.")  
        End If  
    End Sub  
  
    Private Sub BackgroundWorker1_ProgressChanged(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.ProgressChangedEventArgs  
      ) Handles BackgroundWorker1.ProgressChanged  
  
        ' This method runs on the main thread.  
        Dim state As Words.CurrentState =   
            CType(e.UserState, Words.CurrentState)  
        Me.LinesCounted.Text = state.LinesCounted.ToString  
        Me.WordsCounted.Text = state.WordsMatched.ToString  
    End Sub  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>启动和调用运行 WordCount 方法的新线程  
  
1.  将下面的过程添加到程序中：  
  
    ```vb  
    Private Sub BackgroundWorker1_DoWork(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.DoWorkEventArgs  
      ) Handles BackgroundWorker1.DoWork  
  
        ' This event handler is where the actual work is done.  
        ' This method runs on the background thread.  
  
        ' Get the BackgroundWorker object that raised this event.  
        Dim worker As System.ComponentModel.BackgroundWorker  
        worker = CType(sender, System.ComponentModel.BackgroundWorker)  
  
        ' Get the Words object and call the main method.  
        Dim WC As Words = CType(e.Argument, Words)  
        WC.CountWords(worker, e)  
    End Sub  
  
    Sub StartThread()  
        ' This method runs on the main thread.  
        Me.WordsCounted.Text = "0"  
  
        ' Initialize the object that the background worker calls.  
        Dim WC As New Words  
        WC.CompareString = Me.CompareString.Text  
        WC.SourceFile = Me.SourceFile.Text  
  
        ' Start the asynchronous operation.  
        BackgroundWorker1.RunWorkerAsync(WC)  
    End Sub  
    ```  
  
2.  通过窗体上的 `Start` 按钮调用 `StartThread` 方法：  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>实现停止线程的“取消”按钮  
  
-   从 `Cancel` 按钮的 `Click` 事件处理程序中调用 `StopThread` 过程。  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>正在测试  
 现在可以测试应用程序以确保其正常运行。  
  
#### <a name="to-test-the-application"></a>测试应用程序  
  
1.  按 F5 运行该应用程序。  
  
2.  显示窗体时，在 `sourceFile` 框中输入想测试的文件的文件路径。 例如，假设测试文件的名称为 Test.txt，则输入 C:\Test.txt。  
  
3.  在第二个文本框中，输入要让该应用程序在文本文件中搜索的字词或短语。  
  
4.  单击 `Start` 按钮。 `LinesCounted` 按钮应立即开始递增。 完成后，应用程序将显示“计数完成”消息。  
  
#### <a name="to-test-the-cancel-button"></a>测试“取消”按钮  
  
1.  按 F5 启动该应用程序，按照前面过程所述输入文件名和搜索字词。 请确保所选择的文件足够大，以确保在搜索结束之前有时间取消该过程。  
  
2.  单击 `Start` 按钮启动应用程序。  
  
3.  单击 `Cancel` 按钮。 应用程序应立即停止计数。  
  
## <a name="next-steps"></a>后续步骤  
 此应用程序包含一些基本错误处理。 它可检测空白搜索字符串。 可以通过处理其他错误（如超过可以计数的最大字词数或行数）使该程序更加可靠。  
  
## <a name="see-also"></a>请参阅  
 [线程 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [演练： 创作使用 Visual Basic 的一个简单的多线程的组件](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [如何：订阅和取消订阅事件](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
