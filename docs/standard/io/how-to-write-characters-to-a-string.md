---
title: "如何：向字符串写入字符"
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
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d409b9f9cada319c64c4b5a1315b8a5abbd731e9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="b64c9-102">如何：向字符串写入字符</span><span class="sxs-lookup"><span data-stu-id="b64c9-102">How to: Write Characters to a String</span></span>
<span data-ttu-id="b64c9-103">下面的代码示例从字符数组以同步和异步方式向字符串写入字符。</span><span class="sxs-lookup"><span data-stu-id="b64c9-103">The following code examples write characters synchronously and asynchronously from a character array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b64c9-104">示例</span><span class="sxs-lookup"><span data-stu-id="b64c9-104">Example</span></span>  
 <span data-ttu-id="b64c9-105">下面的示例从数组将 5 个字符同步写入到字符串中。</span><span class="sxs-lookup"><span data-stu-id="b64c9-105">The following example writes 5 characters synchronously from an array to a string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="b64c9-106">示例</span><span class="sxs-lookup"><span data-stu-id="b64c9-106">Example</span></span>  
 <span data-ttu-id="b64c9-107">下一个示例从 <xref:System.Windows.Controls.TextBox> 控件异步读取所有字符，并将其存储在数组中。</span><span class="sxs-lookup"><span data-stu-id="b64c9-107">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="b64c9-108">随后，它以异步方式将每个字母或空格字符写入 <xref:System.Windows.Controls.TextBlock> 控件，每个字母或空格字符各占一行（以换行符结尾）。</span><span class="sxs-lookup"><span data-stu-id="b64c9-108">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b64c9-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="b64c9-109">See Also</span></span>  
 <xref:System.IO.StringWriter>  
 <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="b64c9-110">文件和流 I-O</span><span class="sxs-lookup"><span data-stu-id="b64c9-110">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="b64c9-111">异步文件 I/O</span><span class="sxs-lookup"><span data-stu-id="b64c9-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="b64c9-112">如何：枚举目录和文件</span><span class="sxs-lookup"><span data-stu-id="b64c9-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="b64c9-113">如何：对新建的数据文件进行读取和写入</span><span class="sxs-lookup"><span data-stu-id="b64c9-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="b64c9-114">如何：打开并追加到日志文件</span><span class="sxs-lookup"><span data-stu-id="b64c9-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="b64c9-115">如何：从文件读取文本</span><span class="sxs-lookup"><span data-stu-id="b64c9-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="b64c9-116">如何：向文件写入文本</span><span class="sxs-lookup"><span data-stu-id="b64c9-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="b64c9-117">如何：从字符串中读取字符</span><span class="sxs-lookup"><span data-stu-id="b64c9-117">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
