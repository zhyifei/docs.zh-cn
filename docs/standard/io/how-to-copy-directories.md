---
title: 如何：复制目录
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cfe07af216da1c35b093a1ca23e4d48c60a7bfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-directories"></a>如何：复制目录
此示例演示如何使用 I/O 类将目录下的内容同步复制到另一个位置。 在此示例中，用户可以指定是否同时复制子目录。 如果复制子目录，则此示例中的方法将通过对每个后续子目录调用其自身的方法来递归复制它们，直到再也没有子目录可以复制为止。  
  
 有关异步复制文件的示例，请参阅 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [文件和流 I/O](../../../docs/standard/io/index.md)  
 [通用 I/O 任务](../../../docs/standard/io/common-i-o-tasks.md)  
 [异步文件 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)
