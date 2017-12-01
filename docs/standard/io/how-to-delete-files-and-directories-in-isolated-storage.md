---
title: "如何：在独立存储中删除文件和目录"
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
- data storage using isolated storage, deleting files and directories
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 971f27cd25cbe4be3ca3fad6283ab32d4f6db0ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>如何：在独立存储中删除文件和目录
你可以删除目录和文件中的独立的存储文件。 在存储区中，文件名和目录名依赖于操作系统，并指定为虚拟文件系统根目录的相对路径。 在 Windows 操作系统中，它们不区分大小写。  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> 类提供了两个用于删除目录和文件的方法：<xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 和 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>。 如果尝试删除并不存在的文件和目录，则会引发 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 异常。 如果在名称中包含通配符，<xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 将引发 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 异常，并且 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> 会引发 <xref:System.ArgumentException> 异常。  
  
 如果目录中包含任何文件或子目录，<xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 方法将会失败。 可以使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> 和 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> 方法检索现有文件和目录。 有关搜索存储的虚拟文件系统的详细信息，请参阅[How to： 独立存储中查找现有文件和目录](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例创建，然后删除几个目录和文件。  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [独立存储](../../../docs/standard/io/isolated-storage.md)
