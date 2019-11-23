---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 97ed6e06241804bf2f576c910a2235b0cb570bbb
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833735"
---
# <a name="having-entity-sql"></a><span data-ttu-id="282d3-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="282d3-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="282d3-103">为某个组或聚合指定搜索条件。</span><span class="sxs-lookup"><span data-stu-id="282d3-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="282d3-104">Syntax</span></span>  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="282d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="282d3-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="282d3-106">为组或聚合指定要满足的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="282d3-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="282d3-107">当 HAVING 与 GROUP BY ALL 一起使用时，HAVING 子句优先于 ALL。</span><span class="sxs-lookup"><span data-stu-id="282d3-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="282d3-108">备注</span><span class="sxs-lookup"><span data-stu-id="282d3-108">Remarks</span></span>  
 <span data-ttu-id="282d3-109">HAVING 子句用于对分组结果指定附加筛选条件。</span><span class="sxs-lookup"><span data-stu-id="282d3-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="282d3-110">如果在查询表达式中未指定 GROUP BY 子句，则将使用隐式单集组。</span><span class="sxs-lookup"><span data-stu-id="282d3-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="282d3-111">HAVING 只能与[SELECT](select-entity-sql.md)语句一起使用。</span><span class="sxs-lookup"><span data-stu-id="282d3-111">HAVING can be used only with the [SELECT](select-entity-sql.md) statement.</span></span> <span data-ttu-id="282d3-112">如果不使用[GROUP BY](group-by-entity-sql.md) ，则其行为与 WHERE 子句类似。</span><span class="sxs-lookup"><span data-stu-id="282d3-112">When [GROUP BY](group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
<span data-ttu-id="282d3-113">HAVING 子句与 WHERE 子句的工作方式类似，只是它应用在 GROUP BY 操作之后。</span><span class="sxs-lookup"><span data-stu-id="282d3-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="282d3-114">这意味着 HAVING 子句只能引用分组别名和聚合，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="282d3-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example:</span></span>
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="282d3-115">上例将组限定为只包含多个产品的组。</span><span class="sxs-lookup"><span data-stu-id="282d3-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="282d3-116">示例</span><span class="sxs-lookup"><span data-stu-id="282d3-116">Example</span></span>  
 <span data-ttu-id="282d3-117">下面的 Entity SQL 查询使用 HAVING 和 GROUP BY 运算符指定组或聚合的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="282d3-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="282d3-118">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="282d3-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="282d3-119">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="282d3-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="282d3-120">按照[如何：执行返回 PrimitiveType 结果的查询](../how-to-execute-a-query-that-returns-primitivetype-results.md)中的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="282d3-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="282d3-121">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="282d3-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a><span data-ttu-id="282d3-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="282d3-122">See also</span></span>

- [<span data-ttu-id="282d3-123">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="282d3-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="282d3-124">查询表达式</span><span class="sxs-lookup"><span data-stu-id="282d3-124">Query Expressions</span></span>](query-expressions-entity-sql.md)
