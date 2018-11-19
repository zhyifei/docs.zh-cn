---
title: 如何：枚举目录和文件
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de83395df9e8c89a92e85b96ddd15e9f0be6ad5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44207689"
---
# <a name="how-to-enumerate-directories-and-files"></a>如何：枚举目录和文件
通过使用可返回目录和文件名的可枚举字符串集合的方法，可枚举目录和文件。 也可以使用返回 <xref:System.IO.DirectoryInfo>、<xref:System.IO.FileInfo> 或 <xref:System.IO.FileSystemInfo> 对象的可枚举集合的方法。 在处理目录和文件的大型集合时，可枚举的集合能够比数组提供更好的性能。  
  
 还可以使用通过这些方法获取的可枚举集合，为集合类（如 <xref:System.Collections.Generic.List%601> 类）的构造函数提供 <xref:System.Collections.Generic.IEnumerable%601> 参数。  
  
 如果只想获取目录名称或文件名，请使用 <xref:System.IO.Directory> 类的枚举方法。 若要获取目录或文件的其他属性，请使用 <xref:System.IO.DirectoryInfo> 和 <xref:System.IO.FileSystemInfo> 类。  
  
 下表列出了与返回可枚举集合的方法相关的指南。  
  
|要枚举的内容|要返回的可枚举集合|要使用的方法|  
|------------------|-------------------------------------|-------------------|  
|目录|目录名称|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||目录信息 (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|文件|文件名|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||文件信息 (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|文件系统信息|文件系统项|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||文件系统信息 (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 虽然可以使用 <xref:System.IO.SearchOption> 枚举提供的 <xref:System.IO.SearchOption.AllDirectories> 搜索选项迅速枚举父目录的子目录中的所有文件，但未经授权的访问异常 (<xref:System.UnauthorizedAccessException>) 可能会导致枚举不完整。 如果这些异常可能会抛出，可以捕获它们并继续执行，通过先枚举目录，再枚举文件。  
  
### <a name="to-enumerate-directory-names"></a>枚举目录名称的具体步骤  
  
-   使用 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 方法，获取指定路径中顶级目录名称的列表。  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>枚举目录和子目录中的文件名  
  
-   使用 <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 方法可搜索目录及其子目录（可选），并获取与指定搜索模式匹配的文件名称的列表。  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>枚举 DirectoryInfo 对象集合的具体步骤  
  
-   使用 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 方法，获取顶级目录的集合。  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>枚举所有目录中 FileInfo 对象集合的具体步骤  
  
-   使用 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 方法，获取与所有目录中指定搜索模式匹配的文件集合。 此示例先枚举顶级目录以捕获可能的未授权访问异常，再枚举文件。  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>请参阅

- [文件和流 I/O](../../../docs/standard/io/index.md)
