---
title: "如何：打开并追加到日志文件"
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
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60c31339231405a1cbbb98dae37d36ad3c3709c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-and-append-to-a-log-file"></a>如何：打开并追加到日志文件
<xref:System.IO.StreamWriter>和<xref:System.IO.StreamReader>写入到字符和从流读取字符。 下面的代码示例将打开`log.txt`文件以进行输入，或如果它尚不存在，并将信息追加到文件末尾创建文件。 文件的内容然后写入标准输出显示。 作为此示例的替代方法，信息可能存储为一个字符串或字符串数组和<xref:System.IO.File.WriteAllText%2A>或<xref:System.IO.File.WriteAllLines%2A>方法无法用于实现相同的功能。  
  
> [!NOTE]
>  Visual Basic 用户可以选择使用的方法和属性提供的<xref:Microsoft.VisualBasic.Logging.Log>类或<xref:Microsoft.VisualBasic.FileIO.FileSystem>类用于创建或写入日志文件。  
  
## <a name="example"></a>示例  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [如何：枚举目录和文件](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [如何：对新建的数据文件进行读取和写入](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [如何：从文件读取文本](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [如何：向文件写入文本](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [如何：从字符串中读取字符](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [如何：向字符串写入字符](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [文件和流 I-O](../../../docs/standard/io/index.md)
