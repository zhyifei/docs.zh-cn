---
title: 文件太大，无法读取到字节数组中
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 1b04d47cab77269a0ce84ef77c162a4401d99d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585920"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>文件太大，无法读取到字节数组中
您试图从中读取的字节数组到文件的大小超过 4 GB。 `My.Computer.FileSystem.ReadAllBytes`方法无法读取的文件超过此大小。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用<xref:System.IO.StreamReader>以读取文件。 有关详细信息，请参阅[基础知识的.NET Framework 文件 I/O 和文件系统 (Visual Basic 中)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [使用 Visual Basic 访问文件](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [如何：使用 StreamReader 读取文件中的文本](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
