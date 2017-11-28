---
title: "如何：使用组将一个文件拆分成多个文件 (LINQ) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 8179b91c-d778-4e57-884f-77fe5a8e4e40
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 74b7f40b09131cb6e4ed82d64933512c6e0499cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-split-a-file-into-many-files-by-using-groups-linq-c"></a><span data-ttu-id="db26d-102">如何：使用组将一个文件拆分成多个文件 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="db26d-102">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>
<span data-ttu-id="db26d-103">此示例演示一种进行以下操作的方法：合并两个文件的内容，然后创建一组以新方式整理数据的新文件。</span><span class="sxs-lookup"><span data-stu-id="db26d-103">This example shows one way to merge the contents of two files and then create a set of new files that organize the data in a new way.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="db26d-104">创建数据文件</span><span class="sxs-lookup"><span data-stu-id="db26d-104">To create the data files</span></span>  
  
1.  <span data-ttu-id="db26d-105">将下面的姓名复制到名为 names1.txt 的文本文件，然后将此文件保存到项目文件夹：</span><span class="sxs-lookup"><span data-stu-id="db26d-105">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2.  <span data-ttu-id="db26d-106">将下面的姓名复制到名为 names2.txt 的文本文件，然后将此文件保存到项目文件夹：注意这两个文件有一些共同的姓名。</span><span class="sxs-lookup"><span data-stu-id="db26d-106">Copy these names into a text file that is named names2.txt and save it in your project folder: Note that the two files have some names in common.</span></span>  
  
    ```  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="db26d-107">示例</span><span class="sxs-lookup"><span data-stu-id="db26d-107">Example</span></span>  
  
```csharp  
class SplitWithGroups  
{  
    static void Main()  
    {  
        string[] fileA = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] fileB = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Concatenate and remove duplicate names based on  
        // default string comparer  
        var mergeQuery = fileA.Union(fileB);  
  
        // Group the names by the first letter in the last name.  
        var groupQuery = from name in mergeQuery  
                         let n = name.Split(',')  
                         group name by n[0][0] into g  
                         orderby g.Key  
                         select g;  
  
        // Create a new file for each group that was created  
        // Note that nested foreach loops are required to access  
        // individual items with each group.  
        foreach (var g in groupQuery)  
        {  
            // Create the new file name.  
            string fileName = @"../../../testFile_" + g.Key + ".txt";  
  
            // Output to display.  
            Console.WriteLine(g.Key);  
  
            // Write file.  
            using (System.IO.StreamWriter sw = new System.IO.StreamWriter(fileName))  
            {  
                foreach (var item in g)  
                {  
                    sw.WriteLine(item);  
                    // Output to console for example purposes.  
                    Console.WriteLine("   {0}", item);  
                }  
            }  
        }  
        // Keep console window open in debug mode.  
        Console.WriteLine("Files have been written. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:   
    A  
       Aw, Kam Foo  
    B  
       Bankov, Peter  
       Beebe, Ann  
    E  
       El Yassir, Mehdi  
    G  
       Garcia, Hugo  
       Guy, Wey Yuan  
       Garcia, Debra  
       Gilchrist, Beth  
       Giakoumakis, Leo  
    H  
       Holm, Michael  
    L  
       Liu, Jinghao  
    M  
       Myrcha, Jacek  
       McLin, Nkenge  
    N  
       Noriega, Fabricio  
    P  
       Potra, Cristina  
    T  
       Toyoshima, Tim  
 */  
```  
  
 <span data-ttu-id="db26d-108">对于与数据文件位于同一文件夹中的每个组，程序将为这些组编写单独的文件。</span><span class="sxs-lookup"><span data-stu-id="db26d-108">The program writes a separate file for each group in the same folder as the data files.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db26d-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="db26d-109">Compiling the Code</span></span>  
 <span data-ttu-id="db26d-110">创建面向 .NET Framework 3.5 或更高版本的项目，此项目包含对 System.Core.dll 的引用和针对 System.Linq 和 System.IO 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="db26d-110">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db26d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="db26d-111">See Also</span></span>  
 [<span data-ttu-id="db26d-112">LINQ 和字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="db26d-112">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="db26d-113">LINQ 和文件目录 (C#)</span><span class="sxs-lookup"><span data-stu-id="db26d-113">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
