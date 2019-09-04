---
title: '- 拆分（实体 SQL）'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: d4e4c1449b665e6dea22bfcc0ee2277478b4da1a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251051"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="c2efc-102">/（除）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c2efc-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="c2efc-103">一个数字除另一个数字。</span><span class="sxs-lookup"><span data-stu-id="c2efc-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2efc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2efc-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2efc-105">自变量</span><span class="sxs-lookup"><span data-stu-id="c2efc-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="c2efc-106">被除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c2efc-106">The numeric expression to divide.</span></span> <span data-ttu-id="c2efc-107">`dividend` 为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="c2efc-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="c2efc-108">除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c2efc-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="c2efc-109">`divisor` 为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="c2efc-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c2efc-110">结果类型</span><span class="sxs-lookup"><span data-stu-id="c2efc-110">Result Types</span></span>  
 <span data-ttu-id="c2efc-111">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c2efc-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="c2efc-112">有关隐式类型升级的详细信息，请参阅[类型系统](type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="c2efc-112">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2efc-113">示例</span><span class="sxs-lookup"><span data-stu-id="c2efc-113">Example</span></span>  
 <span data-ttu-id="c2efc-114">以下实体 SQL 查询使用/算术运算符将一个数除以另一个数。</span><span class="sxs-lookup"><span data-stu-id="c2efc-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="c2efc-115">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="c2efc-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c2efc-116">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="c2efc-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c2efc-117">[按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="c2efc-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c2efc-118">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="c2efc-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="c2efc-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2efc-119">See also</span></span>

- [<span data-ttu-id="c2efc-120">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="c2efc-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
