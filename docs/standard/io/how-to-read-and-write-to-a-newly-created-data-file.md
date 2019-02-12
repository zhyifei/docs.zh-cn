---
title: 如何：对新建的数据文件进行读取和写入
ms.date: 01/21/2019
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
ms.openlocfilehash: 065907ae0d4a38ff2ef68de6025251e28220ee96
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674615"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="98018-102">如何：对新建的数据文件进行读取和写入</span><span class="sxs-lookup"><span data-stu-id="98018-102">How to: Read and write to a newly created data file</span></span>
<span data-ttu-id="98018-103"><xref:System.IO.BinaryWriter?displayProperty=nameWithType> 和 <xref:System.IO.BinaryReader?displayProperty=nameWithType> 类用于写入和读取字符串以外的数据。</span><span class="sxs-lookup"><span data-stu-id="98018-103">The <xref:System.IO.BinaryWriter?displayProperty=nameWithType> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data other than character strings.</span></span> <span data-ttu-id="98018-104">下面的示例演示如何创建空文件流，向其写入数据并从中读取数据。</span><span class="sxs-lookup"><span data-stu-id="98018-104">The following example shows how to create an empty file stream, write data to it, and read data from it.</span></span> 

<span data-ttu-id="98018-105">示例将在当前目录中创建名为 Test.data 的数据文件，也就同时创建了相关的 <xref:System.IO.BinaryWriter> 和 <xref:System.IO.BinaryReader> 对象，并且 <xref:System.IO.BinaryWriter> 对象用于向 Test.data 写入整数 0 到 10，这会将文件指针置于文件末尾。</span><span class="sxs-lookup"><span data-stu-id="98018-105">The example creates a data file called *Test.data* in the current directory, creates the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects, and uses the <xref:System.IO.BinaryWriter> object to write the integers 0 through 10 to *Test.data*, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="98018-106"><xref:System.IO.BinaryReader> 对象将文件指针设置回原始位置并读取指定的内容。</span><span class="sxs-lookup"><span data-stu-id="98018-106">The <xref:System.IO.BinaryReader> object then sets the file pointer back to the origin and reads out the specified content.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98018-107">如果当前目录中已存在 Test.data，则会引发 <xref:System.IO.IOException> 异常。</span><span class="sxs-lookup"><span data-stu-id="98018-107">If *Test.data* already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="98018-108">使用文件模型选项 <xref:System.IO.FileMode.Create?displayProperty=nameWithType> 而不是 <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> 以始终创建新文件，而不引发异常。</span><span class="sxs-lookup"><span data-stu-id="98018-108">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> rather than <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> to always create a new file without throwing an exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98018-109">示例</span><span class="sxs-lookup"><span data-stu-id="98018-109">Example</span></span>  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="98018-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="98018-110">See also</span></span>

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [<span data-ttu-id="98018-111">如何：枚举目录和文件</span><span class="sxs-lookup"><span data-stu-id="98018-111">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="98018-112">如何：打开并追加到日志文件</span><span class="sxs-lookup"><span data-stu-id="98018-112">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="98018-113">如何：从文件中读取文本</span><span class="sxs-lookup"><span data-stu-id="98018-113">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="98018-114">如何：将文本写入文件</span><span class="sxs-lookup"><span data-stu-id="98018-114">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="98018-115">如何：从字符串中读取字符</span><span class="sxs-lookup"><span data-stu-id="98018-115">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="98018-116">如何：向字符串写入字符</span><span class="sxs-lookup"><span data-stu-id="98018-116">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="98018-117">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="98018-117">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
