---
title: 如何：在 Visual Basic 中将具有特定模式的文件复制到目录中
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
ms.openlocfilehash: 6b8df24014cf809326993958472df4dae213dbab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="4d29b-102">如何：在 Visual Basic 中将具有特定模式的文件复制到目录中</span><span class="sxs-lookup"><span data-stu-id="4d29b-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>
<span data-ttu-id="4d29b-103"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> 方法返回表示文件的路径名的只读字符串集合。</span><span class="sxs-lookup"><span data-stu-id="4d29b-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="4d29b-104">可以使用 `wildCards` 参数来指定特定模式。</span><span class="sxs-lookup"><span data-stu-id="4d29b-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="4d29b-105">如果找不到匹配的文件，则返回空集合。</span><span class="sxs-lookup"><span data-stu-id="4d29b-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="4d29b-106">可以使用 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> 方法将文件复制到目录。</span><span class="sxs-lookup"><span data-stu-id="4d29b-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="4d29b-107">将具有特定模式的文件复制到目录中</span><span class="sxs-lookup"><span data-stu-id="4d29b-107">To copy files with a specific pattern to a directory</span></span>  
  
1.  <span data-ttu-id="4d29b-108">使用 `GetFiles` 方法返回文件的列表。</span><span class="sxs-lookup"><span data-stu-id="4d29b-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="4d29b-109">此示例在指定的目录中返回所有 .rtf 文件。</span><span class="sxs-lookup"><span data-stu-id="4d29b-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     [!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]  
  
2.  <span data-ttu-id="4d29b-110">使用 `CopyFile` 方法复制文件。</span><span class="sxs-lookup"><span data-stu-id="4d29b-110">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="4d29b-111">此示例将文件复制到名为 `testdirectory`的目录中。</span><span class="sxs-lookup"><span data-stu-id="4d29b-111">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]  
  
3.  <span data-ttu-id="4d29b-112">使用 `For` 语句关闭 `Next` 语句。</span><span class="sxs-lookup"><span data-stu-id="4d29b-112">Close the `For` statement with a `Next` statement.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="4d29b-113">示例</span><span class="sxs-lookup"><span data-stu-id="4d29b-113">Example</span></span>  
 <span data-ttu-id="4d29b-114">下面的示例完整地显示了上述代码片段，该示例将指定目录中的所有 .rtf 文件复制到名为 `testdirectory`的目录。</span><span class="sxs-lookup"><span data-stu-id="4d29b-114">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 [!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="4d29b-115">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="4d29b-115">.NET Framework Security</span></span>  
 <span data-ttu-id="4d29b-116">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="4d29b-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4d29b-117">路径由于以下原因之一而无效：是零长度字符串；仅为空白；包含无效字符；是一个设备路径（开头字符为 \\\\.\\）(<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4d29b-118">路径无效，因为它是 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="4d29b-119">目录不存在 (<xref:System.IO.DirectoryNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-119">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="4d29b-120">指向某个现有文件的目录 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-120">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4d29b-121">路径超过了系统定义的最大长度 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="4d29b-122">路径中的文件名或目录名包含冒号 (:)，或格式无效 (<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="4d29b-123">该用户缺少查看该路径所必需的权限 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="4d29b-124">该用户缺少必要的权限 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="4d29b-124">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d29b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d29b-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>  
 [<span data-ttu-id="4d29b-126">如何：查找具有特定模式的子目录</span><span class="sxs-lookup"><span data-stu-id="4d29b-126">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)  
 [<span data-ttu-id="4d29b-127">疑难解答：读取和写入文本文件</span><span class="sxs-lookup"><span data-stu-id="4d29b-127">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 [<span data-ttu-id="4d29b-128">如何：获取目录中的文件集合</span><span class="sxs-lookup"><span data-stu-id="4d29b-128">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
