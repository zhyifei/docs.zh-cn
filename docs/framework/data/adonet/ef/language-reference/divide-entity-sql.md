---
title: '- （除）(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 506553de78ce9fbdf5f3710805906ee8cd5b8757
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760435"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="b0ba9-102">/（除）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b0ba9-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="b0ba9-103">一个数字除另一个数字。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ba9-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0ba9-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="b0ba9-105">自变量</span><span class="sxs-lookup"><span data-stu-id="b0ba9-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="b0ba9-106">被除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-106">The numeric expression to divide.</span></span> <span data-ttu-id="b0ba9-107">`dividend` 为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="b0ba9-108">除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="b0ba9-109">`divisor` 为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b0ba9-110">结果类型</span><span class="sxs-lookup"><span data-stu-id="b0ba9-110">Result Types</span></span>  
 <span data-ttu-id="b0ba9-111">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="b0ba9-112">有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0ba9-113">示例</span><span class="sxs-lookup"><span data-stu-id="b0ba9-113">Example</span></span>  
 <span data-ttu-id="b0ba9-114">以下 Entity SQL 查询使用 / 算术运算符将两个数值相除。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-114">The following Entity SQL query uses the / arithmetic operator to divide one numer by another.</span></span> <span data-ttu-id="b0ba9-115">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b0ba9-116">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="b0ba9-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b0ba9-117">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="b0ba9-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b0ba9-118">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="b0ba9-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="b0ba9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0ba9-119">See Also</span></span>  
 [<span data-ttu-id="b0ba9-120">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="b0ba9-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
