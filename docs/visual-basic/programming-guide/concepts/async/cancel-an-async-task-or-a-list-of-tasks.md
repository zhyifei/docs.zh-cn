---
title: "取消一个异步任务或一组任务 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
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
ms.openlocfilehash: fe2df73aaf49f1b61dafcad9a6c6e0f3d014f8ec
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="025ac-102">取消一个异步任务或一组任务 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="025ac-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>
<span data-ttu-id="025ac-103">您可以设置一个按钮，可用于取消异步应用程序，如果不想等待其完成。</span><span class="sxs-lookup"><span data-stu-id="025ac-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="025ac-104">通过遵循本主题中的示例，您可以在下载网站的列表或一个网站的内容应用程序中添加取消按钮。</span><span class="sxs-lookup"><span data-stu-id="025ac-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>  
  
 <span data-ttu-id="025ac-105">这些示例使用用户界面，[微调异步应用程序 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)描述。</span><span class="sxs-lookup"><span data-stu-id="025ac-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="025ac-106">若要运行的示例，必须具有 Visual Studio 2012 或更高版本和.NET Framework 4.5 或更高版本安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="025ac-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="025ac-107"><a name="BKMK_CancelaTask"></a>取消任务</span><span class="sxs-lookup"><span data-stu-id="025ac-107"><a name="BKMK_CancelaTask"></a> Cancel a Task</span></span>  
 <span data-ttu-id="025ac-108">第一个示例将关联**取消**与单个下载任务的按钮。</span><span class="sxs-lookup"><span data-stu-id="025ac-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="025ac-109">如果应用程序正在下载内容时选择此按钮时，则会取消下载。</span><span class="sxs-lookup"><span data-stu-id="025ac-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="025ac-110">下载示例</span><span class="sxs-lookup"><span data-stu-id="025ac-110">Downloading the Example</span></span>  
 <span data-ttu-id="025ac-111">您可以下载完整的 Windows Presentation Foundation (WPF) 项目，从[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)，然后按照这些步骤。</span><span class="sxs-lookup"><span data-stu-id="025ac-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="025ac-112">解压缩下载的文件，然后启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="025ac-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="025ac-113">在菜单栏上，依次选择 **“文件”**、 **“打开”**和 **“项目/解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="025ac-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="025ac-114">在**打开项目**对话框中，打开保存的示例代码中您解压缩的文件夹，然后为 AsyncFineTuningVB 打开解决方案 (.sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="025ac-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="025ac-115">在**解决方案资源管理器**，打开快捷菜单**CancelATask**项目，，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="025ac-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="025ac-116">选择 F5 键以运行该项目。</span><span class="sxs-lookup"><span data-stu-id="025ac-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="025ac-117">按 Ctrl + F5 键以运行该项目，不对其进行调试。</span><span class="sxs-lookup"><span data-stu-id="025ac-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="025ac-118">如果您不想要下载的项目，你可以查看本主题末尾的 MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="025ac-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="025ac-119">生成示例</span><span class="sxs-lookup"><span data-stu-id="025ac-119">Building the Example</span></span>  
 <span data-ttu-id="025ac-120">添加了以下更改**取消**下载网站的应用程序的按钮。</span><span class="sxs-lookup"><span data-stu-id="025ac-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="025ac-121">如果您不想要下载或生成示例，你可以查看在本主题末尾的"完整的示例"部分中，最终产品。</span><span class="sxs-lookup"><span data-stu-id="025ac-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="025ac-122">星号标记在代码中的更改。</span><span class="sxs-lookup"><span data-stu-id="025ac-122">Asterisks mark the changes in the code.</span></span>  
  
 <span data-ttu-id="025ac-123">若要生成示例自己执行的步骤，请按照"下载示例"部分中的说明进行操作，但选择**StarterCode**作为**启动项目**而不是**CancelATask**。</span><span class="sxs-lookup"><span data-stu-id="025ac-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>  
  
 <span data-ttu-id="025ac-124">然后将以下更改添加到该项目的 MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="025ac-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>  
  
1.  <span data-ttu-id="025ac-125">声明`CancellationTokenSource`变量， `cts`，对其进行访问的所有方法的作用域内。</span><span class="sxs-lookup"><span data-stu-id="025ac-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="025ac-126">添加以下事件处理程序**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="025ac-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="025ac-127">事件处理程序使用<xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>方法来通知`cts`当用户请求取消。</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="025ac-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> method to notify `cts` when the user requests cancellation.</span></span>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  <span data-ttu-id="025ac-128">进行以下更改在事件处理程序**启动**按钮， `startButton_Click`。</span><span class="sxs-lookup"><span data-stu-id="025ac-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>  
  
    -   <span data-ttu-id="025ac-129">实例化`CancellationTokenSource`， `cts`。</span><span class="sxs-lookup"><span data-stu-id="025ac-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   <span data-ttu-id="025ac-130">在调用`AccessTheWebAsync`，包括下载指定的网站的内容，将发送<xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName>属性`cts`作为参数。</xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="025ac-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> property of `cts` as an argument.</span></span> <span data-ttu-id="025ac-131">`Token`属性将消息传播如果请求取消。</span><span class="sxs-lookup"><span data-stu-id="025ac-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="025ac-132">添加显示一条消息，如果用户选择要取消下载操作的 catch 块。</span><span class="sxs-lookup"><span data-stu-id="025ac-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="025ac-133">下面的代码演示所做的更改。</span><span class="sxs-lookup"><span data-stu-id="025ac-133">The following code shows the changes.</span></span>  
  
        ```vb  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
        ```  
  
4.  <span data-ttu-id="025ac-134">在`AccessTheWebAsync`，使用<xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName>重载`GetAsync`中的方法<xref:System.Net.Http.HttpClient>要下载网站内容类型。</xref:System.Net.Http.HttpClient> </xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="025ac-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="025ac-135">传递`ct`、<xref:System.Threading.CancellationToken>参数`AccessTheWebAsync`，作为第二个参数。</xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="025ac-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="025ac-136">令牌携带消息，如果用户选择**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="025ac-136">The token carries the message if the user chooses the **Cancel** button.</span></span>  
  
     <span data-ttu-id="025ac-137">下面的代码演示中的更改`AccessTheWebAsync`。</span><span class="sxs-lookup"><span data-stu-id="025ac-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
    ```  
  
5.  <span data-ttu-id="025ac-138">如果不取消该程序，它将生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="025ac-138">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     <span data-ttu-id="025ac-139">如果您选择**取消**之前该程序的按钮完成的下载内容，该程序生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="025ac-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <span data-ttu-id="025ac-140"><a name="BKMK_CancelaListofTasks"></a>取消任务列表</span><span class="sxs-lookup"><span data-stu-id="025ac-140"><a name="BKMK_CancelaListofTasks"></a> Cancel a List of Tasks</span></span>  
 <span data-ttu-id="025ac-141">您可以扩展前面的示例通过将相关联相同取消多项任务`CancellationTokenSource`与每个任务的实例。</span><span class="sxs-lookup"><span data-stu-id="025ac-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="025ac-142">如果您选择**取消**按钮，你取消尚未完成的所有任务。</span><span class="sxs-lookup"><span data-stu-id="025ac-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="025ac-143">下载示例</span><span class="sxs-lookup"><span data-stu-id="025ac-143">Downloading the Example</span></span>  
 <span data-ttu-id="025ac-144">您可以下载完整的 Windows Presentation Foundation (WPF) 项目，从[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)，然后按照这些步骤。</span><span class="sxs-lookup"><span data-stu-id="025ac-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="025ac-145">解压缩下载的文件，然后启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="025ac-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="025ac-146">在菜单栏上，依次选择 **“文件”**、 **“打开”**和 **“项目/解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="025ac-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="025ac-147">在**打开项目**对话框中，打开保存的示例代码中您解压缩的文件夹，然后为 AsyncFineTuningVB 打开解决方案 (.sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="025ac-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="025ac-148">在**解决方案资源管理器**，打开快捷菜单**CancelAListOfTasks**项目，，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="025ac-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="025ac-149">选择 F5 键以运行该项目。</span><span class="sxs-lookup"><span data-stu-id="025ac-149">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="025ac-150">按 Ctrl + F5 键以运行该项目，不对其进行调试。</span><span class="sxs-lookup"><span data-stu-id="025ac-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="025ac-151">如果您不想要下载的项目，你可以查看本主题末尾的 MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="025ac-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="025ac-152">生成示例</span><span class="sxs-lookup"><span data-stu-id="025ac-152">Building the Example</span></span>  
 <span data-ttu-id="025ac-153">若要将此示例扩展自己执行步骤的请按照"下载示例"部分中的说明进行操作，但选择**CancelATask**作为**启动项目**。</span><span class="sxs-lookup"><span data-stu-id="025ac-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="025ac-154">向该项目中添加了以下更改。</span><span class="sxs-lookup"><span data-stu-id="025ac-154">Add the following changes to that project.</span></span> <span data-ttu-id="025ac-155">星号标记的程序中更改。</span><span class="sxs-lookup"><span data-stu-id="025ac-155">Asterisks mark the changes in the program.</span></span>  
  
1.  <span data-ttu-id="025ac-156">添加一个方法来创建的 web 地址的列表。</span><span class="sxs-lookup"><span data-stu-id="025ac-156">Add a method to create a list of web addresses.</span></span>  
  
    ```vb  
    ' ***Add a method that creates a list of web addresses.  
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
    ```  
  
2.  <span data-ttu-id="025ac-157">在调用方法`AccessTheWebAsync`。</span><span class="sxs-lookup"><span data-stu-id="025ac-157">Call the method in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  <span data-ttu-id="025ac-158">添加下面的循环中`AccessTheWebAsync`来处理列表中的每个 web 地址。</span><span class="sxs-lookup"><span data-stu-id="025ac-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>  
  
    ```vb  
    ' ***Add a loop to process the list of web addresses.  
    For Each url In urlList  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' Argument ct carries the message if the Cancel button is chosen.   
        ' ***Note that the Cancel button can cancel all remaining downloads.  
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
    Next  
    ```  
  
4.  <span data-ttu-id="025ac-159">因为`AccessTheWebAsync`显示的长度，该方法不需要返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="025ac-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="025ac-160">删除返回语句，并将该方法的返回类型更改为<xref:System.Threading.Tasks.Task>而不是<xref:System.Threading.Tasks.Task%601>。</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="025ac-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
<span data-ttu-id="025ac-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="025ac-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="025ac-162">调用方法中的，从`startButton_Click`而不是一个表达式，表达式使用语句。</span><span class="sxs-lookup"><span data-stu-id="025ac-162">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  <span data-ttu-id="025ac-163">如果不取消该程序，它将生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="025ac-163">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
  
    ```  
  
     <span data-ttu-id="025ac-164">如果您选择**取消**按钮之前下载的内容都已完成，则输出包含在取消之前完成的下载的长度。</span><span class="sxs-lookup"><span data-stu-id="025ac-164">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
  
    ```  
  
##  <span data-ttu-id="025ac-165"><a name="BKMK_CompleteExamples"></a>完整示例</span><span class="sxs-lookup"><span data-stu-id="025ac-165"><a name="BKMK_CompleteExamples"></a> Complete Examples</span></span>  
 <span data-ttu-id="025ac-166">以下各节包含有关每个前面的示例的代码。</span><span class="sxs-lookup"><span data-stu-id="025ac-166">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="025ac-167">请注意，您必须添加<xref:System.Net.Http>。</xref:System.Net.Http>的引用</span><span class="sxs-lookup"><span data-stu-id="025ac-167">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="025ac-168">您可以下载的项目[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)。</span><span class="sxs-lookup"><span data-stu-id="025ac-168">You can download the projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
### <a name="cancel-a-task-example"></a><span data-ttu-id="025ac-169">取消任务示例</span><span class="sxs-lookup"><span data-stu-id="025ac-169">Cancel a Task Example</span></span>  
 <span data-ttu-id="025ac-170">下面的代码是取消一项任务的示例的完整 MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="025ac-170">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' ***Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
  
        ' ***Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
End Class  
  
' Output for a successful download:  
  
' Ready to download.  
  
' Length of the downloaded string: 158125.  
  
' Or, if you cancel:  
  
' Ready to download.  
  
' Download canceled.  
```  
  
### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="025ac-171">取消任务列表示例</span><span class="sxs-lookup"><span data-stu-id="025ac-171">Cancel a List of Tasks Example</span></span>  
 <span data-ttu-id="025ac-172">下面的代码是取消的任务列表示例的完整 MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="025ac-172">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>  
  
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
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).  
            Await AccessTheWebAsync(cts.Token)  
            '  ***Small change in the display lines.  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' ***Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' ***Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Add a loop to process the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' ***Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' ***Add a method that creates a list of web addresses.  
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
  
' Output if you do not choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Length of the downloaded string: 158124.  
  
' Length of the downloaded string: 204890.  
  
' Length of the downloaded string: 175488.  
  
' Length of the downloaded string: 145790.  
  
' Downloads complete.  
  
'  Sample output if you choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a><span data-ttu-id="025ac-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="025ac-173">See Also</span></span>  
 <span data-ttu-id="025ac-174"><xref:System.Threading.CancellationTokenSource></xref:System.Threading.CancellationTokenSource></span><span class="sxs-lookup"><span data-stu-id="025ac-174"><xref:System.Threading.CancellationTokenSource></span></span>   
 <span data-ttu-id="025ac-175"><xref:System.Threading.CancellationToken></xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="025ac-175"><xref:System.Threading.CancellationToken></span></span>   
<span data-ttu-id="025ac-176"> [异步编程使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="025ac-176"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="025ac-177"> [微调异步应用程序 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="025ac-177"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="025ac-178"> [异步示例︰ 微调应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="025ac-178"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
