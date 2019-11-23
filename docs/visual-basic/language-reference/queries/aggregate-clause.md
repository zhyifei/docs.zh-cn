---
title: Aggregate Clause
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 5aa4b9afea4b6b26b853d4f4f6d4c8db08554e19
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350870"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="127ba-102">Aggregate 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="127ba-102">Aggregate Clause (Visual Basic)</span></span>
<span data-ttu-id="127ba-103">Applies one or more aggregate functions to a collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="127ba-104">Syntax</span></span>  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="127ba-105">部件</span><span class="sxs-lookup"><span data-stu-id="127ba-105">Parts</span></span>  
  
|<span data-ttu-id="127ba-106">术语</span><span class="sxs-lookup"><span data-stu-id="127ba-106">Term</span></span>|<span data-ttu-id="127ba-107">定义</span><span class="sxs-lookup"><span data-stu-id="127ba-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="127ba-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="127ba-108">Required.</span></span> <span data-ttu-id="127ba-109">Variable used to iterate through the elements of the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="127ba-110">可选。</span><span class="sxs-lookup"><span data-stu-id="127ba-110">Optional.</span></span> <span data-ttu-id="127ba-111">`element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="127ba-111">The type of `element`.</span></span> <span data-ttu-id="127ba-112">If no type is specified, the type of `element` is inferred from `collection`.</span><span class="sxs-lookup"><span data-stu-id="127ba-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="127ba-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="127ba-113">Required.</span></span> <span data-ttu-id="127ba-114">Refers to the collection to operate on.</span><span class="sxs-lookup"><span data-stu-id="127ba-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="127ba-115">可选。</span><span class="sxs-lookup"><span data-stu-id="127ba-115">Optional.</span></span> <span data-ttu-id="127ba-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span><span class="sxs-lookup"><span data-stu-id="127ba-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="127ba-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="127ba-117">Required.</span></span> <span data-ttu-id="127ba-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="127ba-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span><span class="sxs-lookup"><span data-stu-id="127ba-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="127ba-120">If no alias is supplied, the name of the aggregate function is used.</span><span class="sxs-lookup"><span data-stu-id="127ba-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="127ba-121">For examples, see the section about aggregate functions later in this topic.</span><span class="sxs-lookup"><span data-stu-id="127ba-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="127ba-122">备注</span><span class="sxs-lookup"><span data-stu-id="127ba-122">Remarks</span></span>  
 <span data-ttu-id="127ba-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span><span class="sxs-lookup"><span data-stu-id="127ba-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="127ba-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span><span class="sxs-lookup"><span data-stu-id="127ba-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="127ba-125">You can access the computed value by using a member of the query result type.</span><span class="sxs-lookup"><span data-stu-id="127ba-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="127ba-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span><span class="sxs-lookup"><span data-stu-id="127ba-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="127ba-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span><span class="sxs-lookup"><span data-stu-id="127ba-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="127ba-128">They are described in the following section of this topic.</span><span class="sxs-lookup"><span data-stu-id="127ba-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="127ba-129">The result of an aggregate function is included in the query result as a field of the query result type.</span><span class="sxs-lookup"><span data-stu-id="127ba-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="127ba-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span><span class="sxs-lookup"><span data-stu-id="127ba-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="127ba-131">If no alias is supplied, the name of the aggregate function is used.</span><span class="sxs-lookup"><span data-stu-id="127ba-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="127ba-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span><span class="sxs-lookup"><span data-stu-id="127ba-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="127ba-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span><span class="sxs-lookup"><span data-stu-id="127ba-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="127ba-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span><span class="sxs-lookup"><span data-stu-id="127ba-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="127ba-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span><span class="sxs-lookup"><span data-stu-id="127ba-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="127ba-136">聚合函数</span><span class="sxs-lookup"><span data-stu-id="127ba-136">Aggregate Functions</span></span>

<span data-ttu-id="127ba-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span><span class="sxs-lookup"><span data-stu-id="127ba-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="127ba-138">全部</span><span class="sxs-lookup"><span data-stu-id="127ba-138">All</span></span>

<span data-ttu-id="127ba-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span><span class="sxs-lookup"><span data-stu-id="127ba-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="127ba-140">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="127ba-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="127ba-141">任意</span><span class="sxs-lookup"><span data-stu-id="127ba-141">Any</span></span>

<span data-ttu-id="127ba-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span><span class="sxs-lookup"><span data-stu-id="127ba-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="127ba-143">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="127ba-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="127ba-144">平均值</span><span class="sxs-lookup"><span data-stu-id="127ba-144">Average</span></span>

<span data-ttu-id="127ba-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="127ba-146">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="127ba-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="127ba-147">计数</span><span class="sxs-lookup"><span data-stu-id="127ba-147">Count</span></span>

<span data-ttu-id="127ba-148">Counts the number of elements in the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="127ba-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span><span class="sxs-lookup"><span data-stu-id="127ba-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="127ba-150">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="127ba-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="127ba-151">Group</span><span class="sxs-lookup"><span data-stu-id="127ba-151">Group</span></span>

<span data-ttu-id="127ba-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span><span class="sxs-lookup"><span data-stu-id="127ba-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="127ba-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span><span class="sxs-lookup"><span data-stu-id="127ba-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="127ba-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="127ba-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="127ba-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="127ba-155">LongCount</span></span>

<span data-ttu-id="127ba-156">Counts the number of elements in the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="127ba-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span><span class="sxs-lookup"><span data-stu-id="127ba-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="127ba-158">Returns the result as a `Long`.</span><span class="sxs-lookup"><span data-stu-id="127ba-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="127ba-159">For an example, see the `Count` aggregate function.</span><span class="sxs-lookup"><span data-stu-id="127ba-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="127ba-160">最大值</span><span class="sxs-lookup"><span data-stu-id="127ba-160">Max</span></span>

<span data-ttu-id="127ba-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="127ba-162">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="127ba-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="127ba-163">最小值</span><span class="sxs-lookup"><span data-stu-id="127ba-163">Min</span></span>

<span data-ttu-id="127ba-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="127ba-165">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="127ba-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="127ba-166">Sum</span><span class="sxs-lookup"><span data-stu-id="127ba-166">Sum</span></span>

<span data-ttu-id="127ba-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span><span class="sxs-lookup"><span data-stu-id="127ba-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="127ba-168">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="127ba-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="127ba-169">示例</span><span class="sxs-lookup"><span data-stu-id="127ba-169">Example</span></span>  

<span data-ttu-id="127ba-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span><span class="sxs-lookup"><span data-stu-id="127ba-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="127ba-171">Creating User-Defined Aggregate Functions</span><span class="sxs-lookup"><span data-stu-id="127ba-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="127ba-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span><span class="sxs-lookup"><span data-stu-id="127ba-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="127ba-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span><span class="sxs-lookup"><span data-stu-id="127ba-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="127ba-174">有关扩展方法的详细信息，请参阅[扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="127ba-174">For more information about extension methods, see [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="127ba-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span><span class="sxs-lookup"><span data-stu-id="127ba-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="127ba-176">There are two overloads of the `Median` extension method.</span><span class="sxs-lookup"><span data-stu-id="127ba-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="127ba-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span><span class="sxs-lookup"><span data-stu-id="127ba-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="127ba-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span><span class="sxs-lookup"><span data-stu-id="127ba-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="127ba-179">The second overload of the `Median` method can be passed any generic type.</span><span class="sxs-lookup"><span data-stu-id="127ba-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="127ba-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span><span class="sxs-lookup"><span data-stu-id="127ba-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="127ba-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span><span class="sxs-lookup"><span data-stu-id="127ba-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="127ba-182">有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="127ba-182">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="127ba-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span><span class="sxs-lookup"><span data-stu-id="127ba-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="127ba-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span><span class="sxs-lookup"><span data-stu-id="127ba-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="127ba-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span><span class="sxs-lookup"><span data-stu-id="127ba-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="127ba-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="127ba-186">See also</span></span>

- [<span data-ttu-id="127ba-187">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="127ba-187">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="127ba-188">查询</span><span class="sxs-lookup"><span data-stu-id="127ba-188">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="127ba-189">Select 子句</span><span class="sxs-lookup"><span data-stu-id="127ba-189">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="127ba-190">From 子句</span><span class="sxs-lookup"><span data-stu-id="127ba-190">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="127ba-191">Where 子句</span><span class="sxs-lookup"><span data-stu-id="127ba-191">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="127ba-192">Group By 子句</span><span class="sxs-lookup"><span data-stu-id="127ba-192">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
