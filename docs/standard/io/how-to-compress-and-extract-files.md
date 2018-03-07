---
title: "如何：压缩和解压缩文件"
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
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33c9249692998aea8c22ddbf75a5a9b7bdf28708
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="25e88-102">如何：压缩和解压缩文件</span><span class="sxs-lookup"><span data-stu-id="25e88-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="25e88-103"><xref:System.IO.Compression> 命名空间包含以下类型来对文件和流进行压缩或解压缩。</span><span class="sxs-lookup"><span data-stu-id="25e88-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="25e88-104">还可以使用这些类型来读取和修改压缩文件的内容：</span><span class="sxs-lookup"><span data-stu-id="25e88-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="25e88-105">下面的示例演示当使用压缩文件时可以执行的某些功能。</span><span class="sxs-lookup"><span data-stu-id="25e88-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25e88-106">示例</span><span class="sxs-lookup"><span data-stu-id="25e88-106">Example</span></span>  
 <span data-ttu-id="25e88-107">此示例演示如何使用 <xref:System.IO.Compression.ZipFile> 类创建和提取文件扩展名为 .zip 的压缩文件。</span><span class="sxs-lookup"><span data-stu-id="25e88-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="25e88-108">它将文件夹的内容压缩为一个新 .zip 文件，然后将该内容提取到一个新文件夹。</span><span class="sxs-lookup"><span data-stu-id="25e88-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="25e88-109">若要使用 <xref:System.IO.Compression.ZipFile> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。</span><span class="sxs-lookup"><span data-stu-id="25e88-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="25e88-110">示例</span><span class="sxs-lookup"><span data-stu-id="25e88-110">Example</span></span>  
 <span data-ttu-id="25e88-111">下一示例演示如何循环访问现有 .zip 文件的内容并提取扩展名为 .txt 的文件。</span><span class="sxs-lookup"><span data-stu-id="25e88-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="25e88-112">它使用 <xref:System.IO.Compression.ZipArchive> 类访问现有 .zip 文件，使用 <xref:System.IO.Compression.ZipArchiveEntry> 类来检查压缩文件中的各个项。</span><span class="sxs-lookup"><span data-stu-id="25e88-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="25e88-113">它为 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> 对象使用扩展方法 (<xref:System.IO.Compression.ZipArchiveEntry>)。</span><span class="sxs-lookup"><span data-stu-id="25e88-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="25e88-114">扩展方法可以在 <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> 类中使用。</span><span class="sxs-lookup"><span data-stu-id="25e88-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="25e88-115">若要使用 <xref:System.IO.Compression.ZipFileExtensions> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。</span><span class="sxs-lookup"><span data-stu-id="25e88-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="25e88-116">示例</span><span class="sxs-lookup"><span data-stu-id="25e88-116">Example</span></span>  
 <span data-ttu-id="25e88-117">下一个示例使用 <xref:System.IO.Compression.ZipArchive> 类访问现有的 .zip 文件，然后向压缩文件添加新文件。</span><span class="sxs-lookup"><span data-stu-id="25e88-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="25e88-118">当将其添加到现有的 .zip 文件时，会对新文件进行压缩。</span><span class="sxs-lookup"><span data-stu-id="25e88-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="25e88-119">示例</span><span class="sxs-lookup"><span data-stu-id="25e88-119">Example</span></span>  
 <span data-ttu-id="25e88-120">您也可以使用 <xref:System.IO.Compression.GZipStream> 和 <xref:System.IO.Compression.DeflateStream> 类压缩和解压缩数据。</span><span class="sxs-lookup"><span data-stu-id="25e88-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="25e88-121">它们使用相同的压缩算法。</span><span class="sxs-lookup"><span data-stu-id="25e88-121">They use the same compression algorithm.</span></span> <span data-ttu-id="25e88-122">除了 <xref:System.IO.Compression.GZipStream> 提供的方法之外，写入扩展名为 .gz 的文件的压缩 <xref:System.IO.Compression.GZipStream> 对象可以通过使用许多常用工具进行解压缩。</span><span class="sxs-lookup"><span data-stu-id="25e88-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="25e88-123">此示例展示了如何使用 <xref:System.IO.Compression.GZipStream> 类压缩和解压缩文件目录。</span><span class="sxs-lookup"><span data-stu-id="25e88-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="25e88-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="25e88-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="25e88-125">文件和流 I-O</span><span class="sxs-lookup"><span data-stu-id="25e88-125">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
