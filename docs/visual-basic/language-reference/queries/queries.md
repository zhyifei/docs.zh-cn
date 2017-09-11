---
title: "查询 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic]
- LINQ, queries
ms.assetid: 8edc717c-4a24-4cbc-9c16-11f479c935db
caps.latest.revision: 11
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
ms.openlocfilehash: 4a178714055076537033fbda32d7c7c1c544351d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="queries-visual-basic"></a><span data-ttu-id="f682c-102">查询 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f682c-102">Queries (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f682c-103">使您能够创建[!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)]在代码中的表达式。</span><span class="sxs-lookup"><span data-stu-id="f682c-103"> enables you to create [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f682c-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="f682c-104">In This Section</span></span>  
 [<span data-ttu-id="f682c-105">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-105">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 <span data-ttu-id="f682c-106">描述`Aggregate`子句，将一个或多个聚合函数应用到集合。</span><span class="sxs-lookup"><span data-stu-id="f682c-106">Describes the `Aggregate` clause, which applies one or more aggregate functions to a collection.</span></span>  
  
 [<span data-ttu-id="f682c-107">Distinct 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-107">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 <span data-ttu-id="f682c-108">描述`Distinct`子句中，这样就限制了当前的范围变量，以消除重复的值在查询结果中的值。</span><span class="sxs-lookup"><span data-stu-id="f682c-108">Describes the `Distinct` clause, which restricts the values of the current range variable to eliminate duplicate values in query results.</span></span>  
  
 [<span data-ttu-id="f682c-109">From 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-109">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 <span data-ttu-id="f682c-110">描述`From`子句，指定集合和查询的范围变量。</span><span class="sxs-lookup"><span data-stu-id="f682c-110">Describes the `From` clause, which specifies a collection and a range variable for a query.</span></span>  
  
 [<span data-ttu-id="f682c-111">Group By 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-111">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)  
 <span data-ttu-id="f682c-112">描述`Group By`子句，用于对查询结果的元素进行分组，可用于将聚合函数应用到每个组。</span><span class="sxs-lookup"><span data-stu-id="f682c-112">Describes the `Group By` clause, which groups the elements of a query result and can be used to apply aggregate functions to each group.</span></span>  
  
 [<span data-ttu-id="f682c-113">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-113">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 <span data-ttu-id="f682c-114">描述`Group Join`子句，将合并成单个层次结构集合的两个集合。</span><span class="sxs-lookup"><span data-stu-id="f682c-114">Describes the `Group Join` clause, which combines two collections into a single hierarchical collection.</span></span>  
  
 [<span data-ttu-id="f682c-115">Join 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-115">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 <span data-ttu-id="f682c-116">描述`Join`子句，将合并成单个集合的两个集合。</span><span class="sxs-lookup"><span data-stu-id="f682c-116">Describes the `Join` clause, which combines two collections into a single collection.</span></span>  
  
 [<span data-ttu-id="f682c-117">Let 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-117">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 <span data-ttu-id="f682c-118">描述`Let`子句，用于计算一个值，并将其分配给该查询中的新变量。</span><span class="sxs-lookup"><span data-stu-id="f682c-118">Describes the `Let` clause, which computes a value and assigns it to a new variable in the query.</span></span>  
  
 [<span data-ttu-id="f682c-119">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-119">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 <span data-ttu-id="f682c-120">描述`Order By`子句，用于在查询中指定列的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="f682c-120">Describes the `Order By` clause, which specifies the sort order for columns in a query.</span></span>  
  
 [<span data-ttu-id="f682c-121">Select 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-121">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 <span data-ttu-id="f682c-122">描述`Select`子句，声明了一组查询的范围变量。</span><span class="sxs-lookup"><span data-stu-id="f682c-122">Describes the `Select` clause, which declares a set of range variables for a query.</span></span>  
  
 [<span data-ttu-id="f682c-123">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-123">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 <span data-ttu-id="f682c-124">描述`Skip`子句，用于跳过指定的数量的集合中的元素，然后返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="f682c-124">Describes the `Skip` clause, which bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="f682c-125">Skip While 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 <span data-ttu-id="f682c-126">描述`Skip While`子句，只要指定的条件是否跳过集合中的元素`true`，然后返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="f682c-126">Describes the `Skip While` clause, which bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="f682c-127">Take 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-127">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 <span data-ttu-id="f682c-128">描述`Take`子句，从集合中的开头返回指定的数量的连续元素。</span><span class="sxs-lookup"><span data-stu-id="f682c-128">Describes the `Take` clause, which returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
 [<span data-ttu-id="f682c-129">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-129">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 <span data-ttu-id="f682c-130">描述`Take While`子句中，集合中包括的元素，只要指定的条件是`true`并跳过其余元素。</span><span class="sxs-lookup"><span data-stu-id="f682c-130">Describes the `Take While` clause, which includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
 [<span data-ttu-id="f682c-131">Where 子句</span><span class="sxs-lookup"><span data-stu-id="f682c-131">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 <span data-ttu-id="f682c-132">描述`Where`子句，用于指定查询的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="f682c-132">Describes the `Where` clause, which specifies a filtering condition for a query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f682c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f682c-133">See Also</span></span>  
 <span data-ttu-id="f682c-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="f682c-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="f682c-135"> [在 Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f682c-135"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
