---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 34eac0dfd28d39ec68f084ea10dd46693f44eea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248790"
---
# <a name="union-entity-sql"></a><span data-ttu-id="739a4-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="739a4-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="739a4-103">将两个或更多查询的结果组合成单个集合。</span><span class="sxs-lookup"><span data-stu-id="739a4-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="739a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="739a4-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="739a4-105">自变量</span><span class="sxs-lookup"><span data-stu-id="739a4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="739a4-106">返回一个集合以与该集合进行组合的任何有效查询表达式。所有表达式都必须与 `expression`一样属于同一类型或属于公共基类型或派生类型。</span><span class="sxs-lookup"><span data-stu-id="739a4-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="739a4-107">UNION</span><span class="sxs-lookup"><span data-stu-id="739a4-107">UNION</span></span>  
 <span data-ttu-id="739a4-108">指定组合多个集合并将其作为单个集合返回。</span><span class="sxs-lookup"><span data-stu-id="739a4-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="739a4-109">ALL</span><span class="sxs-lookup"><span data-stu-id="739a4-109">ALL</span></span>  
 <span data-ttu-id="739a4-110">指定组合多个集合并将其作为单个集合返回（包括重复项）。</span><span class="sxs-lookup"><span data-stu-id="739a4-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="739a4-111">如果未指定，则从结果集合中删除重复项。</span><span class="sxs-lookup"><span data-stu-id="739a4-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="739a4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="739a4-112">Return Value</span></span>  
 <span data-ttu-id="739a4-113">与 `expression`具有相同类型或属于公共基类型或派生类型的一个集合。</span><span class="sxs-lookup"><span data-stu-id="739a4-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="739a4-114">备注</span><span class="sxs-lookup"><span data-stu-id="739a4-114">Remarks</span></span>  
 <span data-ttu-id="739a4-115">UNION 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="739a4-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="739a4-116">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="739a4-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="739a4-117">有关[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符的优先级信息，请参阅[EXCEPT](except-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="739a4-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="739a4-118">示例</span><span class="sxs-lookup"><span data-stu-id="739a4-118">Example</span></span>  
 <span data-ttu-id="739a4-119">以下 Entity SQL 查询使用 UNION ALL 运算符以将两个查询的结果组合成单个集合。</span><span class="sxs-lookup"><span data-stu-id="739a4-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="739a4-120">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="739a4-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="739a4-121">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="739a4-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="739a4-122">[按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="739a4-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="739a4-123">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="739a4-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="739a4-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="739a4-124">See also</span></span>

- [<span data-ttu-id="739a4-125">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="739a4-125">Entity SQL Reference</span></span>](entity-sql-reference.md)
