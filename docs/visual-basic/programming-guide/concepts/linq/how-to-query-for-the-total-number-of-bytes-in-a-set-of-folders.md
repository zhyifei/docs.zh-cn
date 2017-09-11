---
title: "如何︰ 查询一组文件夹 (LINQ) (Visual Basic 中) 中的字节总数 |Microsoft 文档"
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
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
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
ms.openlocfilehash: bda25acd3065898eeb61dce83d46d7526e825add
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a><span data-ttu-id="b02b4-102">如何︰ 查询一组文件夹 (LINQ) (Visual Basic 中) 中的字节总数</span><span class="sxs-lookup"><span data-stu-id="b02b4-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="b02b4-103">此示例演示如何检索由指定的文件夹中的所有文件和所有子文件夹所用的字节总数。</span><span class="sxs-lookup"><span data-stu-id="b02b4-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b02b4-104">示例</span><span class="sxs-lookup"><span data-stu-id="b02b4-104">Example</span></span>  
 <span data-ttu-id="b02b4-105"><xref:System.Linq.Enumerable.Sum%2A>方法中所选的所有项的值相加时`select`子句。</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="b02b4-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="b02b4-106">您可以轻松地修改此查询以检索在指定的目录树中的最大或最小文件通过调用<xref:System.Linq.Enumerable.Min%2A>或<xref:System.Linq.Enumerable.Max%2A>而不是<xref:System.Linq.Enumerable.Sum%2A>。</xref:System.Linq.Enumerable.Sum%2A>方法</xref:System.Linq.Enumerable.Max%2A></xref:System.Linq.Enumerable.Min%2A></span><span class="sxs-lookup"><span data-stu-id="b02b4-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="b02b4-107">如果只需要计算指定的目录树中的字节数，可以执行此操作而无需创建一个 LINQ 查询，因此这样会导致创建列表集合作为数据源的系统开销的效率。</span><span class="sxs-lookup"><span data-stu-id="b02b4-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="b02b4-108">随着查询变得更加复杂，或者在您需要对同一数据源运行多个查询时，会增加 LINQ 方法的实用性。</span><span class="sxs-lookup"><span data-stu-id="b02b4-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="b02b4-109">查询调用到一个单独的方法来获取文件长度。</span><span class="sxs-lookup"><span data-stu-id="b02b4-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="b02b4-110">这是为了使用可能的异常︰ 如果在另一个线程后删除了该文件将会引发<xref:System.IO.FileInfo>对的调用中创建对象`GetFiles`。</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="b02b4-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="b02b4-111">即使<xref:System.IO.FileInfo>对象已创建，会发生异常因为<xref:System.IO.FileInfo>对象将尝试刷新其<xref:System.IO.FileInfo.Length%2A>属性与第一次访问此属性的最新长度。</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="b02b4-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="b02b4-112">通过将此操作放在查询外的一个 try catch 块中，该代码遵循避免在可能会导致的副作用的查询操作的规则。</span><span class="sxs-lookup"><span data-stu-id="b02b4-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="b02b4-113">一般情况下，当使用例外，以确保应用程序不会保留处于未知状态时，必须格外谨慎。</span><span class="sxs-lookup"><span data-stu-id="b02b4-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b02b4-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="b02b4-114">Compiling the Code</span></span>  
 <span data-ttu-id="b02b4-115">创建一个面向.NET Framework 版本 3.5 或更高版本对 System.Core.dll 的引用与项目和一个`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="b02b4-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02b4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b02b4-116">See Also</span></span>  
 <span data-ttu-id="b02b4-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="b02b4-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="b02b4-118"> [LINQ 和文件目录 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="b02b4-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
