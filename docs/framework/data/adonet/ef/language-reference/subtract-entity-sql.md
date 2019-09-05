---
title: '- 减去（实体 SQL）'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 8b5cfee4c82757e55babdf1ad14f6cf3c743a5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249018"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="96734-102">-（减）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="96734-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="96734-103">两个数字相减。</span><span class="sxs-lookup"><span data-stu-id="96734-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96734-104">语法</span><span class="sxs-lookup"><span data-stu-id="96734-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="96734-105">自变量</span><span class="sxs-lookup"><span data-stu-id="96734-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="96734-106">任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="96734-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="96734-107">结果类型</span><span class="sxs-lookup"><span data-stu-id="96734-107">Result Types</span></span>  
 <span data-ttu-id="96734-108">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="96734-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="96734-109">有关隐式类型升级的详细信息，请参阅[类型系统](type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="96734-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96734-110">示例</span><span class="sxs-lookup"><span data-stu-id="96734-110">Example</span></span>  
 <span data-ttu-id="96734-111">以下 Entity SQL 查询使用 - 算术运算符将两个数字相减。</span><span class="sxs-lookup"><span data-stu-id="96734-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="96734-112">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="96734-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="96734-113">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="96734-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="96734-114">[按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="96734-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="96734-115">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="96734-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="96734-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="96734-116">See also</span></span>

- [<span data-ttu-id="96734-117">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="96734-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
