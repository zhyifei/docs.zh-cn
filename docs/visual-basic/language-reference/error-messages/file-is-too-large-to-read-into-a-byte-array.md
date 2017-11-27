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
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="a5438-102">文件太大，无法读取到字节数组中</span><span class="sxs-lookup"><span data-stu-id="a5438-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="a5438-103">您试图从中读取的字节数组到文件的大小超过 4 GB。</span><span class="sxs-lookup"><span data-stu-id="a5438-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="a5438-104">`My.Computer.FileSystem.ReadAllBytes`方法无法读取的文件超过此大小。</span><span class="sxs-lookup"><span data-stu-id="a5438-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a5438-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a5438-105">To correct this error</span></span>  
  
-   <span data-ttu-id="a5438-106">使用<xref:System.IO.StreamReader>以读取文件。</span><span class="sxs-lookup"><span data-stu-id="a5438-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="a5438-107">有关详细信息，请参阅[基础知识的.NET Framework 文件 I/O 和文件系统 (Visual Basic 中)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)。</span><span class="sxs-lookup"><span data-stu-id="a5438-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5438-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5438-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [<span data-ttu-id="a5438-109">使用 Visual Basic 访问文件</span><span class="sxs-lookup"><span data-stu-id="a5438-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [<span data-ttu-id="a5438-110">如何：使用 StreamReader 读取文件中的文本</span><span class="sxs-lookup"><span data-stu-id="a5438-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
