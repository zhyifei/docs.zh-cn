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
ms.openlocfilehash: 669936d15cfe1ea125ed36ffdfcfd093b6aacbe1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47424423"
---
# <a name="how-to-compress-and-extract-files"></a>如何：压缩和解压缩文件

<xref:System.IO.Compression> 命名空间包含以下类型来对文件和流进行压缩或解压缩。 还可以使用这些类型来读取和修改压缩文件的内容：

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

下面的示例演示当使用压缩文件时可以执行的某些功能。

## <a name="example-1---create-and-extract-a-zip-file"></a>示例 1 - 创建和提取 .zip 文件

以下示例演示如何使用 <xref:System.IO.Compression.ZipFile> 类创建和提取文件扩展名为 .zip 的压缩文件。 它将文件夹的内容压缩为一个新 .zip 文件，然后将该内容提取到一个新文件夹。 若要使用 <xref:System.IO.Compression.ZipFile> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a>示例 2 - 提取特定文件扩展名

下一示例演示如何循环访问现有 .zip 文件的内容并提取扩展名为 .txt 的文件。 它使用 <xref:System.IO.Compression.ZipArchive> 类访问现有 .zip 文件，使用 <xref:System.IO.Compression.ZipArchiveEntry> 类来检查压缩文件中的各个项。 它为 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> 对象使用扩展方法 (<xref:System.IO.Compression.ZipArchiveEntry>)。 扩展方法可以在 <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> 类中使用。 若要使用 <xref:System.IO.Compression.ZipFileExtensions> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。

> [!IMPORTANT]
> 在解压缩文件时，必须查找可以转义出你想要解压缩到的目录的恶意文件路径。 这被称为“路径遍历攻击”。

下面的示例演示如何检查恶意文件路径，并提供一种安全的解压缩方法：

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a>示例 3 - 将新文件添加到现有 .zip 文件

以下示例使用 <xref:System.IO.Compression.ZipArchive> 类访问现有的 .zip 文件，然后向压缩文件添加新文件。 当将其添加到现有的 .zip 文件时，会对新文件进行压缩。

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a>示例 4 - 压缩和解压缩 .gz 文件目录

您也可以使用 <xref:System.IO.Compression.GZipStream> 和 <xref:System.IO.Compression.DeflateStream> 类压缩和解压缩数据。 它们使用相同的压缩算法。 除了 <xref:System.IO.Compression.GZipStream> 提供的方法之外，写入扩展名为 .gz 的文件的压缩 <xref:System.IO.Compression.GZipStream> 对象可以通过使用许多常用工具进行解压缩。 以下示例展示了如何使用 <xref:System.IO.Compression.GZipStream> 类压缩和解压缩文件目录：

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>请参阅

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [文件和流 I/O](../../../docs/standard/io/index.md)
