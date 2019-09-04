---
title: =（等于）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: ec87ec682e1773c001c225567a35b3cedc9c5aba
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251007"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="9c69d-102">=（等于）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9c69d-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="9c69d-103">比较两个表达式是否相等。</span><span class="sxs-lookup"><span data-stu-id="9c69d-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c69d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c69d-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c69d-105">自变量</span><span class="sxs-lookup"><span data-stu-id="9c69d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9c69d-106">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="9c69d-106">Any valid expression.</span></span> <span data-ttu-id="9c69d-107">两个表达式都必须具有可隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9c69d-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9c69d-108">结果类型</span><span class="sxs-lookup"><span data-stu-id="9c69d-108">Result Types</span></span>  
 <span data-ttu-id="9c69d-109">如果左侧表达式等于右侧表达式，则为`true` ；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="9c69d-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c69d-110">备注</span><span class="sxs-lookup"><span data-stu-id="9c69d-110">Remarks</span></span>  
 <span data-ttu-id="9c69d-111">== 运算符等效于 =。</span><span class="sxs-lookup"><span data-stu-id="9c69d-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c69d-112">示例</span><span class="sxs-lookup"><span data-stu-id="9c69d-112">Example</span></span>  
 <span data-ttu-id="9c69d-113">下面的 Entity SQL 查询使用 = 比较运算符比较两个表达式是否相等。</span><span class="sxs-lookup"><span data-stu-id="9c69d-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="9c69d-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="9c69d-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9c69d-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9c69d-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9c69d-116">[按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="9c69d-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="9c69d-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="9c69d-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="9c69d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c69d-118">See also</span></span>

- [<span data-ttu-id="9c69d-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="9c69d-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
