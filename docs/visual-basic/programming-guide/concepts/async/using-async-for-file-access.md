---
title: "使用 Async 以进行文件访问 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
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
ms.openlocfilehash: 85f5fe17a012402c406eed972debd1f5889dd393
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="using-async-for-file-access-visual-basic"></a><span data-ttu-id="d03f5-102">使用异步进行文件访问 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d03f5-102">Using Async for File Access (Visual Basic)</span></span>
<span data-ttu-id="d03f5-103">异步功能可用于访问文件。</span><span class="sxs-lookup"><span data-stu-id="d03f5-103">You can use the Async feature to access files.</span></span> <span data-ttu-id="d03f5-104">通过使用异步功能，您可以调用异步方法而无需使用回调，也不需要跨多个方法或 lambda 表达式来拆分代码。</span><span class="sxs-lookup"><span data-stu-id="d03f5-104">By using the Async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="d03f5-105">若要使同步代码异步，只需调用异步方法而不是一种同步方法中，并向代码中添加几个关键字。</span><span class="sxs-lookup"><span data-stu-id="d03f5-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="d03f5-106">你可以考虑将异步添加到文件访问调用由于以下原因︰</span><span class="sxs-lookup"><span data-stu-id="d03f5-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
-   <span data-ttu-id="d03f5-107">异步使 UI 应用程序响应速度更快，因为启动该操作的 UI 线程可以执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="d03f5-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="d03f5-108">如果 UI 线程必须执行的代码，需要很长时间 （例如超过 50 毫秒为单位），UI 可能会冻结，直到 I/O 完成并且 UI 线程可以再次处理键盘和鼠标输入和其他事件。</span><span class="sxs-lookup"><span data-stu-id="d03f5-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
-   <span data-ttu-id="d03f5-109">异步通过减少线程的需要，可以提高 ASP.NET 的可伸缩性和其他基于服务器的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d03f5-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="d03f5-110">如果应用程序使用每次响应的专用的线程，并且同时处理有&1000; 多个请求，则需要有&1000; 多个线程。</span><span class="sxs-lookup"><span data-stu-id="d03f5-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="d03f5-111">异步操作通常不需要使用一个线程在等待期间。</span><span class="sxs-lookup"><span data-stu-id="d03f5-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="d03f5-112">它们使用现有 I/O 完成线程短暂的结尾。</span><span class="sxs-lookup"><span data-stu-id="d03f5-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
-   <span data-ttu-id="d03f5-113">文件访问操作的延迟可能会在当前条件下很低，但延迟可能会极大地提高了在将来。</span><span class="sxs-lookup"><span data-stu-id="d03f5-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="d03f5-114">例如，文件可能会移动到的服务器，则在世界各地。</span><span class="sxs-lookup"><span data-stu-id="d03f5-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
-   <span data-ttu-id="d03f5-115">添加使用异步功能的开销很小。</span><span class="sxs-lookup"><span data-stu-id="d03f5-115">The added overhead of using the Async feature is small.</span></span>  
  
-   <span data-ttu-id="d03f5-116">异步任务轻松地并行运行。</span><span class="sxs-lookup"><span data-stu-id="d03f5-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="d03f5-117">运行示例</span><span class="sxs-lookup"><span data-stu-id="d03f5-117">Running the Examples</span></span>  
 <span data-ttu-id="d03f5-118">若要运行本主题中的示例，可以创建**WPF 应用程序**或**Windows 窗体应用程序**，然后添加**按钮**。</span><span class="sxs-lookup"><span data-stu-id="d03f5-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="d03f5-119">在按钮的`Click`事件，每个示例中添加对第一种方法的调用。</span><span class="sxs-lookup"><span data-stu-id="d03f5-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="d03f5-120">在下面的示例中，包括以下`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="d03f5-120">In the following examples, include the following `Imports` statements.</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="d03f5-121">使用 FileStream 类</span><span class="sxs-lookup"><span data-stu-id="d03f5-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="d03f5-122">在本主题使用示例<xref:System.IO.FileStream>类，该类包含一个选项，将导致异步 I/O，以在操作系统级别上发生。</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="d03f5-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="d03f5-123">通过使用此选项，可以避免阻塞线程池线程在许多情况下。</span><span class="sxs-lookup"><span data-stu-id="d03f5-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="d03f5-124">若要启用此选项，请指定`useAsync=true`或`options=FileOptions.Asynchronous`构造函数调用中的参数。</span><span class="sxs-lookup"><span data-stu-id="d03f5-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="d03f5-125">不能使用此选项<xref:System.IO.StreamReader>并且<xref:System.IO.StreamWriter>如果您打开它们直接通过指定文件路径。</xref:System.IO.StreamWriter> </xref:System.IO.StreamReader></span><span class="sxs-lookup"><span data-stu-id="d03f5-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="d03f5-126">但是，您可以使用此选项，如果您为他们提供<xref:System.IO.Stream>，<xref:System.IO.FileStream>类打开。</xref:System.IO.FileStream> </xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="d03f5-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="d03f5-127">请注意，异步调用 UI 应用程序中更快即使线程池的线程被阻止，因为在等待期间不会阻止 UI 线程。</span><span class="sxs-lookup"><span data-stu-id="d03f5-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="d03f5-128">编写文本</span><span class="sxs-lookup"><span data-stu-id="d03f5-128">Writing Text</span></span>  
 <span data-ttu-id="d03f5-129">下面的示例将文本写入文件。</span><span class="sxs-lookup"><span data-stu-id="d03f5-129">The following example writes text to a file.</span></span> <span data-ttu-id="d03f5-130">在每个 await 语句，该方法立即退出。</span><span class="sxs-lookup"><span data-stu-id="d03f5-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="d03f5-131">文件 I/O 完成后，该方法恢复在 await 语句后面的语句处。</span><span class="sxs-lookup"><span data-stu-id="d03f5-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="d03f5-132">请注意，async 修饰符使用 await 语句的方法的定义中。</span><span class="sxs-lookup"><span data-stu-id="d03f5-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 <span data-ttu-id="d03f5-133">原始示例具有语句`Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`，这是以下两个语句的缩写式︰</span><span class="sxs-lookup"><span data-stu-id="d03f5-133">The original example has the statement `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, which is a contraction of the following two statements:</span></span>  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 <span data-ttu-id="d03f5-134">第一条语句返回一个任务，并会导致文件处理启动。</span><span class="sxs-lookup"><span data-stu-id="d03f5-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="d03f5-135">与 await 第二个语句会使方法立即退出并返回一个不同的任务。</span><span class="sxs-lookup"><span data-stu-id="d03f5-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="d03f5-136">完成处理更高版本的文件后，执行将返回到 await 后面的语句。</span><span class="sxs-lookup"><span data-stu-id="d03f5-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="d03f5-137">有关详细信息，请参阅[异步程序 (Visual Basic 中) 中的控制流](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)。</span><span class="sxs-lookup"><span data-stu-id="d03f5-137">For more information, see  [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="d03f5-138">读取文本</span><span class="sxs-lookup"><span data-stu-id="d03f5-138">Reading Text</span></span>  
 <span data-ttu-id="d03f5-139">下面的示例从文件读取文本。</span><span class="sxs-lookup"><span data-stu-id="d03f5-139">The following example reads text from a file.</span></span> <span data-ttu-id="d03f5-140">文本要缓冲，这种情况下，将其放入<xref:System.Text.StringBuilder>。</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="d03f5-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="d03f5-141">与不同的是在上一示例中，await 表达式的计算生成的值。</span><span class="sxs-lookup"><span data-stu-id="d03f5-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="d03f5-142"><xref:System.IO.Stream.ReadAsync%2A>方法将返回<xref:System.Threading.Tasks.Task>\< <xref:System.Int32>1>，因此在等待的评估得出`Int32`值 (`numRead`) 操作完成后。</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="d03f5-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="d03f5-143">有关详细信息，请参阅[异步返回类型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d03f5-143">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="d03f5-144">并行的异步 I/O</span><span class="sxs-lookup"><span data-stu-id="d03f5-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="d03f5-145">下面的示例演示通过编写 10 个文本文件的并行处理。</span><span class="sxs-lookup"><span data-stu-id="d03f5-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="d03f5-146">为每个文件<xref:System.IO.Stream.WriteAsync%2A>方法返回一个任务，然后添加到的任务的列表。</xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="d03f5-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="d03f5-147">`Await Task.WhenAll(tasks)`语句将退出方法和简历时文件处理的方法中完成的所有任务。</span><span class="sxs-lookup"><span data-stu-id="d03f5-147">The `Await Task.WhenAll(tasks)` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="d03f5-148">该示例将关闭所有<xref:System.IO.FileStream>实例`Finally`阻止任务完成后。</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="d03f5-148">The example closes all <xref:System.IO.FileStream> instances in a `Finally` block after the tasks are complete.</span></span> <span data-ttu-id="d03f5-149">如果每个`FileStream`中改为创建`Imports`语句，`FileStream`任务完成之前可能进行释放。</span><span class="sxs-lookup"><span data-stu-id="d03f5-149">If each `FileStream` was instead created in a `Imports` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="d03f5-150">请注意，任何性能提升几乎完全从并行处理和不的异步处理。</span><span class="sxs-lookup"><span data-stu-id="d03f5-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="d03f5-151">异步的优点是它不会占用多个线程，并且它不会占用用户界面线程。</span><span class="sxs-lookup"><span data-stu-id="d03f5-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 <span data-ttu-id="d03f5-152">当使用<xref:System.IO.Stream.WriteAsync%2A>和<xref:System.IO.Stream.ReadAsync%2A>方法，您可以指定<xref:System.Threading.CancellationToken>，它可用于取消操作的中间流。</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="d03f5-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="d03f5-153">有关详细信息，请参阅[微调异步应用程序 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)和[托管线程中的取消](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3)。</span><span class="sxs-lookup"><span data-stu-id="d03f5-153">For more information, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d03f5-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d03f5-154">See Also</span></span>  
 <span data-ttu-id="d03f5-155">[异步编程使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="d03f5-155">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="d03f5-156"> [异步返回类型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="d03f5-156"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="d03f5-157"> [异步程序 (Visual Basic 中) 中的控制流](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span><span class="sxs-lookup"><span data-stu-id="d03f5-157"> [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span></span>
