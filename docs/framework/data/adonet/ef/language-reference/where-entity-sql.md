---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 8dd0e34a6669b2147052befb17b8f4ff8395aabc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248487"
---
# <a name="where-entity-sql"></a><span data-ttu-id="98c88-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="98c88-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="98c88-103">WHERE 子句直接应用于[from](from-entity-sql.md)子句之后。</span><span class="sxs-lookup"><span data-stu-id="98c88-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98c88-104">语法</span><span class="sxs-lookup"><span data-stu-id="98c88-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="98c88-105">自变量</span><span class="sxs-lookup"><span data-stu-id="98c88-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="98c88-106">Boolean 类型。</span><span class="sxs-lookup"><span data-stu-id="98c88-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98c88-107">备注</span><span class="sxs-lookup"><span data-stu-id="98c88-107">Remarks</span></span>  
 <span data-ttu-id="98c88-108">WHERE 子句具有与 Transact-sql 所述相同的语义。</span><span class="sxs-lookup"><span data-stu-id="98c88-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="98c88-109">它将源集合的元素限定为传递条件的元素，以此限制查询表达式所生成的对象。</span><span class="sxs-lookup"><span data-stu-id="98c88-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="98c88-110">表达式 `e` 必须为 Boolean 类型。</span><span class="sxs-lookup"><span data-stu-id="98c88-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="98c88-111">WHERE 子句直接应用在 FROM 子句之后，任何分组、排序或投影操作之前。</span><span class="sxs-lookup"><span data-stu-id="98c88-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="98c88-112">FROM 子句中定义的所有元素名称对 WHERE 子句的表达式都是可见的。</span><span class="sxs-lookup"><span data-stu-id="98c88-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c88-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="98c88-113">See also</span></span>

- [<span data-ttu-id="98c88-114">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="98c88-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="98c88-115">查询表达式</span><span class="sxs-lookup"><span data-stu-id="98c88-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
