---
title: 如何：在目录树中查询重复文件 (LINQ)
ms.date: 07/20/2015
ms.assetid: 1ff5562b-0d30-46d1-b426-a04e8f78c840
ms.openlocfilehash: 09ce574c68cbf11c0ee50df663692fd207038758
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44189230"
---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="ae5f0-102">如何：在目录树中查询重复文件 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ae5f0-102">How to: Query for Duplicate Files in a Directory Tree (LINQ) (C#)</span></span>
<span data-ttu-id="ae5f0-103">有时，具有相同名称的文件可能位于多个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-103">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="ae5f0-104">例如，在 Visual Studio 安装文件夹下，多个文件夹中都有 readme.htm 文件。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-104">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="ae5f0-105">此示例显示如何在指定根文件夹下查询此类重复文件名。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-105">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="ae5f0-106">第二个示例显示如何查询大小和创建时间都匹配的文件。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-106">The second example shows how to query for files whose size and creation times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae5f0-107">示例</span><span class="sxs-lookup"><span data-stu-id="ae5f0-107">Example</span></span>  
  
```csharp  
class QueryDuplicateFileNames  
{  
    static void Main(string[] args)  
    {  
        // Uncomment QueryDuplicates2 to run that query.  
        QueryDuplicates();  
        // QueryDuplicates2();  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    static void QueryDuplicates()  
    {  
        // Change the root drive or folder if necessary  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // used in WriteLine to keep the lines shorter  
        int charsToSkip = startFolder.Length;  
  
        // var can be used for convenience with groups.  
        var queryDupNames =  
            from file in fileList  
            group file.FullName.Substring(charsToSkip) by file.Name into fileGroup  
            where fileGroup.Count() > 1  
            select fileGroup;  
  
        // Pass the query to a method that will  
        // output one page at a time.  
        PageOutput<string, string>(queryDupNames);  
    }  
  
    // A Group key that can be passed to a separate method.  
    // Override Equals and GetHashCode to define equality for the key.  
    // Override ToString to provide a friendly name for Key.ToString()  
    class PortableKey  
    {  
        public string Name { get; set; }  
        public DateTime CreationTime { get; set; }  
        public long Length { get; set; }  
  
        public override bool Equals(object obj)  
        {  
            PortableKey other = (PortableKey)obj;  
            return other.CreationTime == this.CreationTime &&  
                   other.Length == this.Length &&  
                   other.Name == this.Name;  
        }  
  
        public override int GetHashCode()  
        {  
            string str = String.Format("{0}{1}{2}", this.CreationTime, this.Length, this.Name);  
            return str.GetHashCode();  
        }  
        public override string ToString()  
        {  
            return String.Format("{0} {1} {2}", this.Name, this.Length, this.CreationTime);  
        }  
    }  
    static void QueryDuplicates2()  
    {  
        // Change the root drive or folder if necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Make the lines shorter for the console display  
        int charsToSkip = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Note the use of a compound key. Files that match  
        // all three properties belong to the same group.  
        // A named type is used to enable the query to be  
        // passed to another method. Anonymous types can also be used  
        // for composite keys but cannot be passed across method boundaries  
        //   
        var queryDupFiles =  
            from file in fileList  
            group file.FullName.Substring(charsToSkip) by  
                new PortableKey { Name = file.Name, CreationTime = file.CreationTime, Length = file.Length } into fileGroup  
            where fileGroup.Count() > 1  
            select fileGroup;  
  
        var list = queryDupFiles.ToList();  
  
        int i = queryDupFiles.Count();  
  
        PageOutput<PortableKey, string>(queryDupFiles);  
    }  
  
    // A generic method to page the output of the QueryDuplications methods  
    // Here the type of the group must be specified explicitly. "var" cannot  
    // be used in method signatures. This method does not display more than one  
    // group per page.  
    private static void PageOutput<K, V>(IEnumerable<System.Linq.IGrouping<K, V>> groupByExtList)  
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
                Console.WriteLine("Filename = {0}", filegroup.Key.ToString() == String.Empty ? "[none]" : filegroup.Key.ToString());  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var fileName in resultPage)  
                {  
                    Console.WriteLine("\t{0}", fileName);  
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
  
 <span data-ttu-id="ae5f0-108">第一个查询使用简单键来确定匹配；此查询可以找到名称相同但内容可能不同的文件。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-108">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="ae5f0-109">第二个查询使用复合键来匹配 <xref:System.IO.FileInfo> 对象的 3 个属性。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-109">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="ae5f0-110">此查询更可能找到名称相同且内容相似或相同的文件。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-110">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae5f0-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="ae5f0-111">Compiling the Code</span></span>  
 <span data-ttu-id="ae5f0-112">创建面向 .NET Framework 3.5 或更高版本的项目，此项目包含对 System.Core.dll 的引用和针对 System.Linq 和 System.IO 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="ae5f0-112">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5f0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae5f0-113">See Also</span></span>

- [<span data-ttu-id="ae5f0-114">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="ae5f0-114">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
- [<span data-ttu-id="ae5f0-115">LINQ 和文件目录 (C#)</span><span class="sxs-lookup"><span data-stu-id="ae5f0-115">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
