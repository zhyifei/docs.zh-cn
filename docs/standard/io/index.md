---
title: 文件和流 I/O
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- IO namespace
- files, I/O
- System.IO namespace
- I/O [.NET Framework]
- streams, I/O
- data streams, I/O
ms.assetid: 4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4452ad2445f81659d04bca3d64885148895aeb88
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50046744"
---
# <a name="file-and-stream-io"></a><span data-ttu-id="7554a-102">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="7554a-102">File and Stream I/O</span></span>
<span data-ttu-id="7554a-103">文件和流 I/O（输入/输出）是指在存储媒介中传入或传出数据。</span><span class="sxs-lookup"><span data-stu-id="7554a-103">File and stream I/O (input/output) refers to the transfer of data either to or from a storage medium.</span></span> <span data-ttu-id="7554a-104">在 .NET Framework 中，`System.IO` 命名空间包含允许以异步方式和同步方式对数据流和文件进行读取和写入操作的类型。</span><span class="sxs-lookup"><span data-stu-id="7554a-104">In the .NET Framework, the `System.IO` namespaces contain types that enable reading and writing, both synchronously and asynchronously, on data streams and files.</span></span> <span data-ttu-id="7554a-105">这些命名空间还包含对文件执行压缩和解压缩的类型，以及通过管道和串行端口启用通信的类型。</span><span class="sxs-lookup"><span data-stu-id="7554a-105">These namespaces also contain types that perform compression and decompression on files, and types that enable communication through pipes and serial ports.</span></span>  
  
 <span data-ttu-id="7554a-106">文件是一个由字节组成的有序的命名集合，它具有永久存储。</span><span class="sxs-lookup"><span data-stu-id="7554a-106">A file is an ordered and named collection of bytes that has persistent storage.</span></span> <span data-ttu-id="7554a-107">在处理文件时，你将处理目录路径、磁盘存储、文件和目录名称。</span><span class="sxs-lookup"><span data-stu-id="7554a-107">When you work with files, you work with directory paths, disk storage, and file and directory names.</span></span> <span data-ttu-id="7554a-108">相反，流是一个字节序列，可用于对后备存储进行读取和写入操作，后备存储可以是多个存储媒介之一（例如，磁盘或内存）。</span><span class="sxs-lookup"><span data-stu-id="7554a-108">In contrast, a stream is a sequence of bytes that you can use to read from and write to a backing store, which can be one of several storage mediums (for example, disks or memory).</span></span> <span data-ttu-id="7554a-109">正如存在除磁盘之外的多种后备存储一样，也存在除文件流之外的多种流（如网络、内存和管道流）。</span><span class="sxs-lookup"><span data-stu-id="7554a-109">Just as there are several backing stores other than disks, there are several kinds of streams other than file streams, such as network, memory, and pipe streams.</span></span>  
  
## <a name="files-and-directories"></a><span data-ttu-id="7554a-110">文件和目录</span><span class="sxs-lookup"><span data-stu-id="7554a-110">Files and Directories</span></span>  
 <span data-ttu-id="7554a-111">你可以使用 <xref:System.IO?displayProperty=nameWithType> 命名空间中的类型与文件和目录进行交互。</span><span class="sxs-lookup"><span data-stu-id="7554a-111">You can use the types in the <xref:System.IO?displayProperty=nameWithType> namespace to interact with files and directories.</span></span> <span data-ttu-id="7554a-112">例如，你可以获取和设置文件和目录的属性，并基于搜索条件检索文件和目录的集合。</span><span class="sxs-lookup"><span data-stu-id="7554a-112">For example, you can get and set properties for files and directories, and retrieve collections of files and directories based on search criteria.</span></span>  

<span data-ttu-id="7554a-113">若要深入了解 Windows 系统中的路径命名约定和 文件路径的表示方式，包括在 .NET Core 1.1 及更高版本和 .NET Framework 4.6.2 及更高版本中支持的 DOS 设备语法，请参阅 [ Windows 系统中的文件路径格式](file-path-formats.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-113">For path naming conventions and the ways to express a file path for Windows systems, including with the DOS device syntax supported in .NET Core 1.1 and later and the .NET Framework 4.6.2 and later, see [File path formats on Windows systems](file-path-formats.md).</span></span> 
  
 <span data-ttu-id="7554a-114">下面是一些常用的文件和目录类：</span><span class="sxs-lookup"><span data-stu-id="7554a-114">Here are some commonly used file and directory classes:</span></span>  
  
-   <span data-ttu-id="7554a-115"><xref:System.IO.File> - 提供用于创建、复制、删除、移动和打开文件的静态方法，并可帮助创建 <xref:System.IO.FileStream> 对象。</span><span class="sxs-lookup"><span data-stu-id="7554a-115"><xref:System.IO.File> - provides static methods for creating, copying, deleting, moving, and opening files, and helps create a <xref:System.IO.FileStream> object.</span></span>  
  
-   <span data-ttu-id="7554a-116"><xref:System.IO.FileInfo> - 提供用于创建、复制、删除、移动和打开文件的实例方法，并可帮助创建 <xref:System.IO.FileStream> 对象。</span><span class="sxs-lookup"><span data-stu-id="7554a-116"><xref:System.IO.FileInfo> - provides instance methods for creating, copying, deleting, moving, and opening files, and helps create a <xref:System.IO.FileStream> object.</span></span>  
  
-   <span data-ttu-id="7554a-117"><xref:System.IO.Directory> - 提供用于创建、移动和枚举目录和子目录的静态方法。</span><span class="sxs-lookup"><span data-stu-id="7554a-117"><xref:System.IO.Directory> - provides static methods for creating, moving, and enumerating through directories and subdirectories.</span></span>  
  
-   <span data-ttu-id="7554a-118"><xref:System.IO.DirectoryInfo> - 提供用于创建、移动和枚举目录和子目录的实例方法。</span><span class="sxs-lookup"><span data-stu-id="7554a-118"><xref:System.IO.DirectoryInfo> - provides instance methods for creating, moving, and enumerating through directories and subdirectories.</span></span>  
  
-   <span data-ttu-id="7554a-119"><xref:System.IO.Path> - 提供用于以跨平台的方式处理目录字符串的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="7554a-119"><xref:System.IO.Path> - provides methods and properties for processing directory strings in a cross-platform manner.</span></span>  
  
 <span data-ttu-id="7554a-120">调用文件系统方法时，应始终提供强大的异常处理。</span><span class="sxs-lookup"><span data-stu-id="7554a-120">You should always provide robust exception handling when calling filesystem methods.</span></span> <span data-ttu-id="7554a-121">有关更多信息，请参阅[处理 I/O 错误异常](handling-io-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-121">For more information, see [Handling I/O errors](handling-io-errors.md).</span></span>
 
 <span data-ttu-id="7554a-122">除了使用这些类之外，Visual Basic 用户还可以对文件 I/O 使用 <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=nameWithType> 类提供的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="7554a-122">In addition to using these classes, Visual Basic users can use the methods and properties provided by the <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=nameWithType> class for file I/O.</span></span>  
  
 <span data-ttu-id="7554a-123">请参阅[如何：复制目录](../../../docs/standard/io/how-to-copy-directories.md)、[如何：创建目录列表](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)和[如何：枚举目录和文件](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-123">See [How to: Copy Directories](../../../docs/standard/io/how-to-copy-directories.md), [How to: Create a Directory Listing](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69), and [How to: Enumerate Directories and Files](../../../docs/standard/io/how-to-enumerate-directories-and-files.md).</span></span>  
  
## <a name="streams"></a><span data-ttu-id="7554a-124">流</span><span class="sxs-lookup"><span data-stu-id="7554a-124">Streams</span></span>  
 <span data-ttu-id="7554a-125">抽象基类 <xref:System.IO.Stream> 支持读取和写入字节。</span><span class="sxs-lookup"><span data-stu-id="7554a-125">The abstract base class <xref:System.IO.Stream> supports reading and writing bytes.</span></span> <span data-ttu-id="7554a-126">所有表示流的类都继承自 <xref:System.IO.Stream> 类。</span><span class="sxs-lookup"><span data-stu-id="7554a-126">All classes that represent streams inherit from the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="7554a-127"><xref:System.IO.Stream> 类及其派生类提供数据源和存储库的常见视图，使程序员不必了解操作系统和基础设备的具体细节。</span><span class="sxs-lookup"><span data-stu-id="7554a-127">The <xref:System.IO.Stream> class and its derived classes provide a common view of data sources and repositories, and isolate the programmer from the specific details of the operating system and underlying devices.</span></span>  
  
 <span data-ttu-id="7554a-128">流涉及三个基本操作：</span><span class="sxs-lookup"><span data-stu-id="7554a-128">Streams involve three fundamental operations:</span></span>  
  
-   <span data-ttu-id="7554a-129">读取 - 将数据从流传输到数据结构（如字节数组）中。</span><span class="sxs-lookup"><span data-stu-id="7554a-129">Reading - transferring data from a stream into a data structure, such as an array of bytes.</span></span>  
  
-   <span data-ttu-id="7554a-130">写入 - 将数据从数据源传输到流。</span><span class="sxs-lookup"><span data-stu-id="7554a-130">Writing - transferring data to a stream from a data source.</span></span>  
  
-   <span data-ttu-id="7554a-131">查找 - 对流中的当前位置进行查询和修改。</span><span class="sxs-lookup"><span data-stu-id="7554a-131">Seeking - querying and modifying the current position within a stream.</span></span>  
  
 <span data-ttu-id="7554a-132">根据基础数据源或存储库，流可能只支持这些功能中的一部分。</span><span class="sxs-lookup"><span data-stu-id="7554a-132">Depending on the underlying data source or repository, a stream might support only some of these capabilities.</span></span> <span data-ttu-id="7554a-133">例如，<xref:System.IO.Pipes.PipeStream> 类不支持查找。</span><span class="sxs-lookup"><span data-stu-id="7554a-133">For example, the <xref:System.IO.Pipes.PipeStream> class does not support seeking.</span></span> <span data-ttu-id="7554a-134">流的 <xref:System.IO.Stream.CanRead%2A>、<xref:System.IO.Stream.CanWrite%2A> 和 <xref:System.IO.Stream.CanSeek%2A> 属性指定流支持的操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-134">The <xref:System.IO.Stream.CanRead%2A>, <xref:System.IO.Stream.CanWrite%2A>, and <xref:System.IO.Stream.CanSeek%2A> properties of a stream specify the operations that the stream supports.</span></span>  
  
 <span data-ttu-id="7554a-135">下面是一些常用的流类：</span><span class="sxs-lookup"><span data-stu-id="7554a-135">Here are some commonly used stream classes:</span></span>  
  
-   <span data-ttu-id="7554a-136"><xref:System.IO.FileStream> - 用于对文件进行读取和写入操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-136"><xref:System.IO.FileStream> – for reading and writing to a file.</span></span>  
  
-   <span data-ttu-id="7554a-137"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> - 用于对独立存储中的文件进行读取或写入操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-137"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> – for reading and writing to a file in isolated storage.</span></span>  
  
-   <span data-ttu-id="7554a-138"><xref:System.IO.MemoryStream> - 用于作为后备存储对内存进行读取和写入操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-138"><xref:System.IO.MemoryStream> – for reading and writing to memory as the backing store.</span></span>  
  
-   <span data-ttu-id="7554a-139"><xref:System.IO.BufferedStream> - 用于改进读取和写入操作的性能。</span><span class="sxs-lookup"><span data-stu-id="7554a-139"><xref:System.IO.BufferedStream> – for improving performance of read and write operations.</span></span>  
  
-   <span data-ttu-id="7554a-140"><xref:System.Net.Sockets.NetworkStream> - 用于通过网络套接字进行读取和写入。</span><span class="sxs-lookup"><span data-stu-id="7554a-140"><xref:System.Net.Sockets.NetworkStream> – for reading and writing over network sockets.</span></span>  
  
-   <span data-ttu-id="7554a-141"><xref:System.IO.Pipes.PipeStream> - 用于通过匿名和命名管道进行读取和写入。</span><span class="sxs-lookup"><span data-stu-id="7554a-141"><xref:System.IO.Pipes.PipeStream> – for reading and writing over anonymous and named pipes.</span></span>  
  
-   <span data-ttu-id="7554a-142"><xref:System.Security.Cryptography.CryptoStream> - 用于将数据流链接到加密转换。</span><span class="sxs-lookup"><span data-stu-id="7554a-142"><xref:System.Security.Cryptography.CryptoStream> – for linking data streams to cryptographic transformations.</span></span>  
  
 <span data-ttu-id="7554a-143">有关异步使用流的示例，请参阅[异步文件 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-143">For an example of working with streams asynchronously, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="readers-and-writers"></a><span data-ttu-id="7554a-144">读取器和编写器</span><span class="sxs-lookup"><span data-stu-id="7554a-144">Readers and Writers</span></span>  
 <span data-ttu-id="7554a-145"><xref:System.IO?displayProperty=nameWithType> 命名空间还提供用于在流中读取和写入已编码字符的类型。</span><span class="sxs-lookup"><span data-stu-id="7554a-145">The <xref:System.IO?displayProperty=nameWithType> namespace also provides types for reading encoded characters from streams and writing them to streams.</span></span> <span data-ttu-id="7554a-146">通常，流用于字节输入和输出。</span><span class="sxs-lookup"><span data-stu-id="7554a-146">Typically, streams are designed for byte input and output.</span></span> <span data-ttu-id="7554a-147">读取器和编写器类型处理编码字符与字节之间的来回转换，以便流可以完成操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-147">The reader and writer types handle the conversion of the encoded characters to and from bytes so the stream can complete the operation.</span></span> <span data-ttu-id="7554a-148">每个读取器和编写器类都与流关联，可以通过类的 `BaseStream` 属性进行检索。</span><span class="sxs-lookup"><span data-stu-id="7554a-148">Each reader and writer class is associated with a stream, which can be retrieved through the class's `BaseStream` property.</span></span>  
  
 <span data-ttu-id="7554a-149">下面是一些常用的读取器和编写器类：</span><span class="sxs-lookup"><span data-stu-id="7554a-149">Here are some commonly used reader and writer classes:</span></span>  
  
-   <span data-ttu-id="7554a-150"><xref:System.IO.BinaryReader> 和 <xref:System.IO.BinaryWriter> - 用于将基元数据类型作为二进制值进行读取和写入。</span><span class="sxs-lookup"><span data-stu-id="7554a-150"><xref:System.IO.BinaryReader> and <xref:System.IO.BinaryWriter> – for reading and writing primitive data types as binary values.</span></span>  
  
-   <span data-ttu-id="7554a-151"><xref:System.IO.StreamReader> 和 <xref:System.IO.StreamWriter> - 用于通过使用编码值在字符和字节之间来回转换来读取和写入字符。</span><span class="sxs-lookup"><span data-stu-id="7554a-151"><xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> – for reading and writing characters by using an encoding value to convert the characters to and from bytes.</span></span>  
  
-   <span data-ttu-id="7554a-152"><xref:System.IO.StringReader> 和 <xref:System.IO.StringWriter> - 用于从字符串读取字符以及将字符写入字符串中。</span><span class="sxs-lookup"><span data-stu-id="7554a-152"><xref:System.IO.StringReader> and <xref:System.IO.StringWriter> – for reading and writing characters to and from strings.</span></span>  
  
-   <span data-ttu-id="7554a-153"><xref:System.IO.TextReader> 和 <xref:System.IO.TextWriter> - 用作其他读取器和编写器（读取和写入字符和字符串，而不是二进制数据）的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="7554a-153"><xref:System.IO.TextReader> and <xref:System.IO.TextWriter> – serve as the abstract base classes for other readers and writers that read and write characters and strings, but not binary data.</span></span>  
  
 <span data-ttu-id="7554a-154">请参阅[如何：从文件读取文本](../../../docs/standard/io/how-to-read-text-from-a-file.md)、[如何：向文件写入文本](../../../docs/standard/io/how-to-write-text-to-a-file.md)、[如何：从字符串中读取字符](../../../docs/standard/io/how-to-read-characters-from-a-string.md)和[如何：向字符串写入字符](../../../docs/standard/io/how-to-write-characters-to-a-string.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-154">See [How to: Read Text from a File](../../../docs/standard/io/how-to-read-text-from-a-file.md), [How to: Write Text to a File](../../../docs/standard/io/how-to-write-text-to-a-file.md), [How to: Read Characters from a String](../../../docs/standard/io/how-to-read-characters-from-a-string.md), and [How to: Write Characters to a String](../../../docs/standard/io/how-to-write-characters-to-a-string.md).</span></span>  
  
## <a name="asynchronous-io-operations"></a><span data-ttu-id="7554a-155">异步 I/O 操作</span><span class="sxs-lookup"><span data-stu-id="7554a-155">Asynchronous I/O Operations</span></span>  
 <span data-ttu-id="7554a-156">读取或写入大量数据会占用大量资源。</span><span class="sxs-lookup"><span data-stu-id="7554a-156">Reading or writing a large amount of data can be resource-intensive.</span></span> <span data-ttu-id="7554a-157">如果你的应用程序需要保持对用户的响应性，则你应异步执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="7554a-157">You should perform these tasks asynchronously if your application needs to remain responsive to the user.</span></span> <span data-ttu-id="7554a-158">在执行同步 I/O 操作时，UI 线程将受阻，直至完成占用大量资源的操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-158">With synchronous I/O operations, the UI thread is blocked until the resource-intensive operation has completed.</span></span>  <span data-ttu-id="7554a-159">在开发 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用时使用异步 I/O 操作可防止造成应用程序已停止工作的印象。</span><span class="sxs-lookup"><span data-stu-id="7554a-159">Use asynchronous I/O operations when developing [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps to prevent creating the impression that your app has stopped working.</span></span>  
  
 <span data-ttu-id="7554a-160">异步成员在其名称中包含 `Async`，如 <xref:System.IO.Stream.CopyToAsync%2A>、<xref:System.IO.Stream.FlushAsync%2A>、<xref:System.IO.Stream.ReadAsync%2A> 和 <xref:System.IO.Stream.WriteAsync%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7554a-160">The asynchronous members contain `Async` in their names, such as the <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>,  <xref:System.IO.Stream.ReadAsync%2A>, and <xref:System.IO.Stream.WriteAsync%2A> methods.</span></span> <span data-ttu-id="7554a-161">你可以将这些方法与 `async` 和 `await` 关键字一起使用。</span><span class="sxs-lookup"><span data-stu-id="7554a-161">You use these methods with the `async` and `await` keywords.</span></span>  
  
 <span data-ttu-id="7554a-162">有关详细信息，请参阅[异步文件 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-162">For more information, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="compression"></a><span data-ttu-id="7554a-163">压缩</span><span class="sxs-lookup"><span data-stu-id="7554a-163">Compression</span></span>  
 <span data-ttu-id="7554a-164">压缩是指减小文件大小以便存储的过程。</span><span class="sxs-lookup"><span data-stu-id="7554a-164">Compression refers to the process of reducing the size of a file for storage.</span></span> <span data-ttu-id="7554a-165">解压缩是提取压缩文件的内容以使这些内容采用可用格式的过程。</span><span class="sxs-lookup"><span data-stu-id="7554a-165">Decompression is the process of extracting the contents of a compressed file so they are in a usable format.</span></span> <span data-ttu-id="7554a-166"><xref:System.IO.Compression?displayProperty=nameWithType> 命名空间包含用于对文件和流进行压缩或解压缩的类型。</span><span class="sxs-lookup"><span data-stu-id="7554a-166">The <xref:System.IO.Compression?displayProperty=nameWithType> namespace contains types for compressing and decompressing files and streams.</span></span>  
  
 <span data-ttu-id="7554a-167">在对文件和流进行压缩和解压缩时，经常使用以下类：</span><span class="sxs-lookup"><span data-stu-id="7554a-167">The following classes are frequently used when compressing and decompressing files and streams:</span></span>  
  
-   <span data-ttu-id="7554a-168"><xref:System.IO.Compression.ZipArchive> - 用于在 zip 存档中创建和检索条目。</span><span class="sxs-lookup"><span data-stu-id="7554a-168"><xref:System.IO.Compression.ZipArchive> – for creating and retrieving entries in the zip archive.</span></span>  
  
-   <span data-ttu-id="7554a-169"><xref:System.IO.Compression.ZipArchiveEntry> - 用于表示压缩文件。</span><span class="sxs-lookup"><span data-stu-id="7554a-169"><xref:System.IO.Compression.ZipArchiveEntry> – for representing a compressed file.</span></span>  
  
-   <span data-ttu-id="7554a-170"><xref:System.IO.Compression.ZipFile> - 用于创建、提取和打开压缩包。</span><span class="sxs-lookup"><span data-stu-id="7554a-170"><xref:System.IO.Compression.ZipFile> – for creating,  extracting, and opening a compressed package.</span></span>  
  
-   <span data-ttu-id="7554a-171"><xref:System.IO.Compression.ZipFileExtensions> - 用于创建和提供压缩包中的条目。</span><span class="sxs-lookup"><span data-stu-id="7554a-171"><xref:System.IO.Compression.ZipFileExtensions> – for creating and extracting entries in a compressed package.</span></span>  
  
-   <span data-ttu-id="7554a-172"><xref:System.IO.Compression.DeflateStream> - 用于使用 Deflate 算法对流进行压缩和解压缩。</span><span class="sxs-lookup"><span data-stu-id="7554a-172"><xref:System.IO.Compression.DeflateStream> – for compressing and decompressing streams using the Deflate algorithm.</span></span>  
  
-   <span data-ttu-id="7554a-173"><xref:System.IO.Compression.GZipStream> - 用于采用 gzip 数据格式对流进行压缩和解压缩。</span><span class="sxs-lookup"><span data-stu-id="7554a-173"><xref:System.IO.Compression.GZipStream> – for compressing and decompressing streams in gzip data format.</span></span>  
  
 <span data-ttu-id="7554a-174">请参阅[如何：压缩和提取文件](../../../docs/standard/io/how-to-compress-and-extract-files.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-174">See [How to: Compress and Extract Files](../../../docs/standard/io/how-to-compress-and-extract-files.md).</span></span>  
  
## <a name="isolated-storage"></a><span data-ttu-id="7554a-175">独立存储</span><span class="sxs-lookup"><span data-stu-id="7554a-175">Isolated Storage</span></span>  
 <span data-ttu-id="7554a-176">独立存储是一种数据存储机制，它在代码与保存的数据之间定义了标准化的关联方式，从而提供隔离性和安全性。</span><span class="sxs-lookup"><span data-stu-id="7554a-176">Isolated storage is a data storage mechanism that provides isolation and safety by defining standardized ways of associating code with saved data.</span></span> <span data-ttu-id="7554a-177">存储提供按用户、程序集和（可选）域隔离的虚拟文件系统。</span><span class="sxs-lookup"><span data-stu-id="7554a-177">The storage provides a virtual file system that is isolated by user, assembly, and (optionally) domain.</span></span> <span data-ttu-id="7554a-178">当你的应用程序无权访问用户文件时，独立存储特别有用。</span><span class="sxs-lookup"><span data-stu-id="7554a-178">Isolated storage is particularly useful when your application does not have permission to access user files.</span></span> <span data-ttu-id="7554a-179">你可以通过一种由计算机的安全策略控制的方式保存应用程序的设置或文件。</span><span class="sxs-lookup"><span data-stu-id="7554a-179">You can save settings or files for your application in a manner that is controlled by the computer's security policy.</span></span>  
  
 <span data-ttu-id="7554a-180">独立存储不可用于 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用；请改用 <xref:Windows.Storage?displayProperty=nameWithType> 命名空间中的应用程序数据类。</span><span class="sxs-lookup"><span data-stu-id="7554a-180">Isolated storage is not available for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps; instead, use application data classes in the <xref:Windows.Storage?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="7554a-181">有关详细信息，请参阅[应用程序数据](https://docs.microsoft.com/previous-versions/windows/apps/hh464917%28v=win.10%29)。</span><span class="sxs-lookup"><span data-stu-id="7554a-181">For more information, see [Application data](https://docs.microsoft.com/previous-versions/windows/apps/hh464917%28v=win.10%29).</span></span>  
  
 <span data-ttu-id="7554a-182">在实现独立存储时，经常使用以下类：</span><span class="sxs-lookup"><span data-stu-id="7554a-182">The following classes are frequently used when implementing isolated storage:</span></span>  
  
-   <span data-ttu-id="7554a-183"><xref:System.IO.IsolatedStorage.IsolatedStorage> - 提供用于独立存储实现的基类。</span><span class="sxs-lookup"><span data-stu-id="7554a-183"><xref:System.IO.IsolatedStorage.IsolatedStorage> – provides the base class for isolated storage implementations.</span></span>  
  
-   <span data-ttu-id="7554a-184"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> - 提供包含文件和目录的独立存储区。</span><span class="sxs-lookup"><span data-stu-id="7554a-184"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> – provides an isolated storage area that contains files and directories.</span></span>  
  
-   <span data-ttu-id="7554a-185"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> - 公开独立存储中的文件。</span><span class="sxs-lookup"><span data-stu-id="7554a-185"><xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> - exposes a file within isolated storage.</span></span>  
  
 <span data-ttu-id="7554a-186">请参阅[独立存储](../../../docs/standard/io/isolated-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-186">See [Isolated Storage](../../../docs/standard/io/isolated-storage.md).</span></span>  
  
## <a name="io-operations-in-windows-store-apps"></a><span data-ttu-id="7554a-187">Windows 应用商店应用程序中的 I/O 操作</span><span class="sxs-lookup"><span data-stu-id="7554a-187">I/O Operations in Windows Store apps</span></span>  
 <span data-ttu-id="7554a-188">[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 包含许多用于对流进行读取和写入操作的类型；但是，该集不包含所有的 .NET Framework I/O 类型。</span><span class="sxs-lookup"><span data-stu-id="7554a-188">The [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] contains many of the types for reading from and writing to streams; however, this set does not include all the .NET Framework I/O types.</span></span>  
  
 <span data-ttu-id="7554a-189">在 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用中使用 I/O 操作时，要注意一些重要差异：</span><span class="sxs-lookup"><span data-stu-id="7554a-189">Some important differences to note when using I/O operations in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps:</span></span>  
  
-   <span data-ttu-id="7554a-190">专门与文件操作相关的类型（如 <xref:System.IO.File>、<xref:System.IO.FileInfo>、<xref:System.IO.Directory> 和 <xref:System.IO.DirectoryInfo>）未包含在[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 中。</span><span class="sxs-lookup"><span data-stu-id="7554a-190">Types specifically related to file operations, such as <xref:System.IO.File>, <xref:System.IO.FileInfo>, <xref:System.IO.Directory> and <xref:System.IO.DirectoryInfo>, are not included in the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)].</span></span> <span data-ttu-id="7554a-191">请改用 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 的 <xref:Windows.Storage?displayProperty=nameWithType> 命名空间中的类型（如 <xref:Windows.Storage.StorageFile> 和 <xref:Windows.Storage.StorageFolder>）。</span><span class="sxs-lookup"><span data-stu-id="7554a-191">Instead, use the types in the <xref:Windows.Storage?displayProperty=nameWithType> namespace of the [!INCLUDE[wrt](../../../includes/wrt-md.md)], such as <xref:Windows.Storage.StorageFile> and <xref:Windows.Storage.StorageFolder>.</span></span>  
  
-   <span data-ttu-id="7554a-192">独立存储不可用；请改用[应用程序数据](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10))。</span><span class="sxs-lookup"><span data-stu-id="7554a-192">Isolated storage is not available; instead, use [application data](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10)).</span></span>  
  
-   <span data-ttu-id="7554a-193">使用异步方法（如 <xref:System.IO.Stream.ReadAsync%2A> 和 <xref:System.IO.Stream.WriteAsync%2A>）可防止 UI 线程受阻。</span><span class="sxs-lookup"><span data-stu-id="7554a-193">Use asynchronous methods, such as <xref:System.IO.Stream.ReadAsync%2A> and <xref:System.IO.Stream.WriteAsync%2A>, to prevent blocking the UI thread.</span></span>  
  
-   <span data-ttu-id="7554a-194">基于路径的压缩类型 <xref:System.IO.Compression.ZipFile> 和 <xref:System.IO.Compression.ZipFileExtensions> 不可用。</span><span class="sxs-lookup"><span data-stu-id="7554a-194">The path-based compression types <xref:System.IO.Compression.ZipFile> and <xref:System.IO.Compression.ZipFileExtensions> are not available.</span></span> <span data-ttu-id="7554a-195">请改用 <xref:Windows.Storage.Compression?displayProperty=nameWithType> 命名空间中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="7554a-195">Instead, use the types in the <xref:Windows.Storage.Compression?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="7554a-196">如果需要，你可以在 .NET Framework 流和 Windows 运行时流之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="7554a-196">You can convert between .NET Framework streams and Windows Runtime streams, if necessary.</span></span> <span data-ttu-id="7554a-197">有关详细信息，请参阅[如何：在 .NET Framework 流和 Windows 运行时流之间进行转换](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)或 [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7554a-197">For more information, see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md) or [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx).</span></span> <!--zz TODO: <xref:System.IO.WindowsRuntimeStreamExtensions>--> 
  
 <span data-ttu-id="7554a-198">若要深入了解 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用中的 I/O 操作，请参阅[快速入门：读取和写入文件](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10))。</span><span class="sxs-lookup"><span data-stu-id="7554a-198">For more information about I/O operations in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span>  
  
## <a name="io-and-security"></a><span data-ttu-id="7554a-199">I/O 和安全性</span><span class="sxs-lookup"><span data-stu-id="7554a-199">I/O and Security</span></span>  
 <span data-ttu-id="7554a-200">在使用 <xref:System.IO?displayProperty=nameWithType> 命名空间中的类时，你必须遵循操作系统安全性要求（如访问控制列表 (ACL)）来控制对文件和目录的访问。</span><span class="sxs-lookup"><span data-stu-id="7554a-200">When you use the classes in the <xref:System.IO?displayProperty=nameWithType> namespace, you must follow operating system security requirements such as access control lists (ACLs) to control access to files and directories.</span></span> <span data-ttu-id="7554a-201">此要求是在所有 <xref:System.Security.Permissions.FileIOPermission> 要求之外的要求。</span><span class="sxs-lookup"><span data-stu-id="7554a-201">This requirement is in addition to any <xref:System.Security.Permissions.FileIOPermission> requirements.</span></span> <span data-ttu-id="7554a-202">可以用编程方式管理 ACL。</span><span class="sxs-lookup"><span data-stu-id="7554a-202">You can manage ACLs programmatically.</span></span> <span data-ttu-id="7554a-203">有关详细信息，请参阅[如何：添加或移除访问控制列表项](../../../docs/standard/io/how-to-add-or-remove-access-control-list-entries.md)。</span><span class="sxs-lookup"><span data-stu-id="7554a-203">For more information, see [How to: Add or Remove Access Control List Entries](../../../docs/standard/io/how-to-add-or-remove-access-control-list-entries.md).</span></span>  
  
 <span data-ttu-id="7554a-204">默认安全策略将阻止 Internet 或 Intranet 应用程序访问用户计算机上的文件。</span><span class="sxs-lookup"><span data-stu-id="7554a-204">Default security policies prevent Internet or intranet applications from accessing files on the user’s computer.</span></span> <span data-ttu-id="7554a-205">因此，在编写将通过 Internet 或 Intranet 下载的代码时，请不要使用需要物理文件路径的 I/O 类。</span><span class="sxs-lookup"><span data-stu-id="7554a-205">Therefore, do not use the I/O classes that require a path to a physical file when writing code that will be downloaded over the Internet or intranet.</span></span> <span data-ttu-id="7554a-206">请转而将[独立存储](../../../docs/standard/io/isolated-storage.md)用于传统 .NET Framework 应用程序，或将[应用程序数据](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10))用于 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用。</span><span class="sxs-lookup"><span data-stu-id="7554a-206">Instead, use [isolated storage](../../../docs/standard/io/isolated-storage.md) for traditional .NET Framework applications, or use [application data](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10)) for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 <span data-ttu-id="7554a-207">仅在构造流时执行安全性检查。</span><span class="sxs-lookup"><span data-stu-id="7554a-207">A security check is performed only when the stream is constructed.</span></span> <span data-ttu-id="7554a-208">因此，请不要打开流并将其传递给受信程度较低的代码或应用程序域。</span><span class="sxs-lookup"><span data-stu-id="7554a-208">Therefore, do not open a stream and then pass it to less-trusted code or application domains.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="7554a-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="7554a-209">Related Topics</span></span>  
  
-   [<span data-ttu-id="7554a-210">通用 I/O 任务</span><span class="sxs-lookup"><span data-stu-id="7554a-210">Common I/O Tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)  
  
 <span data-ttu-id="7554a-211">提供与文件、目录和流关联的 I/O 任务的列表以及指向每个任务的相关内容和示例的链接。</span><span class="sxs-lookup"><span data-stu-id="7554a-211">Provides a list of I/O tasks associated with files, directories, and streams, and links to relevant content and examples for each task.</span></span>  
  
-   [<span data-ttu-id="7554a-212">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="7554a-212">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
  
 <span data-ttu-id="7554a-213">描述异步 I/O 的性能优势和基本操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-213">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
-   [<span data-ttu-id="7554a-214">独立存储</span><span class="sxs-lookup"><span data-stu-id="7554a-214">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
  
 <span data-ttu-id="7554a-215">描述一种数据存储机制，该机制通过定义标准的代码与保存数据的关联方式来提供隔离和安全性。</span><span class="sxs-lookup"><span data-stu-id="7554a-215">Describes a data storage mechanism that provides isolation and safety by defining standardized ways of associating code with saved data.</span></span>  
  
-   [<span data-ttu-id="7554a-216">管道</span><span class="sxs-lookup"><span data-stu-id="7554a-216">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
  
 <span data-ttu-id="7554a-217">描述 .NET Framework 中的匿名和命名管道操作。</span><span class="sxs-lookup"><span data-stu-id="7554a-217">Describes anonymous and named pipe operations in the .NET Framework.</span></span>  
  
-   [<span data-ttu-id="7554a-218">内存映射文件</span><span class="sxs-lookup"><span data-stu-id="7554a-218">Memory-Mapped Files</span></span>](../../../docs/standard/io/memory-mapped-files.md)  
  
 <span data-ttu-id="7554a-219">描述内存映射文件，这些文件包含虚拟内存中磁盘上文件的内容。</span><span class="sxs-lookup"><span data-stu-id="7554a-219">Describes memory-mapped files, which contain the contents of files on disk in virtual memory.</span></span> <span data-ttu-id="7554a-220">可以使用内存映射文件编辑非常大的文件和创建共享内存以进行进程间通信。</span><span class="sxs-lookup"><span data-stu-id="7554a-220">You can use memory-mapped files to edit very large files and to create shared memory for interprocess communication.</span></span>
