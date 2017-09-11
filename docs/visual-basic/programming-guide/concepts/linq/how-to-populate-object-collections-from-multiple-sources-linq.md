---
title: "如何︰ 从多个源 (LINQ) (Visual Basic 中) 填充对象集合 |Microsoft 文档"
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
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
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
ms.openlocfilehash: ab75113ca2609385db8be9d79563e7b71dfd0b5b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a><span data-ttu-id="9f580-102">如何︰ 从多个源 (LINQ) (Visual Basic 中) 填充对象集合</span><span class="sxs-lookup"><span data-stu-id="9f580-102">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="9f580-103">此示例演示如何将来自不同源的数据合并到一系列新的类型。</span><span class="sxs-lookup"><span data-stu-id="9f580-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f580-104">不要尝试将仍在数据库的数据的文件系统中的内存中数据。</span><span class="sxs-lookup"><span data-stu-id="9f580-104">Do not try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="9f580-105">这种跨域联接可以产生未定义的结果，因为联接操作可能定义为数据库查询和其他类型的源的不同方式。</span><span class="sxs-lookup"><span data-stu-id="9f580-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="9f580-106">此外，是这样的操作可能导致内存不足异常，如果数据库中的数据量足够大的风险。</span><span class="sxs-lookup"><span data-stu-id="9f580-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="9f580-107">若要加入数据从一个数据库复制到内存中的数据，首先调用`ToList`或`ToArray`对数据库查询，请然后对返回的集合中执行联接。</span><span class="sxs-lookup"><span data-stu-id="9f580-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="9f580-108">创建数据文件</span><span class="sxs-lookup"><span data-stu-id="9f580-108">To create the data file</span></span>  
  
-   <span data-ttu-id="9f580-109">如中所述，将 names.csv 和 scores.csv 文件复制到项目文件夹中， [How to︰ 内容加入从不同的文件 (LINQ) (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="9f580-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f580-110">示例</span><span class="sxs-lookup"><span data-stu-id="9f580-110">Example</span></span>  
 <span data-ttu-id="9f580-111">下面的示例演示如何使用命名的类型`Student`合并中存储数据的字符串的模拟以.csv 格式的电子表格数据的两个内存中集合。</span><span class="sxs-lookup"><span data-stu-id="9f580-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="9f580-112">字符串的第一个集合表示学生姓名和 Id，并且第二个集合表示学生 ID （在第一列） 和四次考试分数。</span><span class="sxs-lookup"><span data-stu-id="9f580-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="9f580-113">该 ID 用作外键。</span><span class="sxs-lookup"><span data-stu-id="9f580-113">The ID is used as the foreign key.</span></span>  
  
```vb  
Class Student  
    Public FirstName As String  
    Public LastName As String  
    Public ID As Integer  
    Public ExamScores As List(Of Integer)  
End Class  
  
Class PopulateCollection  
  
    Shared Sub Main()  
  
        ' Merge content from spreadsheets into a list of Student objects.  
  
        ' These data files are defined in How to: Join Content from   
        ' Dissimilar Files (LINQ).  
  
        ' Each line of names.csv consists of a last name, a first name, and an  
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111  
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")  
  
        ' Each line of scores.csv consists of an ID number and four test   
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60  
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' The following query merges the content of two dissimilar spreadsheets   
        ' based on common ID values.  
        ' Multiple From clauses are used instead of a Join clause  
        ' in order to store the results of scoreLine.Split.  
        ' Note the dynamic creation of a list of integers for the  
        ' ExamScores member. We skip the first item in the split string   
        ' because it is the student ID, not an exam score.  
        Dim queryNamesScores = From nameLine In names  
                          Let splitName = nameLine.Split(New Char() {","})  
                          From scoreLine In scores  
                          Let splitScoreLine = scoreLine.Split(New Char() {","})  
                          Where splitName(2) = splitScoreLine(0)  
                          Select New Student() With {  
                               .FirstName = splitName(0), .LastName = splitName(1), .ID = splitName(2),  
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1  
                                             Select Convert.ToInt32(scoreAsText)).ToList()}  
  
        ' Optional. Store the query results for faster access in future  
        ' queries. This could be useful with very large data files.  
        Dim students As List(Of Student) = queryNamesScores.ToList()  
  
        ' Display each student's name and exam score average.  
        For Each s In students  
            Console.WriteLine("The average score of " & s.FirstName & " " &  
                              s.LastName & " is " & s.ExamScores.Average())  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
  
' Output:   
' The average score of Omelchenko Svetlana is 82.5  
' The average score of O'Donnell Claire is 72.25  
' The average score of Mortensen Sven is 84.5  
' The average score of Garcia Cesar is 88.25  
' The average score of Garcia Debra is 67  
' The average score of Fakhouri Fadi is 92.25  
' The average score of Feng Hanying is 88  
' The average score of Garcia Hugo is 85.75  
' The average score of Tucker Lance is 81.75  
' The average score of Adams Terry is 85.25  
' The average score of Zabokritski Eugene is 83  
' The average score of Tucker Michael is 92  
```  
  
 <span data-ttu-id="9f580-114">在[Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md)子句中，对象初始值设定项用于实例化每个新`Student`使用两个来源的数据的对象。</span><span class="sxs-lookup"><span data-stu-id="9f580-114">In the [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>  
  
 <span data-ttu-id="9f580-115">如果不需要存储查询的结果，匿名类型可以是命名类型相比，更方便。</span><span class="sxs-lookup"><span data-stu-id="9f580-115">If you do not have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="9f580-116">如果传递的查询结果在执行查询时的方法外，所需命名的类型。</span><span class="sxs-lookup"><span data-stu-id="9f580-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="9f580-117">下面的示例执行相同的任务与前面的示例中，但使用而不是命名类型的匿名类型︰</span><span class="sxs-lookup"><span data-stu-id="9f580-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>  
  
```vb  
' Merge the data by using an anonymous type.   
' Note the dynamic creation of a list of integers for the  
' ExamScores member. We skip 1 because the first string  
' in the array is the student ID, not an exam score.  
Dim queryNamesScores2 =  
    From nameLine In names  
    Let splitName = nameLine.Split(New Char() {","})  
    From scoreLine In scores  
    Let splitScoreLine = scoreLine.Split(New Char() {","})  
    Where splitName(2) = splitScoreLine(0)  
    Select New With  
           {.Last = splitName(0),  
            .First = splitName(1),  
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1  
                           Select Convert.ToInt32(scoreAsText)).ToList()}  
  
' Display each student's name and exam score average.  
For Each s In queryNamesScores2  
    Console.WriteLine("The average score of " & s.First & " " &  
                      s.Last & " is " & s.ExamScores.Average())  
Next  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f580-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="9f580-118">Compiling the Code</span></span>  
 <span data-ttu-id="9f580-119">创建一个面向.NET Framework 版本 3.5 或更高版本对 System.Core.dll 的引用与项目和一个`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="9f580-119">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f580-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f580-120">See Also</span></span>  
 [<span data-ttu-id="9f580-121">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f580-121">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
