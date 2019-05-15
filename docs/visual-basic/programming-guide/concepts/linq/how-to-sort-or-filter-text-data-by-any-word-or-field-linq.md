---
title: 如何：排序或筛选器文本数据，按任意词或字段 (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9df137fe-335b-46e0-aecf-ea8a9eddd4e3
ms.openlocfilehash: 5d6a8d26f28feafecfbddfb8d2b538adc22f1b90
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592463"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-visual-basic"></a><span data-ttu-id="64374-102">如何：排序或筛选器文本数据，按任意词或字段 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64374-102">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="64374-103">下面的示例演示如何按行中的任何字段对结构化文本（如以逗号分隔的值）行进行排序。</span><span class="sxs-lookup"><span data-stu-id="64374-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="64374-104">可以在运行时动态指定字段。</span><span class="sxs-lookup"><span data-stu-id="64374-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="64374-105">假定 scores.csv 中的字段表示学生的 ID 号，后跟一系列四个测试分数。</span><span class="sxs-lookup"><span data-stu-id="64374-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>  
  
### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="64374-106">创建包含数据的文件</span><span class="sxs-lookup"><span data-stu-id="64374-106">To create a file that contains data</span></span>  
  
1. <span data-ttu-id="64374-107">从主题[如何：联接内容从不同的文件 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)并将其保存到你的解决方案文件夹。</span><span class="sxs-lookup"><span data-stu-id="64374-107">Copy the scores.csv data from the topic [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64374-108">示例</span><span class="sxs-lookup"><span data-stu-id="64374-108">Example</span></span>  
  
```vb  
Class SortLines  
  
    Shared Sub Main()  
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' Change this to any value from 0 to 4  
        Dim sortField As Integer = 1  
  
        Console.WriteLine("Sorted highest to lowest by field " & sortField)  
  
        ' Demonstrates how to return query from a method.  
        ' The query is executed here.  
        For Each str As String In SortQuery(scores, sortField)  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    Shared Function SortQuery(  
        ByVal source As IEnumerable(Of String),   
        ByVal num As Integer) As IEnumerable(Of String)  
  
        Dim scoreQuery = From line In source   
                         Let fields = line.Split(New Char() {","})   
                         Order By fields(num) Descending   
                         Select line  
  
        Return scoreQuery  
    End Function  
End Class  
' Output:  
' Sorted highest to lowest by field 1  
' 116, 99, 86, 90, 94  
' 120, 99, 82, 81, 79  
' 111, 97, 92, 81, 60  
' 114, 97, 89, 85, 82  
' 121, 96, 85, 91, 60  
' 122, 94, 92, 91, 91  
' 117, 93, 92, 80, 87  
' 118, 92, 90, 83, 78  
' 113, 88, 94, 65, 91  
' 112, 75, 84, 91, 39  
' 119, 68, 79, 88, 92  
' 115, 35, 72, 91, 70  
```  
  
 <span data-ttu-id="64374-109">此示例还演示如何从函数返回查询变量。</span><span class="sxs-lookup"><span data-stu-id="64374-109">This example also demonstrates how to return a query variable from a Function.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="64374-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="64374-110">Compiling the Code</span></span>  
<span data-ttu-id="64374-111">创建一个 VB.NET 控制台应用程序项目，与`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="64374-111">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64374-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="64374-112">See also</span></span>

- [<span data-ttu-id="64374-113">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64374-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
