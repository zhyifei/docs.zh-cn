---
title: "如何：在 Visual Basic 中创建目录"
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
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
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
ms.openlocfilehash: 1a45a785916b480dcee6e36fd295390266eaa0a0
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="78333-102">如何：在 Visual Basic 中创建目录</span><span class="sxs-lookup"><span data-stu-id="78333-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="78333-103">使用 `My.Computer.FileSystem` 对象的 `CreateDirectory` 方法来创建目录。</span><span class="sxs-lookup"><span data-stu-id="78333-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="78333-104">如果该目录已存在，则不引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="78333-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="78333-105">创建目录</span><span class="sxs-lookup"><span data-stu-id="78333-105">To create a directory</span></span>  
  
-   <span data-ttu-id="78333-106">使用 `CreateDirectory` 方法，指定将在其中创建目录的位置的完整路径。</span><span class="sxs-lookup"><span data-stu-id="78333-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="78333-107">此示例在 `NewDirectory` 中创建目录 `C:\Documents and Settings\All Users\Documents`。</span><span class="sxs-lookup"><span data-stu-id="78333-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     <span data-ttu-id="78333-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="78333-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="78333-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="78333-109">Robust Programming</span></span>  
 <span data-ttu-id="78333-110">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="78333-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="78333-111">目录名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="78333-111">The directory name is malformed.</span></span> <span data-ttu-id="78333-112">例如，它包含非法字符或仅为空白 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="78333-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="78333-113">要创建的目录的父目录为只读 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="78333-113">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="78333-114">目录名称为 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="78333-114">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="78333-115">目录名称过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="78333-115">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="78333-116">目录名称是一个冒号“:”(<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="78333-116">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="78333-117">用户无权创建目录 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="78333-117">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="78333-118">用户在部分信任情况下缺少权限 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="78333-118">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78333-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78333-119">See Also</span></span>  
 <span data-ttu-id="78333-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="78333-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span></span>   
 [<span data-ttu-id="78333-121">创建、删除和移动文件和目录</span><span class="sxs-lookup"><span data-stu-id="78333-121">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)

