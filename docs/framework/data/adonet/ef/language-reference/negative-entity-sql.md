---
title: '- （负号）(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: f33b672ecd635234b8a8859651d117aabdaf14d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745842"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="87a0a-102">-（负号）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="87a0a-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="87a0a-103">返回数值表达式的值的负值。</span><span class="sxs-lookup"><span data-stu-id="87a0a-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="87a0a-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="87a0a-105">自变量</span><span class="sxs-lookup"><span data-stu-id="87a0a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="87a0a-106">任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="87a0a-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="87a0a-107">结果类型</span><span class="sxs-lookup"><span data-stu-id="87a0a-107">Result Types</span></span>  
 <span data-ttu-id="87a0a-108">`expression`的数据类型。</span><span class="sxs-lookup"><span data-stu-id="87a0a-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87a0a-109">备注</span><span class="sxs-lookup"><span data-stu-id="87a0a-109">Remarks</span></span>  
 <span data-ttu-id="87a0a-110">如果 `expression` 为无符号类型，则结果类型将是与 `expression`的类型相关性最密切的有符号类型。</span><span class="sxs-lookup"><span data-stu-id="87a0a-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="87a0a-111">例如，如果 `expression` 属于 Byte 类型，则将返回类型为 Int16 的值。</span><span class="sxs-lookup"><span data-stu-id="87a0a-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a0a-112">示例</span><span class="sxs-lookup"><span data-stu-id="87a0a-112">Example</span></span>  
 <span data-ttu-id="87a0a-113">以下 Entity SQL 查询使用 - 算数运算符以返回数值表达式的值的负值。</span><span class="sxs-lookup"><span data-stu-id="87a0a-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="87a0a-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="87a0a-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="87a0a-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="87a0a-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="87a0a-116">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="87a0a-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="87a0a-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="87a0a-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="87a0a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="87a0a-118">See also</span></span>
- [<span data-ttu-id="87a0a-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="87a0a-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
