---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 9f0f917380e6422da753282216529580f87f1a1a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774720"
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="ec51b-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ec51b-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="ec51b-103">返回从聚合与之相关的当前组分区提取的参数值集合。</span><span class="sxs-lookup"><span data-stu-id="ec51b-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="ec51b-104">`GroupPartition` 聚合是基于组的聚合，没有基于集合的形式。</span><span class="sxs-lookup"><span data-stu-id="ec51b-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec51b-105">语法</span><span class="sxs-lookup"><span data-stu-id="ec51b-105">Syntax</span></span>  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec51b-106">自变量</span><span class="sxs-lookup"><span data-stu-id="ec51b-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ec51b-107">任何 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 表达式。</span><span class="sxs-lookup"><span data-stu-id="ec51b-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec51b-108">备注</span><span class="sxs-lookup"><span data-stu-id="ec51b-108">Remarks</span></span>  
 <span data-ttu-id="ec51b-109">以下查询生成产品列表以及每个产品的订单行数量的集合。</span><span class="sxs-lookup"><span data-stu-id="ec51b-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="ec51b-110">以下两个查询在语义上是相同的：</span><span class="sxs-lookup"><span data-stu-id="ec51b-110">The following two queries are semantically equal:</span></span>  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="ec51b-111">`GROUPPARTITION` 运算符可以与用户定义的聚合函数结合使用。</span><span class="sxs-lookup"><span data-stu-id="ec51b-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
 <span data-ttu-id="ec51b-112">`GROUPPARTITION` 是一个特殊的聚合运算符，它保留对于分组的输入集的引用。</span><span class="sxs-lookup"><span data-stu-id="ec51b-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="ec51b-113">此引用可以用在 GROUP BY 处于作用域内的查询中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="ec51b-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="ec51b-114">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="ec51b-114">For example,</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="ec51b-115">使用正则 GROUP BY，分组的结果处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="ec51b-115">With a regular GROUP BY, the results of the grouping are hidden.</span></span> <span data-ttu-id="ec51b-116">您只能在聚合函数中使用结果。</span><span class="sxs-lookup"><span data-stu-id="ec51b-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="ec51b-117">为了能够看到分组的结果，必须使用子查询使分组的结果与输入集相关。</span><span class="sxs-lookup"><span data-stu-id="ec51b-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="ec51b-118">下面两个查询是等效的：</span><span class="sxs-lookup"><span data-stu-id="ec51b-118">The following two queries are equivalent:</span></span>  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="ec51b-119">如示例中所示，通过 GROUPPARTITION 聚合运算符，可以在分组后更轻松地获得对输入集的引用。</span><span class="sxs-lookup"><span data-stu-id="ec51b-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="ec51b-120">当您使用 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 参数时，GROUPPARTITION 运算符可以在运算符输入中指定任何 `expression` 表达式。</span><span class="sxs-lookup"><span data-stu-id="ec51b-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="ec51b-121">例如，下面针对组分区的所有输入表达式都是有效的：</span><span class="sxs-lookup"><span data-stu-id="ec51b-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="ec51b-122">示例</span><span class="sxs-lookup"><span data-stu-id="ec51b-122">Example</span></span>  
 <span data-ttu-id="ec51b-123">下面的示例演示如何将 GROUPPARTITION 子句与 GROUP BY 子句一起使用。</span><span class="sxs-lookup"><span data-stu-id="ec51b-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="ec51b-124">GROUP BY 子句按照 `SalesOrderHeader` 实体的 `Contact`对这些实体进行分组。</span><span class="sxs-lookup"><span data-stu-id="ec51b-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="ec51b-125">然后，GROUPPARTITION 子句投影每个组的 `TotalDue` 属性，而生成一个十进制值集合。</span><span class="sxs-lookup"><span data-stu-id="ec51b-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
