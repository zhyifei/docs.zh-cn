---
title: 文件太大，无法读取到字节数组中
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800875"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="53186-102">文件太大，无法读取到字节数组中</span><span class="sxs-lookup"><span data-stu-id="53186-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="53186-103">尝试读取到字节数组的文件的大小超过 4 GB。</span><span class="sxs-lookup"><span data-stu-id="53186-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="53186-104">`My.Computer.FileSystem.ReadAllBytes`方法不能读取超过此大小的文件。</span><span class="sxs-lookup"><span data-stu-id="53186-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="53186-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="53186-105">To correct this error</span></span>  
  
-   <span data-ttu-id="53186-106">使用<xref:System.IO.StreamReader>读取该文件。</span><span class="sxs-lookup"><span data-stu-id="53186-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="53186-107">有关详细信息，请参阅[基础知识的.NET Framework 文件 I/O 和文件系统 (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)。</span><span class="sxs-lookup"><span data-stu-id="53186-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53186-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="53186-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="53186-109">使用 Visual Basic 访问文件</span><span class="sxs-lookup"><span data-stu-id="53186-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="53186-110">如何：从文件使用 StreamReader 读取文本</span><span class="sxs-lookup"><span data-stu-id="53186-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
