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
# <a name="how-to-write-characters-to-a-string"></a>如何：向字符串写入字符
下面的代码示例从字符数组以同步和异步方式向字符串写入字符。  
  
## <a name="example"></a>示例  
 下面的示例从数组将 5 个字符同步写入到字符串中。  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a>示例  
 下一个示例从 <xref:System.Windows.Controls.TextBox> 控件异步读取所有字符，并将其存储在数组中。 随后，它以异步方式将每个字母或空格字符写入 <xref:System.Windows.Controls.TextBlock> 控件，每个字母或空格字符各占一行（以换行符结尾）。  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IO.StringWriter>  
 <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
 <xref:System.Text.StringBuilder>  
 [文件和流 I-O](../../../docs/standard/io/index.md)  
 [异步文件 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [如何：枚举目录和文件](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [如何：对新建的数据文件进行读取和写入](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [如何：打开并追加到日志文件](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [如何：从文件读取文本](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [如何：向文件写入文本](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [如何：从字符串中读取字符](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
