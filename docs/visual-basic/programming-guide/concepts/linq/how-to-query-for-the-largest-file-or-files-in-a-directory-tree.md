---
title: "如何︰ 查询多个最大文件或目录树 (LINQ) (Visual Basic 中) 中的文件 |Microsoft 文档"
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
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
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
ms.openlocfilehash: 95c5197b2cb66745201ceac89b78fe67b95ecb75
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="5e6b4-102">如何：查询目录树中的一个或多个最大的文件 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e6b4-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="5e6b4-103">此示例演示与文件大小 （字节） 相关的五个查询︰</span><span class="sxs-lookup"><span data-stu-id="5e6b4-103">This example shows five queries related to file size in bytes:</span></span>  
  
-   <span data-ttu-id="5e6b4-104">如何检索以字节为单位的最大文件大小。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
-   <span data-ttu-id="5e6b4-105">如何检索以字节为单位的最小文件大小。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
-   <span data-ttu-id="5e6b4-106">如何检索<xref:System.IO.FileInfo>从指定的根文件夹下的一个或多个文件夹的对象大或最小文件。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5e6b4-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
-   <span data-ttu-id="5e6b4-107">如何检索一个序列，如 10 个最大文件。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
-   <span data-ttu-id="5e6b4-108">如何为基于其文件大小 （字节），忽略小于指定大小的文件的组的顺序文件。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e6b4-109">示例</span><span class="sxs-lookup"><span data-stu-id="5e6b4-109">Example</span></span>  
 <span data-ttu-id="5e6b4-110">下面的示例包含五个单独的查询显示如何查询和组文件，具体取决于其文件大小 （字节）。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="5e6b4-111">您可以轻松地修改这些示例查询所基于的其他某些属性<xref:System.IO.FileInfo>对象。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5e6b4-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="5e6b4-112">返回一个或多个完成<xref:System.IO.FileInfo>对象，该查询必须首先检查数据中的每个源，然后对它们进行分类的 Length 属性的值。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5e6b4-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="5e6b4-113">然后，它可返回单个对象或序列具有最大长度。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="5e6b4-114">使用<xref:System.Linq.Enumerable.First%2A>来返回列表中的第一个元素。</xref:System.Linq.Enumerable.First%2A></span><span class="sxs-lookup"><span data-stu-id="5e6b4-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="5e6b4-115">使用<xref:System.Linq.Enumerable.Take%2A>返回前的 n 个元素。</xref:System.Linq.Enumerable.Take%2A></span><span class="sxs-lookup"><span data-stu-id="5e6b4-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="5e6b4-116">指定降序排序顺序，可将最小元素放在列表的开头。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="5e6b4-117">查询调用到单独的方法来获取文件大小 （字节），以便使用可能将在其中删除了某个文件在另一个线程自以来的时间段中的情况下引发的异常<xref:System.IO.FileInfo>对的调用中创建对象`GetFiles`。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5e6b4-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="5e6b4-118">即使完成<xref:System.IO.FileInfo>对象已创建，会发生异常因为<xref:System.IO.FileInfo>对象将尝试刷新其<xref:System.IO.FileInfo.Length%2A>使用最新的大小，以字节为单位第一次访问此属性的属性。</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="5e6b4-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="5e6b4-119">通过将此操作放在查询外的一个 try catch 块中，我们遵守规则，避免可能会导致的副作用的查询中的操作。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="5e6b4-120">一般情况下，必须要格外谨慎使用例外情况之外时, 若要确保应用程序不会保留处于未知状态。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5e6b4-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="5e6b4-121">Compiling the Code</span></span>  
 <span data-ttu-id="5e6b4-122">创建一个面向.NET Framework 版本 3.5 或更高版本对 System.Core.dll 的引用与项目和一个`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="5e6b4-122">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6b4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e6b4-123">See Also</span></span>  
 <span data-ttu-id="5e6b4-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="5e6b4-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="5e6b4-125"> [LINQ 和文件目录 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="5e6b4-125"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
