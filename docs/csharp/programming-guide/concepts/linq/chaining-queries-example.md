---
title: "链接查询示例 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 74d3dcaca686487d79a90f28faf4d9c00218f6a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="9aa63-102">链接查询示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="9aa63-102">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="9aa63-103">此示例建立在前一示例的基础上，演示两个都使用延迟执行和迟缓计算的查询链接到一起时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="9aa63-103">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9aa63-104">示例</span><span class="sxs-lookup"><span data-stu-id="9aa63-104">Example</span></span>  
 <span data-ttu-id="9aa63-105">在此示例中，还会引入另一个扩展方法 `AppendString`，该方法将一个指定字符串追加到源集合的每个字符串上，然后生成新的字符串。</span><span class="sxs-lookup"><span data-stu-id="9aa63-105">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="9aa63-106">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="9aa63-106">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="9aa63-107">在此示例中，可以看到，每个扩展方法每次只对源集合中的一个项进行一次操作。</span><span class="sxs-lookup"><span data-stu-id="9aa63-107">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="9aa63-108">在此示例中，可以清楚地看到，尽管已将生成集合的查询链接到了一起，但未具体化任何中间集合。</span><span class="sxs-lookup"><span data-stu-id="9aa63-108">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="9aa63-109">相反，每一项只是从一个迟缓方法传递到下一个迟缓方法。</span><span class="sxs-lookup"><span data-stu-id="9aa63-109">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="9aa63-110">这种方法的内存需求量比另一种方法小得多，在另一种方法中，首先获取一个字符串数组，然后创建第二个字符串数组（其中的字符串都已转换为大写形式），最后创建第三个字符串数组（其中的每个字符串都追加了感叹号）。</span><span class="sxs-lookup"><span data-stu-id="9aa63-110">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="9aa63-111">本教程下一主题演示中间具体化：</span><span class="sxs-lookup"><span data-stu-id="9aa63-111">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
-   [<span data-ttu-id="9aa63-112">中间具体化 (C#)</span><span class="sxs-lookup"><span data-stu-id="9aa63-112">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="9aa63-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aa63-113">See Also</span></span>  
 [<span data-ttu-id="9aa63-114">教程：将查询链接在一起 (C#)</span><span class="sxs-lookup"><span data-stu-id="9aa63-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
