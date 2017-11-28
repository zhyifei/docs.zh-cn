---
title: "如何：对某个词在字符串中出现的次数进行计数 (LINQ) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f8e6f546-7c14-4aa1-8a75-e8d09f3b8ccd
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 56cfe11a0c559e64b11aad02ead3699c71cae2a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-c"></a><span data-ttu-id="6ca5d-102">如何：对某个词在字符串中出现的次数进行计数 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6ca5d-102">How to: Count Occurrences of a Word in a String (LINQ) (C#)</span></span>
<span data-ttu-id="6ca5d-103">此示例演示如何使用 LINQ 查询对指定词在字符串中出现的次数进行计数。</span><span class="sxs-lookup"><span data-stu-id="6ca5d-103">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="6ca5d-104">请注意，若要执行计数，首先需调用 <xref:System.String.Split%2A> 方法来创建词数组。</span><span class="sxs-lookup"><span data-stu-id="6ca5d-104">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="6ca5d-105"><xref:System.String.Split%2A> 方法存在性能开销。</span><span class="sxs-lookup"><span data-stu-id="6ca5d-105">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="6ca5d-106">如果只需要统计字符串的字数，则应考虑改用 <xref:System.Text.RegularExpressions.Regex.Matches%2A> 或 <xref:System.String.IndexOf%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="6ca5d-106">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="6ca5d-107">但是，如果性能不是关键问题，或者已拆分句子以对其执行其他类型的查询，则使用 LINQ 来计数词或短语同样有意义。</span><span class="sxs-lookup"><span data-stu-id="6ca5d-107">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ca5d-108">示例</span><span class="sxs-lookup"><span data-stu-id="6ca5d-108">Example</span></span>  
  
```csharp  
class CountWords  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects" +  
          @" have not been well integrated. Programmers work in C# or Visual Basic" +  
          @" and also in SQL or XQuery. On the one side are concepts such as classes," +  
          @" objects, fields, inheritance, and .NET Framework APIs. On the other side" +  
          @" are tables, columns, rows, nodes, and separate languages for dealing with" +  
          @" them. Data types often require translation between the two worlds; there are" +  
          @" different standard functions. Because the object world has no notion of query, a" +  
          @" query can only be represented as a string without compile-time type checking or" +  
          @" IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" +  
          @" objects in memory is often tedious and error-prone.";  
  
        string searchTerm = "data";  
  
        //Convert the string into an array of words  
        string[] source = text.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' }, StringSplitOptions.RemoveEmptyEntries);  
  
        // Create the query.  Use ToLowerInvariant to match "data" and "Data"   
        var matchQuery = from word in source  
                         where word.ToLowerInvariant() == searchTerm.ToLowerInvariant()  
                         select word;  
  
        // Count the matches, which executes the query.  
        int wordCount = matchQuery.Count();  
        Console.WriteLine("{0} occurrences(s) of the search term \"{1}\" were found.", wordCount, searchTerm);  
  
        // Keep console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
   3 occurrences(s) of the search term "data" were found.  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6ca5d-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="6ca5d-109">Compiling the Code</span></span>  
 <span data-ttu-id="6ca5d-110">创建面向 .NET Framework 3.5 或更高版本的项目，此项目包含对 System.Core.dll 的引用和针对 System.Linq 和 System.IO 命名空间的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="6ca5d-110">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca5d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ca5d-111">See Also</span></span>  
 [<span data-ttu-id="6ca5d-112">LINQ 和字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="6ca5d-112">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
