---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: a5f469a89e86dcfbce4f3fcbc8dea09478522762
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177536"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="be206-103">!</span><span class="sxs-lookup"><span data-stu-id="be206-103">!</span></span> <span data-ttu-id="be206-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="be206-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="be206-105">对 `Boolean` 表达式求反。</span><span class="sxs-lookup"><span data-stu-id="be206-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be206-106">语法</span><span class="sxs-lookup"><span data-stu-id="be206-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="be206-107">自变量</span><span class="sxs-lookup"><span data-stu-id="be206-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="be206-108">返回 Boolean 的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="be206-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be206-109">备注</span><span class="sxs-lookup"><span data-stu-id="be206-109">Remarks</span></span>  
 <span data-ttu-id="be206-110">惊叹号 (!) 与 NOT 运算符具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="be206-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be206-111">示例</span><span class="sxs-lookup"><span data-stu-id="be206-111">Example</span></span>  
 <span data-ttu-id="be206-112">以下 Entity SQL 查询使用 NOT 运算符以对 `Boolean` 表达式求反。</span><span class="sxs-lookup"><span data-stu-id="be206-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="be206-113">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="be206-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="be206-114">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="be206-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="be206-115">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="be206-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="be206-116">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="be206-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="be206-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="be206-117">See also</span></span>

- [<span data-ttu-id="be206-118">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="be206-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
