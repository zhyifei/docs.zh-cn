---
title: "内存映射文件"
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
- memory-mapped files
- inter-process communiation
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2602d431aada7b3e0ee226eed319903492022ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="memory-mapped-files"></a><span data-ttu-id="c9483-102">内存映射文件</span><span class="sxs-lookup"><span data-stu-id="c9483-102">Memory-Mapped Files</span></span>
<span data-ttu-id="c9483-103">内存映射文件包含虚拟内存中文件的内容。</span><span class="sxs-lookup"><span data-stu-id="c9483-103">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="c9483-104">文件和内存空间之间的此映射可让应用程序，包括多个进程，读取和写入到内存中的直接修改的文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-104">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="c9483-105">从开始[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，你可以使用托管的代码与本机 Windows 函数访问内存映射文件相同的方式访问内存映射文件中所述[Managing Memory-Mapped 文件中 Win32](http://go.microsoft.com/fwlink/?linkid=180801)。</span><span class="sxs-lookup"><span data-stu-id="c9483-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files in Win32](http://go.microsoft.com/fwlink/?linkid=180801).</span></span>  
  
 <span data-ttu-id="c9483-106">有两种类型的内存映射文件：</span><span class="sxs-lookup"><span data-stu-id="c9483-106">There are two types of memory-mapped files:</span></span>  
  
-   <span data-ttu-id="c9483-107">持久的内存映射文件</span><span class="sxs-lookup"><span data-stu-id="c9483-107">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="c9483-108">持久化的文件是与磁盘上的源文件相关联的内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-108">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="c9483-109">最后一个过程与文件完成后工作，数据保存到磁盘上的源文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-109">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="c9483-110">这些内存映射文件都适用于使用极大的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-110">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
-   <span data-ttu-id="c9483-111">非持久内存映射文件</span><span class="sxs-lookup"><span data-stu-id="c9483-111">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="c9483-112">非持久化文件是不与磁盘上的文件相关联的内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-112">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="c9483-113">当最后一个进程已完成与文件的工作时，数据将丢失并且垃圾回收功能回收此文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-113">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="c9483-114">这些文件是适用于创建共享的内存用于进程间通信 (IPC)。</span><span class="sxs-lookup"><span data-stu-id="c9483-114">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="c9483-115">过程、 视图和管理内存</span><span class="sxs-lookup"><span data-stu-id="c9483-115">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="c9483-116">可以在多个进程之间共享内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-116">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="c9483-117">通过使用由创建该文件的进程分配的公用名情况下，进程可以映射到同一个内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-117">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="c9483-118">若要使用的内存映射文件，必须创建整个内存映射文件或它的一部分的视图。</span><span class="sxs-lookup"><span data-stu-id="c9483-118">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="c9483-119">此外可以创建多个视图相同部件的内存映射文件中，从而创建并发的内存。</span><span class="sxs-lookup"><span data-stu-id="c9483-119">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="c9483-120">对于保持并发的两个视图，他们必须创建从同一个内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-120">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="c9483-121">多个视图也可能有必要，如果该文件大于内存映射 (32 位计算机上的 2 GB) 的应用程序的逻辑的内存空间的大小。</span><span class="sxs-lookup"><span data-stu-id="c9483-121">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="c9483-122">有两种类型的视图： 流访问视图和随机访问视图。</span><span class="sxs-lookup"><span data-stu-id="c9483-122">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="c9483-123">使用顺序访问文件; 流访问视图非持久化文件和 IPC 建议这样做。</span><span class="sxs-lookup"><span data-stu-id="c9483-123">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="c9483-124">随机访问视图是使用持久文件的首选方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-124">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="c9483-125">内存映射文件访问通过操作系统的内存管理器，以便该文件是自动分成多个页面数并在必要时访问。</span><span class="sxs-lookup"><span data-stu-id="c9483-125">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="c9483-126">无需自己处理内存管理。</span><span class="sxs-lookup"><span data-stu-id="c9483-126">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="c9483-127">下图显示了如何将多个进程可以具有多个并创建在同一时间重叠到相同的内存映射文件视图。</span><span class="sxs-lookup"><span data-stu-id="c9483-127">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>  
  
 <span data-ttu-id="c9483-128">![显示视图授予了内存 &#45; 映射的文件。] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span><span class="sxs-lookup"><span data-stu-id="c9483-128">![Shows views to a memory&#45;mapped file.](../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span></span>  
<span data-ttu-id="c9483-129">多个和重叠的内存映射文件视图</span><span class="sxs-lookup"><span data-stu-id="c9483-129">Multiple and overlapped views to a memory-mapped file</span></span>  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="c9483-130">使用内存映射文件编程</span><span class="sxs-lookup"><span data-stu-id="c9483-130">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="c9483-131">下表提供了有关使用内存映射文件对象和其成员的指南。</span><span class="sxs-lookup"><span data-stu-id="c9483-131">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="c9483-132">任务</span><span class="sxs-lookup"><span data-stu-id="c9483-132">Task</span></span>|<span data-ttu-id="c9483-133">方法或要使用的属性</span><span class="sxs-lookup"><span data-stu-id="c9483-133">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="c9483-134">若要获取<xref:System.IO.MemoryMappedFiles.MemoryMappedFile>表示持久化的内存映射文件从磁盘上的文件的对象。</span><span class="sxs-lookup"><span data-stu-id="c9483-134">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="c9483-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="c9483-136">若要获取<xref:System.IO.MemoryMappedFiles.MemoryMappedFile>表示的非持久化内存映射文件 （不使用磁盘上的文件相关联） 的对象。</span><span class="sxs-lookup"><span data-stu-id="c9483-136">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="c9483-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="c9483-138">- 或 -</span><span class="sxs-lookup"><span data-stu-id="c9483-138">- or -</span></span><br /><br /> <span data-ttu-id="c9483-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="c9483-140">若要获取<xref:System.IO.MemoryMappedFiles.MemoryMappedFile>的现有内存映射文件 （持久化或非持久化） 的对象。</span><span class="sxs-lookup"><span data-stu-id="c9483-140">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="c9483-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="c9483-142">若要获取<xref:System.IO.UnmanagedMemoryStream>给内存映射文件的顺序访问视图的对象。</span><span class="sxs-lookup"><span data-stu-id="c9483-142">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="c9483-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="c9483-144">若要获取<xref:System.IO.UnmanagedMemoryAccessor>对象到内存映射的随机访问视图个。</span><span class="sxs-lookup"><span data-stu-id="c9483-144">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="c9483-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="c9483-146">若要获取<xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle>对象，用于与非托管代码。</span><span class="sxs-lookup"><span data-stu-id="c9483-146">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="c9483-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="c9483-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="c9483-148">- 或 -</span><span class="sxs-lookup"><span data-stu-id="c9483-148">- or -</span></span><br /><br /> <span data-ttu-id="c9483-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="c9483-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="c9483-150">- 或 -</span><span class="sxs-lookup"><span data-stu-id="c9483-150">- or -</span></span><br /><br /> <span data-ttu-id="c9483-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="c9483-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="c9483-152">若要内存分配推迟到一个视图被创建 （仅非持久化文件）。</span><span class="sxs-lookup"><span data-stu-id="c9483-152">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="c9483-153">(若要确定当前系统页面大小，请使用<xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>属性。)</span><span class="sxs-lookup"><span data-stu-id="c9483-153">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="c9483-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>方法与<xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>值。</span><span class="sxs-lookup"><span data-stu-id="c9483-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="c9483-155">- 或 -</span><span class="sxs-lookup"><span data-stu-id="c9483-155">- or -</span></span><br /><br /> <span data-ttu-id="c9483-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>具有方法<xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions>枚举作为参数。</span><span class="sxs-lookup"><span data-stu-id="c9483-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="c9483-157">安全性</span><span class="sxs-lookup"><span data-stu-id="c9483-157">Security</span></span>  
 <span data-ttu-id="c9483-158">可以将访问权限的应用通过使用以下方法采用创建内存映射文件，<xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess>枚举作为参数：</span><span class="sxs-lookup"><span data-stu-id="c9483-158">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="c9483-159">你可以指定通过打开现有的内存映射文件的访问权限<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A>方法采用<xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights>作为参数。</span><span class="sxs-lookup"><span data-stu-id="c9483-159">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="c9483-160">此外，可以包括<xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>包含预定义的访问规则的对象。</span><span class="sxs-lookup"><span data-stu-id="c9483-160">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="c9483-161">若要将新的或更改的访问规则应用于一个内存映射文件，使用<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-161">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="c9483-162">若要检索访问权限或审核从现有的文件的规则，请使用<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c9483-162">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c9483-163">示例</span><span class="sxs-lookup"><span data-stu-id="c9483-163">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="c9483-164">持久的内存映射文件</span><span class="sxs-lookup"><span data-stu-id="c9483-164">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="c9483-165"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A>方法从磁盘上的现有文件创建一个内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-165">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="c9483-166">下面的示例创建一个极大的文件的一部分的内存映射视图和操作它的一部分。</span><span class="sxs-lookup"><span data-stu-id="c9483-166">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 <span data-ttu-id="c9483-167">下面的示例打开另一个进程的同一个内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-167">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="c9483-168">非持久内存映射文件</span><span class="sxs-lookup"><span data-stu-id="c9483-168">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="c9483-169"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>和<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>方法创建一个不映射到现有文件在磁盘上的内存映射文件。</span><span class="sxs-lookup"><span data-stu-id="c9483-169">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="c9483-170">下面的示例由三个单独将布尔值写入到一个内存映射文件的进程 （控制台应用程序） 组成。</span><span class="sxs-lookup"><span data-stu-id="c9483-170">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="c9483-171">发生以下操作序列：</span><span class="sxs-lookup"><span data-stu-id="c9483-171">The following sequence of actions occur:</span></span>  
  
1.  <span data-ttu-id="c9483-172">`Process A`创建内存映射文件，并向其中写入一个值。</span><span class="sxs-lookup"><span data-stu-id="c9483-172">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2.  <span data-ttu-id="c9483-173">`Process B`打开内存映射文件，并向其中写入一个值。</span><span class="sxs-lookup"><span data-stu-id="c9483-173">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3.  <span data-ttu-id="c9483-174">`Process C`打开内存映射文件，并向其中写入一个值。</span><span class="sxs-lookup"><span data-stu-id="c9483-174">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4.  <span data-ttu-id="c9483-175">`Process A`读取并显示为内存映射文件中的值。</span><span class="sxs-lookup"><span data-stu-id="c9483-175">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5.  <span data-ttu-id="c9483-176">后`Process A`完成使用内存映射文件时，该文件立即回收垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c9483-176">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="c9483-177">若要运行此示例，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c9483-177">To run this example, do the following:</span></span>  
  
1.  <span data-ttu-id="c9483-178">编译应用程序并打开三个命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="c9483-178">Compile the applications and open three Command Prompt windows.</span></span>  
  
2.  <span data-ttu-id="c9483-179">在第一个命令提示符窗口中，运行`Process A`。</span><span class="sxs-lookup"><span data-stu-id="c9483-179">In the first Command Prompt window, run `Process A`.</span></span>  
  
3.  <span data-ttu-id="c9483-180">在第二个命令提示符窗口中，运行`Process B`。</span><span class="sxs-lookup"><span data-stu-id="c9483-180">In the second Command Prompt window, run `Process B`.</span></span>  
  
4.  <span data-ttu-id="c9483-181">返回到`Process A`，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="c9483-181">Return to `Process A` and press ENTER.</span></span>  
  
5.  <span data-ttu-id="c9483-182">在第三个命令提示符窗口中，运行`Process C`。</span><span class="sxs-lookup"><span data-stu-id="c9483-182">In the third Command Prompt window, run `Process C`.</span></span>  
  
6.  <span data-ttu-id="c9483-183">返回到`Process A`，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="c9483-183">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="c9483-184">输出`Process A`如下：</span><span class="sxs-lookup"><span data-stu-id="c9483-184">The output of `Process A` is as follows:</span></span>  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="c9483-185">**进程 A**</span><span class="sxs-lookup"><span data-stu-id="c9483-185">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="c9483-186">**进程 B**</span><span class="sxs-lookup"><span data-stu-id="c9483-186">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="c9483-187">**进程 C**</span><span class="sxs-lookup"><span data-stu-id="c9483-187">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c9483-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9483-188">See Also</span></span>  
 [<span data-ttu-id="c9483-189">文件和流 I-O</span><span class="sxs-lookup"><span data-stu-id="c9483-189">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
