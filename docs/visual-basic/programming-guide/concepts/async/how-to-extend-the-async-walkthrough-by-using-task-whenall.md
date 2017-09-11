---
title: "如何︰ 使用 Task.WhenAll (Visual Basic 中) 扩展异步演练 |Microsoft 文档"
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
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
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
ms.openlocfilehash: 91cecc84899c9a87307ed5799485ec60ef341e65
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a><span data-ttu-id="55e05-102">如何︰ 使用 Task.WhenAll (Visual Basic 中) 扩展异步演练</span><span class="sxs-lookup"><span data-stu-id="55e05-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>
<span data-ttu-id="55e05-103">您可以提高中的异步解决方案的性能[演练︰ 使用 Async 和 Await (Visual Basic 中) 通过 Web 访问](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)通过使用<xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>方法。</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="55e05-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="55e05-104">此方法异步等待多个异步操作，表示为一系列的任务。</span><span class="sxs-lookup"><span data-stu-id="55e05-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>  
  
 <span data-ttu-id="55e05-105">您可能已经注意到在本演练的网站下载以不同的速率。</span><span class="sxs-lookup"><span data-stu-id="55e05-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="55e05-106">有时在网站上找到的一个速度很慢，这会延迟所有剩余的下载。</span><span class="sxs-lookup"><span data-stu-id="55e05-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="55e05-107">当您在本演练中运行生成的异步解决方案后，您可以结束该程序轻松地如果不想等待，但更好的选择将开始在同一时间的所有下载，并允许更快地下载继续而无需等待延迟的一个。</span><span class="sxs-lookup"><span data-stu-id="55e05-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>  
  
 <span data-ttu-id="55e05-108">您将应用`Task.WhenAll`方法任务的集合。</span><span class="sxs-lookup"><span data-stu-id="55e05-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="55e05-109">应用程序的`WhenAll`返回集合中的每个任务完成之后未完成一项任务。</span><span class="sxs-lookup"><span data-stu-id="55e05-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="55e05-110">显示的任务来并行运行，但创建没有其他线程。</span><span class="sxs-lookup"><span data-stu-id="55e05-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="55e05-111">可以按任意顺序完成的任务。</span><span class="sxs-lookup"><span data-stu-id="55e05-111">The tasks can complete in any order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="55e05-112">下面的过程描述中开发的异步应用程序的扩展[演练︰ 使用 Async 和 Await (Visual Basic 中) 通过 Web 访问](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)。</span><span class="sxs-lookup"><span data-stu-id="55e05-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="55e05-113">您可以通过完成本演练或下载中的代码中开发应用程序[开发人员代码示例](http://go.microsoft.com/fwlink/?LinkId=255191)。</span><span class="sxs-lookup"><span data-stu-id="55e05-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
>   
>  <span data-ttu-id="55e05-114">若要运行该示例，您必须具有 Visual Studio 2012 或更高版本安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="55e05-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="55e05-115">向你的 GetURLContentsAsync 解决方案中添加 Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="55e05-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>  
  
1.  <span data-ttu-id="55e05-116">添加`ProcessURLAsync`方法的第一个应用程序开发的[演练︰ 使用 Async 和 Await (Visual Basic 中) 通过 Web 访问](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)。</span><span class="sxs-lookup"><span data-stu-id="55e05-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="55e05-117">如果下载中的代码[开发人员代码示例](http://go.microsoft.com/fwlink/?LinkId=255191)，打开 AsyncWalkthrough 项目，然后添加`ProcessURLAsync`MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="55e05-117">If you downloaded the code from  [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="55e05-118">如果通过完成本演练开发的代码，请添加`ProcessURLAsync`的应用程序包括`GetURLContentsAsync`方法。</span><span class="sxs-lookup"><span data-stu-id="55e05-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="55e05-119">此应用程序的 MainWindow.xaml.vb 文件是"完整的代码示例从演练"部分中的第一个示例。</span><span class="sxs-lookup"><span data-stu-id="55e05-119">The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="55e05-120">`ProcessURLAsync`方法整合了正文中的操作`For Each`循环中`SumPageSizesAsync`在原始的演练。</span><span class="sxs-lookup"><span data-stu-id="55e05-120">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="55e05-121">该方法以异步方式对作为字节数组，指定的网站的内容下载然后显示并返回字节数组的长度。</span><span class="sxs-lookup"><span data-stu-id="55e05-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="55e05-122">注释掉或删除`For Each`循环中`SumPageSizesAsync`，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="55e05-122">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0  
    'For Each url In urlList  
  
    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
    '    ' The previous line abbreviates the following two assignment statements.  
  
    '    ' GetURLContentsAsync returns a task. At completion, the task  
    '    ' produces a byte array.  
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
    '    'Dim urlContents As Byte() = Await getContentsTask  
  
    '    DisplayResults(url, urlContents)  
  
    '    ' Update the total.  
    '    total += urlContents.Length  
    'Next  
    ```  
  
3.  <span data-ttu-id="55e05-123">创建任务的集合。</span><span class="sxs-lookup"><span data-stu-id="55e05-123">Create a collection of tasks.</span></span> <span data-ttu-id="55e05-124">下面的代码定义[查询](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)，通过在执行时<xref:System.Linq.Enumerable.ToArray%2A>方法时，创建的每个网站的内容下载的任务的集合。</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="55e05-124">The following code defines a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="55e05-125">该查询进行求值时，会启动任务。</span><span class="sxs-lookup"><span data-stu-id="55e05-125">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="55e05-126">将以下代码添加到方法`SumPageSizesAsync`的声明后`urlList`。</span><span class="sxs-lookup"><span data-stu-id="55e05-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="55e05-127">应用`Task.WhenAll`到集合的任务， `downloadTasks`。</span><span class="sxs-lookup"><span data-stu-id="55e05-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="55e05-128">`Task.WhenAll`返回任务的集合中的所有任务都完成时完成一项任务。</span><span class="sxs-lookup"><span data-stu-id="55e05-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="55e05-129">在下面的示例中，`Await`表达式等待完成单个任务`WhenAll`返回。</span><span class="sxs-lookup"><span data-stu-id="55e05-129">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="55e05-130">表达式计算结果为整数，其中每个整数是一个下载网站的长度的数组。</span><span class="sxs-lookup"><span data-stu-id="55e05-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="55e05-131">添加以下代码到`SumPageSizesAsync`，只是你在上一步中添加的代码之后。</span><span class="sxs-lookup"><span data-stu-id="55e05-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="55e05-132">最后，使用<xref:System.Linq.Enumerable.Sum%2A>方法来对其求和的所有网站的长度。</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="55e05-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="55e05-133">添加以下代码行到`SumPageSizesAsync`。</span><span class="sxs-lookup"><span data-stu-id="55e05-133">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="55e05-134">向 HttpClient.GetByteArrayAsync 解决方案中添加 Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="55e05-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>  
  
1.  <span data-ttu-id="55e05-135">添加以下版本的`ProcessURLAsync`到第二个应用程序中开发的[演练︰ 使用 Async 和 Await (Visual Basic 中) 通过 Web 访问](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)。</span><span class="sxs-lookup"><span data-stu-id="55e05-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="55e05-136">如果下载中的代码[开发人员代码示例](http://go.microsoft.com/fwlink/?LinkId=255191)，打开 AsyncWalkthrough_HttpClient 项目，然后添加`ProcessURLAsync`MainWindow.xaml.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="55e05-136">If you downloaded the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="55e05-137">如果通过完成本演练开发的代码，请添加`ProcessURLAsync`的应用程序使用`HttpClient.GetByteArrayAsync`方法。</span><span class="sxs-lookup"><span data-stu-id="55e05-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="55e05-138">此应用程序的 MainWindow.xaml.vb 文件是"完整的代码示例从演练"部分中的第二个示例。</span><span class="sxs-lookup"><span data-stu-id="55e05-138">The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="55e05-139">`ProcessURLAsync`方法整合了正文中的操作`For Each`循环中`SumPageSizesAsync`在原始的演练。</span><span class="sxs-lookup"><span data-stu-id="55e05-139">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="55e05-140">该方法以异步方式对作为字节数组，指定的网站的内容下载然后显示并返回字节数组的长度。</span><span class="sxs-lookup"><span data-stu-id="55e05-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
     <span data-ttu-id="55e05-141">从唯一的区别`ProcessURLAsync`在前面过程中的方法是使用<xref:System.Net.Http.HttpClient>实例， `client`。</xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="55e05-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="55e05-142">注释掉或删除`For Each`循环中`SumPageSizesAsync`，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="55e05-142">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0   
    'For Each url In urlList   
    '    ' GetByteArrayAsync returns a task. At completion, the task   
    '    ' produces a byte array.   
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)   
  
    '    ' The following two lines can replace the previous assignment statement.   
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)   
    '    'Dim urlContents As Byte() = Await getContentsTask   
  
    '    DisplayResults(url, urlContents)   
  
    '    ' Update the total.   
    '    total += urlContents.Length   
    'Next  
  
    ```  
  
3.  <span data-ttu-id="55e05-143">定义[查询](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)，通过在执行时<xref:System.Linq.Enumerable.ToArray%2A>方法时，创建的每个网站的内容下载的任务的集合。</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="55e05-143">Define a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="55e05-144">该查询进行求值时，会启动任务。</span><span class="sxs-lookup"><span data-stu-id="55e05-144">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="55e05-145">将以下代码添加到方法`SumPageSizesAsync`的声明后`client`和`urlList`。</span><span class="sxs-lookup"><span data-stu-id="55e05-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="55e05-146">接下来，应用`Task.WhenAll`到集合的任务， `downloadTasks`。</span><span class="sxs-lookup"><span data-stu-id="55e05-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="55e05-147">`Task.WhenAll`返回任务的集合中的所有任务都完成时完成一项任务。</span><span class="sxs-lookup"><span data-stu-id="55e05-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="55e05-148">在下面的示例中，`Await`表达式等待完成单个任务`WhenAll`返回。</span><span class="sxs-lookup"><span data-stu-id="55e05-148">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="55e05-149">完成后，`Await`表达式计算结果为整数，其中每个整数是一个下载网站的长度的数组。</span><span class="sxs-lookup"><span data-stu-id="55e05-149">When complete, the `Await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="55e05-150">添加以下代码到`SumPageSizesAsync`，只是你在上一步中添加的代码之后。</span><span class="sxs-lookup"><span data-stu-id="55e05-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="55e05-151">最后，使用<xref:System.Linq.Enumerable.Sum%2A>方法以获取所有网站的长度之和。</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="55e05-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="55e05-152">添加以下代码行到`SumPageSizesAsync`。</span><span class="sxs-lookup"><span data-stu-id="55e05-152">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="55e05-153">测试 Task.WhenAll 解决方案</span><span class="sxs-lookup"><span data-stu-id="55e05-153">To test the Task.WhenAll solutions</span></span>  
  
-   <span data-ttu-id="55e05-154">对于任一解决方案中，选择 F5 键以运行该程序，然后选择**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="55e05-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="55e05-155">输出应类似于中的异步解决方案的输出[演练︰ 使用 Async 和 Await (Visual Basic 中) 通过 Web 访问](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)。</span><span class="sxs-lookup"><span data-stu-id="55e05-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="55e05-156">但请注意，在网站上找到以不同的顺序在每次显示。</span><span class="sxs-lookup"><span data-stu-id="55e05-156">However, notice that the websites appear in a different order each time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55e05-157">示例</span><span class="sxs-lookup"><span data-stu-id="55e05-157">Example</span></span>  
 <span data-ttu-id="55e05-158">下面的代码演示对使用的项目的扩充`GetURLContentsAsync`方法以从 web 下载内容。</span><span class="sxs-lookup"><span data-stu-id="55e05-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.   
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        'Dim total = 0  
        'For Each url In urlList  
  
        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
        '    ' The previous line abbreviates the following two assignment statements.  
  
        '    ' GetURLContentsAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    ' The actions from the foreach loop are moved to this async method.  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                ' CopyToAsync returns a Task, not a Task<T>.  
                Await responseStream.CopyToAsync(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="example"></a><span data-ttu-id="55e05-159">示例</span><span class="sxs-lookup"><span data-stu-id="55e05-159">Example</span></span>  
 <span data-ttu-id="55e05-160">下面的代码显示的项目的使用方法的扩展`HttpClient.GetByteArrayAsync`从 web 下载内容。</span><span class="sxs-lookup"><span data-stu-id="55e05-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        ''<snippet7>  
        'Dim total = 0  
        'For Each url In urlList  
        '    ' GetByteArrayAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    '<snippet31>  
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
        '    '</snippet31>  
  
        '    ' The following two lines can replace the previous assignment statement.  
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://www.msdn.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="55e05-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55e05-161">See Also</span></span>  
 <span data-ttu-id="55e05-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="55e05-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="55e05-163"> [演练︰ 访问 Web 使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="55e05-163"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
