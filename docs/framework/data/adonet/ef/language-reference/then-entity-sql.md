---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: 8d2d7f9a3a1d6ff9f25db3f19bf8f39781469f9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305619"
---
# <a name="then-entity-sql"></a><span data-ttu-id="11edf-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="11edf-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="11edf-103">当 WHEN 子句取值为 `true`时的结果。</span><span class="sxs-lookup"><span data-stu-id="11edf-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11edf-104">语法</span><span class="sxs-lookup"><span data-stu-id="11edf-104">Syntax</span></span>  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="11edf-105">自变量</span><span class="sxs-lookup"><span data-stu-id="11edf-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="11edf-106">任何有效的 Boolean 表达式。</span><span class="sxs-lookup"><span data-stu-id="11edf-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="11edf-107">任何返回集合的有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="11edf-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11edf-108">备注</span><span class="sxs-lookup"><span data-stu-id="11edf-108">Remarks</span></span>  
 <span data-ttu-id="11edf-109">如果 `when_expression` 取值为 `true`，则结果为对应的 `then-expression`。</span><span class="sxs-lookup"><span data-stu-id="11edf-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="11edf-110">如果任何 WHEN 条件均未得以满足，将求出 `else-expression` 的值。</span><span class="sxs-lookup"><span data-stu-id="11edf-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="11edf-111">然而，如果没有 `else-expression`，则结果为空值。</span><span class="sxs-lookup"><span data-stu-id="11edf-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="11edf-112">有关示例，请参阅[用例](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="11edf-112">For an example, see [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11edf-113">示例</span><span class="sxs-lookup"><span data-stu-id="11edf-113">Example</span></span>  
 <span data-ttu-id="11edf-114">以下 Entity SQL 查询使用 CASE 表达式计算一组 `Boolean` 表达式的值。</span><span class="sxs-lookup"><span data-stu-id="11edf-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="11edf-115">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="11edf-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="11edf-116">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="11edf-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="11edf-117">按照中的过程[如何：执行返回 PrimitiveType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="11edf-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="11edf-118">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="11edf-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="11edf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="11edf-119">See also</span></span>

- [<span data-ttu-id="11edf-120">CASE</span><span class="sxs-lookup"><span data-stu-id="11edf-120">CASE</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)
- [<span data-ttu-id="11edf-121">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="11edf-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
