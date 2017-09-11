---
title: "如何：在 Visual Basic 中删除文件"
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
- Delete method
- files, deleting
- files, manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
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
ms.openlocfilehash: e4b0b87fd403556777e0ab5a1edd517687360374
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="0dcd7-102">如何：在 Visual Basic 中删除文件</span><span class="sxs-lookup"><span data-stu-id="0dcd7-102">How to: Delete a File in Visual Basic</span></span>
<span data-ttu-id="0dcd7-103">通过 `My.Computer.FileSystem` 对象的 `DeleteFile` 方法，可以删除文件。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-103">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="0dcd7-104">它提供的选项包括：是否将已删除的文件发送到“回收站”、是否要求用户确认应删除该文件，以及当用户取消操作时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-104">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="0dcd7-105">删除文本文件</span><span class="sxs-lookup"><span data-stu-id="0dcd7-105">To delete a text file</span></span>  
  
-   <span data-ttu-id="0dcd7-106">使用 `DeleteFile` 方法删除文件。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-106">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="0dcd7-107">以下代码演示如何删除名为 `test.txt` 的文件。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-107">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     <span data-ttu-id="0dcd7-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0dcd7-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="0dcd7-109">删除文本文件，并要求用户确认应删除该文件</span><span class="sxs-lookup"><span data-stu-id="0dcd7-109">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
-   <span data-ttu-id="0dcd7-110">使用 `DeleteFile` 方法删除文件，同时将 `showUI` 设置为 `AllDialogs`。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-110">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="0dcd7-111">以下代码演示如何删除名为 `test.txt` 的文件，并允许用户确认是否应删除该文件。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-111">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     <span data-ttu-id="0dcd7-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0dcd7-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="0dcd7-113">删除文本文件并将其发送到“回收站”</span><span class="sxs-lookup"><span data-stu-id="0dcd7-113">To delete a text file and send it to the Recycle Bin</span></span>  
  
-   <span data-ttu-id="0dcd7-114">使用 `DeleteFile` 方法删除文件，并为 `recycle` 参数指定 `SendToRecycleBin`。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-114">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="0dcd7-115">以下代码演示如何删除名为 `test.txt` 的文件并将其发送到“回收站”。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-115">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     <span data-ttu-id="0dcd7-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0dcd7-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0dcd7-117">可靠编程</span><span class="sxs-lookup"><span data-stu-id="0dcd7-117">Robust Programming</span></span>  
 <span data-ttu-id="0dcd7-118">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="0dcd7-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0dcd7-119">路径由于以下原因之一无效：是零长度字符串；仅包含空白；包含无效字符；是一个设备路径（开头字符为 \\\\.\\）(<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-120">路径无效，因为它是 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-121">路径超过了系统定义的最大长度 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-122">路径中的文件名或文件夹名包含冒号 (:)，或其格式无效 (<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-122">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-123">该文件正在使用中 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-123">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-124">该用户缺少查看该路径所必需的权限 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-125">该文件不存在 (<xref:System.IO.FileNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-125">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-126">用户无权删除文件，或文件为只读 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-126">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-127">存在部分信任的情况，在此情况下用户没有足够的权限 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-127">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="0dcd7-128">用户取消了该操作，并且 `onUserCancel` 设置为 `ThrowException` (<xref:System.OperationCanceledException>)。</span><span class="sxs-lookup"><span data-stu-id="0dcd7-128">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dcd7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dcd7-129">See Also</span></span>  
 <span data-ttu-id="0dcd7-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span><span class="sxs-lookup"><span data-stu-id="0dcd7-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span></span>   
 <span data-ttu-id="0dcd7-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="0dcd7-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="0dcd7-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span><span class="sxs-lookup"><span data-stu-id="0dcd7-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span></span>   
 <span data-ttu-id="0dcd7-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span><span class="sxs-lookup"><span data-stu-id="0dcd7-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span></span>   
 [<span data-ttu-id="0dcd7-134">如何：获取目录中的文件集合</span><span class="sxs-lookup"><span data-stu-id="0dcd7-134">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

