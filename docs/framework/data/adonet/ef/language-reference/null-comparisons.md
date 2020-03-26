---
title: Null 比较
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 697c933daeb3c68fb4ea89a957b639a79a9407f8
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249651"
---
# <a name="null-comparisons"></a><span data-ttu-id="4bbaf-102">Null 比较</span><span class="sxs-lookup"><span data-stu-id="4bbaf-102">Null Comparisons</span></span>
<span data-ttu-id="4bbaf-103">数据源中的 `null` 值指示未知的值。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-103">A `null` value in the data source indicates that the value is unknown.</span></span> <span data-ttu-id="4bbaf-104">在 LINQ 到实体查询中，可以检查空值，以便某些计算或比较仅对具有有效或非空数据的行执行。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-104">In LINQ to Entities queries, you can check for null values so that certain calculations or comparisons are only performed on rows that have valid, or non-null, data.</span></span> <span data-ttu-id="4bbaf-105">但是，CLR null 语义可能与数据源的 null 语义不同。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-105">CLR null semantics, however, may differ from the null semantics of the data source.</span></span> <span data-ttu-id="4bbaf-106">大多数数据库使用某个版本的三值逻辑处理 null 比较。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-106">Most databases use a version of three-valued logic to handle null comparisons.</span></span> <span data-ttu-id="4bbaf-107">即，对 null 值的比较不会计算为 `true` 或 `false`，而是计算为 `unknown`。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-107">That is, a comparison against a null value does not evaluate to `true` or `false`, it evaluates to `unknown`.</span></span> <span data-ttu-id="4bbaf-108">通常这是 ANSI null 值的实现，但情况并非总是如此。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-108">Often this is an implementation of ANSI nulls, but this is not always the case.</span></span>  
  
 <span data-ttu-id="4bbaf-109">在 SQL Server 中，null 等于 null 比较默认返回 null 值。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-109">By default in SQL Server, the null-equals-null comparison returns a null value.</span></span> <span data-ttu-id="4bbaf-110">在下面的示例中，结果集中排除了空`ShipDate`行，Transact-SQL 语句将返回 0 行。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-110">In the following example, the rows where `ShipDate` is null are excluded from the result set, and the Transact-SQL statement would return 0 rows.</span></span>  
  
```sql  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 <span data-ttu-id="4bbaf-111">这与 CLR null 语义有很大差异，在 CLR null 语义中 null 等于 null 比较返回 true。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-111">This is very different from the CLR null semantics, where the null-equals-null comparison returns true.</span></span>  
  
 <span data-ttu-id="4bbaf-112">下面的 LINQ 查询以 CLR 表示，但在数据源中执行。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-112">The following LINQ query is expressed in the CLR, but it is executed in the data source.</span></span> <span data-ttu-id="4bbaf-113">由于无法保证在数据源中会遵循 CLR 语义，因此预期行为是不确定的。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-113">Because there is no guarantee that CLR semantics will be honored at the data source, the expected behavior is indeterminate.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a><span data-ttu-id="4bbaf-114">键选择器</span><span class="sxs-lookup"><span data-stu-id="4bbaf-114">Key Selectors</span></span>  
 <span data-ttu-id="4bbaf-115">*键选择器*是标准查询运算符中用于从元素中提取密钥的函数。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-115">A *key selector* is a function used in the standard query operators to extract a key from an element.</span></span> <span data-ttu-id="4bbaf-116">在键选择器函数中，表达式可以与常量进行比较。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-116">In the key selector function, an expression can be compared with a constant.</span></span> <span data-ttu-id="4bbaf-117">如果表达式与 null 常量进行比较或两个 null 常量进行比较，则会展现 CLR null 语义。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-117">CLR null semantics are exhibited if an expression is compared to a null constant or if two null constants are compared.</span></span> <span data-ttu-id="4bbaf-118">如果数据源中具有 null 值的两个列进行比较，则会展现存储 null 语义。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-118">Store null semantics are exhibited if two columns with null values in the data source are compared.</span></span> <span data-ttu-id="4bbaf-119">键选择器出现在许多分组和排序标准查询运算符（如 <xref:System.Linq.Queryable.GroupBy%2A>）中，用于选择对查询结果进行排序或分组所依据的键。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-119">Key selectors are found in many of the grouping and ordering standard query operators, such as <xref:System.Linq.Queryable.GroupBy%2A>, and are used to select keys by which to order or group the query results.</span></span>  
  
## <a name="null-property-on-a-null-object"></a><span data-ttu-id="4bbaf-120">Null 对象上的 Null 属性</span><span class="sxs-lookup"><span data-stu-id="4bbaf-120">Null Property on a Null Object</span></span>  
 <span data-ttu-id="4bbaf-121">在实体框架中，空对象的属性为空。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-121">In the Entity Framework, the properties of a null object are null.</span></span> <span data-ttu-id="4bbaf-122">当尝试引用 CLR 中的 null 对象的属性时，会收到 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-122">When you attempt to reference a property of a null object in the CLR, you will receive a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="4bbaf-123">当 LINQ 查询涉及 null 对象的属性时，可能会导致不一致的行为。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-123">When a LINQ query involves a property of a null object, this can result in inconsistent behavior.</span></span>  
  
 <span data-ttu-id="4bbaf-124">例如，下面的查询在命令树层中执行对 `NewProduct` 的强制转换，这可能导致 `Introduced` 属性为 null。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-124">For example, in the following query, the cast to `NewProduct` is done in the command tree layer, which might result in the `Introduced` property being null.</span></span> <span data-ttu-id="4bbaf-125">如果数据库将 null 比较定义为 <xref:System.DateTime> 比较计算为 true，则会包含该行。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-125">If the database defined null comparisons such that the <xref:System.DateTime> comparison evaluates to true, the row will be included.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a><span data-ttu-id="4bbaf-126">将 Null 集合传递到聚合函数</span><span class="sxs-lookup"><span data-stu-id="4bbaf-126">Passing Null Collections to Aggregate Functions</span></span>  
 <span data-ttu-id="4bbaf-127">在 LINQ 到实体中，当您将支持`IQueryable`聚合函数的集合传递给聚合函数时，聚合操作将在数据库中执行。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-127">In LINQ to Entities, when you pass a collection that supports `IQueryable` to an aggregate function, aggregate operations are performed at the database.</span></span> <span data-ttu-id="4bbaf-128">在内存中执行的查询的结果与在数据库中执行的查询的结果可能有差异。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-128">There might be differences in the results of a query that was performed in-memory and a query that was performed at the database.</span></span> <span data-ttu-id="4bbaf-129">对于内存中查询，如果没有匹配项，查询将返回零。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-129">With an in-memory query, if there are no matches, the query returns zero.</span></span> <span data-ttu-id="4bbaf-130">在数据库中，同一查询返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-130">At the database, the same query returns `null`.</span></span> <span data-ttu-id="4bbaf-131">如果将`null`值传递给 LINQ 聚合函数，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-131">If a `null` value is passed to a LINQ aggregate function, an exception will be thrown.</span></span> <span data-ttu-id="4bbaf-132">要接受可能`null`的值，请将接收查询结果的类型和属性转换为空值类型。</span><span class="sxs-lookup"><span data-stu-id="4bbaf-132">To accept possible `null` values, cast the types and the properties of the types that receive query results to nullable value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bbaf-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bbaf-133">See also</span></span>

- [<span data-ttu-id="4bbaf-134">LINQ to Entities 查询中的表达式</span><span class="sxs-lookup"><span data-stu-id="4bbaf-134">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
