---
title: "在一段时间 (Visual Basic 中) 后取消异步任务 |Microsoft 文档"
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
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
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
ms.openlocfilehash: 9c2c7c09f9af7c9b7bdcb6411b6db6e2ca4984cb
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a><span data-ttu-id="7f39c-102">在一段时间 (Visual Basic 中) 后取消异步任务</span><span class="sxs-lookup"><span data-stu-id="7f39c-102">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>
<span data-ttu-id="7f39c-103">可以通过使用取消异步操作的时间段之后<xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName>方法如果您不想等待操作完成。</xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7f39c-103">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="7f39c-104">此方法会安排在由指定的时间段内未完成任何关联任务的取消`CancelAfter`表达式。</span><span class="sxs-lookup"><span data-stu-id="7f39c-104">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>  
  
 <span data-ttu-id="7f39c-105">此示例将添加到代码中开发的[取消一个异步任务或列表任务 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)以下载网站的列表并显示每个内容的长度。</span><span class="sxs-lookup"><span data-stu-id="7f39c-105">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f39c-106">若要运行的示例，您必须具有 Visual Studio 2012 或更高版本和.NET Framework 4.5 或更高版本安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="7f39c-106">To run the examples, you must have Visual Studio 2012 or later and the .NET Framework 4.5 or later installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="7f39c-107">下载示例</span><span class="sxs-lookup"><span data-stu-id="7f39c-107">Downloading the Example</span></span>  
 <span data-ttu-id="7f39c-108">您可以下载完整的 Windows Presentation Foundation (WPF) 项目，从[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)，然后按照这些步骤。</span><span class="sxs-lookup"><span data-stu-id="7f39c-108">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="7f39c-109">解压缩下载的文件，然后启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="7f39c-109">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7f39c-110">在菜单栏上，依次选择 **“文件”**、 **“打开”**和 **“项目/解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="7f39c-110">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="7f39c-111">在**打开项目**对话框中，打开保存的示例代码中您解压缩的文件夹，然后为 AsyncFineTuningVB 打开解决方案 (.sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="7f39c-111">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="7f39c-112">在**解决方案资源管理器**，打开快捷菜单**CancelAfterTime**项目，，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="7f39c-112">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="7f39c-113">选择 F5 键以运行该项目。</span><span class="sxs-lookup"><span data-stu-id="7f39c-113">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="7f39c-114">按 Ctrl + F5 键以运行该项目，不对其进行调试。</span><span class="sxs-lookup"><span data-stu-id="7f39c-114">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="7f39c-115">运行程序多次以验证输出可能显示为所有网站、 任何网站或某些网站的输出。</span><span class="sxs-lookup"><span data-stu-id="7f39c-115">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>  
  
 <span data-ttu-id="7f39c-116">如果您不想要下载的项目，你可以查看本主题末尾处的 MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="7f39c-116">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="7f39c-117">生成示例</span><span class="sxs-lookup"><span data-stu-id="7f39c-117">Building the Example</span></span>  
 <span data-ttu-id="7f39c-118">本主题中的示例将添加到项目中开发的[取消一个异步任务或列表任务 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)若要取消的任务的列表。</span><span class="sxs-lookup"><span data-stu-id="7f39c-118">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="7f39c-119">该示例使用相同的 UI，尽管**取消**不显式使用按钮。</span><span class="sxs-lookup"><span data-stu-id="7f39c-119">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="7f39c-120">若要生成示例自己执行的步骤，请按照"下载示例"部分中的说明进行操作，但选择**CancelAListOfTasks**作为**启动项目**。</span><span class="sxs-lookup"><span data-stu-id="7f39c-120">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="7f39c-121">向该项目添加本主题中的所做的更改。</span><span class="sxs-lookup"><span data-stu-id="7f39c-121">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="7f39c-122">若要指定的最长时间才会任务都标记为已取消，添加对的调用`CancelAfter`到`startButton_Click`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="7f39c-122">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="7f39c-123">添加带有星号标记。</span><span class="sxs-lookup"><span data-stu-id="7f39c-123">The addition is marked with asterisks.</span></span>  
  
```vb  
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' Instantiate the CancellationTokenSource.  
    cts = New CancellationTokenSource()  
  
    resultsTextBox.Clear()  
  
    Try  
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
        ' can adjust the time.)  
        cts.CancelAfter(2500)  
  
        Await AccessTheWebAsync(cts.Token)  
        resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
    Catch ex As OperationCanceledException  
        resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
    Catch ex As Exception  
        resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
    End Try  
  
    ' Set the CancellationTokenSource to Nothing when the download is complete.  
    cts = Nothing  
End Sub  
```  
  
 <span data-ttu-id="7f39c-124">运行程序多次以验证输出可能显示为所有网站、 任何网站或某些网站的输出。</span><span class="sxs-lookup"><span data-stu-id="7f39c-124">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="7f39c-125">下面的输出是一个示例。</span><span class="sxs-lookup"><span data-stu-id="7f39c-125">The following output is a sample.</span></span>  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
## <a name="complete-example"></a><span data-ttu-id="7f39c-126">完整的示例</span><span class="sxs-lookup"><span data-stu-id="7f39c-126">Complete Example</span></span>  
 <span data-ttu-id="7f39c-127">下面的代码是该示例的 MainWindow.xaml.vb 文件的完整文本。</span><span class="sxs-lookup"><span data-stu-id="7f39c-127">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="7f39c-128">星号标记已针对此示例添加的元素。</span><span class="sxs-lookup"><span data-stu-id="7f39c-128">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="7f39c-129">请注意，您必须添加<xref:System.Net.Http>。</xref:System.Net.Http>的引用</span><span class="sxs-lookup"><span data-stu-id="7f39c-129">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="7f39c-130">您可以下载的项目[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)。</span><span class="sxs-lookup"><span data-stu-id="7f39c-130">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
            ' can adjust the time.)  
            cts.CancelAfter(2500)  
  
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
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
  
        ' Process each element in the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
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
  
' Length of the downloaded string: 35990.  
  
' Length of the downloaded string: 407399.  
  
' Length of the downloaded string: 226091.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f39c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f39c-131">See Also</span></span>  
 <span data-ttu-id="7f39c-132">[异步编程使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f39c-132">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="7f39c-133"> [演练︰ 访问 Web 使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="7f39c-133"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="7f39c-134"> [取消一个异步任务或一组任务 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="7f39c-134"> [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span></span>  
<span data-ttu-id="7f39c-135"> [微调异步应用程序 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="7f39c-135"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="7f39c-136"> [异步示例︰ 微调应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="7f39c-136"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
