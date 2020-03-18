---
title: 如何查询字符串中的字符 (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: d85e488a38a6167505732103b4c540cade6ea9bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345683"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="e1a66-102">如何查询字符串中的字符 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="e1a66-102">How to query for characters in a string (LINQ) (C#)</span></span>
<span data-ttu-id="e1a66-103">因为 <xref:System.String> 类可实现泛型 <xref:System.Collections.Generic.IEnumerable%601> 接口，因此任何字符串都可以字符序列的形式进行查询。</span><span class="sxs-lookup"><span data-stu-id="e1a66-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="e1a66-104">但是，这不是 LINQ 的一般用法。</span><span class="sxs-lookup"><span data-stu-id="e1a66-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="e1a66-105">对于复杂的模式匹配操作，请使用 <xref:System.Text.RegularExpressions.Regex> 类。</span><span class="sxs-lookup"><span data-stu-id="e1a66-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1a66-106">示例</span><span class="sxs-lookup"><span data-stu-id="e1a66-106">Example</span></span>  
 <span data-ttu-id="e1a66-107">以下示例查询一个字符串以确定它所包含的数字数量。</span><span class="sxs-lookup"><span data-stu-id="e1a66-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="e1a66-108">请注意，在第一次执行此查询后将“重用”此查询。</span><span class="sxs-lookup"><span data-stu-id="e1a66-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="e1a66-109">这是可能的，因为查询本身并不存储任何实际的结果。</span><span class="sxs-lookup"><span data-stu-id="e1a66-109">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1a66-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="e1a66-110">Compiling the Code</span></span>  
 <span data-ttu-id="e1a66-111">使用 System.Linq 和 System.IO 命名空间的 `using` 指令创建 C# 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="e1a66-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a66-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1a66-112">See also</span></span>

- [<span data-ttu-id="e1a66-113">LINQ 和字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="e1a66-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="e1a66-114">如何将 LINQ 查询与正则表达式合并 (C#)</span><span class="sxs-lookup"><span data-stu-id="e1a66-114">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
