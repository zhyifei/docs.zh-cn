---
title: "编写流"
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
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a>编写流
一个后备存储是一个存储媒介，如磁盘或内存。 每个不同的后备存储的实现作为实现其自己的流<xref:System.IO.Stream>类。 每种流类型读取和写入字节，from 和 to 其给定的后备存储。 连接到后备存储的流叫做基流。 基流的构造函数具有连接到的后备存储的流所必需的参数。 例如，<xref:System.IO.FileStream>具有指定的路径参数，它指定将如何由进程中，依次类推共享文件的构造函数。  
  
 设计<xref:System.IO>类提供简化的流构成。 基流可以附加到提供所需的功能的一个或多个传递流。 这样可以读取所需的类型，或将其轻松编写，读取器或编写器可以附加到链的结尾。  
  
 下面的代码示例创建**FileStream**围绕现有`MyFile.txt`到缓冲区的顺序`MyFile.txt`。 (请注意， **FileStreams**缓冲默认情况下。)接下来，<xref:System.IO.StreamReader>创建读取字符从**FileStream**，将传递给**StreamReader**作为其构造函数自变量。 <xref:System.IO.StreamReader.ReadLine%2A>直到读取<xref:System.IO.StreamReader.Peek%2A>查找没有更多字符。  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 下面的代码示例创建**FileStream**围绕现有`MyFile.txt`到缓冲区的顺序`MyFile.txt`。 (请注意， **FileStreams**缓冲默认情况下。)接下来， **BinaryReader**创建读取字节从**FileStream**，将传递给**BinaryReader**作为其构造函数自变量。 <xref:System.IO.BinaryReader.ReadByte%2A>直到读取<xref:System.IO.BinaryReader.PeekChar%2A>查找更多字节。  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
