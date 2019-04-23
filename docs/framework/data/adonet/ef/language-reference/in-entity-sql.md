---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: d88f79dbfcd27f0ca0d1e26815d7d2bbee731bcf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331268"
---
# <a name="in-entity-sql"></a><span data-ttu-id="b15df-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b15df-102">IN (Entity SQL)</span></span>
<span data-ttu-id="b15df-103">确定某个值是否与某个集合中的任何值匹配。</span><span class="sxs-lookup"><span data-stu-id="b15df-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15df-104">语法</span><span class="sxs-lookup"><span data-stu-id="b15df-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b15df-105">自变量</span><span class="sxs-lookup"><span data-stu-id="b15df-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="b15df-106">返回匹配值的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="b15df-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="b15df-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="b15df-107">[ NOT ]</span></span>  
 <span data-ttu-id="b15df-108">指定对 IN 的 `Boolean` 结果取反。</span><span class="sxs-lookup"><span data-stu-id="b15df-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="b15df-109">返回集合以测试是否具有匹配的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="b15df-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="b15df-110">所有表达式都必须与 `value`一样属于同一类型或属于公共基类型或派生类型。</span><span class="sxs-lookup"><span data-stu-id="b15df-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b15df-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b15df-111">Return Value</span></span>  
 <span data-ttu-id="b15df-112">如果在集合中找到此值，则为 `true`；如果值为空或集合为空，则为空；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b15df-112">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="b15df-113">使用 NOT IN 可对 IN 的结果取反。</span><span class="sxs-lookup"><span data-stu-id="b15df-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b15df-114">示例</span><span class="sxs-lookup"><span data-stu-id="b15df-114">Example</span></span>  
 <span data-ttu-id="b15df-115">以下 Entity SQL 查询使用 IN 运算符以确定某个值是否与集合中的任何值匹配。</span><span class="sxs-lookup"><span data-stu-id="b15df-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="b15df-116">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="b15df-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b15df-117">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="b15df-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b15df-118">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="b15df-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b15df-119">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="b15df-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="b15df-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b15df-120">See also</span></span>

- [<span data-ttu-id="b15df-121">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="b15df-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
