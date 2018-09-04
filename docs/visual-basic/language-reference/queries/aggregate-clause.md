---
title: Aggregate 子句 (Visual Basic)
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
ms.openlocfilehash: e3ce8ff7da647120e5fd9e3b4cd44cc603eb797d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519481"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="9084b-102">Aggregate 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9084b-102">Aggregate Clause (Visual Basic)</span></span>
<span data-ttu-id="9084b-103">适用于集合的一个或多个聚合函数。</span><span class="sxs-lookup"><span data-stu-id="9084b-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9084b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9084b-104">Syntax</span></span>  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="9084b-105">部件</span><span class="sxs-lookup"><span data-stu-id="9084b-105">Parts</span></span>  
  
|<span data-ttu-id="9084b-106">术语</span><span class="sxs-lookup"><span data-stu-id="9084b-106">Term</span></span>|<span data-ttu-id="9084b-107">定义</span><span class="sxs-lookup"><span data-stu-id="9084b-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="9084b-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="9084b-108">Required.</span></span> <span data-ttu-id="9084b-109">用于循环访问集合的元素的变量。</span><span class="sxs-lookup"><span data-stu-id="9084b-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="9084b-110">可选。</span><span class="sxs-lookup"><span data-stu-id="9084b-110">Optional.</span></span> <span data-ttu-id="9084b-111">`element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="9084b-111">The type of `element`.</span></span> <span data-ttu-id="9084b-112">如果指定没有类型，则类型`element`从推断`collection`。</span><span class="sxs-lookup"><span data-stu-id="9084b-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="9084b-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="9084b-113">Required.</span></span> <span data-ttu-id="9084b-114">表示要操作的集合。</span><span class="sxs-lookup"><span data-stu-id="9084b-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="9084b-115">可选。</span><span class="sxs-lookup"><span data-stu-id="9084b-115">Optional.</span></span> <span data-ttu-id="9084b-116">一个或多个查询子句，如`Where`子句，以优化要向其应用聚合子句的查询结果。</span><span class="sxs-lookup"><span data-stu-id="9084b-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="9084b-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="9084b-117">Required.</span></span> <span data-ttu-id="9084b-118">一个或多个以逗号分隔的表达式用于标识要应用于集合的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="9084b-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="9084b-119">您可以应用于聚合函数指定为查询结果的成员名称的别名。</span><span class="sxs-lookup"><span data-stu-id="9084b-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="9084b-120">如果不提供别名，则使用的聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="9084b-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="9084b-121">有关示例，请参阅有关本主题后面的聚合函数的部分。</span><span class="sxs-lookup"><span data-stu-id="9084b-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9084b-122">备注</span><span class="sxs-lookup"><span data-stu-id="9084b-122">Remarks</span></span>  
 <span data-ttu-id="9084b-123">`Aggregate`子句可用于在查询中包含聚合函数。</span><span class="sxs-lookup"><span data-stu-id="9084b-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="9084b-124">聚合函数对一组值执行检查和计算并返回单个值。</span><span class="sxs-lookup"><span data-stu-id="9084b-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="9084b-125">可以通过使用查询结果类型的成员访问计算的值。</span><span class="sxs-lookup"><span data-stu-id="9084b-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="9084b-126">可以使用标准聚合函数都`All`， `Any`， `Average`， `Count`， `LongCount`， `Max`， `Min`，和`Sum`函数。</span><span class="sxs-lookup"><span data-stu-id="9084b-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="9084b-127">这些函数是熟悉的开发人员熟悉的与 SQL 中的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="9084b-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="9084b-128">它们是本主题的以下部分中所述。</span><span class="sxs-lookup"><span data-stu-id="9084b-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="9084b-129">聚合函数的结果作为查询结果类型的字段包含查询结果中。</span><span class="sxs-lookup"><span data-stu-id="9084b-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="9084b-130">你可以提供聚合函数结果，以指定将保存的聚合值的查询结果类型的成员名称的别名。</span><span class="sxs-lookup"><span data-stu-id="9084b-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="9084b-131">如果不提供别名，则使用的聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="9084b-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="9084b-132">`Aggregate`子句可以开始查询，也可以是作为在查询中的其他子句。</span><span class="sxs-lookup"><span data-stu-id="9084b-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="9084b-133">如果`Aggregate`子句开始查询，则结果为单个值中指定的聚合函数的结果`Into`子句。</span><span class="sxs-lookup"><span data-stu-id="9084b-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="9084b-134">如果在中指定多个聚合函数`Into`子句，查询将返回单个类型使用单独的属性引用中每个聚合函数的结果`Into`子句。</span><span class="sxs-lookup"><span data-stu-id="9084b-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="9084b-135">如果`Aggregate`子句是作为在查询中的其他子句，查询集合中返回的类型都具有一个单独的属性来引用中每个聚合函数的结果`Into`子句。</span><span class="sxs-lookup"><span data-stu-id="9084b-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="9084b-136">聚合函数</span><span class="sxs-lookup"><span data-stu-id="9084b-136">Aggregate Functions</span></span>

<span data-ttu-id="9084b-137">以下是可与标准聚合函数`Aggregate`子句。</span><span class="sxs-lookup"><span data-stu-id="9084b-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="9084b-138">全部</span><span class="sxs-lookup"><span data-stu-id="9084b-138">All</span></span>

<span data-ttu-id="9084b-139">返回`true`如果在集合中的所有元素都满足指定的条件; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="9084b-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="9084b-140">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="9084b-140">The following is an example:</span></span>

[!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]

### <a name="any"></a><span data-ttu-id="9084b-141">任意</span><span class="sxs-lookup"><span data-stu-id="9084b-141">Any</span></span>

<span data-ttu-id="9084b-142">返回`true`如果在集合中的任何元素满足指定的条件; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="9084b-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="9084b-143">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="9084b-143">The following is an example:</span></span>

[!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]

### <a name="average"></a><span data-ttu-id="9084b-144">平均值</span><span class="sxs-lookup"><span data-stu-id="9084b-144">Average</span></span>

<span data-ttu-id="9084b-145">集合中的所有元素的平均值或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="9084b-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="9084b-146">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="9084b-146">The following is an example:</span></span>

[!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]

### <a name="count"></a><span data-ttu-id="9084b-147">计数</span><span class="sxs-lookup"><span data-stu-id="9084b-147">Count</span></span>

<span data-ttu-id="9084b-148">计算集合中的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="9084b-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="9084b-149">您可以提供一个可选`Boolean`表达式来计算仅满足条件的集合中的元素数目。</span><span class="sxs-lookup"><span data-stu-id="9084b-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="9084b-150">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="9084b-150">The following is an example:</span></span>

[!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]

### <a name="group"></a><span data-ttu-id="9084b-151">Group</span><span class="sxs-lookup"><span data-stu-id="9084b-151">Group</span></span>

<span data-ttu-id="9084b-152">为分组的查询结果是指`Group By`或`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="9084b-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="9084b-153">`Group`函数是仅在中有效`Into`子句`Group By`或`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="9084b-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="9084b-154">有关详细信息和示例，请参阅[组 By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)并[Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="9084b-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="9084b-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="9084b-155">LongCount</span></span>

<span data-ttu-id="9084b-156">计算集合中的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="9084b-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="9084b-157">您可以提供一个可选`Boolean`表达式来计算仅满足条件的集合中的元素数目。</span><span class="sxs-lookup"><span data-stu-id="9084b-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="9084b-158">返回的结果`Long`。</span><span class="sxs-lookup"><span data-stu-id="9084b-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="9084b-159">有关示例，请参阅`Count`聚合函数。</span><span class="sxs-lookup"><span data-stu-id="9084b-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="9084b-160">最大值</span><span class="sxs-lookup"><span data-stu-id="9084b-160">Max</span></span>

<span data-ttu-id="9084b-161">集合中的最大值或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="9084b-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="9084b-162">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="9084b-162">The following is an example:</span></span>

[!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]

### <a name="min"></a><span data-ttu-id="9084b-163">最小值</span><span class="sxs-lookup"><span data-stu-id="9084b-163">Min</span></span>

<span data-ttu-id="9084b-164">集合中的最小值或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="9084b-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="9084b-165">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="9084b-165">The following is an example:</span></span>

[!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]

### <a name="sum"></a><span data-ttu-id="9084b-166">Sum</span><span class="sxs-lookup"><span data-stu-id="9084b-166">Sum</span></span>

<span data-ttu-id="9084b-167">集合中的所有元素的总和或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="9084b-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="9084b-168">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="9084b-168">The following is an example:</span></span>

[!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]

## <a name="example"></a><span data-ttu-id="9084b-169">示例</span><span class="sxs-lookup"><span data-stu-id="9084b-169">Example</span></span>  

<span data-ttu-id="9084b-170">下面的示例演示如何使用`Aggregate`子句，以将聚合函数应用到查询结果。</span><span class="sxs-lookup"><span data-stu-id="9084b-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="9084b-171">创建用户定义的聚合函数</span><span class="sxs-lookup"><span data-stu-id="9084b-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="9084b-172">可以在查询表达式中包括你自己的自定义聚合函数，通过添加的扩展方法<xref:System.Collections.Generic.IEnumerable%601>类型。</span><span class="sxs-lookup"><span data-stu-id="9084b-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="9084b-173">计算或操作已引用聚合函数的可枚举集合，然后可以执行自定义方法。</span><span class="sxs-lookup"><span data-stu-id="9084b-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="9084b-174">有关扩展方法的详细信息，请参阅[扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="9084b-174">For more information about extension methods, see [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="9084b-175">例如，下面的示例演示计算一系列数字的中值的自定义聚合函数。</span><span class="sxs-lookup"><span data-stu-id="9084b-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="9084b-176">有两种重载的`Median`扩展方法。</span><span class="sxs-lookup"><span data-stu-id="9084b-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="9084b-177">第一个重载接受，作为输入，类型的集合`IEnumerable(Of Double)`。</span><span class="sxs-lookup"><span data-stu-id="9084b-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="9084b-178">如果`Median`聚合函数调用类型的查询字段`Double`，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="9084b-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="9084b-179">第二个重载`Median`方法可以传递任何泛型类型。</span><span class="sxs-lookup"><span data-stu-id="9084b-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="9084b-180">泛型重载`Median`方法采用一个引用的第二个参数`Func(Of T, Double)`lambda 表达式，以便为相应的值类型的项目类型 （从一个集合） 的值`Double`。</span><span class="sxs-lookup"><span data-stu-id="9084b-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="9084b-181">它然后委托到的其他重载的中值的计算`Median`方法。</span><span class="sxs-lookup"><span data-stu-id="9084b-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="9084b-182">有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="9084b-182">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 <span data-ttu-id="9084b-183">下面的示例演示调用的示例查询`Median`聚合函数类型的集合`Integer`，和类型的集合`Double`。</span><span class="sxs-lookup"><span data-stu-id="9084b-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="9084b-184">调用的查询`Median`聚合函数类型的集合`Double`调用的重载`Median`方法接受类型的集合作为输入， `Double`。</span><span class="sxs-lookup"><span data-stu-id="9084b-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="9084b-185">调用的查询`Median`聚合函数类型的集合`Integer`调用的泛型重载`Median`方法。</span><span class="sxs-lookup"><span data-stu-id="9084b-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9084b-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="9084b-186">See Also</span></span>

- [<span data-ttu-id="9084b-187">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="9084b-187">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
- [<span data-ttu-id="9084b-188">查询</span><span class="sxs-lookup"><span data-stu-id="9084b-188">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
- [<span data-ttu-id="9084b-189">Select 子句</span><span class="sxs-lookup"><span data-stu-id="9084b-189">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
- [<span data-ttu-id="9084b-190">From 子句</span><span class="sxs-lookup"><span data-stu-id="9084b-190">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
- [<span data-ttu-id="9084b-191">Where 子句</span><span class="sxs-lookup"><span data-stu-id="9084b-191">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
- [<span data-ttu-id="9084b-192">Group By 子句</span><span class="sxs-lookup"><span data-stu-id="9084b-192">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
