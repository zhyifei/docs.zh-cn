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
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>如何：对新建的数据文件进行读取和写入
<xref:System.IO.BinaryWriter> 和 <xref:System.IO.BinaryReader?displayProperty=nameWithType> 类用于写入和读取数据，而不是字符串。 下面的示例演示如何向新的空文件流 `Test.data` 写入数据及从中读取数据。 在当前目录中创建了数据文件之后，也就同时创建了相关的 <xref:System.IO.BinaryWriter> 和 <xref:System.IO.BinaryReader> 对象，并且 <xref:System.IO.BinaryWriter> 对象用于向 `Test.data` 写入整数 0 到 10，这会将文件指针置于文件尾。 在将文件指针设置回初始位置后，<xref:System.IO.BinaryReader> 对象会读出指定的内容。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>可靠编程  
 如果当前目录中已存在 `Test.data`，则会引发 <xref:System.IO.IOException> 异常。 当您初始化文件流以始终创建新文件而不引发异常时，请使用文件模式选项 <xref:System.IO.FileMode.Create?displayProperty=nameWithType>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [如何：枚举目录和文件](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [如何：打开并追加到日志文件](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [如何：从文件读取文本](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [如何：向文件写入文本](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [如何：从字符串中读取字符](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [如何：向字符串写入字符](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [文件和流 I/O](../../../docs/standard/io/index.md)
