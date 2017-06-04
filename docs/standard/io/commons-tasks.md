---
title: "通用 I/O 任务 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "I/O, 常规任务"
ms.assetid: bf00c380-706a-4e38-b829-454a480629fc
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
---
# 通用 I/O 任务
<xref:System.IO> 命名空间提供若干个类，通过这些类可以对文件、目录和流执行各种操作（如读取和写入）。  有关更多信息，请参见[文件和流 I\/O](../../../docs/standard/io/index.md)。  
  
## 通用文件任务  
  
|若要执行此操作...|请参见本主题中的示例...|  
|----------------|-------------------|  
|创建文本文件|<xref:System.IO.File.CreateText%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.FileInfo.CreateText%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.File.Create%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.FileInfo.Create%2A?displayProperty=fullName> 方法|  
|写入到文本文件|[如何：向文件写入文本](../../../docs/standard/io/how-to-write-text-to-a-file.md)<br /><br /> [如何：编写文本文件](../Topic/How%20to:%20Write%20a%20Text%20File%20\(C++-CLI\).md)|  
|从文本文件读取|[如何：从文件读取文本](../../../docs/standard/io/how-to-read-text-from-a-file.md)|  
|向文件中追加文本|[如何：打开并追加到日志文件](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)<br /><br /> <xref:System.IO.File.AppendText%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.FileInfo.AppendText%2A?displayProperty=fullName> 方法|  
|重命名或移动文件|<xref:System.IO.File.Move%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.FileInfo.MoveTo%2A?displayProperty=fullName> 方法|  
|删除文件|<xref:System.IO.File.Delete%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.FileInfo.Delete%2A?displayProperty=fullName> 方法|  
|复制文件|<xref:System.IO.File.Copy%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.FileInfo.CopyTo%2A?displayProperty=fullName> 方法|  
|获取文件大小|<xref:System.IO.FileInfo.Length%2A?displayProperty=fullName> 属性|  
|获取文件特性|<xref:System.IO.File.GetAttributes%2A?displayProperty=fullName> 方法|  
|设置文件特性|<xref:System.IO.File.SetAttributes%2A?displayProperty=fullName> 方法|  
|确定文件是否存在|<xref:System.IO.File.Exists%2A?displayProperty=fullName> 方法|  
|从二进制文件读取|[如何：对新建的数据文件进行读取和写入](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|写入二进制文件|[如何：对新建的数据文件进行读取和写入](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|检索文件扩展名|<xref:System.IO.Path.GetExtension%2A?displayProperty=fullName> 方法|  
|检索文件的完全限定路径|<xref:System.IO.Path.GetFullPath%2A?displayProperty=fullName> 方法|  
|检索路径中的文件名和扩展名|<xref:System.IO.Path.GetFileName%2A?displayProperty=fullName> 方法|  
|更改文件扩展名|<xref:System.IO.Path.ChangeExtension%2A?displayProperty=fullName> 方法|  
  
## 通用目录任务  
  
|若要执行此操作...|请参见本主题中的示例...|  
|----------------|-------------------|  
|访问特定文件夹（如“My Documents”）中的文件|[如何：向文件写入文本](../../../docs/standard/io/how-to-write-text-to-a-file.md)|  
|创建目录|<xref:System.IO.Directory.CreateDirectory%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.FileInfo.Directory%2A?displayProperty=fullName> 属性|  
|创建子目录|<xref:System.IO.DirectoryInfo.CreateSubdirectory%2A?displayProperty=fullName> 方法|  
|重命名或移动目录|<xref:System.IO.Directory.Move%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.DirectoryInfo.MoveTo%2A?displayProperty=fullName> 方法|  
|复制目录|[如何：复制目录](../../../docs/standard/io/how-to-copy-directories.md)|  
|删除目录|<xref:System.IO.Directory.Delete%2A?displayProperty=fullName> 方法<br /><br /> <xref:System.IO.DirectoryInfo.Delete%2A?displayProperty=fullName> 方法|  
|查看目录中的文件和子目录|[如何：枚举目录和文件](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)|  
|查明目录大小|<xref:System.IO.Directory?displayProperty=fullName> 类|  
|确定目录是否存在|<xref:System.IO.Directory.Exists%2A?displayProperty=fullName> 方法|  
  
## 请参阅  
 [文件和流 I\/O](../../../docs/standard/io/index.md)   
 [编写流](../../../docs/standard/io/composing-streams.md)   
 [异步文件 I\/O](../../../docs/standard/io/异步文件-i-o.md)