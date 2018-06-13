---
title: 如何：从多个源填充对象集合 (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 8ad7d480-b46c-4ccc-8c57-76f2d04ccc6d
ms.openlocfilehash: 3ff51b0b5f04a44f83db2590bd7005097b1c0161
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323347"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-c"></a><span data-ttu-id="f3648-102">如何：从多个源填充对象集合 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f3648-102">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>
<span data-ttu-id="f3648-103">本示例演示如何将来自不同源的数据合并到一系列新的类型。</span><span class="sxs-lookup"><span data-stu-id="f3648-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3648-104">请勿尝试将内存数据或文件系统中的数据与仍在数据库中的数据进行联接。</span><span class="sxs-lookup"><span data-stu-id="f3648-104">Do not try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="f3648-105">这种跨域联接可能产生未定义的结果，因为可能为数据库查询和其他类型的源定义了联接操作的不同方式。</span><span class="sxs-lookup"><span data-stu-id="f3648-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="f3648-106">此外，如果数据库中的数据量足够大，这样的操作还存在可能导致内存不足的异常的风险。</span><span class="sxs-lookup"><span data-stu-id="f3648-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="f3648-107">若要将数据库中的数据联接到内存数据，首先对数据库查询调用 `ToList` 或 `ToArray`，然后对返回的集合执行联接。</span><span class="sxs-lookup"><span data-stu-id="f3648-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="f3648-108">创建数据文件</span><span class="sxs-lookup"><span data-stu-id="f3648-108">To create the data file</span></span>  
  
-   <span data-ttu-id="f3648-109">按照[如何：联接不同文件中的内容 (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) 中的说明，将 names.csv 和 scores.csv 文件复制到项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3648-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3648-110">示例</span><span class="sxs-lookup"><span data-stu-id="f3648-110">Example</span></span>  
 <span data-ttu-id="f3648-111">下面的示例演示如何使用命名类型 `Student` 存储来自两个内存字符串集合（模拟 .csv 格式的电子表格数据）的合并数据。</span><span class="sxs-lookup"><span data-stu-id="f3648-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="f3648-112">第一个字符串集合代表学生姓名和 ID，第二个集合代表学生 ID（在第一列）和四次考试分数。</span><span class="sxs-lookup"><span data-stu-id="f3648-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="f3648-113">此 ID 用作外键。</span><span class="sxs-lookup"><span data-stu-id="f3648-113">The ID is used as the foreign key.</span></span>  
  
```csharp  
class Student  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int ID { get; set; }  
    public List<int> ExamScores { get; set; }  
}  
  
class PopulateCollection  
{  
    static void Main()  
    {  
        // These data files are defined in How to: Join Content from   
        // Dissimilar Files (LINQ).  
  
        // Each line of names.csv consists of a last name, a first name, and an  
        // ID number, separated by commas. For example, Omelchenko,Svetlana,111  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
  
        // Each line of scores.csv consists of an ID number and four test   
        // scores, separated by commas. For example, 111, 97, 92, 81, 60  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Merge the data sources using a named type.  
        // var could be used instead of an explicit type. Note the dynamic  
        // creation of a list of ints for the ExamScores member. We skip   
        // the first item in the split string because it is the student ID,   
        // not an exam score.  
        IEnumerable<Student> queryNamesScores =  
            from nameLine in names  
            let splitName = nameLine.Split(',')  
            from scoreLine in scores  
            let splitScoreLine = scoreLine.Split(',')  
            where splitName[2] == splitScoreLine[0]  
            select new Student()  
            {  
                FirstName = splitName[0],  
                LastName = splitName[1],  
                ID = Convert.ToInt32(splitName[2]),  
                ExamScores = (from scoreAsText in splitScoreLine.Skip(1)  
                              select Convert.ToInt32(scoreAsText)).  
                              ToList()  
            };  
  
        // Optional. Store the newly created student objects in memory  
        // for faster access in future queries. This could be useful with  
        // very large data files.  
        List<Student> students = queryNamesScores.ToList();  
  
        // Display each student's name and exam score average.  
        foreach (var student in students)  
        {  
            Console.WriteLine("The average score of {0} {1} is {2}.",  
                student.FirstName, student.LastName,  
                student.ExamScores.Average());  
        }  
  
        //Keep console window open in debug mode  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
}  
/* Output:   
    The average score of Omelchenko Svetlana is 82.5.  
    The average score of O'Donnell Claire is 72.25.  
    The average score of Mortensen Sven is 84.5.  
    The average score of Garcia Cesar is 88.25.  
    The average score of Garcia Debra is 67.  
    The average score of Fakhouri Fadi is 92.25.  
    The average score of Feng Hanying is 88.  
    The average score of Garcia Hugo is 85.75.  
    The average score of Tucker Lance is 81.75.  
    The average score of Adams Terry is 85.25.  
    The average score of Zabokritski Eugene is 83.  
    The average score of Tucker Michael is 92.  
 */  
```  
  
 <span data-ttu-id="f3648-114">在 [select](../../../../csharp/language-reference/keywords/select-clause.md) 子句中，对象初始值设定项使用来自两个源的数据实例化每个新的 `Student` 对象。</span><span class="sxs-lookup"><span data-stu-id="f3648-114">In the [select](../../../../csharp/language-reference/keywords/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>  
  
 <span data-ttu-id="f3648-115">如果不需要存储查询的结果，那么和命名类型相比，匿名类型使用起来更方便。</span><span class="sxs-lookup"><span data-stu-id="f3648-115">If you do not have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="f3648-116">如果在执行查询的方法外部传递查询结果，则需要使用命名类型。</span><span class="sxs-lookup"><span data-stu-id="f3648-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="f3648-117">下面的示例执行与前面的示例相同的任务，但使用的是匿名类型，而不是命名类型：</span><span class="sxs-lookup"><span data-stu-id="f3648-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>  
  
```csharp  
// Merge the data sources by using an anonymous type.  
// Note the dynamic creation of a list of ints for the  
// ExamScores member. We skip 1 because the first string  
// in the array is the student ID, not an exam score.  
var queryNamesScores2 =  
    from nameLine in names  
    let splitName = nameLine.Split(',')  
    from scoreLine in scores  
    let splitScoreLine = scoreLine.Split(',')  
    where splitName[2] == splitScoreLine[0]  
    select new  
    {  
        First = splitName[0],  
        Last = splitName[1],  
        ExamScores = (from scoreAsText in splitScoreLine.Skip(1)  
                      select Convert.ToInt32(scoreAsText))  
                      .ToList()  
    };  
  
// Display each student's name and exam score average.  
foreach (var student in queryNamesScores2)  
{  
    Console.WriteLine("The average score of {0} {1} is {2}.",  
        student.First, student.Last, student.ExamScores.Average());  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3648-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="f3648-118">Compiling the Code</span></span>  
 <span data-ttu-id="f3648-119">创建面向 .NET Framework 3.5 或更高版本的项目，此项目包含对 System.Core.dll 的引用和针对 System.Linq 和 System.IO 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="f3648-119">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3648-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3648-120">See Also</span></span>  
 [<span data-ttu-id="f3648-121">LINQ 和字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="f3648-121">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="f3648-122">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="f3648-122">Object and Collection Initializers</span></span>](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [<span data-ttu-id="f3648-123">匿名类型</span><span class="sxs-lookup"><span data-stu-id="f3648-123">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
