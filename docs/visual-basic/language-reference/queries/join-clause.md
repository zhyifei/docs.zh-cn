---
title: Join 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 2186954ab6536988271629c4feba0a40563bfc3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603907"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="10ef0-102">Join 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10ef0-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="10ef0-103">将两个集合合并为单个集合。</span><span class="sxs-lookup"><span data-stu-id="10ef0-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="10ef0-104">联接操作基于匹配键对，使用`Equals`运算符。</span><span class="sxs-lookup"><span data-stu-id="10ef0-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ef0-105">语法</span><span class="sxs-lookup"><span data-stu-id="10ef0-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="10ef0-106">部件</span><span class="sxs-lookup"><span data-stu-id="10ef0-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="10ef0-107">必须的。</span><span class="sxs-lookup"><span data-stu-id="10ef0-107">Required.</span></span> <span data-ttu-id="10ef0-108">一个被联接集合控制变量。</span><span class="sxs-lookup"><span data-stu-id="10ef0-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="10ef0-109">必须的。</span><span class="sxs-lookup"><span data-stu-id="10ef0-109">Required.</span></span> <span data-ttu-id="10ef0-110">集合以与在左侧的标识的集合进行组合`Join`运算符。</span><span class="sxs-lookup"><span data-stu-id="10ef0-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="10ef0-111">A`Join`子句可以嵌套在另一个`Join`子句，或在`Group Join`子句。</span><span class="sxs-lookup"><span data-stu-id="10ef0-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="10ef0-112">可选。</span><span class="sxs-lookup"><span data-stu-id="10ef0-112">Optional.</span></span> <span data-ttu-id="10ef0-113">一个或多个其他`Join`进一步限制查询。</span><span class="sxs-lookup"><span data-stu-id="10ef0-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="10ef0-114">可选。</span><span class="sxs-lookup"><span data-stu-id="10ef0-114">Optional.</span></span> <span data-ttu-id="10ef0-115">一个或多个其他`Group Join`进一步限制查询。</span><span class="sxs-lookup"><span data-stu-id="10ef0-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="10ef0-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="10ef0-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="10ef0-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="10ef0-117">Required.</span></span> <span data-ttu-id="10ef0-118">标识被联接集合的键。</span><span class="sxs-lookup"><span data-stu-id="10ef0-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="10ef0-119">必须使用`Equals`运算符从被联接集合的键进行比较。</span><span class="sxs-lookup"><span data-stu-id="10ef0-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="10ef0-120">你可以通过使用组合联接条件`And`运算符来标识多个密钥。</span><span class="sxs-lookup"><span data-stu-id="10ef0-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="10ef0-121">`key1` 必须从左侧的内容的集合`Join`运算符。</span><span class="sxs-lookup"><span data-stu-id="10ef0-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="10ef0-122">`key2` 必须从右侧的集合`Join`运算符。</span><span class="sxs-lookup"><span data-stu-id="10ef0-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="10ef0-123">联接条件中使用的密钥可以是包含集合中的多个项的表达式。</span><span class="sxs-lookup"><span data-stu-id="10ef0-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="10ef0-124">但是，每个键的表达式可以包含仅其各自的集合中的项。</span><span class="sxs-lookup"><span data-stu-id="10ef0-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10ef0-125">备注</span><span class="sxs-lookup"><span data-stu-id="10ef0-125">Remarks</span></span>  
 <span data-ttu-id="10ef0-126">`Join`子句将基于匹配被联接集合中的键值对的两个集合合并。</span><span class="sxs-lookup"><span data-stu-id="10ef0-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="10ef0-127">生成的集合可以包含标识的左侧的集合中的值的任意组合`Join`运算符和中标识的集合`Join`子句。</span><span class="sxs-lookup"><span data-stu-id="10ef0-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="10ef0-128">该查询将返回仅为其指定的条件的结果`Equals`满足运算符。</span><span class="sxs-lookup"><span data-stu-id="10ef0-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="10ef0-129">这相当于`INNER JOIN`SQL 中。</span><span class="sxs-lookup"><span data-stu-id="10ef0-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="10ef0-130">你可以使用多个`Join`中要联接成单个集合的两个或多个集合的查询子句。</span><span class="sxs-lookup"><span data-stu-id="10ef0-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="10ef0-131">你可以执行隐式联接来组合而无需集合`Join`子句。</span><span class="sxs-lookup"><span data-stu-id="10ef0-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="10ef0-132">若要执行此操作，包括多个`In`中的子句你`From`子句并指定`Where`子句，它标识你想要用于联接的键。</span><span class="sxs-lookup"><span data-stu-id="10ef0-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="10ef0-133">你可以使用`Group Join`子句来组合为单个分层集合的集合。</span><span class="sxs-lookup"><span data-stu-id="10ef0-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="10ef0-134">这就像`LEFT OUTER JOIN`SQL 中。</span><span class="sxs-lookup"><span data-stu-id="10ef0-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10ef0-135">示例</span><span class="sxs-lookup"><span data-stu-id="10ef0-135">Example</span></span>  
 <span data-ttu-id="10ef0-136">下面的代码示例执行隐式联接与其订单与合并的客户的列表。</span><span class="sxs-lookup"><span data-stu-id="10ef0-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="10ef0-137">示例</span><span class="sxs-lookup"><span data-stu-id="10ef0-137">Example</span></span>  
 <span data-ttu-id="10ef0-138">下面的代码示例通过使用联接两个集合`Join`子句。</span><span class="sxs-lookup"><span data-stu-id="10ef0-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="10ef0-139">此示例将生成类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="10ef0-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="10ef0-140">示例</span><span class="sxs-lookup"><span data-stu-id="10ef0-140">Example</span></span>  
 <span data-ttu-id="10ef0-141">下面的代码示例通过使用联接两个集合`Join`子句的两个键列。</span><span class="sxs-lookup"><span data-stu-id="10ef0-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="10ef0-142">此示例将生成类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="10ef0-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="10ef0-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="10ef0-143">See Also</span></span>  
 [<span data-ttu-id="10ef0-144">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="10ef0-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="10ef0-145">查询</span><span class="sxs-lookup"><span data-stu-id="10ef0-145">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="10ef0-146">Select 子句</span><span class="sxs-lookup"><span data-stu-id="10ef0-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="10ef0-147">From 子句</span><span class="sxs-lookup"><span data-stu-id="10ef0-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="10ef0-148">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="10ef0-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="10ef0-149">Where 子句</span><span class="sxs-lookup"><span data-stu-id="10ef0-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
