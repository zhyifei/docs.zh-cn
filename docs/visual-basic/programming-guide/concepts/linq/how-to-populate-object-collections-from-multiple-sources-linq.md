---
title: 如何： 从多个源 (LINQ) (Visual Basic) 填充对象集合
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 6560f853874f9b9a9aeb53bd0678540004fdfcc1
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37070856"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a><span data-ttu-id="ca5f4-102">如何： 从多个源 (LINQ) (Visual Basic) 填充对象集合</span><span class="sxs-lookup"><span data-stu-id="ca5f4-102">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="ca5f4-103">本示例演示如何将来自不同源的数据合并到一系列新的类型。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>

> [!NOTE]
> <span data-ttu-id="ca5f4-104">请勿尝试加入仍在数据库的数据的文件系统中的内存中数据。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-104">Don't try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="ca5f4-105">这种跨域联接可能产生未定义的结果，因为可能为数据库查询和其他类型的源定义了联接操作的不同方式。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="ca5f4-106">此外，如果数据库中的数据量足够大，这样的操作还存在可能导致内存不足的异常的风险。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="ca5f4-107">若要将数据库中的数据联接到内存数据，首先对数据库查询调用 `ToList` 或 `ToArray`，然后对返回的集合执行联接。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>

## <a name="to-create-the-data-file"></a><span data-ttu-id="ca5f4-108">创建数据文件</span><span class="sxs-lookup"><span data-stu-id="ca5f4-108">To create the data file</span></span>

- <span data-ttu-id="ca5f4-109">将的 names.csv 和 scores.csv 文件复制到你的项目文件夹中所述[How to： 内容加入从不同文件 (LINQ) (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="ca5f4-110">示例</span><span class="sxs-lookup"><span data-stu-id="ca5f4-110">Example</span></span>

<span data-ttu-id="ca5f4-111">下面的示例演示如何使用命名类型 `Student` 存储来自两个内存字符串集合（模拟 .csv 格式的电子表格数据）的合并数据。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="ca5f4-112">第一个字符串集合代表学生姓名和 ID，第二个集合代表学生 ID（在第一列）和四次考试分数。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="ca5f4-113">此 ID 用作外键。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-113">The ID is used as the foreign key.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Linq

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
        ' ExamScores member. The first item is skipped in the split string
        ' because it is the student ID, not an exam score.
        Dim queryNamesScores = From nameLine In names
                          Let splitName = nameLine.Split(New Char() {","})
                          From scoreLine In scores
                          Let splitScoreLine = scoreLine.Split(New Char() {","})
                          Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
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

<span data-ttu-id="ca5f4-114">在[Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md)子句，对象初始值设定项用于实例化每个新`Student`从两个源中使用的数据的对象。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-114">In the [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>

<span data-ttu-id="ca5f4-115">如果你不需要存储查询的结果，匿名类型可以更方便比命名类型。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-115">If you don't have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="ca5f4-116">如果在执行查询的方法外部传递查询结果，则需要使用命名类型。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="ca5f4-117">下面的示例执行与前面的示例相同的任务，但使用的是匿名类型，而不是命名类型：</span><span class="sxs-lookup"><span data-stu-id="ca5f4-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>

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
    Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
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

## <a name="compiling-the-code"></a><span data-ttu-id="ca5f4-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="ca5f4-118">Compiling the code</span></span>

<span data-ttu-id="ca5f4-119">创建和编译的项目是面向以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="ca5f4-119">Create and compile a project that targets one of the following options:</span></span>

- <span data-ttu-id="ca5f4-120">.NET framework 版本 3.5 具有对 System.Core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-120">.NET Framework version 3.5 with a reference to System.Core.dll.</span></span>
- <span data-ttu-id="ca5f4-121">.NET framework 版本 4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-121">.NET Framework version 4.0 or higher.</span></span>
- <span data-ttu-id="ca5f4-122">.NET core 版本 1.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ca5f4-122">.NET Core version 1.0 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca5f4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca5f4-123">See also</span></span>

[<span data-ttu-id="ca5f4-124">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca5f4-124">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
