---
title: '- （减）(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: a2f92fa4ad994885a5089b9f8af8a9baf9209b4d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="6cd37-102">-（减）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6cd37-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="6cd37-103">两个数字相减。</span><span class="sxs-lookup"><span data-stu-id="6cd37-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd37-104">语法</span><span class="sxs-lookup"><span data-stu-id="6cd37-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6cd37-105">自变量</span><span class="sxs-lookup"><span data-stu-id="6cd37-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6cd37-106">任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="6cd37-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6cd37-107">结果类型</span><span class="sxs-lookup"><span data-stu-id="6cd37-107">Result Types</span></span>  
 <span data-ttu-id="6cd37-108">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="6cd37-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="6cd37-109">有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="6cd37-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cd37-110">示例</span><span class="sxs-lookup"><span data-stu-id="6cd37-110">Example</span></span>  
 <span data-ttu-id="6cd37-111">以下 Entity SQL 查询使用 - 算术运算符将两个数字相减。</span><span class="sxs-lookup"><span data-stu-id="6cd37-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="6cd37-112">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="6cd37-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6cd37-113">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="6cd37-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="6cd37-114">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="6cd37-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="6cd37-115">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="6cd37-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="6cd37-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cd37-116">See Also</span></span>  
 [<span data-ttu-id="6cd37-117">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="6cd37-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
