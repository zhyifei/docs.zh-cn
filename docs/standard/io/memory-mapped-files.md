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
# <a name="memory-mapped-files"></a>内存映射文件
内存映射文件包含虚拟内存中文件的内容。 文件和内存空间之间的此映射可让应用程序，包括多个进程，读取和写入到内存中的直接修改的文件。 从开始[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，你可以使用托管的代码与本机 Windows 函数访问内存映射文件相同的方式访问内存映射文件中所述[Managing Memory-Mapped 文件中 Win32](http://go.microsoft.com/fwlink/?linkid=180801)。  
  
 有两种类型的内存映射文件：  
  
-   持久的内存映射文件  
  
     持久化的文件是与磁盘上的源文件相关联的内存映射文件。 最后一个过程与文件完成后工作，数据保存到磁盘上的源文件。 这些内存映射文件都适用于使用极大的源代码文件。  
  
-   非持久内存映射文件  
  
     非持久化文件是不与磁盘上的文件相关联的内存映射文件。 当最后一个进程已完成与文件的工作时，数据将丢失并且垃圾回收功能回收此文件。 这些文件是适用于创建共享的内存用于进程间通信 (IPC)。  
  
## <a name="processes-views-and-managing-memory"></a>过程、 视图和管理内存  
 可以在多个进程之间共享内存映射文件。 通过使用由创建该文件的进程分配的公用名情况下，进程可以映射到同一个内存映射文件。  
  
 若要使用的内存映射文件，必须创建整个内存映射文件或它的一部分的视图。 此外可以创建多个视图相同部件的内存映射文件中，从而创建并发的内存。 对于保持并发的两个视图，他们必须创建从同一个内存映射文件。  
  
 多个视图也可能有必要，如果该文件大于内存映射 (32 位计算机上的 2 GB) 的应用程序的逻辑的内存空间的大小。  
  
 有两种类型的视图： 流访问视图和随机访问视图。 使用顺序访问文件; 流访问视图非持久化文件和 IPC 建议这样做。 随机访问视图是使用持久文件的首选方法。  
  
 内存映射文件访问通过操作系统的内存管理器，以便该文件是自动分成多个页面数并在必要时访问。 无需自己处理内存管理。  
  
 下图显示了如何将多个进程可以具有多个并创建在同一时间重叠到相同的内存映射文件视图。  
  
 ![显示视图授予了内存 &#45; 映射的文件。] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")  
多个和重叠的内存映射文件视图  
  
## <a name="programming-with-memory-mapped-files"></a>使用内存映射文件编程  
 下表提供了有关使用内存映射文件对象和其成员的指南。  
  
|任务|方法或要使用的属性|  
|----------|----------------------------------|  
|若要获取<xref:System.IO.MemoryMappedFiles.MemoryMappedFile>表示持久化的内存映射文件从磁盘上的文件的对象。|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> 方法。|  
|若要获取<xref:System.IO.MemoryMappedFiles.MemoryMappedFile>表示的非持久化内存映射文件 （不使用磁盘上的文件相关联） 的对象。|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> 方法。<br /><br /> - 或 -<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> 方法。|  
|若要获取<xref:System.IO.MemoryMappedFiles.MemoryMappedFile>的现有内存映射文件 （持久化或非持久化） 的对象。|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> 方法。|  
|若要获取<xref:System.IO.UnmanagedMemoryStream>给内存映射文件的顺序访问视图的对象。|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> 方法。|  
|若要获取<xref:System.IO.UnmanagedMemoryAccessor>对象到内存映射的随机访问视图个。|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> 方法。|  
|若要获取<xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle>对象，用于与非托管代码。|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> 属性。<br /><br /> - 或 -<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 属性。<br /><br /> - 或 -<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 属性。|  
|若要内存分配推迟到一个视图被创建 （仅非持久化文件）。<br /><br /> (若要确定当前系统页面大小，请使用<xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>属性。)|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>方法与<xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>值。<br /><br /> - 或 -<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>具有方法<xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions>枚举作为参数。|  
  
### <a name="security"></a>安全性  
 可以将访问权限的应用通过使用以下方法采用创建内存映射文件，<xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess>枚举作为参数：  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 你可以指定通过打开现有的内存映射文件的访问权限<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A>方法采用<xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights>作为参数。  
  
 此外，可以包括<xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>包含预定义的访问规则的对象。  
  
 若要将新的或更改的访问规则应用于一个内存映射文件，使用<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>方法。 若要检索访问权限或审核从现有的文件的规则，请使用<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>方法。  
  
## <a name="examples"></a>示例  
  
### <a name="persisted-memory-mapped-files"></a>持久的内存映射文件  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A>方法从磁盘上的现有文件创建一个内存映射文件。  
  
 下面的示例创建一个极大的文件的一部分的内存映射视图和操作它的一部分。  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 下面的示例打开另一个进程的同一个内存映射文件。  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a>非持久内存映射文件  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>和<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>方法创建一个不映射到现有文件在磁盘上的内存映射文件。  
  
 下面的示例由三个单独将布尔值写入到一个内存映射文件的进程 （控制台应用程序） 组成。 发生以下操作序列：  
  
1.  `Process A`创建内存映射文件，并向其中写入一个值。  
  
2.  `Process B`打开内存映射文件，并向其中写入一个值。  
  
3.  `Process C`打开内存映射文件，并向其中写入一个值。  
  
4.  `Process A`读取并显示为内存映射文件中的值。  
  
5.  后`Process A`完成使用内存映射文件时，该文件立即回收垃圾回收。  
  
 若要运行此示例，请执行以下操作：  
  
1.  编译应用程序并打开三个命令提示符窗口。  
  
2.  在第一个命令提示符窗口中，运行`Process A`。  
  
3.  在第二个命令提示符窗口中，运行`Process B`。  
  
4.  返回到`Process A`，然后按 enter 键。  
  
5.  在第三个命令提示符窗口中，运行`Process C`。  
  
6.  返回到`Process A`，然后按 enter 键。  
  
 输出`Process A`如下：  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **进程 A**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **进程 B**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **进程 C**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [文件和流 I-O](../../../docs/standard/io/index.md)
