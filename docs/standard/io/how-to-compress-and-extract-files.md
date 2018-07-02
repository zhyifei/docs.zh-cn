---
title: 如何：压缩和解压缩文件
ms.date: 06/06/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f045f2137d65a66ac025c81e58e66c96bcaca031
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827119"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="9e924-102">如何：压缩和解压缩文件</span><span class="sxs-lookup"><span data-stu-id="9e924-102">How to: Compress and extract files</span></span>

<span data-ttu-id="9e924-103"><xref:System.IO.Compression> 命名空间包含以下类型来对文件和流进行压缩或解压缩。</span><span class="sxs-lookup"><span data-stu-id="9e924-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="9e924-104">还可以使用这些类型来读取和修改压缩文件的内容：</span><span class="sxs-lookup"><span data-stu-id="9e924-104">You can also use these types to read and modify the contents of a compressed file:</span></span>

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="9e924-105">下面的示例演示当使用压缩文件时可以执行的某些功能。</span><span class="sxs-lookup"><span data-stu-id="9e924-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>

## <a name="example-1---create-and-extract-a-zip-file"></a><span data-ttu-id="9e924-106">示例 1 - 创建和提取 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="9e924-106">Example 1 - Create and extract a .zip file</span></span>

<span data-ttu-id="9e924-107">以下示例演示如何使用 <xref:System.IO.Compression.ZipFile> 类创建和提取文件扩展名为 .zip 的压缩文件。</span><span class="sxs-lookup"><span data-stu-id="9e924-107">The following example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="9e924-108">它将文件夹的内容压缩为一个新 .zip 文件，然后将该内容提取到一个新文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e924-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="9e924-109">若要使用 <xref:System.IO.Compression.ZipFile> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。</span><span class="sxs-lookup"><span data-stu-id="9e924-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a><span data-ttu-id="9e924-110">示例 2 - 提取特定文件扩展名</span><span class="sxs-lookup"><span data-stu-id="9e924-110">Example 2 - Extract specific file extensions</span></span>

<span data-ttu-id="9e924-111">下一示例演示如何循环访问现有 .zip 文件的内容并提取扩展名为 .txt 的文件。</span><span class="sxs-lookup"><span data-stu-id="9e924-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="9e924-112">它使用 <xref:System.IO.Compression.ZipArchive> 类访问现有 .zip 文件，使用 <xref:System.IO.Compression.ZipArchiveEntry> 类来检查压缩文件中的各个项。</span><span class="sxs-lookup"><span data-stu-id="9e924-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="9e924-113">它为 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> 对象使用扩展方法 (<xref:System.IO.Compression.ZipArchiveEntry>)。</span><span class="sxs-lookup"><span data-stu-id="9e924-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="9e924-114">扩展方法可以在 <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> 类中使用。</span><span class="sxs-lookup"><span data-stu-id="9e924-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9e924-115">若要使用 <xref:System.IO.Compression.ZipFileExtensions> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。</span><span class="sxs-lookup"><span data-stu-id="9e924-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e924-116">在解压缩文件时，必须查找可以转义出你想要解压缩到的目录的恶意文件路径。</span><span class="sxs-lookup"><span data-stu-id="9e924-116">When unzipping files, you must look for malicious file paths which can escape out of the directory where you want to unzip into.</span></span> <span data-ttu-id="9e924-117">这被称为“路径遍历攻击”。</span><span class="sxs-lookup"><span data-stu-id="9e924-117">This is known as a path traversal attack.</span></span>

<span data-ttu-id="9e924-118">下面的示例演示如何检查恶意文件路径，并提供一种安全的解压缩方法：</span><span class="sxs-lookup"><span data-stu-id="9e924-118">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip:</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a><span data-ttu-id="9e924-119">示例 3 - 将新文件添加到现有 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="9e924-119">Example 3 - Add a new file to an existing .zip file</span></span>

<span data-ttu-id="9e924-120">以下示例使用 <xref:System.IO.Compression.ZipArchive> 类访问现有的 .zip 文件，然后向压缩文件添加新文件。</span><span class="sxs-lookup"><span data-stu-id="9e924-120">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="9e924-121">当将其添加到现有的 .zip 文件时，会对新文件进行压缩。</span><span class="sxs-lookup"><span data-stu-id="9e924-121">The new file gets compressed when you add it to the existing .zip file.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a><span data-ttu-id="9e924-122">示例 4 - 压缩和解压缩 .gz 文件目录</span><span class="sxs-lookup"><span data-stu-id="9e924-122">Example 4 - Compress and decompress a directory of .gz files</span></span>

<span data-ttu-id="9e924-123">您也可以使用 <xref:System.IO.Compression.GZipStream> 和 <xref:System.IO.Compression.DeflateStream> 类压缩和解压缩数据。</span><span class="sxs-lookup"><span data-stu-id="9e924-123">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="9e924-124">它们使用相同的压缩算法。</span><span class="sxs-lookup"><span data-stu-id="9e924-124">They use the same compression algorithm.</span></span> <span data-ttu-id="9e924-125">除了 <xref:System.IO.Compression.GZipStream> 提供的方法之外，写入扩展名为 .gz 的文件的压缩 <xref:System.IO.Compression.GZipStream> 对象可以通过使用许多常用工具进行解压缩。</span><span class="sxs-lookup"><span data-stu-id="9e924-125">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="9e924-126">以下示例展示了如何使用 <xref:System.IO.Compression.GZipStream> 类压缩和解压缩文件目录：</span><span class="sxs-lookup"><span data-stu-id="9e924-126">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9e924-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e924-127">See also</span></span>

<xref:System.IO.Compression.ZipArchive>  
<xref:System.IO.Compression.ZipFile>  
<xref:System.IO.Compression.ZipArchiveEntry>  
<xref:System.IO.Compression.DeflateStream>  
<xref:System.IO.Compression.GZipStream>  
[<span data-ttu-id="9e924-128">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="9e924-128">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
