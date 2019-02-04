---
title: 如何：从字符串中读取字符
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbf213c783d1688e9168265cedc27d2ac7a5a96d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504804"
---
# <a name="how-to-read-characters-from-a-string"></a>如何：从字符串中读取字符
下面的代码示例展示了如何从字符串中异步和同步读取字符。  
  
## <a name="example"></a>示例  
 此示例从字符串中同步读取 13 个字符，将它们存储到数组中，并显示这些字符。 然后，它读取字符串中的剩余字符，将它们存储到数组中（从第六个元素开始），并显示数组的内容。  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a>示例  
 下一个示例从 <xref:System.Windows.Controls.TextBox> 控件异步读取所有字符，并将其存储在数组中。 随后，它以异步方式将每个字母或空格字符写入 <xref:System.Windows.Controls.TextBlock> 控件，每个字母或空格字符各占一行（以换行符结尾）。  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.IO.StringReader>
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>
- [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)
- [NIB：如何：创建目录列表](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)
- [如何：对新建的数据文件进行读取和写入](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [如何：打开并追加到日志文件](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [如何：从文件中读取文本](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [如何：将文本写入文件](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [如何：向字符串写入字符](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [文件和流 I/O](../../../docs/standard/io/index.md)
