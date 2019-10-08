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
ms.openlocfilehash: 8eab7db00515f55b086b5e1beddd149f966cb27a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72001933"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="e8094-102">Join 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8094-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="e8094-103">将两个集合合并为单个集合。</span><span class="sxs-lookup"><span data-stu-id="e8094-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="e8094-104">联接运算基于匹配键，并使用 `Equals` 运算符。</span><span class="sxs-lookup"><span data-stu-id="e8094-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8094-105">语法</span><span class="sxs-lookup"><span data-stu-id="e8094-105">Syntax</span></span>  
  
```vb  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="e8094-106">部件</span><span class="sxs-lookup"><span data-stu-id="e8094-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="e8094-107">必需。</span><span class="sxs-lookup"><span data-stu-id="e8094-107">Required.</span></span> <span data-ttu-id="e8094-108">要联接的集合的控件变量。</span><span class="sxs-lookup"><span data-stu-id="e8094-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="e8094-109">必需。</span><span class="sxs-lookup"><span data-stu-id="e8094-109">Required.</span></span> <span data-ttu-id="e8094-110">要与 `Join` 运算符左侧标识的集合组合的集合。</span><span class="sxs-lookup"><span data-stu-id="e8094-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="e8094-111">@No__t-0 子句可以嵌套在另一个 @no__t 子句中，也可以嵌套在 @no__t 的子句中。</span><span class="sxs-lookup"><span data-stu-id="e8094-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="e8094-112">可选。</span><span class="sxs-lookup"><span data-stu-id="e8094-112">Optional.</span></span> <span data-ttu-id="e8094-113">一个或多个附加 `Join` 子句，用于进一步细化查询。</span><span class="sxs-lookup"><span data-stu-id="e8094-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="e8094-114">可选。</span><span class="sxs-lookup"><span data-stu-id="e8094-114">Optional.</span></span> <span data-ttu-id="e8094-115">一个或多个附加 `Group Join` 子句，用于进一步细化查询。</span><span class="sxs-lookup"><span data-stu-id="e8094-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="e8094-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="e8094-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="e8094-117">必需。</span><span class="sxs-lookup"><span data-stu-id="e8094-117">Required.</span></span> <span data-ttu-id="e8094-118">标识要联接的集合的键。</span><span class="sxs-lookup"><span data-stu-id="e8094-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="e8094-119">必须使用 `Equals` 运算符来比较要联接的集合中的键。</span><span class="sxs-lookup"><span data-stu-id="e8094-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="e8094-120">可以通过使用 `And` 运算符来组合联接条件，以标识多个键。</span><span class="sxs-lookup"><span data-stu-id="e8094-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="e8094-121">`key1` 必须来自 `Join` 运算符左侧的集合。</span><span class="sxs-lookup"><span data-stu-id="e8094-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="e8094-122">@no__t 在 `Join` 运算符右侧的集合中。</span><span class="sxs-lookup"><span data-stu-id="e8094-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="e8094-123">联接条件中使用的键可以是包含集合中多个项的表达式。</span><span class="sxs-lookup"><span data-stu-id="e8094-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="e8094-124">但是，每个键表达式只能包含其各自集合中的项。</span><span class="sxs-lookup"><span data-stu-id="e8094-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8094-125">备注</span><span class="sxs-lookup"><span data-stu-id="e8094-125">Remarks</span></span>  
 <span data-ttu-id="e8094-126">@No__t-0 子句组合了两个集合，这些集合基于要联接的集合中的匹配键值。</span><span class="sxs-lookup"><span data-stu-id="e8094-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="e8094-127">生成的集合可以包含从 `Join` 运算符左侧标识的集合中的任何值组合和 `Join` 子句中标识的集合。</span><span class="sxs-lookup"><span data-stu-id="e8094-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="e8094-128">查询将只返回 @no__t 为0运算符指定的条件的结果。</span><span class="sxs-lookup"><span data-stu-id="e8094-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="e8094-129">这等效于 SQL 中的 @no__t 0。</span><span class="sxs-lookup"><span data-stu-id="e8094-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="e8094-130">您可以使用查询中的多个 `Join` 子句将两个或多个集合联接到一个集合中。</span><span class="sxs-lookup"><span data-stu-id="e8094-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="e8094-131">您可以执行隐式联接来组合集合，而不使用 `Join` 子句。</span><span class="sxs-lookup"><span data-stu-id="e8094-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="e8094-132">为此，请在 @no__t 子句中包含多个 `In` 子句，并指定一个 `Where` 子句，用于标识要用于联接的键。</span><span class="sxs-lookup"><span data-stu-id="e8094-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="e8094-133">可以使用 `Group Join` 子句将集合合并为单个分层集合。</span><span class="sxs-lookup"><span data-stu-id="e8094-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="e8094-134">这类似于 SQL 中的 @no__t 0。</span><span class="sxs-lookup"><span data-stu-id="e8094-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8094-135">示例</span><span class="sxs-lookup"><span data-stu-id="e8094-135">Example</span></span>  
 <span data-ttu-id="e8094-136">下面的代码示例将执行隐式联接，以将客户列表与订单组合在一起。</span><span class="sxs-lookup"><span data-stu-id="e8094-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="e8094-137">示例</span><span class="sxs-lookup"><span data-stu-id="e8094-137">Example</span></span>  
 <span data-ttu-id="e8094-138">下面的代码示例通过使用 `Join` 子句联接两个集合。</span><span class="sxs-lookup"><span data-stu-id="e8094-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]  
  
 <span data-ttu-id="e8094-139">此示例将生成与下面类似的输出：</span><span class="sxs-lookup"><span data-stu-id="e8094-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="e8094-140">示例</span><span class="sxs-lookup"><span data-stu-id="e8094-140">Example</span></span>  
 <span data-ttu-id="e8094-141">下面的代码示例通过使用带有两个键列的 `Join` 子句来联接两个集合。</span><span class="sxs-lookup"><span data-stu-id="e8094-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]  
  
 <span data-ttu-id="e8094-142">该示例将生成类似于以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="e8094-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="e8094-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8094-143">See also</span></span>

- [<span data-ttu-id="e8094-144">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="e8094-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="e8094-145">查询</span><span class="sxs-lookup"><span data-stu-id="e8094-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="e8094-146">Select 子句</span><span class="sxs-lookup"><span data-stu-id="e8094-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="e8094-147">From 子句</span><span class="sxs-lookup"><span data-stu-id="e8094-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="e8094-148">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="e8094-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="e8094-149">Where 子句</span><span class="sxs-lookup"><span data-stu-id="e8094-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
