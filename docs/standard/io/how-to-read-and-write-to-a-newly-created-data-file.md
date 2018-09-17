---
title: 如何：对新建的数据文件进行读取和写入
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65c56a11531f705b7e047e435ec575969d39a616
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45592901"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="cf53c-102">如何：对新建的数据文件进行读取和写入</span><span class="sxs-lookup"><span data-stu-id="cf53c-102">How to: Read and Write to a Newly Created Data File</span></span>
<span data-ttu-id="cf53c-103"><xref:System.IO.BinaryWriter> 和 <xref:System.IO.BinaryReader?displayProperty=nameWithType> 类用于写入和读取数据，而不是字符串。</span><span class="sxs-lookup"><span data-stu-id="cf53c-103">The <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data rather than character strings.</span></span> <span data-ttu-id="cf53c-104">下面的示例演示如何向新的空文件流 `Test.data` 写入数据及从中读取数据。</span><span class="sxs-lookup"><span data-stu-id="cf53c-104">The following example demonstrates how to write data to, and read data from, a new, empty file stream called `Test.data`.</span></span> <span data-ttu-id="cf53c-105">在当前目录中创建了数据文件之后，也就同时创建了相关的 <xref:System.IO.BinaryWriter> 和 <xref:System.IO.BinaryReader> 对象，并且 <xref:System.IO.BinaryWriter> 对象用于向 `Test.data` 写入整数 0 到 10，这会将文件指针置于文件尾。</span><span class="sxs-lookup"><span data-stu-id="cf53c-105">After creating the data file in the current directory, the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects are created, and the <xref:System.IO.BinaryWriter> object is used to write the integers 0 through 10 to `Test.data`, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="cf53c-106">在将文件指针设置回初始位置后，<xref:System.IO.BinaryReader> 对象会读出指定的内容。</span><span class="sxs-lookup"><span data-stu-id="cf53c-106">After setting the file pointer back to the origin, the <xref:System.IO.BinaryReader> object reads out the specified content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf53c-107">示例</span><span class="sxs-lookup"><span data-stu-id="cf53c-107">Example</span></span>  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a><span data-ttu-id="cf53c-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="cf53c-108">Robust Programming</span></span>  
 <span data-ttu-id="cf53c-109">如果当前目录中已存在 `Test.data`，则会引发 <xref:System.IO.IOException> 异常。</span><span class="sxs-lookup"><span data-stu-id="cf53c-109">If `Test.data` already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="cf53c-110">当您初始化文件流以始终创建新文件而不引发异常时，请使用文件模式选项 <xref:System.IO.FileMode.Create?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="cf53c-110">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> when you initialize the file stream to always create a new file without throwing an  exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf53c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf53c-111">See also</span></span>

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [<span data-ttu-id="cf53c-112">如何：枚举目录和文件</span><span class="sxs-lookup"><span data-stu-id="cf53c-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="cf53c-113">如何：打开并追加到日志文件</span><span class="sxs-lookup"><span data-stu-id="cf53c-113">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="cf53c-114">如何：从文件读取文本</span><span class="sxs-lookup"><span data-stu-id="cf53c-114">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="cf53c-115">如何：向文件写入文本</span><span class="sxs-lookup"><span data-stu-id="cf53c-115">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="cf53c-116">如何：从字符串中读取字符</span><span class="sxs-lookup"><span data-stu-id="cf53c-116">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="cf53c-117">如何：向字符串写入字符</span><span class="sxs-lookup"><span data-stu-id="cf53c-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="cf53c-118">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="cf53c-118">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
