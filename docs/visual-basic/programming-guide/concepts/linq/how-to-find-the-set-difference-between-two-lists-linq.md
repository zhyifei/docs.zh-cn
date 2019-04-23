---
title: 如何：查找两个列表 (LINQ) (Visual Basic 中) 之间的差集
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: 3757a588ed37805d6dd2569e1d25b07bd166c2d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324053"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="9b692-102">如何：查找两个列表 (LINQ) (Visual Basic 中) 之间的差集</span><span class="sxs-lookup"><span data-stu-id="9b692-102">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="9b692-103">此示例演示如何使用 LINQ 对两个字符串列表进行比较，并输出那些位于 names1.txt 中但不在 names2.txt 中的行。</span><span class="sxs-lookup"><span data-stu-id="9b692-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="9b692-104">创建数据文件</span><span class="sxs-lookup"><span data-stu-id="9b692-104">To create the data files</span></span>  
  
1. <span data-ttu-id="9b692-105">按照[如何：合并和比较字符串集合 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="9b692-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b692-106">示例</span><span class="sxs-lookup"><span data-stu-id="9b692-106">Example</span></span>  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 <span data-ttu-id="9b692-107">某些类型的查询在 Visual Basic 中的操作，例如<xref:System.Linq.Enumerable.Except%2A>， <xref:System.Linq.Enumerable.Distinct%2A>， <xref:System.Linq.Enumerable.Union%2A>，和<xref:System.Linq.Enumerable.Concat%2A>，仅采用基于方法的语法进行表示。</span><span class="sxs-lookup"><span data-stu-id="9b692-107">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b692-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="9b692-108">Compiling the Code</span></span>  
 <span data-ttu-id="9b692-109">创建面向 .NET Framework 3.5 或更高版本的项目，此项目包含对 System.Core.dll 的引用和用于 System.Linq 命名空间的 `Imports` 语句。</span><span class="sxs-lookup"><span data-stu-id="9b692-109">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b692-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b692-110">See also</span></span>

- [<span data-ttu-id="9b692-111">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b692-111">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
