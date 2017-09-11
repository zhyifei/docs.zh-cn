---
title: "多线程处理 BackgroundWorker 组件 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88d0711c8e417ae5c95b0e109504b69882015241
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="3b2df-102">演练︰ 利用 BackgroundWorker 组件 (Visual Basic 中) 的多线程处理</span><span class="sxs-lookup"><span data-stu-id="3b2df-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="3b2df-103">本演练演示如何创建一个词的匹配项的文本文件中搜索的多线程的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b2df-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="3b2df-104">演示︰</span><span class="sxs-lookup"><span data-stu-id="3b2df-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="3b2df-105">使用可由调用的方法定义一个类<xref:System.ComponentModel.BackgroundWorker>组件。</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="3b2df-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="3b2df-106">处理所引发的事件<xref:System.ComponentModel.BackgroundWorker>组件。</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="3b2df-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="3b2df-107">启动<xref:System.ComponentModel.BackgroundWorker>组件来运行一种方法。</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="3b2df-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="3b2df-108">实现`Cancel`停止按钮<xref:System.ComponentModel.BackgroundWorker>组件。</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="3b2df-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="3b2df-109">创建用户界面</span><span class="sxs-lookup"><span data-stu-id="3b2df-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="3b2df-110">打开新的 Visual Basic Windows 窗体应用程序项目，并创建名为的`Form1`。</span><span class="sxs-lookup"><span data-stu-id="3b2df-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="3b2df-111">添加两个按钮和四个文本框到`Form1`。</span><span class="sxs-lookup"><span data-stu-id="3b2df-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="3b2df-112">下表中所示命名对象。</span><span class="sxs-lookup"><span data-stu-id="3b2df-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="3b2df-113">对象</span><span class="sxs-lookup"><span data-stu-id="3b2df-113">Object</span></span>|<span data-ttu-id="3b2df-114">属性</span><span class="sxs-lookup"><span data-stu-id="3b2df-114">Property</span></span>|<span data-ttu-id="3b2df-115">设置</span><span class="sxs-lookup"><span data-stu-id="3b2df-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="3b2df-116">第一个按钮</span><span class="sxs-lookup"><span data-stu-id="3b2df-116">First button</span></span>|<span data-ttu-id="3b2df-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="3b2df-117">`Name`, `Text`</span></span>|<span data-ttu-id="3b2df-118">开始时开始</span><span class="sxs-lookup"><span data-stu-id="3b2df-118">Start, Start</span></span>|  
    |<span data-ttu-id="3b2df-119">第二个按钮</span><span class="sxs-lookup"><span data-stu-id="3b2df-119">Second button</span></span>|<span data-ttu-id="3b2df-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="3b2df-120">`Name`, `Text`</span></span>|<span data-ttu-id="3b2df-121">取消，取消按钮</span><span class="sxs-lookup"><span data-stu-id="3b2df-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="3b2df-122">第一个文本框中</span><span class="sxs-lookup"><span data-stu-id="3b2df-122">First text box</span></span>|<span data-ttu-id="3b2df-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="3b2df-123">`Name`, `Text`</span></span>|<span data-ttu-id="3b2df-124">SourceFile、""</span><span class="sxs-lookup"><span data-stu-id="3b2df-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="3b2df-125">第二个文本框</span><span class="sxs-lookup"><span data-stu-id="3b2df-125">Second text box</span></span>|<span data-ttu-id="3b2df-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="3b2df-126">`Name`, `Text`</span></span>|<span data-ttu-id="3b2df-127">CompareString，""</span><span class="sxs-lookup"><span data-stu-id="3b2df-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="3b2df-128">第三个文本框</span><span class="sxs-lookup"><span data-stu-id="3b2df-128">Third text box</span></span>|<span data-ttu-id="3b2df-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="3b2df-129">`Name`, `Text`</span></span>|<span data-ttu-id="3b2df-130">WordsCounted，"0"</span><span class="sxs-lookup"><span data-stu-id="3b2df-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="3b2df-131">第四个文本框</span><span class="sxs-lookup"><span data-stu-id="3b2df-131">Fourth text box</span></span>|<span data-ttu-id="3b2df-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="3b2df-132">`Name`, `Text`</span></span>|<span data-ttu-id="3b2df-133">LinesCounted，"0"</span><span class="sxs-lookup"><span data-stu-id="3b2df-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="3b2df-134">添加每个文本框旁边的标签。</span><span class="sxs-lookup"><span data-stu-id="3b2df-134">Add a label next to each text box.</span></span> <span data-ttu-id="3b2df-135">设置`Text`为下表中所示的每个标签的属性。</span><span class="sxs-lookup"><span data-stu-id="3b2df-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="3b2df-136">对象</span><span class="sxs-lookup"><span data-stu-id="3b2df-136">Object</span></span>|<span data-ttu-id="3b2df-137">属性</span><span class="sxs-lookup"><span data-stu-id="3b2df-137">Property</span></span>|<span data-ttu-id="3b2df-138">设置</span><span class="sxs-lookup"><span data-stu-id="3b2df-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="3b2df-139">第一个标签</span><span class="sxs-lookup"><span data-stu-id="3b2df-139">First label</span></span>|`Text`|<span data-ttu-id="3b2df-140">源文件</span><span class="sxs-lookup"><span data-stu-id="3b2df-140">Source File</span></span>|  
    |<span data-ttu-id="3b2df-141">第二个标签</span><span class="sxs-lookup"><span data-stu-id="3b2df-141">Second label</span></span>|`Text`|<span data-ttu-id="3b2df-142">比较字符串</span><span class="sxs-lookup"><span data-stu-id="3b2df-142">Compare String</span></span>|  
    |<span data-ttu-id="3b2df-143">第三个标签</span><span class="sxs-lookup"><span data-stu-id="3b2df-143">Third label</span></span>|`Text`|<span data-ttu-id="3b2df-144">匹配的单词</span><span class="sxs-lookup"><span data-stu-id="3b2df-144">Matching Words</span></span>|  
    |<span data-ttu-id="3b2df-145">第四个标签</span><span class="sxs-lookup"><span data-stu-id="3b2df-145">Fourth label</span></span>|`Text`|<span data-ttu-id="3b2df-146">行计数</span><span class="sxs-lookup"><span data-stu-id="3b2df-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="3b2df-147">若要创建 BackgroundWorker 组件并对其事件订阅</span><span class="sxs-lookup"><span data-stu-id="3b2df-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="3b2df-148">添加<xref:System.ComponentModel.BackgroundWorker>组件从**组件**部分**工具箱**到窗体。</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="3b2df-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="3b2df-149">它将出现在窗体的组件栏。</span><span class="sxs-lookup"><span data-stu-id="3b2df-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="3b2df-150">设置 BackgroundWorker1 对象的以下属性。</span><span class="sxs-lookup"><span data-stu-id="3b2df-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="3b2df-151">属性</span><span class="sxs-lookup"><span data-stu-id="3b2df-151">Property</span></span>|<span data-ttu-id="3b2df-152">设置</span><span class="sxs-lookup"><span data-stu-id="3b2df-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="3b2df-153">True</span><span class="sxs-lookup"><span data-stu-id="3b2df-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="3b2df-154">True</span><span class="sxs-lookup"><span data-stu-id="3b2df-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="3b2df-155">若要定义将在单独的线程运行的方法</span><span class="sxs-lookup"><span data-stu-id="3b2df-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="3b2df-156">从**项目**菜单上，选择**添加类**将类添加到项目。</span><span class="sxs-lookup"><span data-stu-id="3b2df-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="3b2df-157">**添加新项**中会显示对话框。</span><span class="sxs-lookup"><span data-stu-id="3b2df-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="3b2df-158">选择**类**从模板窗口，然后输入`Words.vb`在名称字段中。</span><span class="sxs-lookup"><span data-stu-id="3b2df-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="3b2df-159">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="3b2df-159">Click **Add**.</span></span> <span data-ttu-id="3b2df-160">`Words`显示类。</span><span class="sxs-lookup"><span data-stu-id="3b2df-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="3b2df-161">将下面的代码添加到 `Words` 类中:</span><span class="sxs-lookup"><span data-stu-id="3b2df-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="3b2df-162">若要处理线程中的事件</span><span class="sxs-lookup"><span data-stu-id="3b2df-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="3b2df-163">将以下事件处理程序添加到主窗体︰</span><span class="sxs-lookup"><span data-stu-id="3b2df-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="3b2df-164">若要开始和调用新的线程运行 WordCount 方法</span><span class="sxs-lookup"><span data-stu-id="3b2df-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="3b2df-165">将以下过程添加到您的程序︰</span><span class="sxs-lookup"><span data-stu-id="3b2df-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="3b2df-166">调用`StartThread`方法从`Start`窗体上的按钮︰</span><span class="sxs-lookup"><span data-stu-id="3b2df-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="3b2df-167">若要实现停止该线程的取消按钮</span><span class="sxs-lookup"><span data-stu-id="3b2df-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="3b2df-168">调用`StopThread`过程从`Click`事件处理程序`Cancel`按钮。</span><span class="sxs-lookup"><span data-stu-id="3b2df-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="3b2df-169">测试</span><span class="sxs-lookup"><span data-stu-id="3b2df-169">Testing</span></span>  
 <span data-ttu-id="3b2df-170">现在可以测试应用程序以确保其正常运行。</span><span class="sxs-lookup"><span data-stu-id="3b2df-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="3b2df-171">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="3b2df-171">To test the application</span></span>  
  
1.  <span data-ttu-id="3b2df-172">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b2df-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="3b2df-173">当显示窗体时，输入你想要在测试的文件的文件路径`sourceFile`框。</span><span class="sxs-lookup"><span data-stu-id="3b2df-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="3b2df-174">例如，假设您的测试文件名为 Test.txt 中，输入 C:\Test.txt。</span><span class="sxs-lookup"><span data-stu-id="3b2df-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="3b2df-175">在第二个文本框中，输入一个单词或短语要搜索的文本中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b2df-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="3b2df-176">单击 `Start` 按钮。</span><span class="sxs-lookup"><span data-stu-id="3b2df-176">Click the `Start` button.</span></span> <span data-ttu-id="3b2df-177">`LinesCounted`按钮应当立即开始递增。</span><span class="sxs-lookup"><span data-stu-id="3b2df-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="3b2df-178">完成操作后，应用程序将显示"完成统计"的消息。</span><span class="sxs-lookup"><span data-stu-id="3b2df-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="3b2df-179">若要测试取消按钮</span><span class="sxs-lookup"><span data-stu-id="3b2df-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="3b2df-180">按 F5 以启动该应用程序，并输入在前面过程中所述的的文件名和搜索字词。</span><span class="sxs-lookup"><span data-stu-id="3b2df-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="3b2df-181">请确保所选择的文件足够大，以确保将有时间完成之前将其取消此过程。</span><span class="sxs-lookup"><span data-stu-id="3b2df-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="3b2df-182">单击`Start`按钮以启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b2df-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="3b2df-183">单击 `Cancel` 按钮。</span><span class="sxs-lookup"><span data-stu-id="3b2df-183">Click the `Cancel` button.</span></span> <span data-ttu-id="3b2df-184">应用程序应立即停止计数。</span><span class="sxs-lookup"><span data-stu-id="3b2df-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3b2df-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b2df-185">Next Steps</span></span>  
 <span data-ttu-id="3b2df-186">此应用程序包含一些基本错误处理。</span><span class="sxs-lookup"><span data-stu-id="3b2df-186">This application contains some basic error handling.</span></span> <span data-ttu-id="3b2df-187">它会检测空白搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="3b2df-187">It detects blank search strings.</span></span> <span data-ttu-id="3b2df-188">可以通过处理其他错误，如超出最大次数的单词或进行计数的行，使此程序更加可靠。</span><span class="sxs-lookup"><span data-stu-id="3b2df-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2df-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b2df-189">See Also</span></span>  
 <span data-ttu-id="3b2df-190">[线程处理 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b2df-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="3b2df-191"> [演练︰ 创建使用 Visual Basic 的一个简单的多线程的组件](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span><span class="sxs-lookup"><span data-stu-id="3b2df-191"> [Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span></span>  
<span data-ttu-id="3b2df-192"> [如何：订阅和取消订阅事件](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="3b2df-192"> [How to: Subscribe to and Unsubscribe from Events](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span></span>
