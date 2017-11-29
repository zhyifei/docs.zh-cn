---
title: "在 C# 中编写 LINQ 查询"
description: "如何编写查询。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: f3efbfd232bd7e19d3db56289f57724c71dca064
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="2bfa9-104">在 C# 中编写 LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="2bfa9-104">Write LINQ queries in C#</span></span>

<span data-ttu-id="2bfa9-105">本主题介绍可以用于在 C# 中编写 LINQ 查询的三种方法：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-105">This topic shows the three ways in which you can write a LINQ query in C#:</span></span>  
  
1.  <span data-ttu-id="2bfa9-106">使用查询语法。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-106">Use query syntax.</span></span>  
  
2.  <span data-ttu-id="2bfa9-107">使用方法语法。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-107">Use method syntax.</span></span>  
  
3.  <span data-ttu-id="2bfa9-108">结合使用查询语法和方法语法。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-108">Use a combination of query syntax and method syntax.</span></span>  
  
 <span data-ttu-id="2bfa9-109">下面的示例演示使用前面列出的每种方法的一些简单 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-109">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="2bfa9-110">一般情况下，规则是尽可能使用 (1)，每当需要时使用 (2) 和 (3)。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-110">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bfa9-111">这些查询对简单的内存中集合进行操作；但是，基本语法等同于在 LINQ to Entities 和 LINQ to XML 中使用的语法。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-111">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bfa9-112">示例</span><span class="sxs-lookup"><span data-stu-id="2bfa9-112">Example</span></span>  
  
## <a name="query-syntax"></a><span data-ttu-id="2bfa9-113">查询语法</span><span class="sxs-lookup"><span data-stu-id="2bfa9-113">Query syntax</span></span>  
 <span data-ttu-id="2bfa9-114">编写大多数查询的推荐方式是使用查询语法创建查询表达式。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-114">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="2bfa9-115">下面的示例演示三个查询表达式。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-115">The following example shows three query expressions.</span></span> <span data-ttu-id="2bfa9-116">第一个查询表达式演示如何通过应用包含 `where` 子句的条件来筛选或限制结果。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-116">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="2bfa9-117">它返回源序列中值大于 7 或小于 3 的所有元素。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-117">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="2bfa9-118">第二个表达式演示如何对返回的结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-118">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="2bfa9-119">第三个表达式演示如何根据某个键对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-119">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="2bfa9-120">此查询基于单词的第一个字母返回两个组。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-120">This query returns two groups based on the first letter of the word.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#5](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]  
  
 <span data-ttu-id="2bfa9-121">注意，查询类型为 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-121">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="2bfa9-122">可以使用 `var` 编写所有这些查询，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-122">All of these queries could be written using `var` as shown in the following example:</span></span>  
  
 `var query = from num in numbers...`  
  
 <span data-ttu-id="2bfa9-123">在前面的每个示例中，在 `foreach` 语句或其他语句中循环访问查询变量之前，查询不会实际执行。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-123">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="2bfa9-124">有关详细信息，请参阅 [LINQ 查询介绍](../programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-124">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bfa9-125">示例</span><span class="sxs-lookup"><span data-stu-id="2bfa9-125">Example</span></span>  
  
## <a name="method-syntax"></a><span data-ttu-id="2bfa9-126">方法语法</span><span class="sxs-lookup"><span data-stu-id="2bfa9-126">Method syntax</span></span>  
 <span data-ttu-id="2bfa9-127">某些查询操作必须表示为方法调用。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-127">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="2bfa9-128">最常见的此类方法是可返回单一数值的方法，例如 <xref:System.Linq.Enumerable.Sum%2A>、<xref:System.Linq.Enumerable.Max%2A>、<xref:System.Linq.Enumerable.Min%2A>、<xref:System.Linq.Enumerable.Average%2A> 等。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-128">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="2bfa9-129">这些方法在任何查询中都必须始终最后一个调用，因为它们只表示单个值，不能用作其他查询操作的源。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-129">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="2bfa9-130">下面的示例演示查询表达式中的方法调用：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-130">The following example shows a method call in a query expression:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#6](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="2bfa9-131">示例</span><span class="sxs-lookup"><span data-stu-id="2bfa9-131">Example</span></span>  
 <span data-ttu-id="2bfa9-132">如果方法具有 Action 或 Func 参数，则这些参数以 [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) 表达式的形式提供，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-132">If the method has  Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#7](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]  
  
 <span data-ttu-id="2bfa9-133">在上面的查询中，只有查询 #4 立即执行。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-133">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="2bfa9-134">这是因为它将返回单个值，而不是泛型 <xref:System.Collections.Generic.IEnumerable%601> 集合。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-134">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="2bfa9-135">该方法本身必须使用 `foreach` 才能计算其值。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-135">The method itself has to use `foreach` in order to compute its value.</span></span>  
  
 <span data-ttu-id="2bfa9-136">上面的每个查询可以通过 [var](../language-reference/keywords/var.md) 使用隐式类型化进行编写，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-136">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#8](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="2bfa9-137">示例</span><span class="sxs-lookup"><span data-stu-id="2bfa9-137">Example</span></span>  
  
## <a name="mixed-query-and-method-syntax"></a><span data-ttu-id="2bfa9-138">混合查询和方法语法</span><span class="sxs-lookup"><span data-stu-id="2bfa9-138">Mixed query and method syntax</span></span>  
 <span data-ttu-id="2bfa9-139">此示例演示如何对查询子句的结果使用方法语法。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-139">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="2bfa9-140">只需将查询表达式括在括号中，然后应用点运算符并调用方法。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-140">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="2bfa9-141">在下面的示例中，查询 #7 返回对值介于 3 与 7 之间的数字进行的计数。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-141">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="2bfa9-142">但是通常情况下，最好使用另一个变量存储方法调用的结果。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-142">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="2bfa9-143">采用此方法时，查询不太可能与查询的结果相混淆。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-143">In this manner, the query is less likely to be confused with the results of the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#9](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]  
  
 <span data-ttu-id="2bfa9-144">由于查询 #7 返回单个值而不是集合，因此查询立即执行。</span><span class="sxs-lookup"><span data-stu-id="2bfa9-144">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>  
  
 <span data-ttu-id="2bfa9-145">前面的查询可以通过 `var` 使用隐式类型化进行编写，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-145">The previous query can be written by using implicit typing with `var`, as follows:</span></span>  
  
```csharp  
var numCount = (from num in numbers...  
```  
  
 <span data-ttu-id="2bfa9-146">它可以采用方法语法进行编写，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-146">It can be written in method syntax as follows:</span></span>  
  
```csharp  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 <span data-ttu-id="2bfa9-147">它可以使用显式类型化进行编写，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2bfa9-147">It can be written by using explicit typing, as follows:</span></span>  
  
```csharp  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## <a name="see-also"></a><span data-ttu-id="2bfa9-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bfa9-148">See Also</span></span>  
  <span data-ttu-id="2bfa9-149">[演练：用 C# 编写查询](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="2bfa9-149">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 [<span data-ttu-id="2bfa9-150">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="2bfa9-150">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="2bfa9-151">where 子句</span><span class="sxs-lookup"><span data-stu-id="2bfa9-151">where clause</span></span>](../language-reference/keywords/where-clause.md)
