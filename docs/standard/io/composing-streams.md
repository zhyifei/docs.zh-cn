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
# <a name="composing-streams"></a><span data-ttu-id="5e619-102">编写流</span><span class="sxs-lookup"><span data-stu-id="5e619-102">Composing Streams</span></span>
<span data-ttu-id="5e619-103">一个后备存储是一个存储媒介，如磁盘或内存。</span><span class="sxs-lookup"><span data-stu-id="5e619-103">A backing store is a storage medium, such as a disk or memory.</span></span> <span data-ttu-id="5e619-104">每个不同的后备存储的实现作为实现其自己的流<xref:System.IO.Stream>类。</span><span class="sxs-lookup"><span data-stu-id="5e619-104">Each different backing store implements its own stream as an implementation of the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="5e619-105">每种流类型读取和写入字节，from 和 to 其给定的后备存储。</span><span class="sxs-lookup"><span data-stu-id="5e619-105">Each stream type reads and writes bytes from and to its given backing store.</span></span> <span data-ttu-id="5e619-106">连接到后备存储的流叫做基流。</span><span class="sxs-lookup"><span data-stu-id="5e619-106">Streams that connect to backing stores are called base streams.</span></span> <span data-ttu-id="5e619-107">基流的构造函数具有连接到的后备存储的流所必需的参数。</span><span class="sxs-lookup"><span data-stu-id="5e619-107">Base streams have constructors that have the parameters necessary to connect the stream to the backing store.</span></span> <span data-ttu-id="5e619-108">例如，<xref:System.IO.FileStream>具有指定的路径参数，它指定将如何由进程中，依次类推共享文件的构造函数。</span><span class="sxs-lookup"><span data-stu-id="5e619-108">For example, <xref:System.IO.FileStream> has constructors that specify a path parameter, which specifies how the file will be shared by processes, and so on.</span></span>  
  
 <span data-ttu-id="5e619-109">设计<xref:System.IO>类提供简化的流构成。</span><span class="sxs-lookup"><span data-stu-id="5e619-109">The design of the <xref:System.IO> classes provides simplified stream composing.</span></span> <span data-ttu-id="5e619-110">基流可以附加到提供所需的功能的一个或多个传递流。</span><span class="sxs-lookup"><span data-stu-id="5e619-110">Base streams can be attached to one or more pass-through streams that provide the functionality you want.</span></span> <span data-ttu-id="5e619-111">这样可以读取所需的类型，或将其轻松编写，读取器或编写器可以附加到链的结尾。</span><span class="sxs-lookup"><span data-stu-id="5e619-111">A reader or writer can be attached to the end of the chain so that the preferred types can be read or written easily.</span></span>  
  
 <span data-ttu-id="5e619-112">下面的代码示例创建**FileStream**围绕现有`MyFile.txt`到缓冲区的顺序`MyFile.txt`。</span><span class="sxs-lookup"><span data-stu-id="5e619-112">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="5e619-113">(请注意， **FileStreams**缓冲默认情况下。)接下来，<xref:System.IO.StreamReader>创建读取字符从**FileStream**，将传递给**StreamReader**作为其构造函数自变量。</span><span class="sxs-lookup"><span data-stu-id="5e619-113">(Note that **FileStreams** are buffered by default.) Next, a <xref:System.IO.StreamReader> is created to read characters from the **FileStream**, which is passed to the **StreamReader** as its constructor argument.</span></span> <span data-ttu-id="5e619-114"><xref:System.IO.StreamReader.ReadLine%2A>直到读取<xref:System.IO.StreamReader.Peek%2A>查找没有更多字符。</span><span class="sxs-lookup"><span data-stu-id="5e619-114"><xref:System.IO.StreamReader.ReadLine%2A> reads until <xref:System.IO.StreamReader.Peek%2A> finds no more characters.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 <span data-ttu-id="5e619-115">下面的代码示例创建**FileStream**围绕现有`MyFile.txt`到缓冲区的顺序`MyFile.txt`。</span><span class="sxs-lookup"><span data-stu-id="5e619-115">The following code example creates a **FileStream** around the existing `MyFile.txt` in order to buffer `MyFile.txt`.</span></span> <span data-ttu-id="5e619-116">(请注意， **FileStreams**缓冲默认情况下。)接下来， **BinaryReader**创建读取字节从**FileStream**，将传递给**BinaryReader**作为其构造函数自变量。</span><span class="sxs-lookup"><span data-stu-id="5e619-116">(Note that **FileStreams** are buffered by default.) Next, a **BinaryReader** is created to read bytes from the **FileStream**, which is passed to the **BinaryReader** as its constructor argument.</span></span> <span data-ttu-id="5e619-117"><xref:System.IO.BinaryReader.ReadByte%2A>直到读取<xref:System.IO.BinaryReader.PeekChar%2A>查找更多字节。</span><span class="sxs-lookup"><span data-stu-id="5e619-117"><xref:System.IO.BinaryReader.ReadByte%2A> reads until <xref:System.IO.BinaryReader.PeekChar%2A> finds no more bytes.</span></span>  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="5e619-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e619-118">See Also</span></span>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
