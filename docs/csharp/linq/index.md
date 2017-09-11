---
title: "语言集成查询 (LINQ)"
description: "介绍了 C# 中的语言集成查询 (LINQ)"
keywords: .NET, .NET Core, LINQ, C#
author: BillWagner
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 007cc736-f5cf-4919-b99b-0c00ab2814ce
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: da116ce67428e9349e03dea60b35abd52dcffee2
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="language-integrated-query-linq"></a><span data-ttu-id="28764-104">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="28764-104">Language Integrated Query (LINQ)</span></span>

<span data-ttu-id="28764-105">语言集成查询 (LINQ) 是一系列直接将查询功能集成到 C# 语言的技术统称。</span><span class="sxs-lookup"><span data-stu-id="28764-105">Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language.</span></span> <span data-ttu-id="28764-106">数据查询历来都表示为简单的字符串，没有编译时类型检查或 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="28764-106">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="28764-107">此外，对于每种数据源，还需要学习不同的查询语言：SQL 数据库、XML 文档、各种 Web 服务等。</span><span class="sxs-lookup"><span data-stu-id="28764-107">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="28764-108">借助 LINQ，查询成为了最高级的语言构造，就像类、方法和事件一样。</span><span class="sxs-lookup"><span data-stu-id="28764-108">With LINQ, a query is a first-class language construct, just like classes, methods, events.</span></span>

<span data-ttu-id="28764-109">对于编写查询的开发者来说，LINQ 最明显的“语言集成”部分就是查询表达式。</span><span class="sxs-lookup"><span data-stu-id="28764-109">For a developer who writes queries, the most visible "language-integrated" part of LINQ is the query expression.</span></span> <span data-ttu-id="28764-110">查询表达式采用声明性*查询语法*编写而成。</span><span class="sxs-lookup"><span data-stu-id="28764-110">Query expressions are written in a declarative *query syntax*.</span></span> <span data-ttu-id="28764-111">使用查询语法，可以用最少的代码对数据源执行筛选、排序和分组操作。</span><span class="sxs-lookup"><span data-stu-id="28764-111">By using query syntax, you can perform filtering, ordering, and grouping operations on data sources with a minimum of code.</span></span> <span data-ttu-id="28764-112">可使用相同的基本查询表达式模式来查询和转换 SQL 数据库、ADO .NET 数据集、XML 文档和流以及 .NET 集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="28764-112">You use the same basic query expression patterns to query and transform data in SQL databases, ADO .NET Datasets, XML documents and streams, and .NET collections.</span></span>

<span data-ttu-id="28764-113">下面的示例展示了完整的查询操作。</span><span class="sxs-lookup"><span data-stu-id="28764-113">The following example shows the complete query operation.</span></span> <span data-ttu-id="28764-114">完整的操作包括创建数据源、定义查询表达式和在 `foreach` 语句中执行查询。</span><span class="sxs-lookup"><span data-stu-id="28764-114">The complete operation includes creating a data source, defining the query expression, and executing the query in a `foreach` statement.</span></span>

<span data-ttu-id="28764-115">[!code-cs[csProgGuideLINQ#11](../../../samples/snippets/csharp/concepts/linq/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="28764-115">[!code-cs[csProgGuideLINQ#11](../../../samples/snippets/csharp/concepts/linq/index_1.cs)]</span></span>

## <a name="query-expression-overview"></a><span data-ttu-id="28764-116">查询表达式概述</span><span class="sxs-lookup"><span data-stu-id="28764-116">Query expression overview</span></span>

-   <span data-ttu-id="28764-117">查询表达式可用于查询并转换所有启用了 LINQ 的数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="28764-117">Query expressions can be used to query and to transform data from any LINQ-enabled data source.</span></span> <span data-ttu-id="28764-118">例如，通过一个查询即可检索 SQL 数据库中的数据，并生成 XML 流作为输出。</span><span class="sxs-lookup"><span data-stu-id="28764-118">For example, a single query can retrieve data from a SQL database, and produce an XML stream as output.</span></span>  
  
-   <span data-ttu-id="28764-119">查询表达式易于掌握，因为使用了许多熟悉的 C# 语言构造。</span><span class="sxs-lookup"><span data-stu-id="28764-119">Query expressions are easy to master because they use many familiar C# language constructs.</span></span>  
  
-   <span data-ttu-id="28764-120">查询表达式中的变量全都是强类型，尽管在许多情况下，无需显式提供类型，因为编译器可以推断出。</span><span class="sxs-lookup"><span data-stu-id="28764-120">The variables in a query expression are all strongly typed, although in many cases you do not have to provide the type explicitly because the compiler can infer it.</span></span> <span data-ttu-id="28764-121">有关详细信息，请参阅 [LINQ 查询操作中的类型关系](../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="28764-121">For more information, see [Type relationships in LINQ query operations](../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
-   <span data-ttu-id="28764-122">只有在循环访问查询变量后，才会执行查询（例如，在 `foreach` 语句中）。</span><span class="sxs-lookup"><span data-stu-id="28764-122">A query is not executed until you iterate over the query variable, for example, in a `foreach` statement.</span></span> <span data-ttu-id="28764-123">有关详细信息，请参阅 [LINQ 查询简介](../programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="28764-123">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
-   <span data-ttu-id="28764-124">在编译时，查询表达式根据 C# 规范规则转换成标准查询运算符方法调用。</span><span class="sxs-lookup"><span data-stu-id="28764-124">At compile time, query expressions are converted to Standard Query Operator method calls according to the rules set forth in the C# specification.</span></span> <span data-ttu-id="28764-125">可使用查询语法表示的任何查询都可以使用方法语法进行表示。</span><span class="sxs-lookup"><span data-stu-id="28764-125">Any query that can be expressed by using query syntax can also be expressed by using method syntax.</span></span> <span data-ttu-id="28764-126">不过，在大多数情况下，查询语法的可读性更高，也更为简洁。</span><span class="sxs-lookup"><span data-stu-id="28764-126">However, in most cases query syntax is more readable and concise.</span></span> <span data-ttu-id="28764-127">有关详细信息，请参阅 [C# 语言规范](../language-reference/language-specification/index.md)和[标准查询运算符概述](../programming-guide/concepts/linq/standard-query-operators-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="28764-127">For more information, see [C# language specification](../language-reference/language-specification/index.md) and [Standard query operators overview](../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
-   <span data-ttu-id="28764-128">通常，我们建议在编写 LINQ 查询时尽量使用查询语法，并在必要时尽可能使用方法语法。</span><span class="sxs-lookup"><span data-stu-id="28764-128">As a rule when you write LINQ queries, we recommend that you use query syntax whenever possible and method syntax whenever necessary.</span></span> <span data-ttu-id="28764-129">这两种不同的形式在语义或性能上毫无差异。</span><span class="sxs-lookup"><span data-stu-id="28764-129">There is no semantic or performance difference between the two different forms.</span></span> <span data-ttu-id="28764-130">查询表达式通常比使用方法语法编写的等同表达式更具可读性。</span><span class="sxs-lookup"><span data-stu-id="28764-130">Query expressions are often more readable than equivalent expressions written in method syntax.</span></span>  
  
-   <span data-ttu-id="28764-131">一些查询操作（如 <xref:System.Linq.Enumerable.Count%2A> 或 <xref:System.Linq.Enumerable.Max%2A>）没有等效的查询表达式子句，因此必须表示为方法调用。</span><span class="sxs-lookup"><span data-stu-id="28764-131">Some query operations, such as <xref:System.Linq.Enumerable.Count%2A> or <xref:System.Linq.Enumerable.Max%2A>, have no equivalent query expression clause and must therefore be expressed as a method call.</span></span> <span data-ttu-id="28764-132">可以各种方式结合使用方法语法和查询语法。</span><span class="sxs-lookup"><span data-stu-id="28764-132">Method syntax can be combined with query syntax in various ways.</span></span> <span data-ttu-id="28764-133">有关详细信息，请参阅 [LINQ 中的查询语法和方法语法](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="28764-133">For more information, see [Query syntax and method syntax in LINQ](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
-   <span data-ttu-id="28764-134">查询表达式可被编译成表达式树或委托，具体视应用查询的类型而定。</span><span class="sxs-lookup"><span data-stu-id="28764-134">Query expressions can be compiled to expression trees or to delegates, depending on the type that the query is applied to.</span></span> <span data-ttu-id="28764-135"><xref:System.Collections.Generic.IEnumerable%601> 查询编译为委托。</span><span class="sxs-lookup"><span data-stu-id="28764-135"><xref:System.Collections.Generic.IEnumerable%601> queries are compiled to delegates.</span></span> <span data-ttu-id="28764-136"><xref:System.Linq.IQueryable> 和 <xref:System.Linq.IQueryable%601> 查询编译为表达式树。</span><span class="sxs-lookup"><span data-stu-id="28764-136"><xref:System.Linq.IQueryable> and <xref:System.Linq.IQueryable%601> queries are compiled to expression trees.</span></span> <span data-ttu-id="28764-137">有关详细信息，请参阅[表达式树](../expression-trees.md)。</span><span class="sxs-lookup"><span data-stu-id="28764-137">For more information, see [Expression trees](../expression-trees.md).</span></span>  

## <a name="next-steps"></a><span data-ttu-id="28764-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="28764-138">Next steps</span></span>

<span data-ttu-id="28764-139">若要详细了解 LINQ，请先自行熟悉[查询表达式基础知识](query-expression-basics.md)中的一些基本概念，然后再阅读感兴趣的 LINQ 技术的相关文档：</span><span class="sxs-lookup"><span data-stu-id="28764-139">To learn more details about LINQ, start by becoming familiar with some basic concepts in [Query expression basics](query-expression-basics.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>   
-   <span data-ttu-id="28764-140">XML 文档：[LINQ to XML](../programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="28764-140">XML documents: [LINQ to XML](../programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="28764-141">ADO.NET 实体框架：[LINQ to Entities](../../framework/data/adonet/ef/language-reference/linq-to-entities.md)</span><span class="sxs-lookup"><span data-stu-id="28764-141">ADO.NET Entity Framework: [LINQ to entities](../../framework/data/adonet/ef/language-reference/linq-to-entities.md)</span></span>  
  
-   <span data-ttu-id="28764-142">.NET 集合、文件、字符串等：[LINQ to Objects](../programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="28764-142">.NET collections, files, strings and so on: [LINQ to objects](../programming-guide/concepts/linq/linq-to-objects.md)</span></span>

<span data-ttu-id="28764-143">若要更深入地全面了解 LINQ，请参阅 [C# 中的 LINQ](linq-in-csharp.md)。</span><span class="sxs-lookup"><span data-stu-id="28764-143">To gain a deeper understanding of LINQ in general, see [LINQ in C#](linq-in-csharp.md).</span></span>

<span data-ttu-id="28764-144">若要开始在 C# 中使用 LINQ，请参阅教程[使用 LINQ](../tutorials/working-with-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="28764-144">To start working with LINQ in C#, see the tutorial [Working with LINQ](../tutorials/working-with-linq.md).</span></span>



