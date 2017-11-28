---
title: "如何：在 Visual Basic 中使用 StreamWriter 向文件中写入文本"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 874bb9cb88bbf25cb6208a0a33858855a7b26a49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="e8395-102">如何：在 Visual Basic 中使用 StreamWriter 向文件中写入文本</span><span class="sxs-lookup"><span data-stu-id="e8395-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="e8395-103">此示例将通过 `My.Computer.FileSystem.OpenTextFileWriter` 方法打开 <xref:System.IO.StreamWriter> 对象，并会使用该对象和 <xref:System.IO.StreamWriter> 类的 <xref:System.IO.TextWriter.WriteLine%2A> 方法向文本文件写入字符串。</span><span class="sxs-lookup"><span data-stu-id="e8395-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8395-104">示例</span><span class="sxs-lookup"><span data-stu-id="e8395-104">Example</span></span>  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e8395-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e8395-105">Robust Programming</span></span>  
 <span data-ttu-id="e8395-106">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="e8395-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e8395-107">文件存在且为只读 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="e8395-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="e8395-108">磁盘已满 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="e8395-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="e8395-109">路径名称过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="e8395-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e8395-110">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="e8395-110">.NET Framework Security</span></span>  
 <span data-ttu-id="e8395-111">此示例在文件尚未存在时创建新文件。</span><span class="sxs-lookup"><span data-stu-id="e8395-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="e8395-112">如果某个应用程序需要创建文件，则该应用程序需要针对文件夹的 `Create` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="e8395-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="e8395-113">如果文件已存在，则该应用程序只需要 `Write` 访问权限（这是较弱的特权）。</span><span class="sxs-lookup"><span data-stu-id="e8395-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="e8395-114">如有可能，在部署过程中创建文件，并且仅授予针对单个文件的 `Read` 访问权限（而不是针对 `Create` 文件夹的访问权限）会更加安全。</span><span class="sxs-lookup"><span data-stu-id="e8395-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8395-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8395-115">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>  
 [<span data-ttu-id="e8395-116">如何：读取文本文件</span><span class="sxs-lookup"><span data-stu-id="e8395-116">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)  
 [<span data-ttu-id="e8395-117">写入文件</span><span class="sxs-lookup"><span data-stu-id="e8395-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
