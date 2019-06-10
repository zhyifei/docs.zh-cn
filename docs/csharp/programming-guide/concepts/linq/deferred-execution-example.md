---
title: 延迟执行示例 (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: c9ac87cf2b2af4114e5a20c211b4a6b3f7fced6b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486104"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="b5101-102">延迟执行示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="b5101-102">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="b5101-103">本主题演示延迟执行和迟缓计算如何影响 LINQ to XML 查询的执行。</span><span class="sxs-lookup"><span data-stu-id="b5101-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5101-104">示例</span><span class="sxs-lookup"><span data-stu-id="b5101-104">Example</span></span>  
 <span data-ttu-id="b5101-105">下面的示例演示使用采用延迟执行的扩展方法时的执行顺序。</span><span class="sxs-lookup"><span data-stu-id="b5101-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="b5101-106">此示例声明一个由三个字符串组成的数组。</span><span class="sxs-lookup"><span data-stu-id="b5101-106">The example declares an array of three strings.</span></span> <span data-ttu-id="b5101-107">然后，循环访问 `ConvertCollectionToUpperCase` 所返回的集合。</span><span class="sxs-lookup"><span data-stu-id="b5101-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="b5101-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="b5101-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="b5101-109">请注意，在循环访问 `ConvertCollectionToUpperCase` 所返回的集合时，每一项都从源字符串数组检索，并且在源字符串数组中检索下一项之前，被转换为大写形式。</span><span class="sxs-lookup"><span data-stu-id="b5101-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="b5101-110">可以看到，在 `foreach` 的 `Main` 循环中处理所返回集合的每一项之后，字符串数组才会完全转换为大写形式。</span><span class="sxs-lookup"><span data-stu-id="b5101-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="b5101-111">本教程下一主题演示如何将查询链接到一起：</span><span class="sxs-lookup"><span data-stu-id="b5101-111">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
- [<span data-ttu-id="b5101-112">链接查询示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="b5101-112">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5101-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5101-113">See also</span></span>

- [<span data-ttu-id="b5101-114">教程：将查询链接在一起 (C#)</span><span class="sxs-lookup"><span data-stu-id="b5101-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
