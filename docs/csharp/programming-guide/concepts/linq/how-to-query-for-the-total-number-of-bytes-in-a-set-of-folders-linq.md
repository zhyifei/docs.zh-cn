---
title: 如何：查询一组文件夹中的总字节数 (LINQ)
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: 6a02f5a645c545883c05fc52448d10e3d835d615
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322466"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a><span data-ttu-id="2bb2a-102">如何：查询一组文件夹中的总字节数 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="2bb2a-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>
<span data-ttu-id="2bb2a-103">此示例演示如何检索由指定文件夹及其所有子文件夹中的所有文件使用的字节总数。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bb2a-104">示例</span><span class="sxs-lookup"><span data-stu-id="2bb2a-104">Example</span></span>  
 <span data-ttu-id="2bb2a-105"><xref:System.Linq.Enumerable.Sum%2A> 方法可将 `select` 子句中选择的所有项的值相加。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="2bb2a-106">可轻松修改此查询以检索指定目录树中的最大或最小文件，方法是调用 <xref:System.Linq.Enumerable.Min%2A> 或 <xref:System.Linq.Enumerable.Max%2A> 方法，而不是 <xref:System.Linq.Enumerable.Sum%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```csharp  
class QuerySize  
{  
    public static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\VC#";  
  
        // Take a snapshot of the file system.  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<string> fileList = System.IO.Directory.GetFiles(startFolder, "*.*", System.IO.SearchOption.AllDirectories);  
  
        var fileQuery = from file in fileList  
                        select GetFileLength(file);  
  
        // Cache the results to avoid multiple trips to the file system.  
        long[] fileLengths = fileQuery.ToArray();  
  
        // Return the size of the largest file  
        long largestFile = fileLengths.Max();  
  
        // Return the total number of bytes in all the files under the specified folder.  
        long totalBytes = fileLengths.Sum();  
  
        Console.WriteLine("There are {0} bytes in {1} files under {2}",  
            totalBytes, fileList.Count(), startFolder);  
        Console.WriteLine("The largest files is {0} bytes.", largestFile);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the System.IO.FileInfo.Length property.  
    static long GetFileLength(string filename)  
    {  
        long retval;  
        try  
        {  
            System.IO.FileInfo fi = new System.IO.FileInfo(filename);  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
}  
```  
  
 <span data-ttu-id="2bb2a-107">如果只需对指定目录树中的字节数进行计数，则可以更高效地执行此操作而无需创建 LINQ 查询（这会产生创建列表集合作为数据源的开销）。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="2bb2a-108">随着查询变得更加复杂，或者在必须对相同数据源运行多个查询时，LINQ 方法会更加有用。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="2bb2a-109">查询调用单独的方法来获取文件长度。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="2bb2a-110">这是为了使用在以下情况下会引发的可能异常：在 `GetFiles` 调用中创建了 <xref:System.IO.FileInfo> 对象之后，在其他线程中删除了文件。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="2bb2a-111">即使已创建 <xref:System.IO.FileInfo> 对象，该异常也可能出现，因为 <xref:System.IO.FileInfo> 对象会在首次访问其 <xref:System.IO.FileInfo.Length%2A> 属性时，尝试使用最近长度刷新该属性。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="2bb2a-112">通过将此操作置于查询外部的 try-catch 块中，代码可遵循在查询中避免可能导致副作用的操作这一规则。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="2bb2a-113">一般情况下，在使用异常时必须格外谨慎，以确保应用程序不会处于未知状态。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2bb2a-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="2bb2a-114">Compiling the Code</span></span>  
 <span data-ttu-id="2bb2a-115">创建面向 .NET Framework 3.5 或更高版本的项目，此项目包含对 System.Core.dll 的引用和针对 System.Linq 和 System.IO 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="2bb2a-115">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb2a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bb2a-116">See Also</span></span>  
 [<span data-ttu-id="2bb2a-117">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="2bb2a-117">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="2bb2a-118">LINQ 和文件目录 (C#)</span><span class="sxs-lookup"><span data-stu-id="2bb2a-118">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
