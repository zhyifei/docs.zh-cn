---
title: "如何：在 Visual Basic 中向文件内写入文本"
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
- writing to files
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: 19
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
ms.openlocfilehash: dc6f02d6092a30113b8cb973be225e140eca19ad
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-in-visual-basic"></a><span data-ttu-id="07b88-102">如何：在 Visual Basic 中向文件内写入文本</span><span class="sxs-lookup"><span data-stu-id="07b88-102">How to: Write Text to Files in Visual Basic</span></span>
<span data-ttu-id="07b88-103">可使用 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 方法向文件写入文本。</span><span class="sxs-lookup"><span data-stu-id="07b88-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to write text to files.</span></span> <span data-ttu-id="07b88-104">如果指定的文件不存在，则会创建一个。</span><span class="sxs-lookup"><span data-stu-id="07b88-104">If the specified file does not exist, it is created.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="07b88-105">过程</span><span class="sxs-lookup"><span data-stu-id="07b88-105">Procedure</span></span>  
  
#### <a name="to-write-text-to-a-file"></a><span data-ttu-id="07b88-106">向文件写入文本</span><span class="sxs-lookup"><span data-stu-id="07b88-106">To write text to a file</span></span>  
  
-   <span data-ttu-id="07b88-107">可以使用 `WriteAllText` 方法向文件写入文本，并指定要写入的文件和文本。</span><span class="sxs-lookup"><span data-stu-id="07b88-107">Use the `WriteAllText` method to write text to a file, specifying the file and text to be written.</span></span> <span data-ttu-id="07b88-108">此示例将行 `"This is new text."` 写入名为 `test.txt` 的文件，同时将文本追加到文件中的任何现有文本。</span><span class="sxs-lookup"><span data-stu-id="07b88-108">This example writes the line `"This is new text."` to the file named `test.txt`, appending the text to any existing text in the file.</span></span>  
  
     <span data-ttu-id="07b88-109">[!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="07b88-109">[!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]</span></span>  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a><span data-ttu-id="07b88-110">向文件写入一系列字符串</span><span class="sxs-lookup"><span data-stu-id="07b88-110">To write a series of strings to a file</span></span>  
  
-   <span data-ttu-id="07b88-111">通过字符串集合循环。</span><span class="sxs-lookup"><span data-stu-id="07b88-111">Loop through the string collection.</span></span> <span data-ttu-id="07b88-112">可以使用 `WriteAllText` 方法向文件写入文本，同时指定目标文件以及要添加的字符串，并将 `append` 设置为 `True`。</span><span class="sxs-lookup"><span data-stu-id="07b88-112">Use the `WriteAllText` method to write text to a file, specifying the target file and string to be added and setting `append` to `True`.</span></span>  
  
     <span data-ttu-id="07b88-113">此示例将 `Documents and Settings` 目录中的文件名写入 `FileList.txt`，并在每个文件之间插入回车符，以增强可读性。</span><span class="sxs-lookup"><span data-stu-id="07b88-113">This example writes the names of the files in the `Documents and Settings` directory to `FileList.txt`, inserting a carriage return between each for better readability.</span></span>  
  
     <span data-ttu-id="07b88-114">[!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="07b88-114">[!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="07b88-115">可靠编程</span><span class="sxs-lookup"><span data-stu-id="07b88-115">Robust Programming</span></span>  
 <span data-ttu-id="07b88-116">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="07b88-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="07b88-117">路径由于以下原因之一无效：是零长度字符串；仅包含空白；包含无效字符；是一个设备路径（开头字符为 \\\\.\\）(<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="07b88-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="07b88-118">路径无效，因为它是 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="07b88-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="07b88-119">`File` 指向不存在的路径（<xref:System.IO.FileNotFoundException> 或 <xref:System.IO.DirectoryNotFoundException>）。</span><span class="sxs-lookup"><span data-stu-id="07b88-119">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="07b88-120">文件正由另一个进程使用，或者出现 I/O 错误 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="07b88-120">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="07b88-121">路径超过了系统定义的最大长度 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="07b88-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="07b88-122">路径中的文件名或目录名包含冒号 (:)，或格式无效 (<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="07b88-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="07b88-123">该用户缺少查看该路径所必需的权限 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="07b88-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="07b88-124">磁盘已满，且对 `WriteAllText` 的调用失败 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="07b88-124">The disk is full, and the call to `WriteAllText` fails (<xref:System.IO.IOException>).</span></span>  
  
 <span data-ttu-id="07b88-125">如果在部分信任上下文中运行，该代码可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="07b88-125">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="07b88-126">有关详细信息，请参阅[代码访问安全性基础知识](https://msdn.microsoft.com/library/33tceax8)。</span><span class="sxs-lookup"><span data-stu-id="07b88-126">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b88-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07b88-127">See Also</span></span>  
 <span data-ttu-id="07b88-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="07b88-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="07b88-129"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span><span class="sxs-lookup"><span data-stu-id="07b88-129"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A></span></span>   
 [<span data-ttu-id="07b88-130">如何：读取文本文件</span><span class="sxs-lookup"><span data-stu-id="07b88-130">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)

