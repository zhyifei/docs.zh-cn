---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: e8ef529ea8d2be2ef8eb3a2eb606e7ca8bf13f0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797732"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="8d1a9-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8d1a9-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="8d1a9-103">在 ORDER BY 子句中使用 SKIP 子子句可执行物理分页。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="8d1a9-104">SKIP 不能脱离 ORDER BY 子句单独使用。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d1a9-105">语法</span><span class="sxs-lookup"><span data-stu-id="8d1a9-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8d1a9-106">自变量</span><span class="sxs-lookup"><span data-stu-id="8d1a9-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="8d1a9-107">要跳过的项数。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d1a9-108">备注</span><span class="sxs-lookup"><span data-stu-id="8d1a9-108">Remarks</span></span>  
 <span data-ttu-id="8d1a9-109">如果 ORDER BY 子句中存在 SKIP 表达式子子句，则将根据排序规范对结果排序，结果集将包含从紧接着 SKIP 表达式之后的下一行开始的行。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="8d1a9-110">例如，SKIP 5 将跳过前五行，并返回第六行以及后续行。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d1a9-111">如果 TOP 修饰符和 SKIP 子子句同时出现在同一个查询表达式中， [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询将无效。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="8d1a9-112">应重写查询，将 TOP 表达式更改为 LIMIT 表达式。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d1a9-113">在 [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]中，对非键列同时使用 SKIP 和 ORDER BY 可能返回不正确的结果。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-113">In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="8d1a9-114">如果非键列中有重复数据，那么跳过的行数可能多于指定的行数。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="8d1a9-115">这是由于 [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]对 SKIP 的解释方式造成的。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-115">This is due to how SKIP is translated for [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="8d1a9-116">例如，在下面的代码中，如果 `E.NonKeyColumn` 有重复值，则跳过的行可能超过 5 行：</span><span class="sxs-lookup"><span data-stu-id="8d1a9-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="8d1a9-117">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]查询中的[如何：通过查询结果进行分页](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))使用 ORDER BY 运算符与 SKIP 来指定用于 SELECT 语句中返回对象的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="8d1a9-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d1a9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d1a9-118">See also</span></span>

- [<span data-ttu-id="8d1a9-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="8d1a9-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="8d1a9-120">[如何：页查看查询结果](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8d1a9-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="8d1a9-121">分页</span><span class="sxs-lookup"><span data-stu-id="8d1a9-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="8d1a9-122">TOP</span><span class="sxs-lookup"><span data-stu-id="8d1a9-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
