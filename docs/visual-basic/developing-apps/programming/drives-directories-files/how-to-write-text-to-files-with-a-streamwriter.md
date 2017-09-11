---
title: "如何：在 Visual Basic 中使用 StreamWriter 向文件中写入文本"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, writing to
- text, writing to files
- writing to files, StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ea85d57e9af4fdd640733db5dc2fa8b0ab25325c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="e8b5d-102">如何：在 Visual Basic 中使用 StreamWriter 向文件中写入文本</span><span class="sxs-lookup"><span data-stu-id="e8b5d-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="e8b5d-103">此示例将通过 `My.Computer.FileSystem.OpenTextFileWriter` 方法打开 <xref:System.IO.StreamWriter> 对象，并会使用该对象和 <xref:System.IO.StreamWriter> 类的 <xref:System.IO.TextWriter.WriteLine%2A> 方法向文本文件写入字符串。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8b5d-104">示例</span><span class="sxs-lookup"><span data-stu-id="e8b5d-104">Example</span></span>  
 <span data-ttu-id="e8b5d-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8b5d-105">[!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e8b5d-106">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e8b5d-106">Robust Programming</span></span>  
 <span data-ttu-id="e8b5d-107">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="e8b5d-107">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e8b5d-108">文件存在且为只读 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-108">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="e8b5d-109">磁盘已满 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-109">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="e8b5d-110">路径名称过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-110">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e8b5d-111">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="e8b5d-111">.NET Framework Security</span></span>  
 <span data-ttu-id="e8b5d-112">此示例在文件尚未存在时创建新文件。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-112">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="e8b5d-113">如果某个应用程序需要创建文件，则该应用程序需要针对文件夹的 `Create` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-113">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="e8b5d-114">如果文件已存在，则该应用程序只需要 `Write` 访问权限（这是较弱的特权）。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-114">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="e8b5d-115">如有可能，在部署过程中创建文件，并且仅授予针对单个文件的 `Read` 访问权限（而不是针对 `Create` 文件夹的访问权限）会更加安全。</span><span class="sxs-lookup"><span data-stu-id="e8b5d-115">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b5d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8b5d-116">See Also</span></span>  
 <span data-ttu-id="e8b5d-117"><xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="e8b5d-117"><xref:System.IO.StreamWriter></span></span>   
 <span data-ttu-id="e8b5d-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span><span class="sxs-lookup"><span data-stu-id="e8b5d-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A></span></span>   
 <span data-ttu-id="e8b5d-119">[如何：读取文本文件](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="e8b5d-119">[How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md) </span></span>  
 [<span data-ttu-id="e8b5d-120">写入文件</span><span class="sxs-lookup"><span data-stu-id="e8b5d-120">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)

