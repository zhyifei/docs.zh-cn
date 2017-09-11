---
title: "如何︰ 查找两个列表 (LINQ) (Visual Basic 中) 之间的差集 |Microsoft 文档"
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
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
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
ms.openlocfilehash: 9c00a66c79e080211c92457c0194462698fee98f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="dbd79-102">如何︰ 查找两个列表 (LINQ) (Visual Basic 中) 之间的差集</span><span class="sxs-lookup"><span data-stu-id="dbd79-102">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="dbd79-103">此示例演示如何使用 LINQ 来比较两个列表的字符串和输出 names1.txt 而不在 names2.txt 的那些行。</span><span class="sxs-lookup"><span data-stu-id="dbd79-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="dbd79-104">若要创建的数据文件</span><span class="sxs-lookup"><span data-stu-id="dbd79-104">To create the data files</span></span>  
  
1.  <span data-ttu-id="dbd79-105">Names1.txt names2.txt 复制到您的解决方案文件夹中，如中所示[如何︰ 组合和比较字符串集合 (LINQ) (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd79-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbd79-106">示例</span><span class="sxs-lookup"><span data-stu-id="dbd79-106">Example</span></span>  
  
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
  
 <span data-ttu-id="dbd79-107">某些类型的查询在 Visual Basic 中的操作如<xref:System.Linq.Enumerable.Except%2A>， <xref:System.Linq.Enumerable.Distinct%2A>， <xref:System.Linq.Enumerable.Union%2A>，和<xref:System.Linq.Enumerable.Concat%2A>，只能在基于方法的语法中表示。</xref:System.Linq.Enumerable.Concat%2A> </xref:System.Linq.Enumerable.Union%2A> </xref:System.Linq.Enumerable.Distinct%2A> </xref:System.Linq.Enumerable.Except%2A></span><span class="sxs-lookup"><span data-stu-id="dbd79-107">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dbd79-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="dbd79-108">Compiling the Code</span></span>  
 <span data-ttu-id="dbd79-109">创建一个面向.NET Framework 版本 3.5 或更高版本对 System.Core.dll 的引用与项目和一个`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="dbd79-109">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd79-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbd79-110">See Also</span></span>  
 [<span data-ttu-id="dbd79-111">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbd79-111">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
