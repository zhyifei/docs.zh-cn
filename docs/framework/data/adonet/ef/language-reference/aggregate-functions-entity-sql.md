---
title: "聚合函数 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a7c5675645591ff467d983155e61fb21615a6171
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="aggregate-functions-entity-sql"></a><span data-ttu-id="aea27-102">聚合函数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="aea27-102">Aggregate Functions (Entity SQL)</span></span>
<span data-ttu-id="aea27-103">聚合是一种语言构造，它将集合浓缩为标量以作为组运算的一部分。</span><span class="sxs-lookup"><span data-stu-id="aea27-103">An aggregate is a language construct that condenses a collection into a scalar as a part of a group operation.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="aea27-104"> 聚合分为两种形式：</span><span class="sxs-lookup"><span data-stu-id="aea27-104"> aggregates come in two forms:</span></span>  
  
-   [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="aea27-105">集合函数可能在表达式中的任意位置使用。</span><span class="sxs-lookup"><span data-stu-id="aea27-105"> collection functions that may be used anywhere in an expression.</span></span> <span data-ttu-id="aea27-106">这包括在作用于集合的投影和谓词中使用聚合函数。</span><span class="sxs-lookup"><span data-stu-id="aea27-106">This includes using aggregate functions in projections and predicates that act on collections.</span></span> <span data-ttu-id="aea27-107">集合函数是在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中指定聚合的首选模式。</span><span class="sxs-lookup"><span data-stu-id="aea27-107">Collection functions are the preferred mode of specifying aggregates in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
-   <span data-ttu-id="aea27-108">具有 GROUP BY 子句的表达式中的组聚合。</span><span class="sxs-lookup"><span data-stu-id="aea27-108">Group aggregates in query expressions that have a GROUP BY clause.</span></span> <span data-ttu-id="aea27-109">与在 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 中一样，组聚合接受 DISTINCT 和 ALL 作为聚合输入的修饰符。</span><span class="sxs-lookup"><span data-stu-id="aea27-109">As in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], group aggregates accept DISTINCT and ALL as modifiers to the aggregate input.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="aea27-110">首先尝试将解释为集合函数的表达式，如果表达式处于 SELECT 表达式的上下文中则可将其解释为组聚合。</span><span class="sxs-lookup"><span data-stu-id="aea27-110"> first tries to interpret an expression as a collection function and if the expression is in the context of a SELECT expression it interprets it as a group aggregate.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="aea27-111">定义特殊的聚合运算符调用[GROUPPARTITION](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="aea27-111"> defines a special aggregate operator called [GROUPPARTITION](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md).</span></span> <span data-ttu-id="aea27-112">此运算符，您可以获取对分组的输入集的引用。</span><span class="sxs-lookup"><span data-stu-id="aea27-112">This operator enables you to get a reference to the grouped input set.</span></span> <span data-ttu-id="aea27-113">这样，就可以进行更高级的分组查询，其中，GROUP BY 子句的结果可以用在除组聚合或集合函数之外的位置。</span><span class="sxs-lookup"><span data-stu-id="aea27-113">This allows more advanced grouping queries, where the results of the GROUP BY clause can be used in places other than group aggregate or collection functions.</span></span>  
  
## <a name="collection-functions"></a><span data-ttu-id="aea27-114">集合函数</span><span class="sxs-lookup"><span data-stu-id="aea27-114">Collection Functions</span></span>  
 <span data-ttu-id="aea27-115">集合函数针对集合运行并返回标量值。</span><span class="sxs-lookup"><span data-stu-id="aea27-115">Collection functions operate on collections and return a scalar value.</span></span> <span data-ttu-id="aea27-116">例如，如果 `orders` 是所有 `orders` 的集合，则可以使用以下表达式计算最早的发货日期：</span><span class="sxs-lookup"><span data-stu-id="aea27-116">For example, if `orders` is a collection of all `orders`, you can calculate the earliest ship date with the following expression:</span></span>  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a><span data-ttu-id="aea27-117">组聚合</span><span class="sxs-lookup"><span data-stu-id="aea27-117">Group Aggregates</span></span>  
 <span data-ttu-id="aea27-118">组聚合将按照 GROUP BY 子句定义的方式对组结果进行计算。</span><span class="sxs-lookup"><span data-stu-id="aea27-118">Group aggregates are calculated over a group result as defined by the GROUP BY clause.</span></span> <span data-ttu-id="aea27-119">GROUP BY 子句将数据分区为组。</span><span class="sxs-lookup"><span data-stu-id="aea27-119">The GROUP BY clause partitions data  into groups.</span></span> <span data-ttu-id="aea27-120">对于结果中的每个组，将应用聚合函数，并使用每个组中的元素作为聚合计算的输入来计算单独的聚合。</span><span class="sxs-lookup"><span data-stu-id="aea27-120">For each group in the result, the aggregate function is applied and a separate aggregate is calculated by using the elements in each group as inputs to the aggregate calculation.</span></span> <span data-ttu-id="aea27-121">当在 SELECT 表达式中使用 GROUP BY 子句时，在投影、HAVING 或 ORDER BY 子句中只能存在分组表达式名称、聚合或常量表达式。</span><span class="sxs-lookup"><span data-stu-id="aea27-121">When a GROUP BY clause is used in a SELECT expression, only grouping expression names, aggregates, or constant expressions may be present in the projection, HAVING, or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="aea27-122">以下示例计算每种产品的平均订购数量。</span><span class="sxs-lookup"><span data-stu-id="aea27-122">The following example calculates the average quantity ordered for each product.</span></span>  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 <span data-ttu-id="aea27-123">在 SELECT 表达式中，可以在没有显式 GROUP BY 子句的情况下使用组聚合。</span><span class="sxs-lookup"><span data-stu-id="aea27-123">It is possible to have a group aggregate without an explicit GROUP BY clause in the SELECT expression.</span></span> <span data-ttu-id="aea27-124">所有元素均将被视为单个组，这等同于基于常量指定分组的情况。</span><span class="sxs-lookup"><span data-stu-id="aea27-124">All elements will be treated as a single group, equivalent to the case of specifying a grouping based on a constant.</span></span>  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 <span data-ttu-id="aea27-125">将使用 WHERE 子句表达式可见的相同名称解析范围计算 GROUP BY 子句中使用的表达式。</span><span class="sxs-lookup"><span data-stu-id="aea27-125">Expressions used in the GROUP BY clause are evaluated by using the same name-resolution scope that would be visible to the WHERE clause expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea27-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="aea27-126">See Also</span></span>  
 [<span data-ttu-id="aea27-127">函数</span><span class="sxs-lookup"><span data-stu-id="aea27-127">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
