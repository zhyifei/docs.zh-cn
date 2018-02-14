---
title: "如何：向文件写入文本"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea0ff0d79762ba47214217a261a325aad9f5eaf6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="b674c-102">如何：向文件写入文本</span><span class="sxs-lookup"><span data-stu-id="b674c-102">How to: Write Text to a File</span></span>
<span data-ttu-id="b674c-103">本主题展示了针对 .NET Framework 应用程序或 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用将文本写入文件的几种不同的方式。</span><span class="sxs-lookup"><span data-stu-id="b674c-103">This topic shows different ways you can write text to a file for .NET Framework applications or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="b674c-104">下面的类和方法通常用于将文本写入文件：</span><span class="sxs-lookup"><span data-stu-id="b674c-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
-   <span data-ttu-id="b674c-105"><xref:System.IO.StreamWriter> - 它包含同步写入文件方法（<xref:System.IO.StreamWriter.Write%2A> 或 <xref:System.IO.TextWriter.WriteLine%2A>或者异步写入文件的方法（<xref:System.IO.StreamWriter.WriteAsync%2A> 和 <xref:System.IO.StreamWriter.WriteLineAsync%2A>。</span><span class="sxs-lookup"><span data-stu-id="b674c-105"><xref:System.IO.StreamWriter> - it contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> or <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
-   <span data-ttu-id="b674c-106"><xref:System.IO.File> – 用于 .NET Framework 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b674c-106"><xref:System.IO.File> – to be used with .NET Framework applications.</span></span> <span data-ttu-id="b674c-107">它提供了将文本写入文件的静态方法，如 <xref:System.IO.File.WriteAllLines%2A> 和 <xref:System.IO.File.WriteAllText%2A>，或者向文件中追加文本的静态方法（<xref:System.IO.File.AppendAllLines%2A><xref:System.IO.File.AppendAllText%2A> 或 <xref:System.IO.File.AppendText%2A>。</span><span class="sxs-lookup"><span data-stu-id="b674c-107">It provides static methods to write text to a file such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> or <xref:System.IO.File.AppendText%2A>).</span></span>  
  
-   <span data-ttu-id="b674c-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) - 用于 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用。</span><span class="sxs-lookup"><span data-stu-id="b674c-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) - to be used with [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="b674c-109">它包含将文本写入文件的异步方法（[WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) 或 [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)）或者向文件中追加文本的异步方法（[AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) 或 [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)）。</span><span class="sxs-lookup"><span data-stu-id="b674c-109">It contains asynchronous methods to write text to a file ([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) or [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) or to append text to a file ([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) or [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)).</span></span>  
  
 <span data-ttu-id="b674c-110">这些示例都很简单，以便将重点放在正在执行的任务上。</span><span class="sxs-lookup"><span data-stu-id="b674c-110">The samples have been kept simple in order to focus on the task being performed.</span></span> <span data-ttu-id="b674c-111">为此，这些示例执行最低限度的错误检查和异常处理（如果有）。</span><span class="sxs-lookup"><span data-stu-id="b674c-111">For this reason, the samples perform minimal error checking and exception handling, if any.</span></span> <span data-ttu-id="b674c-112">实际的应用程序通常提供更可靠的错误检查和异常处理。</span><span class="sxs-lookup"><span data-stu-id="b674c-112">A real-world application generally provides more robust error checking and exception handling.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b674c-113">示例</span><span class="sxs-lookup"><span data-stu-id="b674c-113">Example</span></span>  
 <span data-ttu-id="b674c-114">下面的示例演示如何使用 <xref:System.IO.StreamWriter> 类，一次一行同步地将文本写入新文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-114">The following example shows how to synchronously write text to a new file using the <xref:System.IO.StreamWriter> class, one line at a time.</span></span> <span data-ttu-id="b674c-115">新文本文件保存到用户的“我的文档”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b674c-115">The new text file is saved to the user's My Documents folder.</span></span> <span data-ttu-id="b674c-116">因为在 <xref:System.IO.StreamWriter> 语句中已声明并实例化 `using` 对象，所以会调用自动刷新并关闭流的 <xref:System.IO.StreamWriter.Dispose%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b674c-116">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked which automatically flushes and closes the stream.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## <a name="example"></a><span data-ttu-id="b674c-117">示例</span><span class="sxs-lookup"><span data-stu-id="b674c-117">Example</span></span>  
 <span data-ttu-id="b674c-118">下面的示例演示如何使用 <xref:System.IO.StreamWriter> 类将文本追加到现有的文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-118">The following example shows how to append text to an existing file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="b674c-119">它使用上一示例中的同一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-119">It uses the same text file from the previous example.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]     
  
## <a name="example"></a><span data-ttu-id="b674c-120">示例</span><span class="sxs-lookup"><span data-stu-id="b674c-120">Example</span></span>  
 <span data-ttu-id="b674c-121">下面的示例演示如何使用 <xref:System.IO.StreamWriter> 类异步地将文本写入新文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-121">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="b674c-122">为了调用 <xref:System.IO.StreamWriter.WriteAsync%2A> 方法，方法调用需要在 `async` 方法内。</span><span class="sxs-lookup"><span data-stu-id="b674c-122">In order to invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call needs to be within an `async` method.</span></span> <span data-ttu-id="b674c-123">新文本文件保存到用户的“我的文档”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b674c-123">The new text file is saved to the user's My Documents folder.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## <a name="example"></a><span data-ttu-id="b674c-124">示例</span><span class="sxs-lookup"><span data-stu-id="b674c-124">Example</span></span>  
 <span data-ttu-id="b674c-125">下面的示例演示如何使用 <xref:System.IO.File> 类将文本写入新文件并将新的文本行追加到同一文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-125">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="b674c-126"><xref:System.IO.File.WriteAllText%2A> 和 <xref:System.IO.File.AppendAllLines%2A> 方法会自动打开和关闭文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-126">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="b674c-127">如果提供给 <xref:System.IO.File.WriteAllText%2A> 方法的路径已存在，则文件将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="b674c-127">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file will be overwritten.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## <a name="example"></a><span data-ttu-id="b674c-128">示例</span><span class="sxs-lookup"><span data-stu-id="b674c-128">Example</span></span>  
 <span data-ttu-id="b674c-129">下面的示例演示如何将用户输入异步写入到 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用中的一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-129">The following example shows how to asynchronously write user input to a text file in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span> <span data-ttu-id="b674c-130">因为出于安全考虑，从 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用打开文件通常需要使用 [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) 控件。</span><span class="sxs-lookup"><span data-stu-id="b674c-130">Because of security considerations, opening a file from a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app typically requires the use of a [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) control.</span></span> <span data-ttu-id="b674c-131">在该示例中，筛选 `FileOpenPicker` 以显示文本文件。</span><span class="sxs-lookup"><span data-stu-id="b674c-131">In this example, the `FileOpenPicker` is filtered to show text files.</span></span>  
  
```xaml  
<Page  
    x:Class="OpenFileWindowsStore.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:OpenFileWindowsStore"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Button Content="save text to a file" HorizontalAlignment="Left" Margin="103,417,0,0" VerticalAlignment="Top"   
                Width="329" Height="86" FontSize="35" Click="Button_Click"/>  
        <TextBox Name="UserInputTextBox"  FontSize="18" HorizontalAlignment="Left" Margin="106,146,0,0"   
                 TextWrapping="Wrap" Text="Write some text here, and select a file to write it to." VerticalAlignment="Top"   
                 Height="201" Width="558" AcceptsReturn="True"/>  
        <TextBlock Name="StatusTextBox" HorizontalAlignment="Left" Margin="106,570,0,147" TextWrapping="Wrap" Text="Status:"   
                   VerticalAlignment="Center" Height="51" Width="1074" FontSize="18" />  
    </Grid>  
</Page>  
```  
  
 [!code-csharp[OpenFileWindowsStore#Code](../../../samples/snippets/csharp/VS_Snippets_CLR/openfilewindowsstore/cs/mainpage.xaml.cs#code)]
 [!code-vb[OpenFileWindowsStore#Code](../../../samples/snippets/visualbasic/VS_Snippets_CLR/openfilewindowsstore/vb/mainpage.xaml.vb#code)]  
  
## <a name="see-also"></a><span data-ttu-id="b674c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b674c-132">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b674c-133">如何：枚举目录和文件</span><span class="sxs-lookup"><span data-stu-id="b674c-133">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="b674c-134">如何：对新建的数据文件进行读取和写入</span><span class="sxs-lookup"><span data-stu-id="b674c-134">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="b674c-135">如何：打开并追加到日志文件</span><span class="sxs-lookup"><span data-stu-id="b674c-135">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="b674c-136">如何：从文件读取文本</span><span class="sxs-lookup"><span data-stu-id="b674c-136">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="b674c-137">文件和流 I-O</span><span class="sxs-lookup"><span data-stu-id="b674c-137">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
