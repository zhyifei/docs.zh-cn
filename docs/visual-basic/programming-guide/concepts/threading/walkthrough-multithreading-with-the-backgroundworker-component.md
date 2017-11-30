---
title: "多线程处理 BackgroundWorker 组件 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb0734b4bbf3f8bf5b27305754829f1a9f29f42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="30485-102">演练： 利用 BackgroundWorker 组件 (Visual Basic) 的多线程处理</span><span class="sxs-lookup"><span data-stu-id="30485-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="30485-103">本演练演示如何创建在文本文件中搜索单词出现次数的多线程 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="30485-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="30485-104">演示内容包括：</span><span class="sxs-lookup"><span data-stu-id="30485-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="30485-105">使用可由 <xref:System.ComponentModel.BackgroundWorker> 组件调用的方法定义类。</span><span class="sxs-lookup"><span data-stu-id="30485-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="30485-106">处理 <xref:System.ComponentModel.BackgroundWorker> 组件引发的事件。</span><span class="sxs-lookup"><span data-stu-id="30485-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="30485-107">启动 <xref:System.ComponentModel.BackgroundWorker> 组件运行方法。</span><span class="sxs-lookup"><span data-stu-id="30485-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="30485-108">实现停止 <xref:System.ComponentModel.BackgroundWorker> 组件的 `Cancel` 按钮。</span><span class="sxs-lookup"><span data-stu-id="30485-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="30485-109">创建用户界面</span><span class="sxs-lookup"><span data-stu-id="30485-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="30485-110">打开新的 Visual Basic Windows 窗体应用程序项目，并创建名为窗体`Form1`。</span><span class="sxs-lookup"><span data-stu-id="30485-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="30485-111">向 `Form1` 中添加两个按钮和四个文本框。</span><span class="sxs-lookup"><span data-stu-id="30485-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="30485-112">按下表所示命名对象。</span><span class="sxs-lookup"><span data-stu-id="30485-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="30485-113">对象</span><span class="sxs-lookup"><span data-stu-id="30485-113">Object</span></span>|<span data-ttu-id="30485-114">属性</span><span class="sxs-lookup"><span data-stu-id="30485-114">Property</span></span>|<span data-ttu-id="30485-115">设置</span><span class="sxs-lookup"><span data-stu-id="30485-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="30485-116">第一个按钮</span><span class="sxs-lookup"><span data-stu-id="30485-116">First button</span></span>|<span data-ttu-id="30485-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="30485-117">`Name`, `Text`</span></span>|<span data-ttu-id="30485-118">启动，启动</span><span class="sxs-lookup"><span data-stu-id="30485-118">Start, Start</span></span>|  
    |<span data-ttu-id="30485-119">第二个按钮</span><span class="sxs-lookup"><span data-stu-id="30485-119">Second button</span></span>|<span data-ttu-id="30485-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="30485-120">`Name`, `Text`</span></span>|<span data-ttu-id="30485-121">取消，取消</span><span class="sxs-lookup"><span data-stu-id="30485-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="30485-122">第一个文本框</span><span class="sxs-lookup"><span data-stu-id="30485-122">First text box</span></span>|<span data-ttu-id="30485-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="30485-123">`Name`, `Text`</span></span>|<span data-ttu-id="30485-124">SourceFile，""</span><span class="sxs-lookup"><span data-stu-id="30485-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="30485-125">第二个文本框</span><span class="sxs-lookup"><span data-stu-id="30485-125">Second text box</span></span>|<span data-ttu-id="30485-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="30485-126">`Name`, `Text`</span></span>|<span data-ttu-id="30485-127">CompareString，""</span><span class="sxs-lookup"><span data-stu-id="30485-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="30485-128">第三个文本框</span><span class="sxs-lookup"><span data-stu-id="30485-128">Third text box</span></span>|<span data-ttu-id="30485-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="30485-129">`Name`, `Text`</span></span>|<span data-ttu-id="30485-130">WordsCounted，"0"</span><span class="sxs-lookup"><span data-stu-id="30485-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="30485-131">第四个文本框</span><span class="sxs-lookup"><span data-stu-id="30485-131">Fourth text box</span></span>|<span data-ttu-id="30485-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="30485-132">`Name`, `Text`</span></span>|<span data-ttu-id="30485-133">LinesCounted，"0"</span><span class="sxs-lookup"><span data-stu-id="30485-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="30485-134">在每个文本框旁添加一个标签。</span><span class="sxs-lookup"><span data-stu-id="30485-134">Add a label next to each text box.</span></span> <span data-ttu-id="30485-135">为每个标签设置 `Text` 属性，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="30485-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="30485-136">对象</span><span class="sxs-lookup"><span data-stu-id="30485-136">Object</span></span>|<span data-ttu-id="30485-137">属性</span><span class="sxs-lookup"><span data-stu-id="30485-137">Property</span></span>|<span data-ttu-id="30485-138">设置</span><span class="sxs-lookup"><span data-stu-id="30485-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="30485-139">第一个标签</span><span class="sxs-lookup"><span data-stu-id="30485-139">First label</span></span>|`Text`|<span data-ttu-id="30485-140">源文件</span><span class="sxs-lookup"><span data-stu-id="30485-140">Source File</span></span>|  
    |<span data-ttu-id="30485-141">第二个标签</span><span class="sxs-lookup"><span data-stu-id="30485-141">Second label</span></span>|`Text`|<span data-ttu-id="30485-142">比较字符串</span><span class="sxs-lookup"><span data-stu-id="30485-142">Compare String</span></span>|  
    |<span data-ttu-id="30485-143">第三个标签</span><span class="sxs-lookup"><span data-stu-id="30485-143">Third label</span></span>|`Text`|<span data-ttu-id="30485-144">匹配的单词</span><span class="sxs-lookup"><span data-stu-id="30485-144">Matching Words</span></span>|  
    |<span data-ttu-id="30485-145">第四个标签</span><span class="sxs-lookup"><span data-stu-id="30485-145">Fourth label</span></span>|`Text`|<span data-ttu-id="30485-146">行计数</span><span class="sxs-lookup"><span data-stu-id="30485-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="30485-147">创建 BackgroundWorker 组件并订阅其事件</span><span class="sxs-lookup"><span data-stu-id="30485-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="30485-148">从“工具箱”的“组件”部分，将 <xref:System.ComponentModel.BackgroundWorker> 组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="30485-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="30485-149">它将出现在窗体的组件栏中。</span><span class="sxs-lookup"><span data-stu-id="30485-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="30485-150">设置 BackgroundWorker1 对象的以下属性。</span><span class="sxs-lookup"><span data-stu-id="30485-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="30485-151">属性</span><span class="sxs-lookup"><span data-stu-id="30485-151">Property</span></span>|<span data-ttu-id="30485-152">设置</span><span class="sxs-lookup"><span data-stu-id="30485-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="30485-153">True</span><span class="sxs-lookup"><span data-stu-id="30485-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="30485-154">True</span><span class="sxs-lookup"><span data-stu-id="30485-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="30485-155">定义将在单独线程上运行的方法</span><span class="sxs-lookup"><span data-stu-id="30485-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="30485-156">在“项目”菜单中，选择“添加类”以将类添加到项目。</span><span class="sxs-lookup"><span data-stu-id="30485-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="30485-157">随即出现“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="30485-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="30485-158">从模板窗口选择“类”，然后在名称字段中输入 `Words.vb`。</span><span class="sxs-lookup"><span data-stu-id="30485-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="30485-159">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="30485-159">Click **Add**.</span></span> <span data-ttu-id="30485-160">随即出现 `Words` 类。</span><span class="sxs-lookup"><span data-stu-id="30485-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="30485-161">将下面的代码添加到 `Words` 类中:</span><span class="sxs-lookup"><span data-stu-id="30485-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="30485-162">处理线程中的事件</span><span class="sxs-lookup"><span data-stu-id="30485-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="30485-163">将以下事件处理程序添加到主窗体：</span><span class="sxs-lookup"><span data-stu-id="30485-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="30485-164">启动和调用运行 WordCount 方法的新线程</span><span class="sxs-lookup"><span data-stu-id="30485-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="30485-165">将下面的过程添加到程序中：</span><span class="sxs-lookup"><span data-stu-id="30485-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="30485-166">通过窗体上的 `Start` 按钮调用 `StartThread` 方法：</span><span class="sxs-lookup"><span data-stu-id="30485-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="30485-167">实现停止线程的“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="30485-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="30485-168">从 `Cancel` 按钮的 `Click` 事件处理程序中调用 `StopThread` 过程。</span><span class="sxs-lookup"><span data-stu-id="30485-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="30485-169">测试</span><span class="sxs-lookup"><span data-stu-id="30485-169">Testing</span></span>  
 <span data-ttu-id="30485-170">现在可以测试应用程序以确保其正常运行。</span><span class="sxs-lookup"><span data-stu-id="30485-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="30485-171">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="30485-171">To test the application</span></span>  
  
1.  <span data-ttu-id="30485-172">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="30485-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="30485-173">显示窗体时，在 `sourceFile` 框中输入想测试的文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="30485-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="30485-174">例如，假设测试文件的名称为 Test.txt，则输入 C:\Test.txt。</span><span class="sxs-lookup"><span data-stu-id="30485-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="30485-175">在第二个文本框中，输入要让该应用程序在文本文件中搜索的字词或短语。</span><span class="sxs-lookup"><span data-stu-id="30485-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="30485-176">单击 `Start` 按钮。</span><span class="sxs-lookup"><span data-stu-id="30485-176">Click the `Start` button.</span></span> <span data-ttu-id="30485-177">`LinesCounted` 按钮应立即开始递增。</span><span class="sxs-lookup"><span data-stu-id="30485-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="30485-178">完成后，应用程序将显示“计数完成”消息。</span><span class="sxs-lookup"><span data-stu-id="30485-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="30485-179">测试“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="30485-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="30485-180">按 F5 启动该应用程序，按照前面过程所述输入文件名和搜索字词。</span><span class="sxs-lookup"><span data-stu-id="30485-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="30485-181">请确保所选择的文件足够大，以确保在搜索结束之前有时间取消该过程。</span><span class="sxs-lookup"><span data-stu-id="30485-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="30485-182">单击 `Start` 按钮启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="30485-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="30485-183">单击 `Cancel` 按钮。</span><span class="sxs-lookup"><span data-stu-id="30485-183">Click the `Cancel` button.</span></span> <span data-ttu-id="30485-184">应用程序应立即停止计数。</span><span class="sxs-lookup"><span data-stu-id="30485-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="30485-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="30485-185">Next Steps</span></span>  
 <span data-ttu-id="30485-186">此应用程序包含一些基本错误处理。</span><span class="sxs-lookup"><span data-stu-id="30485-186">This application contains some basic error handling.</span></span> <span data-ttu-id="30485-187">它可检测空白搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="30485-187">It detects blank search strings.</span></span> <span data-ttu-id="30485-188">可以通过处理其他错误（如超过可以计数的最大字词数或行数）使该程序更加可靠。</span><span class="sxs-lookup"><span data-stu-id="30485-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30485-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30485-189">See Also</span></span>  
 [<span data-ttu-id="30485-190">线程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30485-190">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="30485-191">演练： 创作使用 Visual Basic 的一个简单的多线程的组件</span><span class="sxs-lookup"><span data-stu-id="30485-191">Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic</span></span>](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [<span data-ttu-id="30485-192">如何：订阅和取消订阅事件</span><span class="sxs-lookup"><span data-stu-id="30485-192">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
