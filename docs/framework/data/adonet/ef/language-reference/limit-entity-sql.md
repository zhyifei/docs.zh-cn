---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 945aec734f7e71c2a2f24c9bb3632030cede15ec
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826292"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="1def5-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1def5-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="1def5-103">在 ORDER BY 子句中使用 LIMIT 子子句可执行物理分页。</span><span class="sxs-lookup"><span data-stu-id="1def5-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="1def5-104">LIMIT 不能脱离 ORDER BY 子句单独使用。</span><span class="sxs-lookup"><span data-stu-id="1def5-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1def5-105">语法</span><span class="sxs-lookup"><span data-stu-id="1def5-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1def5-106">自变量</span><span class="sxs-lookup"><span data-stu-id="1def5-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="1def5-107">将选择的项的数量。</span><span class="sxs-lookup"><span data-stu-id="1def5-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="1def5-108">如果 ORDER BY 子句中存在 LIMIT 表达式子子句，则将根据排序规范对查询排序，并且结果行数将受到 LIMIT 表达式限制。</span><span class="sxs-lookup"><span data-stu-id="1def5-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="1def5-109">例如，LIMIT 5 将结果集限制为 5 个实例或行。</span><span class="sxs-lookup"><span data-stu-id="1def5-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="1def5-110">LIMIT 的功能与 TOP 相当，区别之处是 LIMIT 要求 ORDER BY 子句存在。</span><span class="sxs-lookup"><span data-stu-id="1def5-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="1def5-111">SKIP 和 LIMIT 可独立与 ORDER BY 子句一起使用。</span><span class="sxs-lookup"><span data-stu-id="1def5-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1def5-112">如果 TOP 修饰符和 SKIP 子子句出现在同一个查询表达式中，Entity SQL 查询将被视为无效。</span><span class="sxs-lookup"><span data-stu-id="1def5-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="1def5-113">应重写查询，将 TOP 表达式更改为 LIMIT 表达式。</span><span class="sxs-lookup"><span data-stu-id="1def5-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1def5-114">示例</span><span class="sxs-lookup"><span data-stu-id="1def5-114">Example</span></span>  
 <span data-ttu-id="1def5-115">下面的 Entity SQL 查询将 LIMIT 和 ORDER BY 运算符结合使用来指定用于 SELECT 语句所返回的对象的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="1def5-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="1def5-116">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="1def5-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1def5-117">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="1def5-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1def5-118">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="1def5-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="1def5-119">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="1def5-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="1def5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="1def5-120">See also</span></span>
- [<span data-ttu-id="1def5-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="1def5-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="1def5-122">[如何：页查看查询结果](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1def5-122">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="1def5-123">分页</span><span class="sxs-lookup"><span data-stu-id="1def5-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="1def5-124">TOP</span><span class="sxs-lookup"><span data-stu-id="1def5-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
