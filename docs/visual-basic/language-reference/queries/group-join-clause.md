---
title: Group Join 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 3da4ca2db299a65b2c0f1fa259bbaabe4f53aa33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945309"
---
# <a name="group-join-clause-visual-basic"></a><span data-ttu-id="c1f8d-102">Group Join 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1f8d-102">Group Join Clause (Visual Basic)</span></span>
<span data-ttu-id="c1f8d-103">将两个集合合并为单个分层集合。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-103">Combines two collections into a single hierarchical collection.</span></span> <span data-ttu-id="c1f8d-104">联接运算基于匹配键。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-104">The join operation is based on matching keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1f8d-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1f8d-105">Syntax</span></span>  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="c1f8d-106">部件</span><span class="sxs-lookup"><span data-stu-id="c1f8d-106">Parts</span></span>  
  
|<span data-ttu-id="c1f8d-107">术语</span><span class="sxs-lookup"><span data-stu-id="c1f8d-107">Term</span></span>|<span data-ttu-id="c1f8d-108">定义</span><span class="sxs-lookup"><span data-stu-id="c1f8d-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="c1f8d-109">必需。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-109">Required.</span></span> <span data-ttu-id="c1f8d-110">要联接的集合控制变量。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-110">The control variable for the collection being joined.</span></span>|  
|`type`|<span data-ttu-id="c1f8d-111">可选。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-111">Optional.</span></span> <span data-ttu-id="c1f8d-112">`element` 的类型。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-112">The type of `element`.</span></span> <span data-ttu-id="c1f8d-113">如果没有`type`指定的类型`element`从推断`collection`。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-113">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="c1f8d-114">必需。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-114">Required.</span></span> <span data-ttu-id="c1f8d-115">要与位于左侧和右侧的集合合并的集合`Group Join`运算符。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-115">The collection to combine with the collection that is on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="c1f8d-116">一个`Group Join`子句可以嵌套在`Join`子句或另一个`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-116">A `Group Join` clause can be nested in a `Join` clause or in another `Group Join` clause.</span></span>|  
|<span data-ttu-id="c1f8d-117">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="c1f8d-117">`key1` `Equals` `key2`</span></span>|<span data-ttu-id="c1f8d-118">必需。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-118">Required.</span></span> <span data-ttu-id="c1f8d-119">标识要联接的集合的键。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-119">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="c1f8d-120">必须使用`Equals`运算符比较要联接的集合中的密钥。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-120">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="c1f8d-121">您可以通过使用组合联接条件`And`运算符来标识多个密钥。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-121">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="c1f8d-122">`key1`参数必须是从左侧集合`Join`运算符。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-122">The `key1` parameter must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="c1f8d-123">`key2`参数必须是从右侧集合`Join`运算符。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-123">The `key2` parameter must be from the collection on the right side of the `Join` operator.</span></span><br /><br /> <span data-ttu-id="c1f8d-124">联接条件中使用的密钥可以包含多个集合中的项的表达式。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-124">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="c1f8d-125">但是，每个键的表达式可以包含仅从其各自的集合的项。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-125">However, each key expression can contain only items from its respective collection.</span></span>|  
|`expressionList`|<span data-ttu-id="c1f8d-126">必需。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-126">Required.</span></span> <span data-ttu-id="c1f8d-127">标识如何聚合的组集合中元素的一个或多个表达式。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-127">One or more expressions that identify how the groups of elements from the collection are aggregated.</span></span> <span data-ttu-id="c1f8d-128">若要标识分组结果的成员名称，请使用`Group`关键字 (`<alias> = Group`)。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-128">To identify a member name for the grouped results, use the `Group` keyword (`<alias> = Group`).</span></span> <span data-ttu-id="c1f8d-129">还可以包含聚合函数以将其应用于该组。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-129">You can also include aggregate functions to apply to the group.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1f8d-130">备注</span><span class="sxs-lookup"><span data-stu-id="c1f8d-130">Remarks</span></span>  
 <span data-ttu-id="c1f8d-131">`Group Join`子句将两个集合根据匹配的键值从要联接的集合。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-131">The `Group Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="c1f8d-132">生成的集合可以包含引用的元素的集合中第一个集合中的键值匹配的第二个集合的成员。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-132">The resulting collection can contain a member that references a collection of elements from the second collection that match the key value from the first collection.</span></span> <span data-ttu-id="c1f8d-133">此外可以指定要应用于分组元素从第二个集合的聚合函数。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-133">You can also specify aggregate functions to apply to the grouped elements from the second collection.</span></span> <span data-ttu-id="c1f8d-134">有关聚合函数的信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-134">For information about aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="c1f8d-135">例如，考虑，经理的集合和员工的集合。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-135">Consider, for example, a collection of managers and a collection of employees.</span></span> <span data-ttu-id="c1f8d-136">从这两个集合的元素具有 ManagerID 属性，用于标识向特定经理的员工。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-136">Elements from both collections have a ManagerID property that identifies the employees that report to a particular manager.</span></span> <span data-ttu-id="c1f8d-137">联接运算的结果将包含每个管理器和员工具有匹配 ManagerID 值的结果。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-137">The results from a join operation would contain a result for each manager and employee with a matching ManagerID value.</span></span> <span data-ttu-id="c1f8d-138">从结果`Group Join`操作将包含管理器的完整列表。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-138">The results from a `Group Join` operation would contain the complete list of managers.</span></span> <span data-ttu-id="c1f8d-139">每个管理器结果都将包含所引用的是特定的管理器的匹配项的员工列表的成员。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-139">Each manager result would have a member that referenced the list of employees that were a match for the specific manager.</span></span>  
  
 <span data-ttu-id="c1f8d-140">产生的集合`Group Join`操作可以包含从集合中标识的值的任意组合`From`子句和表达式中标识`Into`子句`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-140">The collection resulting from a `Group Join` operation can contain any combination of values from the collection identified in the `From` clause and the expressions identified in the `Into` clause of the `Group Join` clause.</span></span> <span data-ttu-id="c1f8d-141">有关有效表达式的详细信息`Into`子句，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-141">For more information about valid expressions for the `Into` clause, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="c1f8d-142">一个`Group Join`操作将从上左侧和右侧的标识集合中返回所有结果`Group Join`运算符。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-142">A `Group Join` operation will return all results from the collection identified on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="c1f8d-143">即使被联接集合中没有匹配项，这是如此。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-143">This is true even if there are no matches in the collection being joined.</span></span> <span data-ttu-id="c1f8d-144">这就像`LEFT OUTER JOIN`SQL 中。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-144">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="c1f8d-145">可以使用`Join`子句来组合成单个集合的集合。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-145">You can use the `Join` clause to combine collections into a single collection.</span></span> <span data-ttu-id="c1f8d-146">这相当于`INNER JOIN`SQL 中。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-146">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1f8d-147">示例</span><span class="sxs-lookup"><span data-stu-id="c1f8d-147">Example</span></span>  
 <span data-ttu-id="c1f8d-148">下面的代码示例通过使用联接两个集合`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="c1f8d-148">The following code example joins two collections by using the `Group Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="c1f8d-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1f8d-149">See also</span></span>

- [<span data-ttu-id="c1f8d-150">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="c1f8d-150">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c1f8d-151">查询</span><span class="sxs-lookup"><span data-stu-id="c1f8d-151">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="c1f8d-152">Select 子句</span><span class="sxs-lookup"><span data-stu-id="c1f8d-152">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="c1f8d-153">From 子句</span><span class="sxs-lookup"><span data-stu-id="c1f8d-153">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="c1f8d-154">Join 子句</span><span class="sxs-lookup"><span data-stu-id="c1f8d-154">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="c1f8d-155">Where 子句</span><span class="sxs-lookup"><span data-stu-id="c1f8d-155">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="c1f8d-156">Group By 子句</span><span class="sxs-lookup"><span data-stu-id="c1f8d-156">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
