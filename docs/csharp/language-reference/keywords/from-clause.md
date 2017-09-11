---
title: "from 子句（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- from_CSharpKeyword
- from
dev_langs:
- CSharp
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f0165144acfa8d0928015e8222179f7e69f19644
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="from-clause-c-reference"></a><span data-ttu-id="ec55c-102">from 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ec55c-102">from clause (C# Reference)</span></span>
<span data-ttu-id="ec55c-103">查询表达式必须以 `from` 子句开头。</span><span class="sxs-lookup"><span data-stu-id="ec55c-103">A query expression must begin with a `from` clause.</span></span> <span data-ttu-id="ec55c-104">此外，查询表达式可包含也以 `from` 子句开头的子查询。</span><span class="sxs-lookup"><span data-stu-id="ec55c-104">Additionally, a query expression can contain sub-queries, which also begin with a `from` clause.</span></span> <span data-ttu-id="ec55c-105">`from` 子句指定下列各项：</span><span class="sxs-lookup"><span data-stu-id="ec55c-105">The `from` clause specifies the following:</span></span>  
  
-   <span data-ttu-id="ec55c-106">将在其上运行查询或子查询的数据源。</span><span class="sxs-lookup"><span data-stu-id="ec55c-106">The data source on which the query or sub-query will be run.</span></span>  
  
-   <span data-ttu-id="ec55c-107">表示源序列中每个元素的本地范围变量。</span><span class="sxs-lookup"><span data-stu-id="ec55c-107">A local *range variable* that represents each element in the source sequence.</span></span>  
  
 <span data-ttu-id="ec55c-108">范围变量和数据源已强类型化。</span><span class="sxs-lookup"><span data-stu-id="ec55c-108">Both the range variable and the data source are strongly typed.</span></span> <span data-ttu-id="ec55c-109">`from` 子句中引用的数据源必须具有 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601> 类型之一，或 <xref:System.Linq.IQueryable%601> 等派生类型。</span><span class="sxs-lookup"><span data-stu-id="ec55c-109">The data source referenced in the `from` clause must have a type of <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, or a derived type such as <xref:System.Linq.IQueryable%601>.</span></span>  
  
 <span data-ttu-id="ec55c-110">在下面的示例中，`numbers` 是数据源，`num` 是范围变量。</span><span class="sxs-lookup"><span data-stu-id="ec55c-110">In the following example, `numbers` is the data source and `num` is the range variable.</span></span> <span data-ttu-id="ec55c-111">请注意，这两个变量都已强类型化，即使使用 [var](../../../csharp/language-reference/keywords/var.md) 关键字也是如此。</span><span class="sxs-lookup"><span data-stu-id="ec55c-111">Note that both variables are strongly typed even through the [var](../../../csharp/language-reference/keywords/var.md) keyword is used.</span></span>  
  
 <span data-ttu-id="ec55c-112">[!code-cs[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec55c-112">[!code-cs[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_1.cs)]</span></span>  
  
## <a name="the-range-variable"></a><span data-ttu-id="ec55c-113">范围变量</span><span class="sxs-lookup"><span data-stu-id="ec55c-113">The Range Variable</span></span>  
 <span data-ttu-id="ec55c-114">数据源实现 <xref:System.Collections.Generic.IEnumerable%601> 时，编译器推断范围变量的类型。</span><span class="sxs-lookup"><span data-stu-id="ec55c-114">The compiler infers the type of the range variable when the data source implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="ec55c-115">例如，如果源具有 `IEnumerable<Customer>` 类型，则范围变量会被推断为 `Customer`。</span><span class="sxs-lookup"><span data-stu-id="ec55c-115">For example, if the source has a type of `IEnumerable<Customer>`, then the range variable is inferred to be `Customer`.</span></span> <span data-ttu-id="ec55c-116">仅在以下情况下必须显式指定类型：源是 <xref:System.Collections.ArrayList> 等非泛型 `IEnumerable` 类型时。</span><span class="sxs-lookup"><span data-stu-id="ec55c-116">The only time that you must specify the type explicitly is when the source is a non-generic `IEnumerable` type such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="ec55c-117">有关详细信息，请参阅[如何：使用 LINQ 查询 ArrayList](http://msdn.microsoft.com/library/c318b79a-fa4d-4de3-b62d-c1162beb267e)。</span><span class="sxs-lookup"><span data-stu-id="ec55c-117">For more information, see [How to: Query an ArrayList with LINQ](http://msdn.microsoft.com/library/c318b79a-fa4d-4de3-b62d-c1162beb267e).</span></span>  
  
 <span data-ttu-id="ec55c-118">在以上示例中，`num` 推断为 `int` 类型。</span><span class="sxs-lookup"><span data-stu-id="ec55c-118">In the previous example `num` is inferred to be of type `int`.</span></span> <span data-ttu-id="ec55c-119">由于强类型化了范围变量，所以可以在其上调用方法，或将其用于其他操作中。</span><span class="sxs-lookup"><span data-stu-id="ec55c-119">Because the range variable is strongly typed, you can call methods on it or use it in other operations.</span></span> <span data-ttu-id="ec55c-120">例如，不再编写 `select num`，而编写 `select num.ToString()`，使查询表达式返回字符串序列，而不是整数序列。</span><span class="sxs-lookup"><span data-stu-id="ec55c-120">For example, instead of writing `select num`, you could write `select num.ToString()` to cause the query expression to return a sequence of strings instead of integers.</span></span> <span data-ttu-id="ec55c-121">或者可以编写 `select n + 10`，使表达式返回序列 14、11、13、12、10。</span><span class="sxs-lookup"><span data-stu-id="ec55c-121">Or you could write `select n + 10` to cause the expression to return the sequence 14, 11, 13, 12, 10.</span></span> <span data-ttu-id="ec55c-122">有关详细信息，请参阅 [select 子句](../../../csharp/language-reference/keywords/select-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="ec55c-122">For more information, see [select clause](../../../csharp/language-reference/keywords/select-clause.md).</span></span>  
  
 <span data-ttu-id="ec55c-123">范围变量与 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句中的迭代变量类似，一项非常重要的区别除外：范围变量从不实际存储来自源的数据。</span><span class="sxs-lookup"><span data-stu-id="ec55c-123">The range variable is like an iteration variable in a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement except for one very important difference: a range variable never actually stores data from the source.</span></span> <span data-ttu-id="ec55c-124">它只是一种语法上的便利，使执行查询时，查询能够描述将发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ec55c-124">It just a syntactic convenience that enables the query to describe what will occur when the query is executed.</span></span> <span data-ttu-id="ec55c-125">有关详细信息，请参阅 [LINQ 查询简介 (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="ec55c-125">For more information, see [Introduction to LINQ Queries (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="compound-from-clauses"></a><span data-ttu-id="ec55c-126">复合 from 子句</span><span class="sxs-lookup"><span data-stu-id="ec55c-126">Compound from Clauses</span></span>  
 <span data-ttu-id="ec55c-127">在某些情况下，源序列中的每个元素可能本身就是一个序列，或者包含一个序列。</span><span class="sxs-lookup"><span data-stu-id="ec55c-127">In some cases, each element in the source sequence may itself be either a sequence or contain a sequence.</span></span> <span data-ttu-id="ec55c-128">例如，数据源可能是 `IEnumerable<Student>`，其中序列中的每个学生对象都包含测试分数的列表。</span><span class="sxs-lookup"><span data-stu-id="ec55c-128">For example, your data source may be an `IEnumerable<Student>` where each student object in the sequence contains a list of test scores.</span></span> <span data-ttu-id="ec55c-129">要访问每个 `Student` 元素的内部列表，可以使用复合 `from` 子句。</span><span class="sxs-lookup"><span data-stu-id="ec55c-129">To access the inner list within each `Student` element, you can use compound `from` clauses.</span></span> <span data-ttu-id="ec55c-130">这种方法类似于使用嵌套的 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="ec55c-130">The technique is like using nested [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statements.</span></span> <span data-ttu-id="ec55c-131">可以向任一 `from`子句添加 [where](../../../csharp/language-reference/keywords/partial-method.md) 或 [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) 子句筛选结果。</span><span class="sxs-lookup"><span data-stu-id="ec55c-131">You can add [where](../../../csharp/language-reference/keywords/partial-method.md) or [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clauses to either `from` clause to filter the results.</span></span> <span data-ttu-id="ec55c-132">下面的示例演示 `Student` 对象的序列，其中每个对象都包含一个整数内部 `List`，表示测验分数。</span><span class="sxs-lookup"><span data-stu-id="ec55c-132">The following example shows a sequence of `Student` objects, each of which contains an inner `List` of integers representing test scores.</span></span> <span data-ttu-id="ec55c-133">访问内部列表可使用复合 `from` 子句。</span><span class="sxs-lookup"><span data-stu-id="ec55c-133">To access the inner list, use a compound `from` clause.</span></span> <span data-ttu-id="ec55c-134">如有必要，可以在这两个 `from` 子句间插入子句。</span><span class="sxs-lookup"><span data-stu-id="ec55c-134">You can insert clauses between the two `from` clauses if necessary.</span></span>  
  
 <span data-ttu-id="ec55c-135">[!code-cs[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec55c-135">[!code-cs[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_2.cs)]</span></span>  
  
## <a name="using-multiple-from-clauses-to-perform-joins"></a><span data-ttu-id="ec55c-136">使用多个 from 子句执行联接</span><span class="sxs-lookup"><span data-stu-id="ec55c-136">Using Multiple from Clauses to Perform Joins</span></span>  
 <span data-ttu-id="ec55c-137">复合 `from` 子句用于访问单个数据源中的内部集合。</span><span class="sxs-lookup"><span data-stu-id="ec55c-137">A compound `from` clause is used to access inner collections in a single data source.</span></span> <span data-ttu-id="ec55c-138">但是，查询也可以包含多个 `from` 子句，这些子句从独立的数据源生成补充查询。</span><span class="sxs-lookup"><span data-stu-id="ec55c-138">However, a query can also contain multiple `from` clauses that generate supplemental queries from independent data sources.</span></span> <span data-ttu-id="ec55c-139">通过此方法，可以执行使用 [join 子句](../../../csharp/language-reference/keywords/join-clause.md) 无法实现的某类联接操作。</span><span class="sxs-lookup"><span data-stu-id="ec55c-139">This technique enables you to perform certain types of join operations that are not possible by using the [join clause](../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
 <span data-ttu-id="ec55c-140">下面的示例演示两个 `from` 子句如何用于形成两个数据源的完全交叉联接。</span><span class="sxs-lookup"><span data-stu-id="ec55c-140">The following example shows how two `from` clauses can be used to form a complete cross join of two data sources.</span></span>  
  
 <span data-ttu-id="ec55c-141">[!code-cs[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec55c-141">[!code-cs[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_3.cs)]</span></span>  
  
 <span data-ttu-id="ec55c-142">有关使用多个 `from` 子句的联接操作的详细信息，请参阅[如何：执行自定义联接操作](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="ec55c-142">For more information about join operations that use multiple `from` clauses, see [How to: Perform Custom Join Operations](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec55c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec55c-143">See Also</span></span>  
 <span data-ttu-id="ec55c-144">[查询关键字 (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="ec55c-144">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 [<span data-ttu-id="ec55c-145">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="ec55c-145">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

