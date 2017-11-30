---
title: "如何：从文件读取文本"
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
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 026f6ae4dd9aee340d6a9ffb931d0525ae75654a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-text-from-a-file"></a>如何：从文件读取文本
下面的示例演示如何使用适用于桌面应用的 .NET 以异步方式和同步方式从文本文件中读取文本。 在这两个示例中，当你创建 <xref:System.IO.StreamReader> 类的实例时，你会提供文件的绝对路径或相对路径。 以下示例假定名为 TestFile.txt 的文件位于此应用程序所在的文件夹中。  
  
 这些代码示例不适用于针对 Windows 应用商店应用的开发，因为 Windows 运行时提供了对文件进行读写操作的不同的流类型。 有关演示如何从 Windows 应用商店应用的上下文中的文件中读取文本的示例，请参阅[快速入门： 读取和写入文件](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)。 有关演示如何在.NET Framework 流与 Windows 运行时流之间进行转换的示例，请参阅[如何： 转换之间.NET Framework 流与 Windows 运行时流](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)。  
  
## <a name="example"></a>示例  
 第一个示例演示控制台应用程序中的同步读取操作。 在此示例中，使用流读取器打开文本文件，将内容复制到一个字符串中，然后将字符串输出到控制台。  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>示例  
 第二个示例演示 Windows Presentation Foundation (WPF) 应用程序中的异步读取操作。  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [异步文件 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [NIB： 如何： 创建目录列表](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [快速入门： 读取和写入文件](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [如何：在 .NET Framework 流和 Windows 运行时流之间进行转换](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [如何：对新建的数据文件进行读取和写入](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [如何：打开并追加到日志文件](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [如何：向文件写入文本](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [如何：从字符串中读取字符](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [如何：向字符串写入字符](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [文件和流 I-O](../../../docs/standard/io/index.md)
