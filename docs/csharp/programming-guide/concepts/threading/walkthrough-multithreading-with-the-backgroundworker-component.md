---
title: "演练：利用 BackgroundWorker 组件进行多线程处理 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 72d6e9ab42ca270ebe0691be23ebe181b973620d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a><span data-ttu-id="feff6-102">演练：利用 BackgroundWorker 组件进行多线程处理 (C#)</span><span class="sxs-lookup"><span data-stu-id="feff6-102">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>
<span data-ttu-id="feff6-103">本演练演示如何创建在文本文件中搜索单词出现次数的多线程 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="feff6-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="feff6-104">演示内容包括：</span><span class="sxs-lookup"><span data-stu-id="feff6-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="feff6-105">使用可由 <xref:System.ComponentModel.BackgroundWorker> 组件调用的方法定义类。</span><span class="sxs-lookup"><span data-stu-id="feff6-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="feff6-106">处理 <xref:System.ComponentModel.BackgroundWorker> 组件引发的事件。</span><span class="sxs-lookup"><span data-stu-id="feff6-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="feff6-107">启动 <xref:System.ComponentModel.BackgroundWorker> 组件运行方法。</span><span class="sxs-lookup"><span data-stu-id="feff6-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="feff6-108">实现停止 <xref:System.ComponentModel.BackgroundWorker> 组件的 `Cancel` 按钮。</span><span class="sxs-lookup"><span data-stu-id="feff6-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="feff6-109">创建用户界面</span><span class="sxs-lookup"><span data-stu-id="feff6-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="feff6-110">打开新的 C# Windows 窗体应用程序项目，并创建名为 `Form1` 的窗体。</span><span class="sxs-lookup"><span data-stu-id="feff6-110">Open a new C# Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="feff6-111">向 `Form1` 中添加两个按钮和四个文本框。</span><span class="sxs-lookup"><span data-stu-id="feff6-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="feff6-112">按下表所示命名对象。</span><span class="sxs-lookup"><span data-stu-id="feff6-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="feff6-113">对象</span><span class="sxs-lookup"><span data-stu-id="feff6-113">Object</span></span>|<span data-ttu-id="feff6-114">属性</span><span class="sxs-lookup"><span data-stu-id="feff6-114">Property</span></span>|<span data-ttu-id="feff6-115">设置</span><span class="sxs-lookup"><span data-stu-id="feff6-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="feff6-116">第一个按钮</span><span class="sxs-lookup"><span data-stu-id="feff6-116">First button</span></span>|<span data-ttu-id="feff6-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="feff6-117">`Name`, `Text`</span></span>|<span data-ttu-id="feff6-118">启动，启动</span><span class="sxs-lookup"><span data-stu-id="feff6-118">Start, Start</span></span>|  
    |<span data-ttu-id="feff6-119">第二个按钮</span><span class="sxs-lookup"><span data-stu-id="feff6-119">Second button</span></span>|<span data-ttu-id="feff6-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="feff6-120">`Name`, `Text`</span></span>|<span data-ttu-id="feff6-121">取消，取消</span><span class="sxs-lookup"><span data-stu-id="feff6-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="feff6-122">第一个文本框</span><span class="sxs-lookup"><span data-stu-id="feff6-122">First text box</span></span>|<span data-ttu-id="feff6-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="feff6-123">`Name`, `Text`</span></span>|<span data-ttu-id="feff6-124">SourceFile，""</span><span class="sxs-lookup"><span data-stu-id="feff6-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="feff6-125">第二个文本框</span><span class="sxs-lookup"><span data-stu-id="feff6-125">Second text box</span></span>|<span data-ttu-id="feff6-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="feff6-126">`Name`, `Text`</span></span>|<span data-ttu-id="feff6-127">CompareString，""</span><span class="sxs-lookup"><span data-stu-id="feff6-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="feff6-128">第三个文本框</span><span class="sxs-lookup"><span data-stu-id="feff6-128">Third text box</span></span>|<span data-ttu-id="feff6-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="feff6-129">`Name`, `Text`</span></span>|<span data-ttu-id="feff6-130">WordsCounted，"0"</span><span class="sxs-lookup"><span data-stu-id="feff6-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="feff6-131">第四个文本框</span><span class="sxs-lookup"><span data-stu-id="feff6-131">Fourth text box</span></span>|<span data-ttu-id="feff6-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="feff6-132">`Name`, `Text`</span></span>|<span data-ttu-id="feff6-133">LinesCounted，"0"</span><span class="sxs-lookup"><span data-stu-id="feff6-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="feff6-134">在每个文本框旁添加一个标签。</span><span class="sxs-lookup"><span data-stu-id="feff6-134">Add a label next to each text box.</span></span> <span data-ttu-id="feff6-135">为每个标签设置 `Text` 属性，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="feff6-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="feff6-136">对象</span><span class="sxs-lookup"><span data-stu-id="feff6-136">Object</span></span>|<span data-ttu-id="feff6-137">属性</span><span class="sxs-lookup"><span data-stu-id="feff6-137">Property</span></span>|<span data-ttu-id="feff6-138">设置</span><span class="sxs-lookup"><span data-stu-id="feff6-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="feff6-139">第一个标签</span><span class="sxs-lookup"><span data-stu-id="feff6-139">First label</span></span>|`Text`|<span data-ttu-id="feff6-140">源文件</span><span class="sxs-lookup"><span data-stu-id="feff6-140">Source File</span></span>|  
    |<span data-ttu-id="feff6-141">第二个标签</span><span class="sxs-lookup"><span data-stu-id="feff6-141">Second label</span></span>|`Text`|<span data-ttu-id="feff6-142">比较字符串</span><span class="sxs-lookup"><span data-stu-id="feff6-142">Compare String</span></span>|  
    |<span data-ttu-id="feff6-143">第三个标签</span><span class="sxs-lookup"><span data-stu-id="feff6-143">Third label</span></span>|`Text`|<span data-ttu-id="feff6-144">匹配的单词</span><span class="sxs-lookup"><span data-stu-id="feff6-144">Matching Words</span></span>|  
    |<span data-ttu-id="feff6-145">第四个标签</span><span class="sxs-lookup"><span data-stu-id="feff6-145">Fourth label</span></span>|`Text`|<span data-ttu-id="feff6-146">行计数</span><span class="sxs-lookup"><span data-stu-id="feff6-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="feff6-147">创建 BackgroundWorker 组件并订阅其事件</span><span class="sxs-lookup"><span data-stu-id="feff6-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="feff6-148">从“工具箱”的“组件”部分，将 <xref:System.ComponentModel.BackgroundWorker> 组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="feff6-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="feff6-149">它将出现在窗体的组件栏中。</span><span class="sxs-lookup"><span data-stu-id="feff6-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="feff6-150">为 backgroundWorker1 对象设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="feff6-150">Set the following properties for the backgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="feff6-151">属性</span><span class="sxs-lookup"><span data-stu-id="feff6-151">Property</span></span>|<span data-ttu-id="feff6-152">设置</span><span class="sxs-lookup"><span data-stu-id="feff6-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="feff6-153">True</span><span class="sxs-lookup"><span data-stu-id="feff6-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="feff6-154">True</span><span class="sxs-lookup"><span data-stu-id="feff6-154">True</span></span>|  
  
3.  <span data-ttu-id="feff6-155">订阅 backgroundWorker1 对象的事件。</span><span class="sxs-lookup"><span data-stu-id="feff6-155">Subscribe to the events of the backgroundWorker1 object.</span></span> <span data-ttu-id="feff6-156">在“属性”窗口的顶部，单击“事件”图标。</span><span class="sxs-lookup"><span data-stu-id="feff6-156">At the top of the **Properties** window, click the **Events** icon.</span></span> <span data-ttu-id="feff6-157">双击 `RunWorkerCompleted` 事件，创建一个事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="feff6-157">Double-click the `RunWorkerCompleted` event to create an event handler method.</span></span> <span data-ttu-id="feff6-158">对 `ProgressChanged` 和 `DoWork` 事件执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="feff6-158">Do the same for the `ProgressChanged` and `DoWork` events.</span></span>  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="feff6-159">定义将在单独线程上运行的方法</span><span class="sxs-lookup"><span data-stu-id="feff6-159">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="feff6-160">在“项目”菜单中，选择“添加类”以将类添加到项目。</span><span class="sxs-lookup"><span data-stu-id="feff6-160">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="feff6-161">随即出现“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="feff6-161">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="feff6-162">从模板窗口选择“类”，然后在名称字段中输入 `Words.cs`。</span><span class="sxs-lookup"><span data-stu-id="feff6-162">Select **Class** from the templates window and enter `Words.cs` in the name field.</span></span>  
  
3.  <span data-ttu-id="feff6-163">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="feff6-163">Click **Add**.</span></span> <span data-ttu-id="feff6-164">随即出现 `Words` 类。</span><span class="sxs-lookup"><span data-stu-id="feff6-164">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="feff6-165">将下面的代码添加到 `Words` 类中:</span><span class="sxs-lookup"><span data-stu-id="feff6-165">Add the following code to the `Words` class:</span></span>  
  
    ```csharp  
    public class Words  
    {  
        // Object to store the current state, for passing to the caller.  
        public class CurrentState  
        {  
            public int LinesCounted;  
            public int WordsMatched;  
        }  
  
        public string SourceFile;  
        public string CompareString;  
        private int WordCount;  
        private int LinesCounted;  
  
        public void CountWords(  
            System.ComponentModel.BackgroundWorker worker,  
            System.ComponentModel.DoWorkEventArgs e)  
        {  
            // Initialize the variables.  
            CurrentState state = new CurrentState();  
            string line = "";  
            int elapsedTime = 20;  
            DateTime lastReportDateTime = DateTime.Now;  
  
            if (CompareString == null ||  
                CompareString == System.String.Empty)  
            {  
                throw new Exception("CompareString not specified.");  
            }  
  
            // Open a new stream.  
            using (System.IO.StreamReader myStream = new System.IO.StreamReader(SourceFile))  
            {  
                // Process lines while there are lines remaining in the file.  
                while (!myStream.EndOfStream)  
                {  
                    if (worker.CancellationPending)  
                    {  
                        e.Cancel = true;  
                        break;  
                    }  
                    else  
                    {  
                        line = myStream.ReadLine();  
                        WordCount += CountInString(line, CompareString);  
                        LinesCounted += 1;  
  
                        // Raise an event so the form can monitor progress.  
                        int compare = DateTime.Compare(  
                            DateTime.Now, lastReportDateTime.AddMilliseconds(elapsedTime));  
                        if (compare > 0)  
                        {  
                            state.LinesCounted = LinesCounted;  
                            state.WordsMatched = WordCount;  
                            worker.ReportProgress(0, state);  
                            lastReportDateTime = DateTime.Now;  
                        }  
                    }  
                    // Uncomment for testing.  
                    //System.Threading.Thread.Sleep(5);  
                }  
  
                // Report the final count values.  
                state.LinesCounted = LinesCounted;  
                state.WordsMatched = WordCount;  
                worker.ReportProgress(0, state);  
            }  
        }  
  
        private int CountInString(  
            string SourceString,  
            string CompareString)  
        {  
            // This function counts the number of times  
            // a word is found in a line.  
            if (SourceString == null)  
            {  
                return 0;  
            }  
  
            string EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString);  
  
            System.Text.RegularExpressions.Regex regex;  
            regex = new System.Text.RegularExpressions.Regex(   
                // To count all occurrences of the string, even within words, remove  
                // both instances of @"\b" from the following line.  
                @"\b" + EscapedCompareString + @"\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase);  
  
            System.Text.RegularExpressions.MatchCollection matches;  
            matches = regex.Matches(SourceString);  
            return matches.Count;  
        }  
  
    }  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="feff6-166">处理线程中的事件</span><span class="sxs-lookup"><span data-stu-id="feff6-166">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="feff6-167">将以下事件处理程序添加到主窗体：</span><span class="sxs-lookup"><span data-stu-id="feff6-167">Add the following event handlers to your main form:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_RunWorkerCompleted(object sender, RunWorkerCompletedEventArgs e)  
    {  
    // This event handler is called when the background thread finishes.  
    // This method runs on the main thread.  
    if (e.Error != null)  
        MessageBox.Show("Error: " + e.Error.Message);  
    else if (e.Cancelled)  
        MessageBox.Show("Word counting canceled.");  
    else  
        MessageBox.Show("Finished counting words.");  
    }  
  
    private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)  
    {  
        // This method runs on the main thread.  
        Words.CurrentState state =  
            (Words.CurrentState)e.UserState;  
        this.LinesCounted.Text = state.LinesCounted.ToString();  
        this.WordsCounted.Text = state.WordsMatched.ToString();  
    }  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="feff6-168">启动和调用运行 WordCount 方法的新线程</span><span class="sxs-lookup"><span data-stu-id="feff6-168">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="feff6-169">将下面的过程添加到程序中：</span><span class="sxs-lookup"><span data-stu-id="feff6-169">Add the following procedures to your program:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)  
    {  
        // This event handler is where the actual work is done.  
        // This method runs on the background thread.  
  
        // Get the BackgroundWorker object that raised this event.  
        System.ComponentModel.BackgroundWorker worker;  
        worker = (System.ComponentModel.BackgroundWorker)sender;  
  
        // Get the Words object and call the main method.  
        Words WC = (Words)e.Argument;  
        WC.CountWords(worker, e);  
    }  
  
    private void StartThread()  
    {  
        // This method runs on the main thread.  
        this.WordsCounted.Text = "0";  
  
        // Initialize the object that the background worker calls.  
        Words WC = new Words();  
        WC.CompareString = this.CompareString.Text;  
        WC.SourceFile = this.SourceFile.Text;  
  
        // Start the asynchronous operation.  
        backgroundWorker1.RunWorkerAsync(WC);  
    }  
    ```  
  
2.  <span data-ttu-id="feff6-170">通过窗体上的 `Start` 按钮调用 `StartThread` 方法：</span><span class="sxs-lookup"><span data-stu-id="feff6-170">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="feff6-171">实现停止线程的“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="feff6-171">To implement a Cancel button that stops the thread</span></span>  
  
    -   <span data-ttu-id="feff6-172">从 `Cancel` 按钮的 `Click` 事件处理程序中调用 `StopThread` 过程。</span><span class="sxs-lookup"><span data-stu-id="feff6-172">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
        ```  
  
## <a name="testing"></a><span data-ttu-id="feff6-173">测试</span><span class="sxs-lookup"><span data-stu-id="feff6-173">Testing</span></span>  
 <span data-ttu-id="feff6-174">现在可以测试应用程序以确保其正常运行。</span><span class="sxs-lookup"><span data-stu-id="feff6-174">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="feff6-175">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="feff6-175">To test the application</span></span>  
  
1.  <span data-ttu-id="feff6-176">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="feff6-176">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="feff6-177">显示窗体时，在 `sourceFile` 框中输入想测试的文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="feff6-177">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="feff6-178">例如，假设测试文件的名称为 Test.txt，则输入 C:\Test.txt。</span><span class="sxs-lookup"><span data-stu-id="feff6-178">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="feff6-179">在第二个文本框中，输入要让该应用程序在文本文件中搜索的字词或短语。</span><span class="sxs-lookup"><span data-stu-id="feff6-179">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="feff6-180">单击 `Start` 按钮。</span><span class="sxs-lookup"><span data-stu-id="feff6-180">Click the `Start` button.</span></span> <span data-ttu-id="feff6-181">`LinesCounted` 按钮应立即开始递增。</span><span class="sxs-lookup"><span data-stu-id="feff6-181">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="feff6-182">完成后，应用程序将显示“计数完成”消息。</span><span class="sxs-lookup"><span data-stu-id="feff6-182">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="feff6-183">测试“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="feff6-183">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="feff6-184">按 F5 启动该应用程序，按照前面过程所述输入文件名和搜索字词。</span><span class="sxs-lookup"><span data-stu-id="feff6-184">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="feff6-185">请确保所选择的文件足够大，以确保在搜索结束之前有时间取消该过程。</span><span class="sxs-lookup"><span data-stu-id="feff6-185">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="feff6-186">单击 `Start` 按钮启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="feff6-186">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="feff6-187">单击 `Cancel` 按钮。</span><span class="sxs-lookup"><span data-stu-id="feff6-187">Click the `Cancel` button.</span></span> <span data-ttu-id="feff6-188">应用程序应立即停止计数。</span><span class="sxs-lookup"><span data-stu-id="feff6-188">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="feff6-189">后续步骤</span><span class="sxs-lookup"><span data-stu-id="feff6-189">Next Steps</span></span>  
 <span data-ttu-id="feff6-190">此应用程序包含一些基本错误处理。</span><span class="sxs-lookup"><span data-stu-id="feff6-190">This application contains some basic error handling.</span></span> <span data-ttu-id="feff6-191">它可检测空白搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="feff6-191">It detects blank search strings.</span></span> <span data-ttu-id="feff6-192">可以通过处理其他错误（如超过可以计数的最大字词数或行数）使该程序更加可靠。</span><span class="sxs-lookup"><span data-stu-id="feff6-192">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feff6-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feff6-193">See Also</span></span>  
 <span data-ttu-id="feff6-194">[线程处理 [C#]](../../../../csharp/programming-guide/concepts/threading/index.md)</span><span class="sxs-lookup"><span data-stu-id="feff6-194">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)</span></span>  
 [<span data-ttu-id="feff6-195">如何：订阅和取消订阅事件</span><span class="sxs-lookup"><span data-stu-id="feff6-195">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
