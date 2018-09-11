---
title: 对数据排序 (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 6a7f687895385bfb77d2a1e3e785742a794bb1b6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44209415"
---
# <a name="sorting-data-c"></a><span data-ttu-id="fa758-102">对数据排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="fa758-102">Sorting Data (C#)</span></span>
<span data-ttu-id="fa758-103">排序操作基于一个或多个属性对序列的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="fa758-104">第一个排序条件对元素执行主要排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="fa758-105">通过指定第二个排序条件，您可以对每个主要排序组内的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="fa758-106">下图演示对一个字符序列执行按字母排序操作的结果。</span><span class="sxs-lookup"><span data-stu-id="fa758-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="fa758-107">![LINQ 排序操作](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="fa758-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="fa758-108">下节列出了对数据进行排序的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="fa758-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa758-109">方法</span><span class="sxs-lookup"><span data-stu-id="fa758-109">Methods</span></span>  
  
|<span data-ttu-id="fa758-110">方法名</span><span class="sxs-lookup"><span data-stu-id="fa758-110">Method Name</span></span>|<span data-ttu-id="fa758-111">描述</span><span class="sxs-lookup"><span data-stu-id="fa758-111">Description</span></span>|<span data-ttu-id="fa758-112">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="fa758-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="fa758-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="fa758-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="fa758-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="fa758-114">OrderBy</span></span>|<span data-ttu-id="fa758-115">按升序对值排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fa758-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="fa758-116">OrderByDescending</span></span>|<span data-ttu-id="fa758-117">按降序对值排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fa758-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="fa758-118">ThenBy</span></span>|<span data-ttu-id="fa758-119">按升序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fa758-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="fa758-120">ThenByDescending</span></span>|<span data-ttu-id="fa758-121">按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fa758-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="fa758-122">Reverse</span></span>|<span data-ttu-id="fa758-123">反转集合中元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="fa758-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="fa758-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="fa758-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="fa758-125">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="fa758-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="fa758-126">主要排序示例</span><span class="sxs-lookup"><span data-stu-id="fa758-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="fa758-127">主要升序排序</span><span class="sxs-lookup"><span data-stu-id="fa758-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="fa758-128">下面的示例演示如何在 LINQ 查询中使用 `orderby` 子句按字符串长度对数组中的字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="fa758-129">主要降序排序</span><span class="sxs-lookup"><span data-stu-id="fa758-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="fa758-130">下面的示例演示如何在 LINQ 查询中使用 `orderby descending` 子句按字符串的第一个字母对字符串进行降序排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="fa758-131">次要排序示例</span><span class="sxs-lookup"><span data-stu-id="fa758-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="fa758-132">次要升序排序</span><span class="sxs-lookup"><span data-stu-id="fa758-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="fa758-133">下面的示例演示如何在 LINQ 查询中使用 `orderby` 子句对数组中的字符串执行主要和次要排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="fa758-134">首先按字符串长度，其次按字符串的第一个字母，对字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="fa758-135">次要降序排序</span><span class="sxs-lookup"><span data-stu-id="fa758-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="fa758-136">下面的示例演示如何在 LINQ 查询中使用 `orderby descending` 子句按升序执行主要排序，按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="fa758-137">首先按字符串长度，其次按字符串的第一个字母，对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="fa758-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa758-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa758-138">See Also</span></span>

- <xref:System.Linq>  
- [<span data-ttu-id="fa758-139">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="fa758-139">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="fa758-140">orderby 子句</span><span class="sxs-lookup"><span data-stu-id="fa758-140">orderby clause</span></span>](../../../../csharp/language-reference/keywords/orderby-clause.md)  
- [<span data-ttu-id="fa758-141">如何：对 Join 子句的结果进行排序</span><span class="sxs-lookup"><span data-stu-id="fa758-141">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
- [<span data-ttu-id="fa758-142">如何：按任意词或字段对文本数据进行排序或筛选 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fa758-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
