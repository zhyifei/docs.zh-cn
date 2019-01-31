---
title: 对数据排序 (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: dfa0a4a030cab8ec33c90d8edaef0d6070755034
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721898"
---
# <a name="sorting-data-c"></a><span data-ttu-id="b587e-102">对数据排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="b587e-102">Sorting Data (C#)</span></span>
<span data-ttu-id="b587e-103">排序操作基于一个或多个属性对序列的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="b587e-104">第一个排序条件对元素执行主要排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="b587e-105">通过指定第二个排序条件，您可以对每个主要排序组内的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="b587e-106">下图演示对一个字符序列执行按字母排序操作的结果。</span><span class="sxs-lookup"><span data-stu-id="b587e-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="b587e-107">![LINQ 排序操作](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="b587e-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="b587e-108">下节列出了对数据进行排序的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="b587e-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b587e-109">方法</span><span class="sxs-lookup"><span data-stu-id="b587e-109">Methods</span></span>  
  
|<span data-ttu-id="b587e-110">方法名</span><span class="sxs-lookup"><span data-stu-id="b587e-110">Method Name</span></span>|<span data-ttu-id="b587e-111">说明</span><span class="sxs-lookup"><span data-stu-id="b587e-111">Description</span></span>|<span data-ttu-id="b587e-112">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="b587e-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="b587e-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="b587e-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b587e-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="b587e-114">OrderBy</span></span>|<span data-ttu-id="b587e-115">按升序对值排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b587e-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="b587e-116">OrderByDescending</span></span>|<span data-ttu-id="b587e-117">按降序对值排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b587e-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="b587e-118">ThenBy</span></span>|<span data-ttu-id="b587e-119">按升序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b587e-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="b587e-120">ThenByDescending</span></span>|<span data-ttu-id="b587e-121">按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b587e-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="b587e-122">Reverse</span></span>|<span data-ttu-id="b587e-123">反转集合中元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="b587e-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="b587e-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="b587e-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="b587e-125">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="b587e-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="b587e-126">主要排序示例</span><span class="sxs-lookup"><span data-stu-id="b587e-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="b587e-127">主要升序排序</span><span class="sxs-lookup"><span data-stu-id="b587e-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="b587e-128">下面的示例演示如何在 LINQ 查询中使用 `orderby` 子句按字符串长度对数组中的字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="b587e-129">主要降序排序</span><span class="sxs-lookup"><span data-stu-id="b587e-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="b587e-130">下面的示例演示如何在 LINQ 查询中使用 `orderby descending` 子句按字符串的第一个字母对字符串进行降序排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="b587e-131">次要排序示例</span><span class="sxs-lookup"><span data-stu-id="b587e-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="b587e-132">次要升序排序</span><span class="sxs-lookup"><span data-stu-id="b587e-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="b587e-133">下面的示例演示如何在 LINQ 查询中使用 `orderby` 子句对数组中的字符串执行主要和次要排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="b587e-134">首先按字符串长度，其次按字符串的第一个字母，对字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="b587e-135">次要降序排序</span><span class="sxs-lookup"><span data-stu-id="b587e-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="b587e-136">下面的示例演示如何在 LINQ 查询中使用 `orderby descending` 子句按升序执行主要排序，按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="b587e-137">首先按字符串长度，其次按字符串的第一个字母，对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="b587e-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b587e-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="b587e-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b587e-139">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="b587e-139">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b587e-140">orderby 子句</span><span class="sxs-lookup"><span data-stu-id="b587e-140">orderby clause</span></span>](../../../../csharp/language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="b587e-141">如何：对 join 子句的结果进行排序</span><span class="sxs-lookup"><span data-stu-id="b587e-141">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="b587e-142">如何：按任意词或字段对文本数据进行排序或筛选 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b587e-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
