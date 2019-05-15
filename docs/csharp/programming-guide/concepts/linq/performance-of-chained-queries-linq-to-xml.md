---
title: 链接的查询的性能 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: da01901a8c4208965a339cb3cf446f054f65638b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596848"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a><span data-ttu-id="51d62-102">链接的查询的性能 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="51d62-102">Performance of Chained Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="51d62-103">LINQ（以及 LINQ to XML）的一个最重要优点是，链接查询的执行性能与单个更大更复杂的查询一样好。</span><span class="sxs-lookup"><span data-stu-id="51d62-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="51d62-104">链接查询是一种将另一个查询作为其源的查询。</span><span class="sxs-lookup"><span data-stu-id="51d62-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="51d62-105">例如，在下面的简单代码中，`query2` 使用 `query1` 作为其源：</span><span class="sxs-lookup"><span data-stu-id="51d62-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 <span data-ttu-id="51d62-106">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="51d62-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="51d62-107">此链接查询提供与循环访问链接列表相同的性能配置文件。</span><span class="sxs-lookup"><span data-stu-id="51d62-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
- <span data-ttu-id="51d62-108"><xref:System.Xml.Linq.XContainer.Elements%2A> 轴具有与循环访问链接列表基本相同的性能。</span><span class="sxs-lookup"><span data-stu-id="51d62-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="51d62-109"><xref:System.Xml.Linq.XContainer.Elements%2A> 作为具有延迟执行功能的迭代器实现。</span><span class="sxs-lookup"><span data-stu-id="51d62-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="51d62-110">这意味着它除了循环访问链接列表外还执行一些操作，例如分配迭代器对象和跟踪执行状态。</span><span class="sxs-lookup"><span data-stu-id="51d62-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="51d62-111">此项工作可以分为两类：设置迭代器时完成的工作和每次迭代过程中完成的工作。</span><span class="sxs-lookup"><span data-stu-id="51d62-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="51d62-112">设置工作是固定的少量工作，而每次迭代过程中完成的工作与源集合中的项数成正比。</span><span class="sxs-lookup"><span data-stu-id="51d62-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
- <span data-ttu-id="51d62-113">在 `query1` 中，`where` 子句将使查询调用 <xref:System.Linq.Enumerable.Where%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="51d62-113">In `query1`, the `where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="51d62-114">此方法也作为迭代器实现。</span><span class="sxs-lookup"><span data-stu-id="51d62-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="51d62-115">设置工作包括实例化将引用 lambda 表达式的委托和对迭代器的常规设置。</span><span class="sxs-lookup"><span data-stu-id="51d62-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="51d62-116">每次迭代时，都将调用该委托以执行谓词。</span><span class="sxs-lookup"><span data-stu-id="51d62-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="51d62-117">设置工作和每次迭代过程中完成的工作类似于循环访问轴期间完成的工作。</span><span class="sxs-lookup"><span data-stu-id="51d62-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
- <span data-ttu-id="51d62-118">在 `query1` 中，select 子句将使查询调用 <xref:System.Linq.Enumerable.Select%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="51d62-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="51d62-119">此方法与 <xref:System.Linq.Enumerable.Where%2A> 方法具有相同的性能配置文件。</span><span class="sxs-lookup"><span data-stu-id="51d62-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
- <span data-ttu-id="51d62-120">`query2` 中的 `where` 子句和 `select` 子句与 `query1` 中的相应语句具有相同的性能配置文件。</span><span class="sxs-lookup"><span data-stu-id="51d62-120">In `query2`, both the `where` clause and the `select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="51d62-121">因此，通过 `query2` 执行的迭代与第一个查询源中的项数（即，线形时间）成正比。</span><span class="sxs-lookup"><span data-stu-id="51d62-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span> <span data-ttu-id="51d62-122">相应的 Visual Basic 示例将具有相同的性能配置文件。</span><span class="sxs-lookup"><span data-stu-id="51d62-122">A corresponding Visual Basic example would have the same performance profile.</span></span>  
  
 <span data-ttu-id="51d62-123">有关迭代器的详细信息，请参阅 [yield](../../../../csharp/language-reference/keywords/yield.md)。</span><span class="sxs-lookup"><span data-stu-id="51d62-123">For more information on iterators, see [yield](../../../../csharp/language-reference/keywords/yield.md).</span></span>  
  
 <span data-ttu-id="51d62-124">有关将查询链接在一起的更详细教程，请参阅[教程：将查询链接在一起](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)。</span><span class="sxs-lookup"><span data-stu-id="51d62-124">For a more detailed tutorial on chaining queries together, see [Tutorial: Chaining Queries Together](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d62-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="51d62-125">See also</span></span>

- [<span data-ttu-id="51d62-126">性能 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="51d62-126">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
