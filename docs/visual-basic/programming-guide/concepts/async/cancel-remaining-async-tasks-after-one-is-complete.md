---
title: "异步任务取消剩余一个后完成 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1b70822edd972ac33614ab49faad6ff50b0e80b7
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a><span data-ttu-id="78de9-102">异步任务取消剩余一个后完成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78de9-102">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>
<span data-ttu-id="78de9-103">通过使用<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>方法和<xref:System.Threading.CancellationToken>，您可以在一个任务完成后取消所有剩余任务。</xref:System.Threading.CancellationToken> </xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="78de9-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="78de9-104">`WhenAny`方法采用的参数是任务的集合。</span><span class="sxs-lookup"><span data-stu-id="78de9-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="78de9-105">该方法开始的所有任务，并返回单个任务。</span><span class="sxs-lookup"><span data-stu-id="78de9-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="78de9-106">在集合中的任何任务完成后，单个任务已完成。</span><span class="sxs-lookup"><span data-stu-id="78de9-106">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="78de9-107">此示例演示如何结合使用取消标记`WhenAny`来占用的第一个任务完成的任务的集合，并用于取消剩余任务。</span><span class="sxs-lookup"><span data-stu-id="78de9-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="78de9-108">每个任务的形式下载网站的内容。</span><span class="sxs-lookup"><span data-stu-id="78de9-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="78de9-109">本示例显示的第一个下载完成的内容的长度，并取消其他下载内容。</span><span class="sxs-lookup"><span data-stu-id="78de9-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78de9-110">若要运行的示例，必须具有 Visual Studio 2012 或更高版本和.NET Framework 4.5 或更高版本安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="78de9-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="78de9-111">下载示例</span><span class="sxs-lookup"><span data-stu-id="78de9-111">Downloading the Example</span></span>  
 <span data-ttu-id="78de9-112">您可以下载完整的 Windows Presentation Foundation (WPF) 项目，从[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)，然后按照这些步骤。</span><span class="sxs-lookup"><span data-stu-id="78de9-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="78de9-113">解压缩下载的文件，然后启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="78de9-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="78de9-114">在菜单栏上，依次选择 **“文件”**、 **“打开”**和 **“项目/解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="78de9-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="78de9-115">在**打开项目**对话框中，打开保存的示例代码中您解压缩的文件夹，然后为 AsyncFineTuningVB 打开解决方案 (.sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="78de9-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="78de9-116">在**解决方案资源管理器**，打开快捷菜单**CancelAfterOneTask**项目，，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="78de9-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="78de9-117">选择 F5 键以运行该项目。</span><span class="sxs-lookup"><span data-stu-id="78de9-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="78de9-118">按 Ctrl + F5 键以运行该项目，不对其进行调试。</span><span class="sxs-lookup"><span data-stu-id="78de9-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="78de9-119">运行程序多次以验证其他的下载完成第一次。</span><span class="sxs-lookup"><span data-stu-id="78de9-119">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="78de9-120">如果您不想要下载的项目，你可以查看本主题末尾处的 MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="78de9-120">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="78de9-121">生成示例</span><span class="sxs-lookup"><span data-stu-id="78de9-121">Building the Example</span></span>  
 <span data-ttu-id="78de9-122">本主题中的示例将添加到项目中开发的[取消一个异步任务或列表任务](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0)若要取消的任务的列表。</span><span class="sxs-lookup"><span data-stu-id="78de9-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) to cancel a list of tasks.</span></span> <span data-ttu-id="78de9-123">该示例使用相同的 UI，尽管**取消**不显式使用按钮。</span><span class="sxs-lookup"><span data-stu-id="78de9-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="78de9-124">若要生成示例自己执行的步骤，请按照"下载示例"部分中的说明进行操作，但选择**CancelAListOfTasks**作为**启动项目**。</span><span class="sxs-lookup"><span data-stu-id="78de9-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="78de9-125">向该项目添加本主题中的所做的更改。</span><span class="sxs-lookup"><span data-stu-id="78de9-125">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="78de9-126">MainWindow.xaml.vb 文件中的**CancelAListOfTasks**项目中，通过将每个网站的处理步骤从中的循环移动开始转换`AccessTheWebAsync`与下面的异步方法。</span><span class="sxs-lookup"><span data-stu-id="78de9-126">In the MainWindow.xaml.vb file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```vb  
' ***Bundle the processing steps for a website into one async method.  
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
    ' GetAsync returns a Task(Of HttpResponseMessage).   
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
    ' Retrieve the website contents from the HttpResponseMessage.  
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
    Return urlContents.Length  
End Function  
```  
  
 <span data-ttu-id="78de9-127">在`AccessTheWebAsync`，此示例使用一个查询，<xref:System.Linq.Enumerable.ToArray%2A>方法，与`WhenAny`方法创建并启动任务的数组。</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="78de9-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="78de9-128">应用程序的`WhenAny`数组时将返回到一项任务，处于等待状态，计算结果为第一项任务来访问数组中完成的任务。</span><span class="sxs-lookup"><span data-stu-id="78de9-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="78de9-129">进行中的以下更改`AccessTheWebAsync`。</span><span class="sxs-lookup"><span data-stu-id="78de9-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="78de9-130">星号标记的代码文件中的更改。</span><span class="sxs-lookup"><span data-stu-id="78de9-130">Asterisks mark the changes in the code file.</span></span>  
  
1.  <span data-ttu-id="78de9-131">注释掉或删除该循环。</span><span class="sxs-lookup"><span data-stu-id="78de9-131">Comment out or delete the loop.</span></span>  
  
2.  <span data-ttu-id="78de9-132">创建一个查询，在执行时，生成的常规任务的集合。</span><span class="sxs-lookup"><span data-stu-id="78de9-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="78de9-133">每次调用`ProcessURLAsync`返回<xref:System.Threading.Tasks.Task%601>其中`TResult`是一个整数。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="78de9-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
<span data-ttu-id="78de9-134"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="78de9-134"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
3.  <span data-ttu-id="78de9-135">调用`ToArray`执行查询并启动任务。</span><span class="sxs-lookup"><span data-stu-id="78de9-135">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="78de9-136">应用程序的`WhenAny`方法在下一步将执行查询，并启动任务，而无需使用`ToArray`，但其他方法可能不会。</span><span class="sxs-lookup"><span data-stu-id="78de9-136">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="78de9-137">最安全的做法是明确强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="78de9-137">The safest practice is to force execution of the query explicitly.</span></span>  
  
<span data-ttu-id="78de9-138"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="78de9-138"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
4.  <span data-ttu-id="78de9-139">调用`WhenAny`上的任务的集合。</span><span class="sxs-lookup"><span data-stu-id="78de9-139">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="78de9-140">`WhenAny`返回`Task(Of Task(Of Integer))`或`Task<Task<int>>`。</span><span class="sxs-lookup"><span data-stu-id="78de9-140">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="78de9-141">也就是说，`WhenAny`评估的任务返回单个`Task(Of Integer)`或`Task<int>`时等待。</span><span class="sxs-lookup"><span data-stu-id="78de9-141">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="78de9-142">该单个任务将集合中要完成的第一个任务。</span><span class="sxs-lookup"><span data-stu-id="78de9-142">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="78de9-143">第一次已完成的任务分配给`firstFinishedTask`。</span><span class="sxs-lookup"><span data-stu-id="78de9-143">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="78de9-144">一种`firstFinishedTask`是<xref:System.Threading.Tasks.Task%601>其中`TResult`是一个整数，因为这是返回类型的`ProcessURLAsync`。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="78de9-144">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
```vb  
' ***Call WhenAny and then await the result. The task that finishes   
' first is assigned to firstFinishedTask.  
Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
```  
  
5.  <span data-ttu-id="78de9-145">在此示例中，您只的感兴趣先完成的任务。</span><span class="sxs-lookup"><span data-stu-id="78de9-145">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="78de9-146">因此，使用<xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>若要取消剩余任务。</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="78de9-146">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> to cancel the remaining tasks.</span></span>  
  
```vb  
' ***Cancel the rest of the downloads. You just want the first one.  
cts.Cancel()  
```  
  
6.  <span data-ttu-id="78de9-147">最后，await`firstFinishedTask`要检索的下载内容的长度。</span><span class="sxs-lookup"><span data-stu-id="78de9-147">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
```vb  
Dim length = Await firstFinishedTask  
resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
```  
  
 <span data-ttu-id="78de9-148">运行程序多次以验证其他的下载完成第一次。</span><span class="sxs-lookup"><span data-stu-id="78de9-148">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="78de9-149">完整的示例</span><span class="sxs-lookup"><span data-stu-id="78de9-149">Complete Example</span></span>  
 <span data-ttu-id="78de9-150">下面的代码是该示例的完整 MainWindow.xaml.vb 或 MainWindow.xaml.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="78de9-150">The following code is the complete MainWindow.xaml.vb or MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="78de9-151">星号标记已针对此示例添加的元素。</span><span class="sxs-lookup"><span data-stu-id="78de9-151">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="78de9-152">请注意，您必须添加<xref:System.Net.Http>。</xref:System.Net.Http>的引用</span><span class="sxs-lookup"><span data-stu-id="78de9-152">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="78de9-153">您可以下载的项目[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)。</span><span class="sxs-lookup"><span data-stu-id="78de9-153">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Download complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' You can still include a Cancel button if you want to.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        '' Comment out or delete the loop.  
        ''For Each url In urlList  
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).   
        ''    ' Argument ct carries the message if the Cancel button is chosen.   
        ''    ' Note that the Cancel button can cancel all remaining downloads.  
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ''    ' Retrieve the website contents from the HttpResponseMessage.  
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ''    resultsTextBox.Text &=  
        ''        String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        ''Next  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToArray to execute the query and start the download tasks.   
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' ***Call WhenAny and then await the result. The task that finishes   
        ' first is assigned to firstFinishedTask.  
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
        ' ***Cancel the rest of the downloads. You just want the first one.  
        cts.Cancel()  
  
        ' ***Await the first completed task and display the results  
        ' Run the program several times to demonstrate that different  
        ' websites can finish first.  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
    End Function  
  
    ' ***Bundle the processing steps for a website into one async method.  
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        Return urlContents.Length  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
End Class  
  
' Sample output:  
  
' Length of the downloaded website:  158856  
  
' Download complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="78de9-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78de9-154">See Also</span></span>  
 <span data-ttu-id="78de9-155"><xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="78de9-155"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
<span data-ttu-id="78de9-156"> [微调异步应用程序 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="78de9-156"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="78de9-157"> [异步编程使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="78de9-157"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="78de9-158"> [异步示例︰ 微调应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="78de9-158"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
