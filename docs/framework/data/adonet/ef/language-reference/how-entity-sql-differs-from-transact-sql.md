---
title: Entity SQL 与 Transact-SQL 有何不同
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 299cb9bbe90c72619cf809a8fc673fca456bd6fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150226"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="e7b90-102">Entity SQL 与 Transact-SQL 有何不同</span><span class="sxs-lookup"><span data-stu-id="e7b90-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="e7b90-103">本主题介绍和交易[!INCLUDE[esql](../../../../../../includes/esql-md.md)]SQL 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e7b90-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="e7b90-104">继承和关系支持</span><span class="sxs-lookup"><span data-stu-id="e7b90-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-105">直接使用概念实体架构并支持诸如继承和关系等概念模型功能。</span><span class="sxs-lookup"><span data-stu-id="e7b90-105">works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="e7b90-106">使用继承时，从父类型实例集合中选择子类型的实例通常是有用的。</span><span class="sxs-lookup"><span data-stu-id="e7b90-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="e7b90-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]中的[类型](oftype-entity-sql.md)运算符（类似于`oftype`C# 序列中）提供此功能。</span><span class="sxs-lookup"><span data-stu-id="e7b90-107">The [oftype](oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="e7b90-108">集合支持</span><span class="sxs-lookup"><span data-stu-id="e7b90-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-109">将集合视为一类实体。</span><span class="sxs-lookup"><span data-stu-id="e7b90-109">treats collections as first-class entities.</span></span> <span data-ttu-id="e7b90-110">例如：</span><span class="sxs-lookup"><span data-stu-id="e7b90-110">For example:</span></span>  
  
- <span data-ttu-id="e7b90-111">集合表达式在 `from` 子句中有效。</span><span class="sxs-lookup"><span data-stu-id="e7b90-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="e7b90-112">`in` 和 `exists` 子查询已被一般化，以允许使用任何集合。</span><span class="sxs-lookup"><span data-stu-id="e7b90-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="e7b90-113">子查询是一种集合。</span><span class="sxs-lookup"><span data-stu-id="e7b90-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="e7b90-114">`e1 in e2` 和 `exists(e)` 是执行这些运算的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 构造。</span><span class="sxs-lookup"><span data-stu-id="e7b90-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="e7b90-115">集运算（例如 `union`、`intersect` 和 `except`）现在对集合执行运算。</span><span class="sxs-lookup"><span data-stu-id="e7b90-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="e7b90-116">联接对集合执行运算。</span><span class="sxs-lookup"><span data-stu-id="e7b90-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="e7b90-117">对表达式的支持</span><span class="sxs-lookup"><span data-stu-id="e7b90-117">Support for Expressions</span></span>  
 <span data-ttu-id="e7b90-118">Transact-SQL 具有子查询（表）和表达式（行和列）。</span><span class="sxs-lookup"><span data-stu-id="e7b90-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="e7b90-119">要支持集合和嵌套集合，[!INCLUDE[esql](../../../../../../includes/esql-md.md)]使一切成为表达式。</span><span class="sxs-lookup"><span data-stu-id="e7b90-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e7b90-120">比 Transact-SQL 更可组合， 每个表达式都可以在任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="e7b90-120">is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="e7b90-121">查询表达式总是产生投影类型的集合，并且可以在允许使用集合表达式的任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="e7b90-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="e7b90-122">有关 中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]不支持的 Transact SQL 表达式的信息，请参阅[。](unsupported-expressions-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="e7b90-122">For information about Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="e7b90-123">下面是所有有效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询。</span><span class="sxs-lookup"><span data-stu-id="e7b90-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="e7b90-124">子查询统一处理</span><span class="sxs-lookup"><span data-stu-id="e7b90-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="e7b90-125">鉴于它强调表，Transact-SQL 对子查询执行上下文解释。</span><span class="sxs-lookup"><span data-stu-id="e7b90-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="e7b90-126">例如，`from` 子句中的子查询被视为多集（表）。</span><span class="sxs-lookup"><span data-stu-id="e7b90-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="e7b90-127">但是，`select` 子句中使用的同一子查询被视为标量子查询。</span><span class="sxs-lookup"><span data-stu-id="e7b90-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="e7b90-128">同样，运算符左侧`in`使用的子查询被视为标量子查询，而右侧应被视为多集子查询。</span><span class="sxs-lookup"><span data-stu-id="e7b90-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-129">消除了这些差异。</span><span class="sxs-lookup"><span data-stu-id="e7b90-129">eliminates these differences.</span></span> <span data-ttu-id="e7b90-130">表达式具有不依赖于使用它的上下文的统一解释。</span><span class="sxs-lookup"><span data-stu-id="e7b90-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e7b90-131">将所有子查询视为多集子查询。</span><span class="sxs-lookup"><span data-stu-id="e7b90-131">considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="e7b90-132">如果需要从子查询获取标量值，则 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 会提供对集合（在此情况下为子查询）进行运算的 `anyelement` 运算符，并从集合中提取单一实例值。</span><span class="sxs-lookup"><span data-stu-id="e7b90-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="e7b90-133">避免对子查询执行隐式强制转换</span><span class="sxs-lookup"><span data-stu-id="e7b90-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="e7b90-134">与统一处理子查询相关的一个副作用是将子查询隐式转换为标量值。</span><span class="sxs-lookup"><span data-stu-id="e7b90-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="e7b90-135">具体而言，在 Transact-SQL 中，多组行（具有单个字段）隐式转换为数据类型为字段的标量值。</span><span class="sxs-lookup"><span data-stu-id="e7b90-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-136">不支持这种隐式强制。</span><span class="sxs-lookup"><span data-stu-id="e7b90-136">does not support this implicit coercion.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-137">提供 ANYELEMENT 运算符从集合中提取单一实例值，并提供 `select value` 子句以避免在查询表达式中创建行包装。</span><span class="sxs-lookup"><span data-stu-id="e7b90-137">provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="e7b90-138">Select Value：避免隐式行包装</span><span class="sxs-lookup"><span data-stu-id="e7b90-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="e7b90-139">Transact-SQL 子查询中的 select 子查询中隐式创建围绕子句中的项的行包装器。</span><span class="sxs-lookup"><span data-stu-id="e7b90-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="e7b90-140">这意味着我们无法创建标量或对象的集合。</span><span class="sxs-lookup"><span data-stu-id="e7b90-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="e7b90-141">Transact-SQL 允许在具有一个字段的行型和相同数据类型的单例值之间隐式强制。</span><span class="sxs-lookup"><span data-stu-id="e7b90-141">Transact-SQL allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-142">提供了 `select value` 子句，以跳过隐式行构建。</span><span class="sxs-lookup"><span data-stu-id="e7b90-142">provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="e7b90-143">在 `select value` 子句中只能指定一个项。</span><span class="sxs-lookup"><span data-stu-id="e7b90-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="e7b90-144">在使用这样的子句时，不会对 `select` 子句中的项构造行包装，并且可生成所需形状的集合，例如：`select value a`。</span><span class="sxs-lookup"><span data-stu-id="e7b90-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-145">还提供了用于构造任意行的行构造函数。</span><span class="sxs-lookup"><span data-stu-id="e7b90-145">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="e7b90-146">`select` 接受投影中的一个或多个元素，并生成含有字段的数据记录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7b90-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="e7b90-147">左相关与别名化</span><span class="sxs-lookup"><span data-stu-id="e7b90-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="e7b90-148">在 Transact-SQL 中，给定作用域中的表达式（单个子句`select`（`from`如 或 ） 不能引用之前在同一作用域中定义的表达式。</span><span class="sxs-lookup"><span data-stu-id="e7b90-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="e7b90-149">SQL 的某些方言（包括 Transact-SQL）确实支持`from`子句中的有限形式。</span><span class="sxs-lookup"><span data-stu-id="e7b90-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-150">在 `from` 子句中对左相关进行了一般化，并且对它们进行了统一处理。</span><span class="sxs-lookup"><span data-stu-id="e7b90-150">generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="e7b90-151">`from` 子句中的表达式无需使用额外的语法，即可引用同一子句中先前的定义（位于左侧的定义）。</span><span class="sxs-lookup"><span data-stu-id="e7b90-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-152">还对涉及 `group by` 子句的查询施加了额外的限制。</span><span class="sxs-lookup"><span data-stu-id="e7b90-152">also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="e7b90-153">此类查询的 `select` 子句和 `having` 子句中的表达式只能通过其别名引用 `group by` 关键字。</span><span class="sxs-lookup"><span data-stu-id="e7b90-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="e7b90-154">以下构造在 Transact-SQL 中有效，但不在[!INCLUDE[esql](../../../../../../includes/esql-md.md)]中：</span><span class="sxs-lookup"><span data-stu-id="e7b90-154">The following construct is valid in Transact-SQL but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="e7b90-155">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 执行此操作</span><span class="sxs-lookup"><span data-stu-id="e7b90-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="e7b90-156">引用表（集合）的列（属性）</span><span class="sxs-lookup"><span data-stu-id="e7b90-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="e7b90-157">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的所有列引用都必须用表别名限定。</span><span class="sxs-lookup"><span data-stu-id="e7b90-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="e7b90-158">以下构造（假设是`a`表`T`的有效列）在 Transact-SQL 中有效，但在 中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]无效。</span><span class="sxs-lookup"><span data-stu-id="e7b90-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="e7b90-159">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 形式为</span><span class="sxs-lookup"><span data-stu-id="e7b90-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="e7b90-160">表别名在 `from` 子句中是可选的。</span><span class="sxs-lookup"><span data-stu-id="e7b90-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="e7b90-161">表名称被用作隐式别名。</span><span class="sxs-lookup"><span data-stu-id="e7b90-161">The name of the table is used as the implicit alias.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-162">还允许使用以下形式：</span><span class="sxs-lookup"><span data-stu-id="e7b90-162">allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="e7b90-163">通过对象导航</span><span class="sxs-lookup"><span data-stu-id="e7b90-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="e7b90-164">Transact-SQL 使用"." 表示法来引用表的列（一行）。</span><span class="sxs-lookup"><span data-stu-id="e7b90-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-165">扩展了这一表示法（借用自编程语言）为通过对象的属性导航提供支持。</span><span class="sxs-lookup"><span data-stu-id="e7b90-165">extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="e7b90-166">例如，如果 `p` 是 Person 类型的表达式，则下面是用于引用此人地址所在城市的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 语法。</span><span class="sxs-lookup"><span data-stu-id="e7b90-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="e7b90-167">不支持 \*</span><span class="sxs-lookup"><span data-stu-id="e7b90-167">No Support for \*</span></span>  
 <span data-ttu-id="e7b90-168">Transact-SQL 支持将限定的 + 语法作为整个行的别名，并将\*限定语法 （t.\*） 作为该表字段的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e7b90-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="e7b90-169">此外，Transact-SQL 允许特殊计数 （\*） 聚合，其中包括 null。</span><span class="sxs-lookup"><span data-stu-id="e7b90-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-170">不支持 \* 构造。</span><span class="sxs-lookup"><span data-stu-id="e7b90-170">does not support the \* construct.</span></span> <span data-ttu-id="e7b90-171">`select * from T`窗体的转算 SQL 查询，`select T1.* from T1, T2...`并可以分别以[!INCLUDE[esql](../../../../../../includes/esql-md.md)]和`select value t from T as t``select value t1 from T1 as t1, T2 as t2...`表示。</span><span class="sxs-lookup"><span data-stu-id="e7b90-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="e7b90-172">此外，这些构造还处理继承（值可替换性），同时将 `select *` 变体限制到所声明类型的顶级属性。</span><span class="sxs-lookup"><span data-stu-id="e7b90-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-173">不支持 `count(*)` 聚合。</span><span class="sxs-lookup"><span data-stu-id="e7b90-173">does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="e7b90-174">请改用 `count(0)`。</span><span class="sxs-lookup"><span data-stu-id="e7b90-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="e7b90-175">对 Group By 的更改</span><span class="sxs-lookup"><span data-stu-id="e7b90-175">Changes to Group By</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-176">支持 `group by` 关键字的别名化。</span><span class="sxs-lookup"><span data-stu-id="e7b90-176">supports aliasing of `group by` keys.</span></span> <span data-ttu-id="e7b90-177">`select` 子句和 `having` 子句中的表达式必须通过这些别名引用 `group by` 关键字。</span><span class="sxs-lookup"><span data-stu-id="e7b90-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="e7b90-178">例如，以下 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 语法：</span><span class="sxs-lookup"><span data-stu-id="e7b90-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="e7b90-179">...等效于以下交易 SQL：</span><span class="sxs-lookup"><span data-stu-id="e7b90-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="e7b90-180">基于集合的聚合</span><span class="sxs-lookup"><span data-stu-id="e7b90-180">Collection-Based Aggregates</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-181">支持两种合计。</span><span class="sxs-lookup"><span data-stu-id="e7b90-181">supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="e7b90-182">基于集合的合计对集合进行运算，并且产生合计结果。</span><span class="sxs-lookup"><span data-stu-id="e7b90-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="e7b90-183">它们可以出现在查询中的任何位置，并且不需要 `group by` 子句。</span><span class="sxs-lookup"><span data-stu-id="e7b90-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="e7b90-184">例如：</span><span class="sxs-lookup"><span data-stu-id="e7b90-184">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-185">还支持 SQL 样式的合计。</span><span class="sxs-lookup"><span data-stu-id="e7b90-185">also supports SQL-style aggregates.</span></span> <span data-ttu-id="e7b90-186">例如：</span><span class="sxs-lookup"><span data-stu-id="e7b90-186">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="e7b90-187">ORDER BY 子句用法</span><span class="sxs-lookup"><span data-stu-id="e7b90-187">ORDER BY Clause Usage</span></span>  
<span data-ttu-id="e7b90-188">Transact-SQL`ORDER BY`允许仅在最`SELECT .. FROM .. WHERE`顶层块中指定子句。</span><span class="sxs-lookup"><span data-stu-id="e7b90-188">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="e7b90-189">在[!INCLUDE[esql](../../../../../../includes/esql-md.md)]中可以使用嵌套`ORDER BY`表达式，它可以放置在查询的任意位置，但不会保留嵌套查询中的排序。</span><span class="sxs-lookup"><span data-stu-id="e7b90-189">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="e7b90-190">标识符</span><span class="sxs-lookup"><span data-stu-id="e7b90-190">Identifiers</span></span>  
 <span data-ttu-id="e7b90-191">在 Transact-SQL 中，标识符比较基于当前数据库的排序规则。</span><span class="sxs-lookup"><span data-stu-id="e7b90-191">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="e7b90-192">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中，标识符始终不区分大小写但区分重音（即，[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 区分重音字符和非重音字符；例如，“a”不等于“ấ”）。</span><span class="sxs-lookup"><span data-stu-id="e7b90-192">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-193">将看上去相同但来自不同代码页的字母视为不同的字符。</span><span class="sxs-lookup"><span data-stu-id="e7b90-193">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="e7b90-194">有关详细信息，请参阅[输入字符集](input-character-set-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="e7b90-194">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="e7b90-195">Transact-SQL 功能在 Entity SQL 中不可用</span><span class="sxs-lookup"><span data-stu-id="e7b90-195">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="e7b90-196">以下 Transact-SQL 功能在 中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]不可用。</span><span class="sxs-lookup"><span data-stu-id="e7b90-196">The following Transact-SQL functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="e7b90-197">DML</span><span class="sxs-lookup"><span data-stu-id="e7b90-197">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-198">当前未提供对 DML 语句（insert、update、delete）的支持。</span><span class="sxs-lookup"><span data-stu-id="e7b90-198">currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="e7b90-199">DDL</span><span class="sxs-lookup"><span data-stu-id="e7b90-199">DDL</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-200">的当前版本未提供对 DDL 的支持。</span><span class="sxs-lookup"><span data-stu-id="e7b90-200">provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="e7b90-201">命令式编程</span><span class="sxs-lookup"><span data-stu-id="e7b90-201">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e7b90-202">与 Transact-SQL 不同，不提供命令式编程的支持。</span><span class="sxs-lookup"><span data-stu-id="e7b90-202">provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="e7b90-203">请改而使用编程语言。</span><span class="sxs-lookup"><span data-stu-id="e7b90-203">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="e7b90-204">分组函数</span><span class="sxs-lookup"><span data-stu-id="e7b90-204">Grouping Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-205">尚未提供对分组函数（例如，CUBE、ROLLUP 和 GROUPING_SET）的支持。</span><span class="sxs-lookup"><span data-stu-id="e7b90-205">does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="e7b90-206">分析函数</span><span class="sxs-lookup"><span data-stu-id="e7b90-206">Analytic Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-207">尚未提供对解析函数的支持。</span><span class="sxs-lookup"><span data-stu-id="e7b90-207">does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="e7b90-208">内置函数、运算符</span><span class="sxs-lookup"><span data-stu-id="e7b90-208">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e7b90-209">支持 Transact-SQL 内置函数和运算符的子集。</span><span class="sxs-lookup"><span data-stu-id="e7b90-209">supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="e7b90-210">这些运算符和函数可能受到主要存储提供程序的支持。</span><span class="sxs-lookup"><span data-stu-id="e7b90-210">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-211">使用在提供程序清单中声明的特定于存储的函数。</span><span class="sxs-lookup"><span data-stu-id="e7b90-211">uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="e7b90-212">此外，实体框架允许您声明要使用的内置和用户定义的现有存储函数[!INCLUDE[esql](../../../../../../includes/esql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e7b90-212">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="e7b90-213">提示</span><span class="sxs-lookup"><span data-stu-id="e7b90-213">Hints</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-214">不提供查询提示机制。</span><span class="sxs-lookup"><span data-stu-id="e7b90-214">does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="e7b90-215">查询结果批处理</span><span class="sxs-lookup"><span data-stu-id="e7b90-215">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-216">不支持查询结果批处理。</span><span class="sxs-lookup"><span data-stu-id="e7b90-216">does not support batching query results.</span></span> <span data-ttu-id="e7b90-217">例如，以下是有效的 Transact-SQL（作为批处理发送）：</span><span class="sxs-lookup"><span data-stu-id="e7b90-217">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="e7b90-218">但是，等效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不受支持：</span><span class="sxs-lookup"><span data-stu-id="e7b90-218">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e7b90-219">仅支持在每个命令中使用一个由结果生成的查询语句。</span><span class="sxs-lookup"><span data-stu-id="e7b90-219">only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b90-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7b90-220">See also</span></span>

- [<span data-ttu-id="e7b90-221">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="e7b90-221">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="e7b90-222">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="e7b90-222">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
