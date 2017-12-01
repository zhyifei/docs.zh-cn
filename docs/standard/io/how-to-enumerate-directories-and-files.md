---
title: "如何：枚举目录和文件"
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
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>如何：枚举目录和文件
通过使用可返回目录和文件名的可枚举字符串集合的方法，可枚举目录和文件。 你还可以使用返回的可枚举集合的方法<xref:System.IO.DirectoryInfo>， <xref:System.IO.FileInfo>，或<xref:System.IO.FileSystemInfo>对象。 在处理目录和文件的大型集合时，可枚举的集合能够比数组提供更好的性能。  
  
 您可以使用这些方法从获取的可枚举集合来提供<xref:System.Collections.Generic.IEnumerable%601>参数构造函数的集合类，如<xref:System.Collections.Generic.List%601>类。  
  
 如果你想要获取仅目录或文件的名称，使用的枚举方法<xref:System.IO.Directory>类。 如果你想要获取目录或文件的其他属性，使用<xref:System.IO.DirectoryInfo>和<xref:System.IO.FileSystemInfo>类。  
  
 下表提供了返回可枚举集合的方法的指南。  
  
|若要枚举|要返回的可枚举集合|要使用的方法|  
|------------------|-------------------------------------|-------------------|  
|目录|目录名称|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||目录信息 (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|文件|文件名|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||文件信息 (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|文件系统信息|文件系统项|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||文件系统信息 (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 虽然可以使用 <xref:System.IO.SearchOption.AllDirectories> 枚举提供的 <xref:System.IO.SearchOption> 搜索选项迅速枚举父目录的子目录中的所有文件，但未经授权的访问异常 (<xref:System.UnauthorizedAccessException>) 可能会导致枚举不完整。 如果可能，这些例外是，你可以捕获它们并继续通过首先枚举目录，然后枚举文件。  
  
### <a name="to-enumerate-directory-names"></a>若要枚举目录名称  
  
-   使用<xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>方法来获取指定路径中的顶级目录名称的列表。  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>枚举目录和子目录中的文件名  
  
-   使用 <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 方法可搜索目录及其子目录（可选），并获取与指定搜索模式匹配的文件名称的列表。  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>若要枚举的 DirectoryInfo 对象的集合  
  
-   使用<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>方法来获取顶级目录的集合。  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>若要枚举的所有目录中的 FileInfo 对象的集合  
  
-   使用<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>方法来获取与所有目录中指定的搜索模式匹配的文件的集合。 本示例首先枚举顶级目录以捕获可能的未经授权的访问异常，然后枚举文件。  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [文件和流 I-O](../../../docs/standard/io/index.md)
