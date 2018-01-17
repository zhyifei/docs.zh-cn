---
title: "如何：在 Visual Basic 中创建文件"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1ce74601136c870097d6d558e1f3ff12ba1c212
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-file-in-visual-basic"></a><span data-ttu-id="acf83-102">如何：在 Visual Basic 中创建文件</span><span class="sxs-lookup"><span data-stu-id="acf83-102">How to: Create a File in Visual Basic</span></span>
<span data-ttu-id="acf83-103">此示例使用 <xref:System.IO.File> 类中的 <xref:System.IO.File.Create%2A> 方法在指定的路径中创建一个空文本文件。</span><span class="sxs-lookup"><span data-stu-id="acf83-103">This example creates an empty text file at the specified path using the <xref:System.IO.File.Create%2A> method in the <xref:System.IO.File> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acf83-104">示例</span><span class="sxs-lookup"><span data-stu-id="acf83-104">Example</span></span>  
 [!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="acf83-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="acf83-105">Compiling the Code</span></span>  
 <span data-ttu-id="acf83-106">使用 `file` 变量写入文件。</span><span class="sxs-lookup"><span data-stu-id="acf83-106">Use the `file` variable to write to the file.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="acf83-107">可靠编程</span><span class="sxs-lookup"><span data-stu-id="acf83-107">Robust Programming</span></span>  
 <span data-ttu-id="acf83-108">如果该文件已存在，则替换它。</span><span class="sxs-lookup"><span data-stu-id="acf83-108">If the file already exists, it is replaced.</span></span>  
  
 <span data-ttu-id="acf83-109">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="acf83-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="acf83-110">路径名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="acf83-110">The path name is malformed.</span></span> <span data-ttu-id="acf83-111">例如，它包含非法字符或仅为空白 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="acf83-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="acf83-112">路径是只读的 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="acf83-112">The path is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="acf83-113">路径名称为 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="acf83-113">The path name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="acf83-114">路径名称过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="acf83-114">The path name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="acf83-115">路径无效 (<xref:System.IO.DirectoryNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="acf83-115">The path is invalid (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="acf83-116">路径仅为冒号“:”(<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="acf83-116">The path is only a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="acf83-117">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="acf83-117">.NET Framework Security</span></span>  
 <span data-ttu-id="acf83-118">在部分信任的环境中可能引发 <xref:System.Security.SecurityException>。</span><span class="sxs-lookup"><span data-stu-id="acf83-118">A <xref:System.Security.SecurityException> may be thrown in partial-trust environments.</span></span>  
  
 <span data-ttu-id="acf83-119">调用 <xref:System.IO.File.Create%2A> 方法需要 <xref:System.Security.Permissions.FileIOPermission>。</span><span class="sxs-lookup"><span data-stu-id="acf83-119">The call to the <xref:System.IO.File.Create%2A> method requires <xref:System.Security.Permissions.FileIOPermission>.</span></span>  
  
 <span data-ttu-id="acf83-120">如果用户无权创建文件，将引发 <xref:System.UnauthorizedAccessException>。</span><span class="sxs-lookup"><span data-stu-id="acf83-120">An <xref:System.UnauthorizedAccessException> is thrown if the user does not have permission to create the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf83-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="acf83-121">See Also</span></span>  
 <xref:System.IO>  
 <xref:System.IO.File.Create%2A>  
 [<span data-ttu-id="acf83-122">通过部分受信任的代码使用库</span><span class="sxs-lookup"><span data-stu-id="acf83-122">Using Libraries from Partially Trusted Code</span></span>](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)  
 [<span data-ttu-id="acf83-123">代码访问安全性基础知识</span><span class="sxs-lookup"><span data-stu-id="acf83-123">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
