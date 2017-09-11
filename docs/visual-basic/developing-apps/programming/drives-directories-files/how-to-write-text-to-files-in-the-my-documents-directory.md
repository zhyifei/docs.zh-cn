---
title: "如何：在 Visual Basic 中将文本写入“我的文档”目录中的文件"
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
- examples [Visual Basic], text files
- writing to files, in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
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
ms.openlocfilehash: c900072d184469ead75bb76a3e152edce357a34f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="70bd1-102">如何：在 Visual Basic 中将文本写入“我的文档”目录中的文件</span><span class="sxs-lookup"><span data-stu-id="70bd1-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="70bd1-103">`My.Computer.FileSystem.SpecialDirectories` 对象允许用户访问特殊目录，如 MyDocuments 目录。</span><span class="sxs-lookup"><span data-stu-id="70bd1-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="70bd1-104">过程</span><span class="sxs-lookup"><span data-stu-id="70bd1-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="70bd1-105">在“我的文档”目录中写入新的文本文件</span><span class="sxs-lookup"><span data-stu-id="70bd1-105">To write new text files in the My Documents directory</span></span>  
  
1.  <span data-ttu-id="70bd1-106">使用 `My.Computer.FileSystem.SpecialDirectories.MyDocuments` 属性提供路径。</span><span class="sxs-lookup"><span data-stu-id="70bd1-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     <span data-ttu-id="70bd1-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="70bd1-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span></span>  
  
2.  <span data-ttu-id="70bd1-108">使用 `WriteAllText` 方法将文本写入指定文件。</span><span class="sxs-lookup"><span data-stu-id="70bd1-108">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     <span data-ttu-id="70bd1-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="70bd1-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="70bd1-110">示例</span><span class="sxs-lookup"><span data-stu-id="70bd1-110">Example</span></span>  
 <span data-ttu-id="70bd1-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="70bd1-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70bd1-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="70bd1-112">Compiling the Code</span></span>  
 <span data-ttu-id="70bd1-113">将 `test.txt` 替换为要写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="70bd1-113">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="70bd1-114">可靠编程</span><span class="sxs-lookup"><span data-stu-id="70bd1-114">Robust Programming</span></span>  
 <span data-ttu-id="70bd1-115">此代码会重新引发向文件写入文本时可能发生的所有异常。</span><span class="sxs-lookup"><span data-stu-id="70bd1-115">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="70bd1-116">可以通过使用 Windows 窗体控件（如限制用户选择有效文件名的 [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) 和 [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) 组件）减少引发异常的可能性。</span><span class="sxs-lookup"><span data-stu-id="70bd1-116">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) and the [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="70bd1-117">但是，使用这些控件并不能做到万无一失。</span><span class="sxs-lookup"><span data-stu-id="70bd1-117">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="70bd1-118">文件系统可以在用户选择文件和代码执行的间隙时间内更改。</span><span class="sxs-lookup"><span data-stu-id="70bd1-118">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="70bd1-119">因此，处理文件时，几乎总是需要处理异常。</span><span class="sxs-lookup"><span data-stu-id="70bd1-119">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="70bd1-120">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="70bd1-120">.NET Framework Security</span></span>  
 <span data-ttu-id="70bd1-121">如果在部分信任上下文中运行，该代码可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="70bd1-121">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="70bd1-122">有关详细信息，请参阅[代码访问安全性基础知识](https://msdn.microsoft.com/library/33tceax8)。</span><span class="sxs-lookup"><span data-stu-id="70bd1-122">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
 <span data-ttu-id="70bd1-123">此示例创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="70bd1-123">This example creates a new file.</span></span> <span data-ttu-id="70bd1-124">如果某个应用程序需要创建文件，则该应用程序需要文件夹的“创建”权限。</span><span class="sxs-lookup"><span data-stu-id="70bd1-124">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="70bd1-125">可使用访问控制列表设置权限。</span><span class="sxs-lookup"><span data-stu-id="70bd1-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="70bd1-126">如果文件已存在，则该应用程序只需要“写入”权限（这是较弱的权限）。</span><span class="sxs-lookup"><span data-stu-id="70bd1-126">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="70bd1-127">如有可能，在部署过程中创建文件，并且仅授予针对单个文件的“读取”权限（而不是针对文件夹授予“创建”权限）会更加安全。</span><span class="sxs-lookup"><span data-stu-id="70bd1-127">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="70bd1-128">此外，较安全的做法是将数据写入用户文件夹，而不是根文件夹或“Program Files”文件夹。</span><span class="sxs-lookup"><span data-stu-id="70bd1-128">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="70bd1-129">有关详细信息，请参阅 [ACL 技术概述](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045)。</span><span class="sxs-lookup"><span data-stu-id="70bd1-129">For more information, see [ACL Technology Overview](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bd1-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70bd1-130">See Also</span></span>  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>

