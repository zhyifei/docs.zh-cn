---
title: Entity SQL 与 Transact-SQL 有何不同
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 54d7a3fa8ce6e8a0aba6194bfc034eb4d47dbf60
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489927"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="e9927-102">Entity SQL 与 Transact-SQL 有何不同</span><span class="sxs-lookup"><span data-stu-id="e9927-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="e9927-103">本主题介绍之间的差异[!INCLUDE[esql](../../../../../../includes/esql-md.md)]和 Transact SQL。</span><span class="sxs-lookup"><span data-stu-id="e9927-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="e9927-104">继承和关系支持</span><span class="sxs-lookup"><span data-stu-id="e9927-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-105">直接使用概念实体架构并支持诸如继承和关系等概念模型功能。</span><span class="sxs-lookup"><span data-stu-id="e9927-105">works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="e9927-106">使用继承时，从父类型实例集合中选择子类型的实例通常是有用的。</span><span class="sxs-lookup"><span data-stu-id="e9927-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="e9927-107">[Oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)中的运算符[!INCLUDE[esql](../../../../../../includes/esql-md.md)](类似于`oftype`在C#序列) 提供了此功能。</span><span class="sxs-lookup"><span data-stu-id="e9927-107">The [oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="e9927-108">集合支持</span><span class="sxs-lookup"><span data-stu-id="e9927-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-109">将集合视为一类实体。</span><span class="sxs-lookup"><span data-stu-id="e9927-109">treats collections as first-class entities.</span></span> <span data-ttu-id="e9927-110">例如：</span><span class="sxs-lookup"><span data-stu-id="e9927-110">For example:</span></span>  
  
- <span data-ttu-id="e9927-111">集合表达式在 `from` 子句中有效。</span><span class="sxs-lookup"><span data-stu-id="e9927-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="e9927-112">`in` 和 `exists` 子查询已被一般化，以允许使用任何集合。</span><span class="sxs-lookup"><span data-stu-id="e9927-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="e9927-113">子查询是一种集合。</span><span class="sxs-lookup"><span data-stu-id="e9927-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="e9927-114">`e1 in e2` 和 `exists(e)` 是执行这些运算的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 构造。</span><span class="sxs-lookup"><span data-stu-id="e9927-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="e9927-115">集运算（例如 `union`、`intersect` 和 `except`）现在对集合执行运算。</span><span class="sxs-lookup"><span data-stu-id="e9927-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="e9927-116">联接对集合执行运算。</span><span class="sxs-lookup"><span data-stu-id="e9927-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="e9927-117">对表达式的支持</span><span class="sxs-lookup"><span data-stu-id="e9927-117">Support for Expressions</span></span>  
 <span data-ttu-id="e9927-118">Transact SQL 具有子查询 （表） 和表达式 （行和列）。</span><span class="sxs-lookup"><span data-stu-id="e9927-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="e9927-119">为了支持集合和嵌套的集合，[!INCLUDE[esql](../../../../../../includes/esql-md.md)]使所有内容均表达式。</span><span class="sxs-lookup"><span data-stu-id="e9927-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-120">比 TRANSACT-SQL 更具有组合性 — 每个表达式可以任意位置使用。</span><span class="sxs-lookup"><span data-stu-id="e9927-120">is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="e9927-121">查询表达式总是产生投影类型的集合，并且可以在允许使用集合表达式的任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="e9927-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="e9927-122">有关 TRANSACT-SQL 表达式中不支持的信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]，请参阅[不支持的表达式](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="e9927-122">For information about Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="e9927-123">下面是所有有效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询。</span><span class="sxs-lookup"><span data-stu-id="e9927-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="e9927-124">子查询统一处理</span><span class="sxs-lookup"><span data-stu-id="e9927-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="e9927-125">TRANSACT-SQL 提供其重点放在表，执行上下文解释子查询。</span><span class="sxs-lookup"><span data-stu-id="e9927-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="e9927-126">例如，`from` 子句中的子查询被视为多集（表）。</span><span class="sxs-lookup"><span data-stu-id="e9927-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="e9927-127">但是，`select` 子句中使用的同一子查询被视为标量子查询。</span><span class="sxs-lookup"><span data-stu-id="e9927-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="e9927-128">同样，在左侧和右侧的上使用的子查询`in`运算符被视为标量子查询，而右侧的数字应为多集子的查询。</span><span class="sxs-lookup"><span data-stu-id="e9927-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-129">消除了这些差异。</span><span class="sxs-lookup"><span data-stu-id="e9927-129">eliminates these differences.</span></span> <span data-ttu-id="e9927-130">表达式具有不依赖于使用它的上下文的统一解释。</span><span class="sxs-lookup"><span data-stu-id="e9927-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-131">将视为多集子查询所有子查询。</span><span class="sxs-lookup"><span data-stu-id="e9927-131">considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="e9927-132">如果需要从子查询获取标量值，则 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 会提供对集合（在此情况下为子查询）进行运算的 `anyelement` 运算符，并从集合中提取单一实例值。</span><span class="sxs-lookup"><span data-stu-id="e9927-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="e9927-133">避免对子查询执行隐式强制转换</span><span class="sxs-lookup"><span data-stu-id="e9927-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="e9927-134">与统一处理子查询相关的一个副作用是将子查询隐式转换为标量值。</span><span class="sxs-lookup"><span data-stu-id="e9927-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="e9927-135">具体而言，在 TRANSACT-SQL，（具有单个字段） 的行多重集是隐式转换为标量值的数据类型与字段。</span><span class="sxs-lookup"><span data-stu-id="e9927-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-136">不支持这种隐式强制。</span><span class="sxs-lookup"><span data-stu-id="e9927-136">does not support this implicit coercion.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-137">提供 ANYELEMENT 运算符从集合中提取单一实例值，并提供 `select value` 子句以避免在查询表达式中创建行包装。</span><span class="sxs-lookup"><span data-stu-id="e9927-137">provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="e9927-138">选择值：避免隐式行包装器</span><span class="sxs-lookup"><span data-stu-id="e9927-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="e9927-139">Select 子句的 TRANSACT-SQL 子查询中隐式子句中创建行包装的项。</span><span class="sxs-lookup"><span data-stu-id="e9927-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="e9927-140">这意味着我们无法创建标量或对象的集合。</span><span class="sxs-lookup"><span data-stu-id="e9927-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="e9927-141">TRANSACT-SQL 允许具有一个字段的行类型与相同的数据类型的单一实例值之间的隐式强制转换。</span><span class="sxs-lookup"><span data-stu-id="e9927-141">Transact-SQL allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-142">提供了 `select value` 子句，以跳过隐式行构建。</span><span class="sxs-lookup"><span data-stu-id="e9927-142">provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="e9927-143">在 `select value` 子句中只能指定一个项。</span><span class="sxs-lookup"><span data-stu-id="e9927-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="e9927-144">在使用这样的子句时，不会对 `select` 子句中的项构造行包装，并且可生成所需形状的集合，例如：`select value a`。</span><span class="sxs-lookup"><span data-stu-id="e9927-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-145">还提供了用于构造任意行的行构造函数。</span><span class="sxs-lookup"><span data-stu-id="e9927-145">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="e9927-146">`select` 接受投影中的一个或多个元素，并生成含有字段的数据记录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e9927-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="e9927-147">左相关与别名化</span><span class="sxs-lookup"><span data-stu-id="e9927-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="e9927-148">在 TRANSACT-SQL 中的给定作用域的表达式 (一个子句喜欢`select`或`from`) 不能引用在同一范围中前面定义的表达式。</span><span class="sxs-lookup"><span data-stu-id="e9927-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="e9927-149">某些语言 （包括 Transact SQL） 的 SQL 支持这些中的有限的形式`from`子句。</span><span class="sxs-lookup"><span data-stu-id="e9927-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-150">在 `from` 子句中对左相关进行了一般化，并且对它们进行了统一处理。</span><span class="sxs-lookup"><span data-stu-id="e9927-150">generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="e9927-151">`from` 子句中的表达式无需使用额外的语法，即可引用同一子句中先前的定义（位于左侧的定义）。</span><span class="sxs-lookup"><span data-stu-id="e9927-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-152">还对涉及 `group by` 子句的查询施加了额外的限制。</span><span class="sxs-lookup"><span data-stu-id="e9927-152">also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="e9927-153">此类查询的 `select` 子句和 `having` 子句中的表达式只能通过其别名引用 `group by` 关键字。</span><span class="sxs-lookup"><span data-stu-id="e9927-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="e9927-154">下面的构造是在 TRANSACT-SQL，但不是在有效[!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e9927-154">The following construct is valid in Transact-SQL but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 <span data-ttu-id="e9927-155">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 执行此操作</span><span class="sxs-lookup"><span data-stu-id="e9927-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="e9927-156">引用表（集合）的列（属性）</span><span class="sxs-lookup"><span data-stu-id="e9927-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="e9927-157">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的所有列引用都必须用表别名限定。</span><span class="sxs-lookup"><span data-stu-id="e9927-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="e9927-158">以下构造 (假定`a`是表的有效列`T`) 是有效的在 TRANSACT-SQL 中但不能在[!INCLUDE[esql](../../../../../../includes/esql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e9927-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```  
select a from T  
```  
  
 <span data-ttu-id="e9927-159">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 形式为</span><span class="sxs-lookup"><span data-stu-id="e9927-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```  
select t.a as A from T as t  
```  
  
 <span data-ttu-id="e9927-160">表别名在 `from` 子句中是可选的。</span><span class="sxs-lookup"><span data-stu-id="e9927-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="e9927-161">表名称被用作隐式别名。</span><span class="sxs-lookup"><span data-stu-id="e9927-161">The name of the table is used as the implicit alias.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-162">还允许使用以下形式：</span><span class="sxs-lookup"><span data-stu-id="e9927-162">allows the following form as well:</span></span>  
  
```  
select Tab.a from Tab  
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="e9927-163">通过对象导航</span><span class="sxs-lookup"><span data-stu-id="e9927-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="e9927-164">使用 transact SQL"。"表示法来引用列的 （某行的） 表。</span><span class="sxs-lookup"><span data-stu-id="e9927-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-165">扩展了这一表示法（借用自编程语言）为通过对象的属性导航提供支持。</span><span class="sxs-lookup"><span data-stu-id="e9927-165">extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="e9927-166">例如，如果 `p` 是 Person 类型的表达式，则下面是用于引用此人地址所在城市的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 语法。</span><span class="sxs-lookup"><span data-stu-id="e9927-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```  
p.Address.City   
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="e9927-167">不支持 \*</span><span class="sxs-lookup"><span data-stu-id="e9927-167">No Support for \*</span></span>  
 <span data-ttu-id="e9927-168">TRANSACT-SQL 支持非限定 \* 语法作为整个行，并限定的别名\*语法 (t.\*) 作为该表字段的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e9927-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="e9927-169">-此外，允许一个特殊的计数 (\*) 聚合，其中包括 null 值。</span><span class="sxs-lookup"><span data-stu-id="e9927-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-170">不支持 \* 构造。</span><span class="sxs-lookup"><span data-stu-id="e9927-170">does not support the \* construct.</span></span> <span data-ttu-id="e9927-171">窗体的 transact SQL 查询`select * from T`并`select T1.* from T1, T2...`可以用来表示[!INCLUDE[esql](../../../../../../includes/esql-md.md)]作为`select value t from T as t`和`select value t1 from T1 as t1, T2 as t2...`分别。</span><span class="sxs-lookup"><span data-stu-id="e9927-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="e9927-172">此外，这些构造还处理继承（值可替换性），同时将 `select *` 变体限制到所声明类型的顶级属性。</span><span class="sxs-lookup"><span data-stu-id="e9927-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-173">不支持 `count(*)` 聚合。</span><span class="sxs-lookup"><span data-stu-id="e9927-173">does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="e9927-174">请改用 `count(0)`。</span><span class="sxs-lookup"><span data-stu-id="e9927-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="e9927-175">对 Group By 的更改</span><span class="sxs-lookup"><span data-stu-id="e9927-175">Changes to Group By</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-176">支持 `group by` 关键字的别名化。</span><span class="sxs-lookup"><span data-stu-id="e9927-176">supports aliasing of `group by` keys.</span></span> <span data-ttu-id="e9927-177">`select` 子句和 `having` 子句中的表达式必须通过这些别名引用 `group by` 关键字。</span><span class="sxs-lookup"><span data-stu-id="e9927-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="e9927-178">例如，以下 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 语法：</span><span class="sxs-lookup"><span data-stu-id="e9927-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 <span data-ttu-id="e9927-179">...等效于以下 TRANSACT-SQL:</span><span class="sxs-lookup"><span data-stu-id="e9927-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="e9927-180">基于集合的聚合</span><span class="sxs-lookup"><span data-stu-id="e9927-180">Collection-Based Aggregates</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-181">支持两种合计。</span><span class="sxs-lookup"><span data-stu-id="e9927-181">supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="e9927-182">基于集合的合计对集合进行运算，并且产生合计结果。</span><span class="sxs-lookup"><span data-stu-id="e9927-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="e9927-183">它们可以出现在查询中的任何位置，并且不需要 `group by` 子句。</span><span class="sxs-lookup"><span data-stu-id="e9927-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="e9927-184">例如：</span><span class="sxs-lookup"><span data-stu-id="e9927-184">For example:</span></span>  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-185">还支持 SQL 样式的合计。</span><span class="sxs-lookup"><span data-stu-id="e9927-185">also supports SQL-style aggregates.</span></span> <span data-ttu-id="e9927-186">例如：</span><span class="sxs-lookup"><span data-stu-id="e9927-186">For example:</span></span>  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="e9927-187">ORDER BY 子句用法</span><span class="sxs-lookup"><span data-stu-id="e9927-187">ORDER BY Clause Usage</span></span>  
 <span data-ttu-id="e9927-188">TRANSACT-SQL 允许 ORDER BY 子句来指定仅在最顶层中选择...</span><span class="sxs-lookup"><span data-stu-id="e9927-188">Transact-SQL allows ORDER BY clauses to be specified only in the topmost SELECT ..</span></span> <span data-ttu-id="e9927-189">从。</span><span class="sxs-lookup"><span data-stu-id="e9927-189">FROM ..</span></span> <span data-ttu-id="e9927-190">WHERE 块中指定 ORDER BY 子句。</span><span class="sxs-lookup"><span data-stu-id="e9927-190">WHERE block.</span></span> <span data-ttu-id="e9927-191">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中，可以使用嵌套的 ORDER BY 表达式，并且可以将其放置在查询中的任何地方，但不会保留嵌套查询中的排序。</span><span class="sxs-lookup"><span data-stu-id="e9927-191">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested ORDER BY expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="e9927-192">标识符</span><span class="sxs-lookup"><span data-stu-id="e9927-192">Identifiers</span></span>  
 <span data-ttu-id="e9927-193">在 TRANSACT-SQL，标识符比较基于当前数据库的排序规则。</span><span class="sxs-lookup"><span data-stu-id="e9927-193">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="e9927-194">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中，标识符始终不区分大小写但区分重音（即，[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 区分重音字符和非重音字符；例如，“a”不等于“ấ”）。</span><span class="sxs-lookup"><span data-stu-id="e9927-194">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-195">将看上去相同但来自不同代码页的字母视为不同的字符。</span><span class="sxs-lookup"><span data-stu-id="e9927-195">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="e9927-196">有关详细信息，请参阅[输入字符集](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="e9927-196">For more information, see [Input Character Set](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="e9927-197">Transact-SQL 功能在 Entity SQL 中不可用</span><span class="sxs-lookup"><span data-stu-id="e9927-197">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="e9927-198">下面的 TRANSACT-SQL 功能不可用在[!INCLUDE[esql](../../../../../../includes/esql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e9927-198">The following Transact-SQL functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="e9927-199">DML</span><span class="sxs-lookup"><span data-stu-id="e9927-199">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-200">当前未提供对 DML 语句（insert、update、delete）的支持。</span><span class="sxs-lookup"><span data-stu-id="e9927-200">currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="e9927-201">DDL</span><span class="sxs-lookup"><span data-stu-id="e9927-201">DDL</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-202">的当前版本未提供对 DDL 的支持。</span><span class="sxs-lookup"><span data-stu-id="e9927-202">provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="e9927-203">命令式编程</span><span class="sxs-lookup"><span data-stu-id="e9927-203">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-204">提供对命令式编程中，与 TRANSACT-SQL 不同不支持。</span><span class="sxs-lookup"><span data-stu-id="e9927-204">provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="e9927-205">请改而使用编程语言。</span><span class="sxs-lookup"><span data-stu-id="e9927-205">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="e9927-206">分组函数</span><span class="sxs-lookup"><span data-stu-id="e9927-206">Grouping Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-207">尚未提供对分组函数（例如，CUBE、ROLLUP 和 GROUPING_SET）的支持。</span><span class="sxs-lookup"><span data-stu-id="e9927-207">does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="e9927-208">解析函数</span><span class="sxs-lookup"><span data-stu-id="e9927-208">Analytic Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-209">尚未提供对解析函数的支持。</span><span class="sxs-lookup"><span data-stu-id="e9927-209">does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="e9927-210">内置函数、运算符</span><span class="sxs-lookup"><span data-stu-id="e9927-210">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-211">支持一部分 Transact-SQL 内置函数和运算符。</span><span class="sxs-lookup"><span data-stu-id="e9927-211">supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="e9927-212">这些运算符和函数可能受到主要存储提供程序的支持。</span><span class="sxs-lookup"><span data-stu-id="e9927-212">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-213">使用在提供程序清单中声明的特定于存储的函数。</span><span class="sxs-lookup"><span data-stu-id="e9927-213">uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="e9927-214">此外，[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]允许您声明内置和用户定义的现有存储函数，以供[!INCLUDE[esql](../../../../../../includes/esql-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="e9927-214">Additionally, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="e9927-215">提示</span><span class="sxs-lookup"><span data-stu-id="e9927-215">Hints</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-216">不提供查询提示机制。</span><span class="sxs-lookup"><span data-stu-id="e9927-216">does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="e9927-217">查询结果批处理</span><span class="sxs-lookup"><span data-stu-id="e9927-217">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-218">不支持查询结果批处理。</span><span class="sxs-lookup"><span data-stu-id="e9927-218">does not support batching query results.</span></span> <span data-ttu-id="e9927-219">例如，下面是有效 Transact-SQL （成批发送）：</span><span class="sxs-lookup"><span data-stu-id="e9927-219">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```  
select * from products;  
select * from catagories;  
```  
  
 <span data-ttu-id="e9927-220">但是，等效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不受支持：</span><span class="sxs-lookup"><span data-stu-id="e9927-220">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e9927-221">仅支持在每个命令中使用一个由结果生成的查询语句。</span><span class="sxs-lookup"><span data-stu-id="e9927-221">only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9927-222">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9927-222">See also</span></span>

- [<span data-ttu-id="e9927-223">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="e9927-223">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="e9927-224">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="e9927-224">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)
