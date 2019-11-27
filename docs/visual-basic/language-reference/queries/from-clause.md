---
title: From 子句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: a63fb41fc2b0ad885acf76ad5d56e446922f5b90
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343781"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="dfbc1-102">From 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfbc1-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="dfbc1-103">指定一个或多个范围变量以及要查询的集合。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfbc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="dfbc1-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="dfbc1-105">部件</span><span class="sxs-lookup"><span data-stu-id="dfbc1-105">Parts</span></span>  
  
|<span data-ttu-id="dfbc1-106">术语</span><span class="sxs-lookup"><span data-stu-id="dfbc1-106">Term</span></span>|<span data-ttu-id="dfbc1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="dfbc1-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="dfbc1-108">必需。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-108">Required.</span></span> <span data-ttu-id="dfbc1-109">用于循环访问集合中的元素的*范围变量*。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="dfbc1-110">当查询循环访问 `collection`时，范围变量用于引用 `collection` 的每个成员。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="dfbc1-111">必须为可枚举类型。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="dfbc1-112">可选。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-112">Optional.</span></span> <span data-ttu-id="dfbc1-113">`element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-113">The type of `element`.</span></span> <span data-ttu-id="dfbc1-114">如果未指定 `type`，则 `element` 的类型将从 `collection`推断。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="dfbc1-115">必需。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-115">Required.</span></span> <span data-ttu-id="dfbc1-116">引用要查询的集合。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="dfbc1-117">必须为可枚举类型。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfbc1-118">备注</span><span class="sxs-lookup"><span data-stu-id="dfbc1-118">Remarks</span></span>  
 <span data-ttu-id="dfbc1-119">`From` 子句用于标识查询的源数据和用于引用源集合中的元素的变量。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="dfbc1-120">这些变量称为*范围变量*。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-120">These variables are called *range variables*.</span></span> <span data-ttu-id="dfbc1-121">查询需要 `From` 子句，除非使用 `Aggregate` 子句标识仅返回聚合结果的查询。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="dfbc1-122">有关详细信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="dfbc1-123">您可以在查询中指定多个 `From` 子句来识别要联接的多个集合。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="dfbc1-124">指定多个集合时，它们将被单独循环访问，如果相关，可以联接它们。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="dfbc1-125">您可以使用 `Select` 子句隐式联接集合，或者使用 `Join` 或 `Group Join` 子句显式联接集合。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="dfbc1-126">作为替代方法，您可以在单个 `From` 子句中指定多个范围变量和集合，其中每个相关范围变量和集合用逗号分隔开。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="dfbc1-127">下面的代码示例演示了 `From` 子句的两种语法选项。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="dfbc1-128">`From` 子句定义查询的作用域，该作用域类似于 `For` 循环的作用域。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="dfbc1-129">因此，查询范围内的每个 `element` 范围变量都必须具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="dfbc1-130">由于您可以为查询指定多个 `From` 子句，因此后续 `From` 子句可以引用 `From` 子句中的范围变量，或者它们可以引用上一个 `From` 子句中的范围变量。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="dfbc1-131">例如，下面的示例显示一个嵌套的 `From` 子句，其中第二个子句中的集合基于第一个子句中范围变量的属性。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="dfbc1-132">每个 `From` 子句可以后跟其他查询子句的任意组合，以优化查询。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="dfbc1-133">可以通过以下方式优化查询：</span><span class="sxs-lookup"><span data-stu-id="dfbc1-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="dfbc1-134">使用 `From` 和 `Select` 子句隐式组合多个集合，或使用 `Join` 或 `Group Join` 子句显式组合多个集合。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="dfbc1-135">使用 `Where` 子句来筛选查询结果。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="dfbc1-136">使用 `Order By` 子句对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="dfbc1-137">使用 `Group By` 子句将相似结果组合在一起。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="dfbc1-138">使用 `Aggregate` 子句标识要为整个查询结果计算的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="dfbc1-139">使用 `Let` 子句引入一个迭代变量，该变量的值由表达式而不是集合确定。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="dfbc1-140">使用 `Distinct` 子句忽略重复的查询结果。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="dfbc1-141">使用 `Skip`、`Take`、`Skip While`和 `Take While` 子句标识要返回的结果的各部分。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfbc1-142">示例</span><span class="sxs-lookup"><span data-stu-id="dfbc1-142">Example</span></span>  
 <span data-ttu-id="dfbc1-143">下面的查询表达式使用 `From` 子句为 `customers` 集合中的每个 `Customer` 对象声明一个范围变量 `cust`。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="dfbc1-144">`Where` 子句使用范围变量将输出限制为指定区域的客户。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="dfbc1-145">`For Each` 循环将在查询结果中显示每个客户的公司名称。</span><span class="sxs-lookup"><span data-stu-id="dfbc1-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="dfbc1-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfbc1-146">See also</span></span>

- [<span data-ttu-id="dfbc1-147">查询</span><span class="sxs-lookup"><span data-stu-id="dfbc1-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="dfbc1-148">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="dfbc1-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="dfbc1-149">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="dfbc1-150">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="dfbc1-151">Select 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="dfbc1-152">Where 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="dfbc1-153">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="dfbc1-154">Distinct 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="dfbc1-155">Join 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="dfbc1-156">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="dfbc1-157">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="dfbc1-158">Let 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="dfbc1-159">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="dfbc1-160">Take 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="dfbc1-161">Skip While 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="dfbc1-162">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="dfbc1-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
