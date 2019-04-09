---
title: '- （减）(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: d7eee2fdb8e61711b453f4f444cc8dc8d5a43558
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128825"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="e05b0-102">-（减）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e05b0-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="e05b0-103">两个数字相减。</span><span class="sxs-lookup"><span data-stu-id="e05b0-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e05b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="e05b0-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e05b0-105">自变量</span><span class="sxs-lookup"><span data-stu-id="e05b0-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e05b0-106">任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="e05b0-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e05b0-107">结果类型</span><span class="sxs-lookup"><span data-stu-id="e05b0-107">Result Types</span></span>  
 <span data-ttu-id="e05b0-108">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e05b0-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="e05b0-109">有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="e05b0-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e05b0-110">示例</span><span class="sxs-lookup"><span data-stu-id="e05b0-110">Example</span></span>  
 <span data-ttu-id="e05b0-111">以下 Entity SQL 查询使用 - 算术运算符将两个数字相减。</span><span class="sxs-lookup"><span data-stu-id="e05b0-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="e05b0-112">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="e05b0-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e05b0-113">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e05b0-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e05b0-114">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="e05b0-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e05b0-115">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="e05b0-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="e05b0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e05b0-116">See also</span></span>

- [<span data-ttu-id="e05b0-117">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="e05b0-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
