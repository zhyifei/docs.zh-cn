---
title: + （添加）
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: 62bb4782f135309eed8efa7e182fd8b75f92e126
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040295"
---
# <a name="-add"></a><span data-ttu-id="cc184-102">+（添加）</span><span class="sxs-lookup"><span data-stu-id="cc184-102">+ (Add)</span></span>
<span data-ttu-id="cc184-103">将两个数相加。</span><span class="sxs-lookup"><span data-stu-id="cc184-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc184-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc184-104">Syntax</span></span>  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc184-105">自变量</span><span class="sxs-lookup"><span data-stu-id="cc184-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cc184-106">任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="cc184-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cc184-107">结果类型</span><span class="sxs-lookup"><span data-stu-id="cc184-107">Result Types</span></span>  
 <span data-ttu-id="cc184-108">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cc184-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="cc184-109">有关隐式类型升级的详细信息，请参阅[类型系统](type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="cc184-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc184-110">备注</span><span class="sxs-lookup"><span data-stu-id="cc184-110">Remarks</span></span>  
 <span data-ttu-id="cc184-111">对于 EDM.String 类型，加法指的是串联。</span><span class="sxs-lookup"><span data-stu-id="cc184-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc184-112">示例</span><span class="sxs-lookup"><span data-stu-id="cc184-112">Example</span></span>  
 <span data-ttu-id="cc184-113">以下 Entity SQL 查询使用 + 算术运算符将两个数值相加。</span><span class="sxs-lookup"><span data-stu-id="cc184-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="cc184-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="cc184-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cc184-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="cc184-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cc184-116">执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="cc184-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="cc184-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="cc184-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="cc184-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc184-118">See also</span></span>

- [<span data-ttu-id="cc184-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="cc184-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="cc184-120">概念模型类型 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="cc184-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
