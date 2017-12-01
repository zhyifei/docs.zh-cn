---
title: "如何：在独立存储中创建文件和目录"
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
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>如何：在独立存储中创建文件和目录
获得独立存储区之后，您可以创建用于存储数据的目录和文件。 在存储区中，则将文件和目录名称指定相对于根目录的虚拟文件系统。  
  
 若要创建目录，请使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> 实例方法。 如果您为不存在的目录指定了一个子目录，则会同时创建这两个目录。 如果您指定的目录已存在，该方法将返回而不创建目录，并且不会引发异常。 但是，如果您指定的目录名称包含无效字符，将引发 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 异常。  
  
 若要创建文件，请使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> 方法。  
  
 在 Windows 操作系统，独立存储文件和目录名不区分大小写。 这样，如果您创建了一个名为 `ThisFile.txt` 的文件，然后又创建了名为 `THISFILE.TXT` 的另一个文件，实际上只创建了一个文件。 文件名称将保留其原始的大小写，用于显示目的。  
  
## <a name="example"></a>示例  
 下面的代码示例说明了如何在独立存储区中创建文件和目录。  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [独立存储](../../../docs/standard/io/isolated-storage.md)
