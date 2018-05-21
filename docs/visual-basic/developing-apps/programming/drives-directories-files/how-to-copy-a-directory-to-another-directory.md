---
title: 如何：在 Visual Basic 中将一个目录复制到另一个目录
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
ms.openlocfilehash: 9b6e095d061619cf9d2e2d87a7247cbdbc51cbe2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a><span data-ttu-id="4e2bd-102">如何：在 Visual Basic 中将一个目录复制到另一个目录</span><span class="sxs-lookup"><span data-stu-id="4e2bd-102">How to: Copy a Directory to Another Directory in Visual Basic</span></span>
<span data-ttu-id="4e2bd-103">使用 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> 方法将一个目录复制到另一个目录。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-103">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> method to copy a directory to another directory.</span></span> <span data-ttu-id="4e2bd-104">此方法复制目录的内容以及目录本身。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-104">This method copies the contents of the directory as well as the directory itself.</span></span> <span data-ttu-id="4e2bd-105">如果目标目录不存在，则将创建它。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-105">If the target directory does not exist, it will be created.</span></span> <span data-ttu-id="4e2bd-106">如果目标位置中存在具有相同名称的目录，并且 `overwrite` 设置为 `False`，则将合并这两个目录的内容。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-106">If a directory with the same name exists in the target location and `overwrite` is set to `False`, the contents of the two directories will be merged.</span></span> <span data-ttu-id="4e2bd-107">操作期间可为此目录指定新名称。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-107">You can specify a new name for the directory during the operation.</span></span>  
  
 <span data-ttu-id="4e2bd-108">复制目录中的文件时，可能会因特定文件引发异常，例如将 `overwrite` 设为 `False`，在合并期间存在的文件。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-108">When copying files within a directory, exceptions may be thrown that are caused by specific file, such as a file existing during a merge while `overwrite` is set to `False`.</span></span> <span data-ttu-id="4e2bd-109">如果引发此类异常，那么这些异常将合并为一个异常，其 `Data` 属性保存的条目中文件或目录路径为键，特定的异常消息包含在对应的值中。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-109">When such exceptions are thrown, they are consolidated into a single exception, whose `Data` property holds entries in which the file or directory path is the key and the specific exception message is contained in the corresponding value.</span></span>  
  
### <a name="to-copy-a-directory-to-another-directory"></a><span data-ttu-id="4e2bd-110">将目录复制到另一个目录</span><span class="sxs-lookup"><span data-stu-id="4e2bd-110">To copy a directory to another directory</span></span>  
  
-   <span data-ttu-id="4e2bd-111">使用 `CopyDirectory` 方法指定源和目标目录名称。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-111">Use the `CopyDirectory` method, specifying source and destination directory names.</span></span> <span data-ttu-id="4e2bd-112">下面的示例将名为 `TestDirectory1` 的目录复制到 `TestDirectory2`，并覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-112">The following example copies the directory named `TestDirectory1` into `TestDirectory2`, overwriting existing files.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]  
  
     <span data-ttu-id="4e2bd-113">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-113">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="4e2bd-114">在代码片段选取器中，该代码段位于“文件系统 - 处理驱动器、文件夹和文件”。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-114">In the code snippet picker, it is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="4e2bd-115">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-115">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e2bd-116">可靠编程</span><span class="sxs-lookup"><span data-stu-id="4e2bd-116">Robust Programming</span></span>  
 <span data-ttu-id="4e2bd-117">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="4e2bd-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4e2bd-118">为目录指定的新名称包含冒号 (:) 和斜杠（\ 或 /）(<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-118">The new name specified for the directory contains a colon (:) or slash (\ or /) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-119">路径由于以下原因之一无效：是零长度字符串；仅包含空白；包含无效字符；是一个设备路径（开头字符为 \\\\.\\）(<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-120">路径无效，因为它是 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-121">`destinationDirectoryName` 为 `Nothing` 或空字符串 (<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="4e2bd-121">`destinationDirectoryName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="4e2bd-122">源目录不存在 (<xref:System.IO.DirectoryNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-122">The source directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-123">源目录是一个根目录 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-123">The source directory is a root directory (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-124">合并路径指向现有文件 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-124">The combined path points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-125">源路径和目标路径相同 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-125">The source path and target path are the same (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-126">`ShowUI` 设为 `UIOption.AllDialogs`，并且用户取消了操作，或不能复制目录中的一个或多个文件 (<xref:System.OperationCanceledException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-126">`ShowUI` is set to `UIOption.AllDialogs` and the user cancels the operation, or one or more files in the directory cannot be copied (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-127">操作是循环的 (<xref:System.InvalidOperationException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-127">The operation is cyclic (<xref:System.InvalidOperationException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-128">路径包含一个冒号 (:) (<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-128">The path contains a colon (:) (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-129">路径超过了系统定义的最大长度 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-129">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-130">路径中的文件名或文件夹名包含冒号 (:)，或其格式无效 (<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-130">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-131">该用户缺少查看该路径所必需的权限 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-131">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="4e2bd-132">目标文件存在，但不能访问 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="4e2bd-132">A destination file exists but cannot be accessed (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2bd-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e2bd-133">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>  
 [<span data-ttu-id="4e2bd-134">如何：查找具有特定模式的子目录</span><span class="sxs-lookup"><span data-stu-id="4e2bd-134">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)  
 [<span data-ttu-id="4e2bd-135">如何：获取目录中的文件集合</span><span class="sxs-lookup"><span data-stu-id="4e2bd-135">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
