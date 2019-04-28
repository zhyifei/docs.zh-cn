---
title: + （添加）
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: 8ecbb7a8b38625f248dbfb5974bb8c64eb482ca2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605725"
---
# <a name="-add"></a><span data-ttu-id="fb6f5-102">+（添加）</span><span class="sxs-lookup"><span data-stu-id="fb6f5-102">+ (Add)</span></span>
<span data-ttu-id="fb6f5-103">将两个数相加。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb6f5-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb6f5-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb6f5-105">自变量</span><span class="sxs-lookup"><span data-stu-id="fb6f5-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="fb6f5-106">任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fb6f5-107">结果类型</span><span class="sxs-lookup"><span data-stu-id="fb6f5-107">Result Types</span></span>  
 <span data-ttu-id="fb6f5-108">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="fb6f5-109">有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb6f5-110">备注</span><span class="sxs-lookup"><span data-stu-id="fb6f5-110">Remarks</span></span>  
 <span data-ttu-id="fb6f5-111">对于 EDM.String 类型，加法指的是串联。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb6f5-112">示例</span><span class="sxs-lookup"><span data-stu-id="fb6f5-112">Example</span></span>  
 <span data-ttu-id="fb6f5-113">以下 Entity SQL 查询使用 + 算术运算符将两个数值相加。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="fb6f5-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fb6f5-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="fb6f5-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="fb6f5-116">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6f5-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="fb6f5-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="fb6f5-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="fb6f5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb6f5-118">See also</span></span>

- [<span data-ttu-id="fb6f5-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="fb6f5-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="fb6f5-120">概念模型类型 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="fb6f5-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
