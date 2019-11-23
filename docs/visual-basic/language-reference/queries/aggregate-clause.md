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
ms.openlocfilehash: 50a53cd45cc428541c90fbf82089518be2212fae
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004802"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="8ac2e-102">Aggregate 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ac2e-102">Aggregate Clause (Visual Basic)</span></span>
<span data-ttu-id="8ac2e-103">将一个或多个聚合函数应用于集合。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ac2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ac2e-104">Syntax</span></span>  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="8ac2e-105">部件</span><span class="sxs-lookup"><span data-stu-id="8ac2e-105">Parts</span></span>  
  
|<span data-ttu-id="8ac2e-106">术语</span><span class="sxs-lookup"><span data-stu-id="8ac2e-106">Term</span></span>|<span data-ttu-id="8ac2e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="8ac2e-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="8ac2e-108">必需。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-108">Required.</span></span> <span data-ttu-id="8ac2e-109">用于循环访问集合中的元素的变量。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="8ac2e-110">可选。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-110">Optional.</span></span> <span data-ttu-id="8ac2e-111">`element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-111">The type of `element`.</span></span> <span data-ttu-id="8ac2e-112">如果未指定类型，则从 `collection`推断 `element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="8ac2e-113">必需。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-113">Required.</span></span> <span data-ttu-id="8ac2e-114">引用要对其执行操作的集合。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="8ac2e-115">可选。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-115">Optional.</span></span> <span data-ttu-id="8ac2e-116">一个或多个查询子句（如 `Where` 子句），用于优化要将聚合子句或子句应用于的查询结果。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="8ac2e-117">必需。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-117">Required.</span></span> <span data-ttu-id="8ac2e-118">一个或多个以逗号分隔的表达式，用于标识要应用于集合的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="8ac2e-119">您可以向聚合函数应用别名，以指定查询结果的成员名称。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="8ac2e-120">如果未提供别名，则使用聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="8ac2e-121">有关示例，请参阅本主题后面的有关聚合函数的部分。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ac2e-122">备注</span><span class="sxs-lookup"><span data-stu-id="8ac2e-122">Remarks</span></span>  
 <span data-ttu-id="8ac2e-123">`Aggregate` 子句可用于在查询中包括聚合函数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="8ac2e-124">聚合函数对一组值执行检查和计算，并返回单个值。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="8ac2e-125">您可以使用查询结果类型的成员访问计算值。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="8ac2e-126">可使用的标准聚合函数包括 `All`、`Any`、`Average`、`Count`、`LongCount`、`Max`、`Min`和 `Sum` 函数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="8ac2e-127">这些函数对熟悉 SQL 中聚合的开发人员非常熟悉。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="8ac2e-128">本主题的下一节将对其进行介绍。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="8ac2e-129">聚合函数的结果作为查询结果类型的字段包含在查询结果中。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="8ac2e-130">您可以为聚合函数结果提供别名，以指定将保存聚合值的查询结果类型的成员名称。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="8ac2e-131">如果未提供别名，则使用聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="8ac2e-132">`Aggregate` 子句可以开始查询，也可以在查询中将其作为附加子句包括在内。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="8ac2e-133">如果 `Aggregate` 子句开始查询，则结果为单个值，该值是在 `Into` 子句中指定的聚合函数的结果。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="8ac2e-134">如果在 `Into` 子句中指定了多个聚合函数，则查询将返回单一类型，该类型具有一个单独的属性，用于在 `Into` 子句中引用每个聚合函数的结果。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="8ac2e-135">如果在查询中将 `Aggregate` 子句作为附加子句包含，则在查询集合中返回的类型将具有一个单独的属性，用于在 `Into` 子句中引用每个聚合函数的结果。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="8ac2e-136">聚合函数</span><span class="sxs-lookup"><span data-stu-id="8ac2e-136">Aggregate Functions</span></span>

<span data-ttu-id="8ac2e-137">下面是可与 `Aggregate` 子句一起使用的标准聚合函数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="8ac2e-138">全部</span><span class="sxs-lookup"><span data-stu-id="8ac2e-138">All</span></span>

<span data-ttu-id="8ac2e-139">如果集合中的所有元素都满足指定的条件，则返回 `true`;否则，将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="8ac2e-140">以下是一个实例：</span><span class="sxs-lookup"><span data-stu-id="8ac2e-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="8ac2e-141">任何</span><span class="sxs-lookup"><span data-stu-id="8ac2e-141">Any</span></span>

<span data-ttu-id="8ac2e-142">如果集合中的任何元素满足指定的条件，则返回 `true`;否则，将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="8ac2e-143">以下是一个实例：</span><span class="sxs-lookup"><span data-stu-id="8ac2e-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="8ac2e-144">平均值</span><span class="sxs-lookup"><span data-stu-id="8ac2e-144">Average</span></span>

<span data-ttu-id="8ac2e-145">计算集合中所有元素的平均值，或为集合中的所有元素计算提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="8ac2e-146">以下是一个实例：</span><span class="sxs-lookup"><span data-stu-id="8ac2e-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="8ac2e-147">计数</span><span class="sxs-lookup"><span data-stu-id="8ac2e-147">Count</span></span>

<span data-ttu-id="8ac2e-148">计算集合中元素的数目。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="8ac2e-149">您可以提供一个可选的 `Boolean` 表达式，以便仅对集合中满足条件的元素数进行计数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="8ac2e-150">以下是一个实例：</span><span class="sxs-lookup"><span data-stu-id="8ac2e-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="8ac2e-151">组</span><span class="sxs-lookup"><span data-stu-id="8ac2e-151">Group</span></span>

<span data-ttu-id="8ac2e-152">指作为 `Group By` 或 `Group Join` 子句的结果进行分组的查询结果。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="8ac2e-153">`Group` 函数仅在 `Group By` 或 `Group Join` 子句的 `Into` 子句中有效。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="8ac2e-154">有关详细信息和示例，请参阅[Group By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)和[group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="8ac2e-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="8ac2e-155">LongCount</span></span>

<span data-ttu-id="8ac2e-156">计算集合中元素的数目。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="8ac2e-157">您可以提供一个可选的 `Boolean` 表达式，以便仅对集合中满足条件的元素数进行计数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="8ac2e-158">以 `Long`的形式返回结果。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="8ac2e-159">有关示例，请参阅 `Count` 聚合函数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="8ac2e-160">最大值</span><span class="sxs-lookup"><span data-stu-id="8ac2e-160">Max</span></span>

<span data-ttu-id="8ac2e-161">计算集合中的最大值，或为集合中的所有元素计算提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="8ac2e-162">以下是一个实例：</span><span class="sxs-lookup"><span data-stu-id="8ac2e-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="8ac2e-163">Min</span><span class="sxs-lookup"><span data-stu-id="8ac2e-163">Min</span></span>

<span data-ttu-id="8ac2e-164">计算集合中的最小值，或为集合中的所有元素计算提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="8ac2e-165">以下是一个实例：</span><span class="sxs-lookup"><span data-stu-id="8ac2e-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="8ac2e-166">Sum</span><span class="sxs-lookup"><span data-stu-id="8ac2e-166">Sum</span></span>

<span data-ttu-id="8ac2e-167">计算集合中所有元素的和，或为集合中的所有元素计算提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="8ac2e-168">以下是一个实例：</span><span class="sxs-lookup"><span data-stu-id="8ac2e-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="8ac2e-169">示例</span><span class="sxs-lookup"><span data-stu-id="8ac2e-169">Example</span></span>  

<span data-ttu-id="8ac2e-170">下面的示例演示如何使用 `Aggregate` 子句将聚合函数应用于查询结果。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="8ac2e-171">创建用户定义聚合函数</span><span class="sxs-lookup"><span data-stu-id="8ac2e-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="8ac2e-172">您可以通过向 <xref:System.Collections.Generic.IEnumerable%601> 类型添加扩展方法，在查询表达式中包含您自己的自定义聚合函数。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="8ac2e-173">然后，您的自定义方法可以对引用了聚合函数的可枚举集合执行计算或操作。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="8ac2e-174">有关扩展方法的详细信息，请参阅[扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-174">For more information about extension methods, see [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="8ac2e-175">例如，下面的示例显示了一个自定义聚合函数，该函数计算数字集合的中间值。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="8ac2e-176">`Median` 扩展方法有两个重载。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="8ac2e-177">第一次重载接受 `IEnumerable(Of Double)`类型的集合作为输入。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="8ac2e-178">如果为 `Double`类型的查询字段调用 `Median` 聚合函数，则将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="8ac2e-179">可以将 `Median` 方法的第二个重载传递到任何泛型类型。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="8ac2e-180">`Median` 方法的泛型重载使用第二个参数，该参数引用 `Func(Of T, Double)` lambda 表达式，以便将类型（来自集合）的值投影为类型 `Double`的相应值。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="8ac2e-181">然后，它将中间值的计算委托给 `Median` 方法的其他重载。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="8ac2e-182">有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-182">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="8ac2e-183">下面的示例演示了在 `Integer`类型的集合上调用 `Median` 聚合函数的示例查询，以及 `Double`类型的集合。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="8ac2e-184">对类型为 `Double` 的集合调用 `Median` 聚合函数的查询将调用接受作为输入的 `Median` 方法的重载，作为 `Double`类型的集合。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="8ac2e-185">对类型的集合调用 `Median` 聚合函数的查询 `Integer` 调用 `Median` 方法的泛型重载。</span><span class="sxs-lookup"><span data-stu-id="8ac2e-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="8ac2e-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ac2e-186">See also</span></span>

- [<span data-ttu-id="8ac2e-187">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="8ac2e-187">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8ac2e-188">查询</span><span class="sxs-lookup"><span data-stu-id="8ac2e-188">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="8ac2e-189">Select 子句</span><span class="sxs-lookup"><span data-stu-id="8ac2e-189">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="8ac2e-190">From 子句</span><span class="sxs-lookup"><span data-stu-id="8ac2e-190">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8ac2e-191">Where 子句</span><span class="sxs-lookup"><span data-stu-id="8ac2e-191">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="8ac2e-192">Group By 子句</span><span class="sxs-lookup"><span data-stu-id="8ac2e-192">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
