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
ms.openlocfilehash: 21781db637c71abbbe9366bc95b6ee4c89ac2246
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61712625"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="850d0-102">Aggregate 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="850d0-102">Aggregate Clause (Visual Basic)</span></span>
<span data-ttu-id="850d0-103">适用于集合的一个或多个聚合函数。</span><span class="sxs-lookup"><span data-stu-id="850d0-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="850d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="850d0-104">Syntax</span></span>  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="850d0-105">部件</span><span class="sxs-lookup"><span data-stu-id="850d0-105">Parts</span></span>  
  
|<span data-ttu-id="850d0-106">术语</span><span class="sxs-lookup"><span data-stu-id="850d0-106">Term</span></span>|<span data-ttu-id="850d0-107">定义</span><span class="sxs-lookup"><span data-stu-id="850d0-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="850d0-108">必需。</span><span class="sxs-lookup"><span data-stu-id="850d0-108">Required.</span></span> <span data-ttu-id="850d0-109">用于循环访问集合的元素的变量。</span><span class="sxs-lookup"><span data-stu-id="850d0-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="850d0-110">可选。</span><span class="sxs-lookup"><span data-stu-id="850d0-110">Optional.</span></span> <span data-ttu-id="850d0-111">`element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="850d0-111">The type of `element`.</span></span> <span data-ttu-id="850d0-112">如果指定没有类型，则类型`element`从推断`collection`。</span><span class="sxs-lookup"><span data-stu-id="850d0-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="850d0-113">必需。</span><span class="sxs-lookup"><span data-stu-id="850d0-113">Required.</span></span> <span data-ttu-id="850d0-114">表示要操作的集合。</span><span class="sxs-lookup"><span data-stu-id="850d0-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="850d0-115">可选。</span><span class="sxs-lookup"><span data-stu-id="850d0-115">Optional.</span></span> <span data-ttu-id="850d0-116">一个或多个查询子句，如`Where`子句，以优化要向其应用聚合子句的查询结果。</span><span class="sxs-lookup"><span data-stu-id="850d0-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="850d0-117">必需。</span><span class="sxs-lookup"><span data-stu-id="850d0-117">Required.</span></span> <span data-ttu-id="850d0-118">一个或多个以逗号分隔的表达式用于标识要应用于集合的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="850d0-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="850d0-119">您可以应用于聚合函数指定为查询结果的成员名称的别名。</span><span class="sxs-lookup"><span data-stu-id="850d0-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="850d0-120">如果不提供别名，则使用的聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="850d0-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="850d0-121">有关示例，请参阅有关本主题后面的聚合函数的部分。</span><span class="sxs-lookup"><span data-stu-id="850d0-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="850d0-122">备注</span><span class="sxs-lookup"><span data-stu-id="850d0-122">Remarks</span></span>  
 <span data-ttu-id="850d0-123">`Aggregate`子句可用于在查询中包含聚合函数。</span><span class="sxs-lookup"><span data-stu-id="850d0-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="850d0-124">聚合函数对一组值执行检查和计算并返回单个值。</span><span class="sxs-lookup"><span data-stu-id="850d0-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="850d0-125">可以通过使用查询结果类型的成员访问计算的值。</span><span class="sxs-lookup"><span data-stu-id="850d0-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="850d0-126">可以使用标准聚合函数都`All`， `Any`， `Average`， `Count`， `LongCount`， `Max`， `Min`，和`Sum`函数。</span><span class="sxs-lookup"><span data-stu-id="850d0-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="850d0-127">这些函数是熟悉的开发人员熟悉的与 SQL 中的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="850d0-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="850d0-128">它们是本主题的以下部分中所述。</span><span class="sxs-lookup"><span data-stu-id="850d0-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="850d0-129">聚合函数的结果作为查询结果类型的字段包含查询结果中。</span><span class="sxs-lookup"><span data-stu-id="850d0-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="850d0-130">你可以提供聚合函数结果，以指定将保存的聚合值的查询结果类型的成员名称的别名。</span><span class="sxs-lookup"><span data-stu-id="850d0-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="850d0-131">如果不提供别名，则使用的聚合函数的名称。</span><span class="sxs-lookup"><span data-stu-id="850d0-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="850d0-132">`Aggregate`子句可以开始查询，也可以是作为在查询中的其他子句。</span><span class="sxs-lookup"><span data-stu-id="850d0-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="850d0-133">如果`Aggregate`子句开始查询，则结果为单个值中指定的聚合函数的结果`Into`子句。</span><span class="sxs-lookup"><span data-stu-id="850d0-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="850d0-134">如果在中指定多个聚合函数`Into`子句，查询将返回单个类型使用单独的属性引用中每个聚合函数的结果`Into`子句。</span><span class="sxs-lookup"><span data-stu-id="850d0-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="850d0-135">如果`Aggregate`子句是作为在查询中的其他子句，查询集合中返回的类型都具有一个单独的属性来引用中每个聚合函数的结果`Into`子句。</span><span class="sxs-lookup"><span data-stu-id="850d0-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="850d0-136">聚合函数</span><span class="sxs-lookup"><span data-stu-id="850d0-136">Aggregate Functions</span></span>

<span data-ttu-id="850d0-137">以下是可与标准聚合函数`Aggregate`子句。</span><span class="sxs-lookup"><span data-stu-id="850d0-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="850d0-138">全部</span><span class="sxs-lookup"><span data-stu-id="850d0-138">All</span></span>

<span data-ttu-id="850d0-139">返回`true`如果在集合中的所有元素都满足指定的条件; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="850d0-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="850d0-140">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="850d0-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="850d0-141">任意</span><span class="sxs-lookup"><span data-stu-id="850d0-141">Any</span></span>

<span data-ttu-id="850d0-142">返回`true`如果在集合中的任何元素满足指定的条件; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="850d0-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="850d0-143">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="850d0-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="850d0-144">平均值</span><span class="sxs-lookup"><span data-stu-id="850d0-144">Average</span></span>

<span data-ttu-id="850d0-145">集合中的所有元素的平均值或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="850d0-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="850d0-146">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="850d0-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="850d0-147">计数</span><span class="sxs-lookup"><span data-stu-id="850d0-147">Count</span></span>

<span data-ttu-id="850d0-148">计算集合中的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="850d0-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="850d0-149">您可以提供一个可选`Boolean`表达式来计算仅满足条件的集合中的元素数目。</span><span class="sxs-lookup"><span data-stu-id="850d0-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="850d0-150">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="850d0-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="850d0-151">Group</span><span class="sxs-lookup"><span data-stu-id="850d0-151">Group</span></span>

<span data-ttu-id="850d0-152">为分组的查询结果是指`Group By`或`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="850d0-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="850d0-153">`Group`函数是仅在中有效`Into`子句`Group By`或`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="850d0-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="850d0-154">有关详细信息和示例，请参阅[组 By 子句](../../../visual-basic/language-reference/queries/group-by-clause.md)并[Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="850d0-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="850d0-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="850d0-155">LongCount</span></span>

<span data-ttu-id="850d0-156">计算集合中的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="850d0-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="850d0-157">您可以提供一个可选`Boolean`表达式来计算仅满足条件的集合中的元素数目。</span><span class="sxs-lookup"><span data-stu-id="850d0-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="850d0-158">返回的结果`Long`。</span><span class="sxs-lookup"><span data-stu-id="850d0-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="850d0-159">有关示例，请参阅`Count`聚合函数。</span><span class="sxs-lookup"><span data-stu-id="850d0-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="850d0-160">最大值</span><span class="sxs-lookup"><span data-stu-id="850d0-160">Max</span></span>

<span data-ttu-id="850d0-161">集合中的最大值或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="850d0-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="850d0-162">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="850d0-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="850d0-163">最小值</span><span class="sxs-lookup"><span data-stu-id="850d0-163">Min</span></span>

<span data-ttu-id="850d0-164">集合中的最小值或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="850d0-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="850d0-165">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="850d0-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="850d0-166">Sum</span><span class="sxs-lookup"><span data-stu-id="850d0-166">Sum</span></span>

<span data-ttu-id="850d0-167">集合中的所有元素的总和或计算的集合中的所有元素提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="850d0-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="850d0-168">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="850d0-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="850d0-169">示例</span><span class="sxs-lookup"><span data-stu-id="850d0-169">Example</span></span>  

<span data-ttu-id="850d0-170">下面的示例演示如何使用`Aggregate`子句，以将聚合函数应用到查询结果。</span><span class="sxs-lookup"><span data-stu-id="850d0-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="850d0-171">创建用户定义的聚合函数</span><span class="sxs-lookup"><span data-stu-id="850d0-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="850d0-172">可以在查询表达式中包括你自己的自定义聚合函数，通过添加的扩展方法<xref:System.Collections.Generic.IEnumerable%601>类型。</span><span class="sxs-lookup"><span data-stu-id="850d0-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="850d0-173">计算或操作已引用聚合函数的可枚举集合，然后可以执行自定义方法。</span><span class="sxs-lookup"><span data-stu-id="850d0-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="850d0-174">有关扩展方法的详细信息，请参阅[扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="850d0-174">For more information about extension methods, see [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="850d0-175">例如，下面的示例演示计算一系列数字的中值的自定义聚合函数。</span><span class="sxs-lookup"><span data-stu-id="850d0-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="850d0-176">有两种重载的`Median`扩展方法。</span><span class="sxs-lookup"><span data-stu-id="850d0-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="850d0-177">第一个重载接受，作为输入，类型的集合`IEnumerable(Of Double)`。</span><span class="sxs-lookup"><span data-stu-id="850d0-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="850d0-178">如果`Median`聚合函数调用类型的查询字段`Double`，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="850d0-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="850d0-179">第二个重载`Median`方法可以传递任何泛型类型。</span><span class="sxs-lookup"><span data-stu-id="850d0-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="850d0-180">泛型重载`Median`方法采用一个引用的第二个参数`Func(Of T, Double)`lambda 表达式，以便为相应的值类型的项目类型 （从一个集合） 的值`Double`。</span><span class="sxs-lookup"><span data-stu-id="850d0-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="850d0-181">它然后委托到的其他重载的中值的计算`Median`方法。</span><span class="sxs-lookup"><span data-stu-id="850d0-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="850d0-182">有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="850d0-182">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="850d0-183">下面的示例演示调用的示例查询`Median`聚合函数类型的集合`Integer`，和类型的集合`Double`。</span><span class="sxs-lookup"><span data-stu-id="850d0-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="850d0-184">调用的查询`Median`聚合函数类型的集合`Double`调用的重载`Median`方法接受类型的集合作为输入， `Double`。</span><span class="sxs-lookup"><span data-stu-id="850d0-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="850d0-185">调用的查询`Median`聚合函数类型的集合`Integer`调用的泛型重载`Median`方法。</span><span class="sxs-lookup"><span data-stu-id="850d0-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="850d0-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="850d0-186">See also</span></span>

- [<span data-ttu-id="850d0-187">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="850d0-187">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="850d0-188">查询</span><span class="sxs-lookup"><span data-stu-id="850d0-188">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="850d0-189">Select 子句</span><span class="sxs-lookup"><span data-stu-id="850d0-189">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="850d0-190">From 子句</span><span class="sxs-lookup"><span data-stu-id="850d0-190">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="850d0-191">Where 子句</span><span class="sxs-lookup"><span data-stu-id="850d0-191">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="850d0-192">Group By 子句</span><span class="sxs-lookup"><span data-stu-id="850d0-192">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
