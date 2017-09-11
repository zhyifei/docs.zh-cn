---
title: "如何：在 Visual Basic 中创建文件"
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
- text files, creating
- files, creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
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
ms.openlocfilehash: d06d274b31afad0a437405d1679e0be7548f2e14
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="81605-102">如何：在 Visual Basic 中创建文件</span><span class="sxs-lookup"><span data-stu-id="81605-102">How to: Create a File in Visual Basic</span></span>
<span data-ttu-id="81605-103">此示例使用 <xref:System.IO.File> 类中的 <xref:System.IO.File.Create%2A> 方法在指定的路径中创建一个空文本文件。</span><span class="sxs-lookup"><span data-stu-id="81605-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81605-104">示例</span><span class="sxs-lookup"><span data-stu-id="81605-104">Example</span></span>  
 <span data-ttu-id="81605-105">[!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="81605-105">[!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81605-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="81605-106">Compiling the Code</span></span>  
 <span data-ttu-id="81605-107">使用 `file` 变量写入文件。</span><span class="sxs-lookup"><span data-stu-id="81605-107">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="81605-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="81605-108">Robust Programming</span></span>  
 <span data-ttu-id="81605-109">如果该文件已存在，则替换它。</span><span class="sxs-lookup"><span data-stu-id="81605-109">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="81605-110">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="81605-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="81605-111">路径名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="81605-111">The path name is malformed.</span></span> <span data-ttu-id="81605-112">例如，它包含非法字符或仅为空白 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="81605-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="81605-113">路径是只读的 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="81605-113">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="81605-114">路径名称为 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="81605-114">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="81605-115">路径名称过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="81605-115">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="81605-116">路径无效 (<xref:System.IO.DirectoryNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="81605-116">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="81605-117">路径仅为冒号“:”(<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="81605-117">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="81605-118">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="81605-118">.NET Framework Security</span></span>  
 <span data-ttu-id="81605-119">在部分信任的环境中可能引发 <xref:System.Security.SecurityException>。</span><span class="sxs-lookup"><span data-stu-id="81605-119">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="81605-120">调用 <xref:System.IO.File.Create%2A> 方法需要 <xref:System.Security.Permissions.FileIOPermission>。</span><span class="sxs-lookup"><span data-stu-id="81605-120">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="81605-121">如果用户无权创建文件，将引发 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="81605-121">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81605-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81605-122">See Also</span></span>  
 <span data-ttu-id="81605-123"><xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="81605-123"><xref:System.IO></span></span>   
 <span data-ttu-id="81605-124"><xref:System.IO.File.Create%2A></span><span class="sxs-lookup"><span data-stu-id="81605-124"><xref:System.IO.File.Create%2A></span></span>   
 <span data-ttu-id="81605-125">[通过部分受信任的代码使用库](../../../../framework/misc/using-libraries-from-partially-trusted-code.md) </span><span class="sxs-lookup"><span data-stu-id="81605-125">[Using Libraries from Partially Trusted Code](../../../../framework/misc/using-libraries-from-partially-trusted-code.md) </span></span>  
 [<span data-ttu-id="81605-126">代码访问安全性基础知识</span><span class="sxs-lookup"><span data-stu-id="81605-126">Code Access Security Basics</span></span>](https://msdn.microsoft.com/library/33tceax8)

