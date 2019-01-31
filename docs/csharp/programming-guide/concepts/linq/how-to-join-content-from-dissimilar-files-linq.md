---
title: 如何：联接不同文件的内容 (LINQ) (C#)
ms.date: 06/27/2018
ms.assetid: aa2d12a6-70a9-492f-a6db-b2b850d46811
ms.openlocfilehash: 5fb954bee6433d28ffb47f789b41492349f7ab42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698409"
---
# <a name="how-to-join-content-from-dissimilar-files-linq-c"></a><span data-ttu-id="0e680-102">如何：联接不同文件的内容 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0e680-102">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>

<span data-ttu-id="0e680-103">本示例演示如何联接两个逗号分隔文件中的数据，这两个文件共享一个用作匹配键的公共值。</span><span class="sxs-lookup"><span data-stu-id="0e680-103">This example shows how to join data from two comma-delimited files that share a common value that is used as a matching key.</span></span> <span data-ttu-id="0e680-104">如果需要合并来自两个电子表格的数据，或者从一个电子表格和具有另一种格式的文件合并到一个新文件时，此技术很有用。</span><span class="sxs-lookup"><span data-stu-id="0e680-104">This technique can be useful if you have to combine data from two spreadsheets, or from a spreadsheet and from a file that has another format, into a new file.</span></span> <span data-ttu-id="0e680-105">可以修改此示例以用于任何类型的结构化文本。</span><span class="sxs-lookup"><span data-stu-id="0e680-105">You can modify the example to work with any kind of structured text.</span></span>  
  
## <a name="to-create-the-data-files"></a><span data-ttu-id="0e680-106">创建数据文件</span><span class="sxs-lookup"><span data-stu-id="0e680-106">To create the data files</span></span>
  
1.  <span data-ttu-id="0e680-107">将以下行复制到名为 scores.csv 的文件，并将文件保存到项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e680-107">Copy the following lines into a file that is named *scores.csv* and save it to your project folder.</span></span> <span data-ttu-id="0e680-108">此文件表示电子表格数据。</span><span class="sxs-lookup"><span data-stu-id="0e680-108">The file represents spreadsheet data.</span></span> <span data-ttu-id="0e680-109">第 1 列是学生的 ID，第 2 至 5 列是测验分数。</span><span class="sxs-lookup"><span data-stu-id="0e680-109">Column 1 is the student's ID, and columns 2 through 5 are test scores.</span></span>  
  
    ```  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
2.  <span data-ttu-id="0e680-110">将以下行复制到名为 names.csv 的文件，并将文件保存到项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e680-110">Copy the following lines into a file that is named *names.csv* and save it to your project folder.</span></span> <span data-ttu-id="0e680-111">此文件表示电子表格，其中包含学生的姓氏、名字和学生 ID。</span><span class="sxs-lookup"><span data-stu-id="0e680-111">The file represents a spreadsheet that contains the student's last name, first name, and student ID.</span></span>  
  
    ```  
    Omelchenko,Svetlana,111  
    O'Donnell,Claire,112  
    Mortensen,Sven,113  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Hugo,118  
    Tucker,Lance,119  
    Adams,Terry,120  
    Zabokritski,Eugene,121  
    Tucker,Michael,122  
    ```  
  
## <a name="example"></a><span data-ttu-id="0e680-112">示例</span><span class="sxs-lookup"><span data-stu-id="0e680-112">Example</span></span>  

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class JoinStrings  
{  
    static void Main()  
    {  
        // Join content from dissimilar files that contain  
        // related information. File names.csv contains the student  
        // name plus an ID number. File scores.csv contains the ID   
        // and a set of four test scores. The following query joins  
        // the scores to the student names by using ID as a  
        // matching key.  
  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Name:    Last[0],       First[1],  ID[2]  
        //          Omelchenko,    Svetlana,  11  
        // Score:   StudentID[0],  Exam1[1]   Exam2[2],  Exam3[3],  Exam4[4]  
        //          111,           97,        92,        81,        60  
  
        // This query joins two dissimilar spreadsheets based on common ID value.  
        // Multiple from clauses are used instead of a join clause  
        // in order to store results of id.Split.  
        IEnumerable<string> scoreQuery1 =  
            from name in names  
            let nameFields = name.Split(',')  
            from id in scores  
            let scoreFields = id.Split(',')  
            where Convert.ToInt32(nameFields[2]) == Convert.ToInt32(scoreFields[0])
            select nameFields[0] + "," + scoreFields[1] + "," + scoreFields[2]   
                   + "," + scoreFields[3] + "," + scoreFields[4];  
  
        // Pass a query variable to a method and execute it  
        // in the method. The query itself is unchanged.  
        OutputQueryResults(scoreQuery1, "Merge two spreadsheets:");  
  
        // Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    static void OutputQueryResults(IEnumerable<string> query, string message)  
    {  
        Console.WriteLine(System.Environment.NewLine + message);  
        foreach (string item in query)  
        {  
            Console.WriteLine(item);  
        }  
        Console.WriteLine("{0} total names in list", query.Count());  
    }  
}  
/* Output:  
Merge two spreadsheets:
Omelchenko, 97, 92, 81, 60
O'Donnell, 75, 84, 91, 39
Mortensen, 88, 94, 65, 91
Garcia, 97, 89, 85, 82
Garcia, 35, 72, 91, 70
Fakhouri, 99, 86, 90, 94
Feng, 93, 92, 80, 87
Garcia, 92, 90, 83, 78
Tucker, 68, 79, 88, 92
Adams, 99, 82, 81, 79
Zabokritski, 96, 85, 91, 60
Tucker, 94, 92, 91, 91
12 total names in list
 */  
```

## <a name="compiling-the-code"></a><span data-ttu-id="0e680-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="0e680-113">Compiling the code</span></span>

<span data-ttu-id="0e680-114">创建并编译面向下列选项之一的项目：</span><span class="sxs-lookup"><span data-stu-id="0e680-114">Create and compile a project that targets one of the following options:</span></span>

- <span data-ttu-id="0e680-115">.NET Framework 版本 3.5，含对 System.Core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="0e680-115">.NET Framework version 3.5 with a reference to System.Core.dll.</span></span>
- <span data-ttu-id="0e680-116">.NET Framework 版本 4.0或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0e680-116">.NET Framework version 4.0 or higher.</span></span>
- <span data-ttu-id="0e680-117">.NET Core 版本 1.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0e680-117">.NET Core version 1.0 or higher.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e680-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e680-118">See also</span></span>

- [<span data-ttu-id="0e680-119">LINQ 和字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="0e680-119">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="0e680-120">LINQ 和文件目录 (C#)</span><span class="sxs-lookup"><span data-stu-id="0e680-120">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
