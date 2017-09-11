---
title: "如何︰ 使用 (Visual Basic 中) 的 LINQ 查询 ArrayList |Microsoft 文档"
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
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 59dd2fb9af093e2e27d5db75e0e7b886f47f2a57
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a><span data-ttu-id="51144-102">如何︰ 使用 (Visual Basic 中) 的 LINQ 查询 ArrayList</span><span class="sxs-lookup"><span data-stu-id="51144-102">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>
<span data-ttu-id="51144-103">当使用 LINQ 来查询非泛型<xref:System.Collections.IEnumerable>这类的集合<xref:System.Collections.ArrayList>，所以必须显式声明的范围变量，以反映在集合中的对象的特定类型的类型。</xref:System.Collections.ArrayList> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="51144-103">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="51144-104">例如，如果您有<xref:System.Collections.ArrayList>的`Student`对象，您[From 子句](../../../../visual-basic/language-reference/queries/from-clause.md)应如下所示︰</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="51144-104">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) should look like this:</span></span>  
  
```  
Dim query = From student As Student In arrList   
...  
```  
  
 <span data-ttu-id="51144-105">通过指定的范围变量的类型，您要强制转换中的每项<xref:System.Collections.ArrayList>到`Student`。</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="51144-105">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="51144-106">使用显式类型化的范围变量在查询表达式等效于调用<xref:System.Linq.Enumerable.Cast%2A>方法。</xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="51144-106">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="51144-107"><xref:System.Linq.Enumerable.Cast%2A>如果无法执行指定的强制转换，将引发异常。</xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="51144-107"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="51144-108"><xref:System.Linq.Enumerable.Cast%2A>和<xref:System.Linq.Enumerable.OfType%2A>是对非泛型操作的两个标准查询运算符方法<xref:System.Collections.IEnumerable>类型。</xref:System.Collections.IEnumerable> </xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="51144-108"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="51144-109">在 Visual Basic 中，您必须显式调用<xref:System.Linq.Enumerable.Cast%2A>方法要确保特定范围的变量类型的数据源。</xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="51144-109">In Visual Basic, you must explicitly call the <xref:System.Linq.Enumerable.Cast%2A> method on the data source to ensure a specific range variable type.</span></span> <span data-ttu-id="51144-110">有关详细信息，请参阅[查询操作 (Visual Basic 中) 中的类型关系](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="51144-110">For more information, see[Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51144-111">示例</span><span class="sxs-lookup"><span data-stu-id="51144-111">Example</span></span>  
 <span data-ttu-id="51144-112">下面的示例演示一个简单的查询对<xref:System.Collections.ArrayList>。</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="51144-112">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="51144-113">请注意，本示例使用对象初始值设定项，当代码调用<xref:System.Collections.ArrayList.Add%2A>方法，但这并不是必需。</xref:System.Collections.ArrayList.Add%2A></span><span class="sxs-lookup"><span data-stu-id="51144-113">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```vb  
Imports System.Collections  
Imports System.Linq  
  
Module Module1  
  
    Public Class Student  
        Public Property FirstName As String  
        Public Property LastName As String  
        Public Property Scores As Integer()  
    End Class  
  
    Sub Main()  
  
        Dim student1 As New Student With {.FirstName = "Svetlana",   
                                     .LastName = "Omelchenko",   
                                     .Scores = New Integer() {98, 92, 81, 60}}  
        Dim student2 As New Student With {.FirstName = "Claire",   
                                    .LastName = "O'Donnell",   
                                    .Scores = New Integer() {75, 84, 91, 39}}  
        Dim student3 As New Student With {.FirstName = "Cesar",   
                                    .LastName = "Garcia",   
                                    .Scores = New Integer() {97, 89, 85, 82}}  
        Dim student4 As New Student With {.FirstName = "Sven",   
                                    .LastName = "Mortensen",   
                                    .Scores = New Integer() {88, 94, 65, 91}}  
  
        Dim arrList As New ArrayList()  
        arrList.Add(student1)  
        arrList.Add(student2)  
        arrList.Add(student3)  
        arrList.Add(student4)  
  
        ' Use an explicit type for non-generic collections  
        Dim query = From student As Student In arrList   
                    Where student.Scores(0) > 95   
                    Select student  
  
        For Each student As Student In query  
            Console.WriteLine(student.LastName & ": " & student.Scores(0))  
        Next  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Module  
' Output:  
'   Omelchenko: 98  
'   Garcia: 97  
```  
  
## <a name="see-also"></a><span data-ttu-id="51144-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51144-114">See Also</span></span>  
 [<span data-ttu-id="51144-115">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51144-115">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

