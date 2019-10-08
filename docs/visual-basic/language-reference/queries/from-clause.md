---
title: From 子句 (Visual Basic)
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
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004778"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="c9e95-102">From 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9e95-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="c9e95-103">指定一个或多个范围变量以及要查询的集合。</span><span class="sxs-lookup"><span data-stu-id="c9e95-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e95-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9e95-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="c9e95-105">部件</span><span class="sxs-lookup"><span data-stu-id="c9e95-105">Parts</span></span>  
  
|<span data-ttu-id="c9e95-106">术语</span><span class="sxs-lookup"><span data-stu-id="c9e95-106">Term</span></span>|<span data-ttu-id="c9e95-107">定义</span><span class="sxs-lookup"><span data-stu-id="c9e95-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="c9e95-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c9e95-108">Required.</span></span> <span data-ttu-id="c9e95-109">用于循环访问集合中的元素的*范围变量*。</span><span class="sxs-lookup"><span data-stu-id="c9e95-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="c9e95-110">范围变量用于引用 `collection` 的每个成员，因为查询会循环访问 @no__t。</span><span class="sxs-lookup"><span data-stu-id="c9e95-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="c9e95-111">必须为可枚举类型。</span><span class="sxs-lookup"><span data-stu-id="c9e95-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="c9e95-112">可选。</span><span class="sxs-lookup"><span data-stu-id="c9e95-112">Optional.</span></span> <span data-ttu-id="c9e95-113">`element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="c9e95-113">The type of `element`.</span></span> <span data-ttu-id="c9e95-114">如果未指定 `type`，则从 @no__t 中推断 @no__t 的类型。</span><span class="sxs-lookup"><span data-stu-id="c9e95-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="c9e95-115">必需。</span><span class="sxs-lookup"><span data-stu-id="c9e95-115">Required.</span></span> <span data-ttu-id="c9e95-116">引用要查询的集合。</span><span class="sxs-lookup"><span data-stu-id="c9e95-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="c9e95-117">必须为可枚举类型。</span><span class="sxs-lookup"><span data-stu-id="c9e95-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9e95-118">备注</span><span class="sxs-lookup"><span data-stu-id="c9e95-118">Remarks</span></span>  
 <span data-ttu-id="c9e95-119">@No__t-0 子句用于标识查询的源数据和用于引用源集合中的元素的变量。</span><span class="sxs-lookup"><span data-stu-id="c9e95-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="c9e95-120">这些变量称为*范围变量*。</span><span class="sxs-lookup"><span data-stu-id="c9e95-120">These variables are called *range variables*.</span></span> <span data-ttu-id="c9e95-121">查询需要 `From` 子句，除非使用 `Aggregate` 子句标识仅返回聚合结果的查询。</span><span class="sxs-lookup"><span data-stu-id="c9e95-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="c9e95-122">有关详细信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="c9e95-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="c9e95-123">您可以在查询中指定多个 `From` 子句来识别要联接的多个集合。</span><span class="sxs-lookup"><span data-stu-id="c9e95-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="c9e95-124">指定多个集合时，它们将被单独循环访问，如果相关，可以联接它们。</span><span class="sxs-lookup"><span data-stu-id="c9e95-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="c9e95-125">您可以通过使用 `Select` 子句隐式联接集合，或者使用 @no__t 或 `Group Join` 子句显式联接集合。</span><span class="sxs-lookup"><span data-stu-id="c9e95-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="c9e95-126">作为替代方法，您可以在单个 @no__t 0 子句中指定多个范围变量和集合，其中每个相关范围变量和集合用逗号分隔开。</span><span class="sxs-lookup"><span data-stu-id="c9e95-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="c9e95-127">下面的代码示例显示 `From` 子句的语法选项。</span><span class="sxs-lookup"><span data-stu-id="c9e95-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="c9e95-128">@No__t-0 子句定义查询的作用域，这与 @no__t 循环的作用域类似。</span><span class="sxs-lookup"><span data-stu-id="c9e95-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="c9e95-129">因此，查询范围内的每个 @no__t 0 范围变量都必须具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="c9e95-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="c9e95-130">因为您可以为查询指定多个 `From` 子句，所以后面的 @no__t 子句可以引用 @no__t 2 子句中的范围变量，也可以引用前面的 `From` 子句中的范围变量。</span><span class="sxs-lookup"><span data-stu-id="c9e95-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="c9e95-131">例如，下面的示例演示一个嵌套的 @no__t 0 子句，其中第二个子句中的集合基于第一个子句中范围变量的属性。</span><span class="sxs-lookup"><span data-stu-id="c9e95-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="c9e95-132">每个 `From` 子句可后接其他查询子句的任意组合，以优化查询。</span><span class="sxs-lookup"><span data-stu-id="c9e95-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="c9e95-133">可以通过以下方式优化查询：</span><span class="sxs-lookup"><span data-stu-id="c9e95-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="c9e95-134">使用 @no__t 0 和 `Select` 子句隐式组合多个集合，或使用 `Join` 或 @no__t 子句显式合并多个集合。</span><span class="sxs-lookup"><span data-stu-id="c9e95-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="c9e95-135">使用 `Where` 子句来筛选查询结果。</span><span class="sxs-lookup"><span data-stu-id="c9e95-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="c9e95-136">使用 `Order By` 子句对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="c9e95-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="c9e95-137">使用 `Group By` 子句将相似结果组合在一起。</span><span class="sxs-lookup"><span data-stu-id="c9e95-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="c9e95-138">使用 `Aggregate` 子句标识要为整个查询结果计算的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="c9e95-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="c9e95-139">使用 `Let` 子句来引入一个迭代变量，该变量的值由表达式而不是集合确定。</span><span class="sxs-lookup"><span data-stu-id="c9e95-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="c9e95-140">使用 `Distinct` 子句忽略重复的查询结果。</span><span class="sxs-lookup"><span data-stu-id="c9e95-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="c9e95-141">通过使用 `Skip`、`Take`、`Skip While` 和 @no__t 3 子句来标识要返回的结果的各部分。</span><span class="sxs-lookup"><span data-stu-id="c9e95-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9e95-142">示例</span><span class="sxs-lookup"><span data-stu-id="c9e95-142">Example</span></span>  
 <span data-ttu-id="c9e95-143">下面的查询表达式使用 `From` 子句为 @no__t 集合中的每个 `Customer` 对象声明一个范围变量 `cust`。</span><span class="sxs-lookup"><span data-stu-id="c9e95-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="c9e95-144">@No__t-0 子句使用范围变量将输出限制为指定区域的客户。</span><span class="sxs-lookup"><span data-stu-id="c9e95-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="c9e95-145">@No__t-0 循环显示查询结果中每个客户的公司名称。</span><span class="sxs-lookup"><span data-stu-id="c9e95-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="c9e95-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9e95-146">See also</span></span>

- [<span data-ttu-id="c9e95-147">查询</span><span class="sxs-lookup"><span data-stu-id="c9e95-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="c9e95-148">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="c9e95-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c9e95-149">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="c9e95-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="c9e95-150">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="c9e95-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="c9e95-151">Select 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="c9e95-152">Where 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="c9e95-153">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="c9e95-154">Distinct 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="c9e95-155">Join 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="c9e95-156">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="c9e95-157">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="c9e95-158">Let 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="c9e95-159">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="c9e95-160">Take 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="c9e95-161">Skip While 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="c9e95-162">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="c9e95-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
