---
title: 撰写嵌套的 Entity SQL 查询
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 87a9877b7c865fbe393d91365d03bab8f56377c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589468"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="dad99-102">撰写嵌套的 Entity SQL 查询</span><span class="sxs-lookup"><span data-stu-id="dad99-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="dad99-103">是一种功能丰富的语言。</span><span class="sxs-lookup"><span data-stu-id="dad99-103">is a rich functional language.</span></span> <span data-ttu-id="dad99-104">构建基块[!INCLUDE[esql](../../../../../../includes/esql-md.md)]是一个表达式。</span><span class="sxs-lookup"><span data-stu-id="dad99-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="dad99-105">与传统 SQL 不同[!INCLUDE[esql](../../../../../../includes/esql-md.md)]并不仅限于表格结果集：[!INCLUDE[esql](../../../../../../includes/esql-md.md)]支持编写文本、 参数或嵌套的表达式可以具有的复杂表达式。</span><span class="sxs-lookup"><span data-stu-id="dad99-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="dad99-106">在表达式中的值可以参数化或其他表达式构成。</span><span class="sxs-lookup"><span data-stu-id="dad99-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="dad99-107">嵌套表达式</span><span class="sxs-lookup"><span data-stu-id="dad99-107">Nested Expressions</span></span>  
 <span data-ttu-id="dad99-108">嵌套表达式可以放置在任何可接受其返回类型值的位置。</span><span class="sxs-lookup"><span data-stu-id="dad99-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="dad99-109">例如：</span><span class="sxs-lookup"><span data-stu-id="dad99-109">For example:</span></span>  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="dad99-110">嵌套查询可以放在投影子句中。</span><span class="sxs-lookup"><span data-stu-id="dad99-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="dad99-111">例如：</span><span class="sxs-lookup"><span data-stu-id="dad99-111">For example:</span></span>  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="dad99-112">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中，嵌套查询必须括在括号中：</span><span class="sxs-lookup"><span data-stu-id="dad99-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="dad99-113">下面的示例演示如何中正确嵌套表达式[!INCLUDE[esql](../../../../../../includes/esql-md.md)]:[如何：两个查询的联合排序](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)。</span><span class="sxs-lookup"><span data-stu-id="dad99-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="dad99-114">投影中的嵌套查询</span><span class="sxs-lookup"><span data-stu-id="dad99-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="dad99-115">投影子句中的嵌套查询可在服务器上转换为笛卡尔积查询。</span><span class="sxs-lookup"><span data-stu-id="dad99-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="dad99-116">在某些后端服务器（包括 SLQ Server）中，这会导致 TempDB 表变得过大，对服务器性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="dad99-116">In some backend servers, including SLQ Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="dad99-117">以下是这种查询的一个示例：</span><span class="sxs-lookup"><span data-stu-id="dad99-117">The following is an example of such a query:</span></span>  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="dad99-118">嵌套查询排序</span><span class="sxs-lookup"><span data-stu-id="dad99-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="dad99-119">在实体框架中，嵌套表达式可置于查询中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="dad99-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="dad99-120">Entity SQL 为编写查询提供了非常大的灵活性，可以在编写的查询中包含对嵌套查询的排序。</span><span class="sxs-lookup"><span data-stu-id="dad99-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="dad99-121">但是，将不保留嵌套查询的顺序。</span><span class="sxs-lookup"><span data-stu-id="dad99-121">However, the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="dad99-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="dad99-122">See also</span></span>
- [<span data-ttu-id="dad99-123">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="dad99-123">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
