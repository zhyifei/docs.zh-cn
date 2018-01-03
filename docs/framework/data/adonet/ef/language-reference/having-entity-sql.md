---
title: HAVING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 92949205801e5bc498fdaaa67c2fa228140a2eb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="having-entity-sql"></a><span data-ttu-id="0b4f3-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0b4f3-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="0b4f3-103">指定组或聚合的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b4f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b4f3-104">Syntax</span></span>  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b4f3-105">自变量</span><span class="sxs-lookup"><span data-stu-id="0b4f3-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="0b4f3-106">指定组或聚合应满足的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="0b4f3-107">当 HAVING 与 GROUP BY ALL 一起使用时，HAVING 子句优先于 ALL。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b4f3-108">备注</span><span class="sxs-lookup"><span data-stu-id="0b4f3-108">Remarks</span></span>  
 <span data-ttu-id="0b4f3-109">HAVING 子句用于对分组结果指定附加筛选条件。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="0b4f3-110">如果在查询表达式中未指定 GROUP BY 子句，则将使用隐式单集组。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b4f3-111">HAVING 可仅与[选择](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)语句。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-111">HAVING can be used only with the [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statement.</span></span> <span data-ttu-id="0b4f3-112">当[GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)是未使用，HAVING 的行为方式类似的 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-112">When [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
 <span data-ttu-id="0b4f3-113">HAVING 子句与 WHERE 子句的工作方式类似，只是它应用在 GROUP BY 操作之后。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="0b4f3-114">这意味着 HAVING 子句只能引用分组别名和聚合，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example.</span></span>  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="0b4f3-115">上例将组限定为只包含多个产品的组。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b4f3-116">示例</span><span class="sxs-lookup"><span data-stu-id="0b4f3-116">Example</span></span>  
 <span data-ttu-id="0b4f3-117">下面的 Entity SQL 查询使用 HAVING 和 GROUP BY 运算符指定组或聚合的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="0b4f3-118">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0b4f3-119">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="0b4f3-119">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0b4f3-120">按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="0b4f3-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="0b4f3-121">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="0b4f3-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a><span data-ttu-id="0b4f3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b4f3-122">See Also</span></span>  
 [<span data-ttu-id="0b4f3-123">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="0b4f3-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="0b4f3-124">查询表达式</span><span class="sxs-lookup"><span data-stu-id="0b4f3-124">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
