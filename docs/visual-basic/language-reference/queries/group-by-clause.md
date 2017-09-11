---
title: "Group By 子句 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement
- Group By clause
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a27e2f15e61456b2e7ac0ede81c66cdb4e8fd612
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="0dae3-102">Group By 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0dae3-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="0dae3-103">对查询结果的元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="0dae3-103">Groups the elements of a query result.</span></span> <span data-ttu-id="0dae3-104">也可用于将聚合函数应用于每个组。</span><span class="sxs-lookup"><span data-stu-id="0dae3-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="0dae3-105">分组运算基于一个或多个键。</span><span class="sxs-lookup"><span data-stu-id="0dae3-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dae3-106">语法</span><span class="sxs-lookup"><span data-stu-id="0dae3-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="0dae3-107">部件</span><span class="sxs-lookup"><span data-stu-id="0dae3-107">Parts</span></span>  
  
-   <span data-ttu-id="0dae3-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="0dae3-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="0dae3-109">可选。</span><span class="sxs-lookup"><span data-stu-id="0dae3-109">Optional.</span></span> <span data-ttu-id="0dae3-110">分组结果中将包括一个或多个显式标识字段的查询变量的一个或多个字段。</span><span class="sxs-lookup"><span data-stu-id="0dae3-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="0dae3-111">如果未指定字段，则分组结果中将包括一个或多个查询变量的所有字段。</span><span class="sxs-lookup"><span data-stu-id="0dae3-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="0dae3-112">必需。</span><span class="sxs-lookup"><span data-stu-id="0dae3-112">Required.</span></span> <span data-ttu-id="0dae3-113">标识键以用于确定元素所在的组的表达式。</span><span class="sxs-lookup"><span data-stu-id="0dae3-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="0dae3-114">可以指定多个键以形成组合键。</span><span class="sxs-lookup"><span data-stu-id="0dae3-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="0dae3-115">可选。</span><span class="sxs-lookup"><span data-stu-id="0dae3-115">Optional.</span></span> <span data-ttu-id="0dae3-116">与 `keyExp1` 结合以形成组合键的一个或多个其他键。</span><span class="sxs-lookup"><span data-stu-id="0dae3-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="0dae3-117">必需。</span><span class="sxs-lookup"><span data-stu-id="0dae3-117">Required.</span></span> <span data-ttu-id="0dae3-118">标识如何对组进行聚合的一个或多个表达式。</span><span class="sxs-lookup"><span data-stu-id="0dae3-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="0dae3-119">若要标识分组结果的成员名称，请使用 `Group` 关键字，它可以采用以下任意一种形式：</span><span class="sxs-lookup"><span data-stu-id="0dae3-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="0dae3-120">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0dae3-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="0dae3-121">还可以包含聚合函数以将其应用于该组。</span><span class="sxs-lookup"><span data-stu-id="0dae3-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dae3-122">备注</span><span class="sxs-lookup"><span data-stu-id="0dae3-122">Remarks</span></span>  
 <span data-ttu-id="0dae3-123">可以使用 `Group By` 子句来将查询的结果分解为组。</span><span class="sxs-lookup"><span data-stu-id="0dae3-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="0dae3-124">分组基于某个键或包含多个键的组合键。</span><span class="sxs-lookup"><span data-stu-id="0dae3-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="0dae3-125">与匹配的键值相关联的元素包括在同一组中。</span><span class="sxs-lookup"><span data-stu-id="0dae3-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="0dae3-126">使用 `aggregateList` 子句的 `Into` 参数和 `Group` 关键字来标识用于引用该组的成员名称。</span><span class="sxs-lookup"><span data-stu-id="0dae3-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="0dae3-127">还可以将聚合函数包括在 `Into` 子句中，以计算分组元素的值。</span><span class="sxs-lookup"><span data-stu-id="0dae3-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="0dae3-128">标准聚合函数的列表，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="0dae3-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dae3-129">示例</span><span class="sxs-lookup"><span data-stu-id="0dae3-129">Example</span></span>  
 <span data-ttu-id="0dae3-130">下面的代码示例根据客户所在的位置（国家/地区）对客户列表进行分组，并提供了每个组中的客户计数。</span><span class="sxs-lookup"><span data-stu-id="0dae3-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="0dae3-131">按国家/地区名称对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="0dae3-131">The results are ordered by country name.</span></span> <span data-ttu-id="0dae3-132">按城市名称对分组结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="0dae3-132">The grouped results are ordered by city name.</span></span>  
  
 <span data-ttu-id="0dae3-133">[!code-vb[VbSimpleQuerySamples #&11;](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0dae3-133">[!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dae3-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dae3-134">See Also</span></span>  
 <span data-ttu-id="0dae3-135">[在 Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="0dae3-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="0dae3-136"> [查询](../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="0dae3-136"> [Queries](../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="0dae3-137"> [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="0dae3-137"> [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md) </span></span>  
<span data-ttu-id="0dae3-138"> [From 子句](../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="0dae3-138"> [From Clause](../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="0dae3-139"> [Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="0dae3-139"> [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="0dae3-140"> [Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="0dae3-140"> [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="0dae3-141"> [Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0dae3-141"> [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)</span></span>
