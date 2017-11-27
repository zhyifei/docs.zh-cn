---
title: "文件太大，无法读取到字节数组中"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bbdb5a4dcaa22ca84428ef28c8838a6d9a0ee1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>文件太大，无法读取到字节数组中
您试图从中读取的字节数组到文件的大小超过 4 GB。 `My.Computer.FileSystem.ReadAllBytes`方法无法读取的文件超过此大小。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用<xref:System.IO.StreamReader>以读取文件。 有关详细信息，请参阅[基础知识的.NET Framework 文件 I/O 和文件系统 (Visual Basic 中)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [使用 Visual Basic 访问文件](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [如何：使用 StreamReader 读取文件中的文本](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
