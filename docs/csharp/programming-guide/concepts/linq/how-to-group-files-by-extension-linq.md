---
title: 如何：按扩展名对文件进行分组 (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 21a98320-a5a1-4981-82d8-6a637e7d9018
ms.openlocfilehash: 320d89c78a317f49d98d4dc139aaa3df05fcd6f3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857883"
---
# <a name="how-to-group-files-by-extension-linq-c"></a><span data-ttu-id="fd6fb-102">如何：按扩展名对文件进行分组 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fd6fb-102">How to: Group Files by Extension (LINQ) (C#)</span></span>
<span data-ttu-id="fd6fb-103">本示例演示如何使用 LINQ 来执行高级分组和对文件或文件夹列表执行排序操作。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-103">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="fd6fb-104">它还演示如何使用 <xref:System.Linq.Enumerable.Skip%2A> 和 <xref:System.Linq.Enumerable.Take%2A> 方法在控制台窗口中对输出进行分页。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-104">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd6fb-105">示例</span><span class="sxs-lookup"><span data-stu-id="fd6fb-105">Example</span></span>  
 <span data-ttu-id="fd6fb-106">下面的查询演示如何按文件扩展名对指定的目录树的内容进行分组。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-106">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
```csharp  
class GroupByExtension  
{  
    // This query will sort all the files under the specified folder  
    //  and subfolder into groups keyed by the file extension.  
    private static void Main()  
    {  
        // Take a snapshot of the file system.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Used in WriteLine to trim output lines.  
        int trimLength = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Create the query.  
        var queryGroupByExt =  
            from file in fileList  
            group file by file.Extension.ToLower() into fileGroup  
            orderby fileGroup.Key  
            select fileGroup;  
  
        // Display one group at a time. If the number of   
        // entries is greater than the number of lines  
        // in the console window, then page the output.  
        PageOutput(trimLength, queryGroupByExt);  
    }  
  
    // This method specifically handles group queries of FileInfo objects with string keys.  
    // It can be modified to work for any long listings of data. Note that explicit typing  
    // must be used in method signatures. The groupbyExtList parameter is a query that produces  
    // groups of FileInfo objects with string keys.  
    private static void PageOutput(int rootLength,  
                                    IEnumerable<System.Linq.IGrouping<string, System.IO.FileInfo>> groupByExtList)  
    {  
        // Flag to break out of paging loop.  
        bool goAgain = true;  
  
        // "3" = 1 line for extension + 1 for "Press any key" + 1 for input cursor.  
        int numLines = Console.WindowHeight - 3;  
  
        // Iterate through the outer collection of groups.  
        foreach (var filegroup in groupByExtList)  
        {  
            // Start a new extension at the top of a page.  
            int currentLine = 0;  
  
            // Output only as many lines of the current group as will fit in the window.  
            do  
            {  
                Console.Clear();  
                Console.WriteLine(filegroup.Key == String.Empty ? "[none]" : filegroup.Key);  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var f in resultPage)  
                {  
                    Console.WriteLine("\t{0}", f.FullName.Substring(rootLength));  
                }  
  
                // Increment the line counter.  
                currentLine += numLines;  
  
                // Give the user a chance to escape.  
                Console.WriteLine("Press any key to continue or the 'End' key to break...");  
                ConsoleKey key = Console.ReadKey().Key;  
                if (key == ConsoleKey.End)  
                {  
                    goAgain = false;  
                    break;  
                }  
            } while (currentLine < filegroup.Count());  
  
            if (goAgain == false)  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="fd6fb-107">此程序的输出可能很长，具体取决于本地文件系统的详细信息和 `startFolder` 的设置。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-107">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="fd6fb-108">为了能够查看所有结果，此示例演示如何对结果进行分页。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-108">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="fd6fb-109">相同的方法适用于 Windows 和 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-109">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="fd6fb-110">请注意，由于代码对组中的项进行分页，因此需要使用 `foreach` 循环。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-110">Notice that because the code pages the items in a group, a nested `foreach` loop is required.</span></span> <span data-ttu-id="fd6fb-111">此外，还有一些其他逻辑用于计算列表中的当前位置，以及使用户能够停止分页并退出程序。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-111">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="fd6fb-112">在此特定情况下，根据原始查询的缓存结果运行分页查询。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-112">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="fd6fb-113">在其他上下文中，如 LINQ to SQL，则不需要此类缓存。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-113">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd6fb-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="fd6fb-114">Compiling the Code</span></span>  
 <span data-ttu-id="fd6fb-115">创建面向 .NET Framework 3.5 或更高版本的项目，此项目包含对 System.Core.dll 的引用和针对 System.Linq 和 System.IO 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="fd6fb-115">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd6fb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd6fb-116">See Also</span></span>

- [<span data-ttu-id="fd6fb-117">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="fd6fb-117">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
- [<span data-ttu-id="fd6fb-118">LINQ 和文件目录 (C#)</span><span class="sxs-lookup"><span data-stu-id="fd6fb-118">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
