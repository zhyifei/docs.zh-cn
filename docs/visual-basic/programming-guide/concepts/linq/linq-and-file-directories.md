---
title: "LINQ 和文件目录 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b9e814c9e9f8519522f288657d6940b07a0b3094
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-file-directories-visual-basic"></a><span data-ttu-id="f3223-102">LINQ 和文件目录 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3223-102">LINQ and File Directories (Visual Basic)</span></span>
<span data-ttu-id="f3223-103">许多文件系统操作实质上是查询，因此非常适合 LINQ 方法。</span><span class="sxs-lookup"><span data-stu-id="f3223-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="f3223-104">请注意，本部分中的查询非破坏性。</span><span class="sxs-lookup"><span data-stu-id="f3223-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="f3223-105">它们不用于更改原始文件或文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="f3223-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="f3223-106">这遵循该规则查询不应引起任何副作用。</span><span class="sxs-lookup"><span data-stu-id="f3223-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="f3223-107">一般情况下，修改源数据的任何代码 （包括执行的查询创建 / 更新 / 删除运算符） 应始终独立于只查询数据的代码。</span><span class="sxs-lookup"><span data-stu-id="f3223-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="f3223-108">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="f3223-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="f3223-109">如何︰ 查询具有指定的特性或名称 (Visual Basic 中) 的文件</span><span class="sxs-lookup"><span data-stu-id="f3223-109">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="f3223-110">演示如何通过检查一个或多个属性文件中搜索其<xref:System.IO.FileInfo>对象。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="f3223-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="f3223-111">如何︰ 通过扩展 (LINQ) (Visual Basic 中) 的文件进行分组</span><span class="sxs-lookup"><span data-stu-id="f3223-111">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="f3223-112">演示如何返回组<xref:System.IO.FileInfo>对象基于其文件扩展名。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="f3223-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="f3223-113">如何︰ 查询一组文件夹 (LINQ) (Visual Basic 中) 中的字节总数</span><span class="sxs-lookup"><span data-stu-id="f3223-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 <span data-ttu-id="f3223-114">演示如何返回指定的目录树中的所有文件中的总字节数。</span><span class="sxs-lookup"><span data-stu-id="f3223-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="f3223-115">[如何︰ 比较两个文件夹 (LINQ) (Visual Basic 中) 的内容](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span><span class="sxs-lookup"><span data-stu-id="f3223-115">[How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="f3223-116">演示如何返回两个指定的文件夹中存在的所有文件和也的所有文件都位于一个文件夹，但不是在其他。</span><span class="sxs-lookup"><span data-stu-id="f3223-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="f3223-117">如何︰ 查询多个最大文件或目录树 (LINQ) (Visual Basic 中) 中的文件</span><span class="sxs-lookup"><span data-stu-id="f3223-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 <span data-ttu-id="f3223-118">演示如何在目录树中返回的最大或最小的文件或指定的数量的文件。</span><span class="sxs-lookup"><span data-stu-id="f3223-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="f3223-119">如何︰ 查询目录树 (LINQ) (Visual Basic 中) 中的重复文件</span><span class="sxs-lookup"><span data-stu-id="f3223-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="f3223-120">演示如何在指定的目录树中的多个位置中发生的所有文件名称的都组。</span><span class="sxs-lookup"><span data-stu-id="f3223-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="f3223-121">此外演示如何执行更复杂的比较基于自定义比较器。</span><span class="sxs-lookup"><span data-stu-id="f3223-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="f3223-122">如何︰ 查询文件夹 (LINQ) (Visual Basic 中) 中的文件的内容</span><span class="sxs-lookup"><span data-stu-id="f3223-122">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 <span data-ttu-id="f3223-123">演示如何遍历树中的文件夹，打开每个文件，以及查询文件的内容。</span><span class="sxs-lookup"><span data-stu-id="f3223-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="f3223-124">注释</span><span class="sxs-lookup"><span data-stu-id="f3223-124">Comments</span></span>  
 <span data-ttu-id="f3223-125">在创建的数据源，准确地表示文件系统的内容，并能正确处理异常时涉及是某种程度的复杂性。</span><span class="sxs-lookup"><span data-stu-id="f3223-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="f3223-126">本部分中的示例创建的快照集合<xref:System.IO.FileInfo>对象，表示指定的根文件夹下的所有文件和所有子文件夹。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="f3223-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="f3223-127">实际状态的每个<xref:System.IO.FileInfo>在何时开始和结束执行查询之间的时间可能会更改。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="f3223-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="f3223-128">例如，您可以创建一份<xref:System.IO.FileInfo>要用作数据源对象。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="f3223-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="f3223-129">如果您尝试访问`Length`属性在查询中，<xref:System.IO.FileInfo>对象将尝试访问文件系统来更新的值`Length`。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="f3223-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="f3223-130">如果该文件不再存在，则会出现<xref:System.IO.FileNotFoundException>在查询中，即使您不文件系统直接查询。</xref:System.IO.FileNotFoundException></span><span class="sxs-lookup"><span data-stu-id="f3223-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="f3223-131">本部分中的某些查询使用一个单独的方法使用在某些情况下这些特定异常。</span><span class="sxs-lookup"><span data-stu-id="f3223-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="f3223-132">另一个选项是使您通过使用<xref:System.IO.FileSystemWatcher>。</xref:System.IO.FileSystemWatcher>动态更新的数据源</span><span class="sxs-lookup"><span data-stu-id="f3223-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3223-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3223-133">See Also</span></span>  
 [<span data-ttu-id="f3223-134">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3223-134">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
