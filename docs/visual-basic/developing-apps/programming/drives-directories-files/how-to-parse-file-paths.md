---
title: "如何：在 Visual Basic 中分析文件路径"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 913fe45cf6fc7afdc6e0f31e028bc18808cecf89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="c195c-102">如何：在 Visual Basic 中分析文件路径</span><span class="sxs-lookup"><span data-stu-id="c195c-102">How to: Parse File Paths in Visual Basic</span></span>
<span data-ttu-id="c195c-103">分析文件路径时，可参考 <xref:Microsoft.VisualBasic.FileIO.FileSystem> 对象提供的多种有用的方法。</span><span class="sxs-lookup"><span data-stu-id="c195c-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
-   <span data-ttu-id="c195c-104"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> 方法采用了两个路径并返回格式正确的组合路径。</span><span class="sxs-lookup"><span data-stu-id="c195c-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
-   <span data-ttu-id="c195c-105"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> 方法将返回所提供的路径的父级的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="c195c-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
-   <span data-ttu-id="c195c-106"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 方法将返回一个 <xref:System.IO.FileInfo> 对象，查询该对象可确定文件的属性，例如文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="c195c-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="c195c-107">不要根据文件的扩展名来判断文件的内容。</span><span class="sxs-lookup"><span data-stu-id="c195c-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="c195c-108">例如，文件 Form1.vb 可能不是 Visual Basic 源文件。</span><span class="sxs-lookup"><span data-stu-id="c195c-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="c195c-109">确定文件的名称和路径</span><span class="sxs-lookup"><span data-stu-id="c195c-109">To determine a file's name and path</span></span>  
  
-   <span data-ttu-id="c195c-110">可使用 <xref:System.IO.FileInfo.DirectoryName%2A> 对象的 <xref:System.IO.FileInfo.Name%2A> 和 <xref:System.IO.FileInfo> 属性来确定文件的名称和路径。</span><span class="sxs-lookup"><span data-stu-id="c195c-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="c195c-111">此示例确定了名称和路径，并将其显示了出来。</span><span class="sxs-lookup"><span data-stu-id="c195c-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="c195c-112">组合文件的名称和目录以创建完整的路径</span><span class="sxs-lookup"><span data-stu-id="c195c-112">To combine a file's name and directory to create the full path</span></span>  
  
-   <span data-ttu-id="c195c-113">使用 `CombinePath` 方法，用于提供目录和名称。</span><span class="sxs-lookup"><span data-stu-id="c195c-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="c195c-114">此示例采用了上例中创建的字符串 `folderPath` 和 `fileName` ，然后将其组合在一起并显示结果。</span><span class="sxs-lookup"><span data-stu-id="c195c-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c195c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c195c-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>  
 <xref:System.IO.FileInfo>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>  
 [<span data-ttu-id="c195c-116">如何：获取目录中的文件集合</span><span class="sxs-lookup"><span data-stu-id="c195c-116">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
