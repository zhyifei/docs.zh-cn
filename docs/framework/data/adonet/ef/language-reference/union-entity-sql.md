---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 736b92f7aac89c309b37a8ac61a295c8d1495d6b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323286"
---
# <a name="union-entity-sql"></a><span data-ttu-id="ff447-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ff447-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="ff447-103">将两个或更多查询的结果组合成单个集合。</span><span class="sxs-lookup"><span data-stu-id="ff447-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff447-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff447-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff447-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ff447-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ff447-106">返回一个集合以与该集合进行组合的任何有效查询表达式。所有表达式都必须与 `expression`一样属于同一类型或属于公共基类型或派生类型。</span><span class="sxs-lookup"><span data-stu-id="ff447-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="ff447-107">UNION</span><span class="sxs-lookup"><span data-stu-id="ff447-107">UNION</span></span>  
 <span data-ttu-id="ff447-108">指定组合多个集合并将其作为单个集合返回。</span><span class="sxs-lookup"><span data-stu-id="ff447-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="ff447-109">ALL</span><span class="sxs-lookup"><span data-stu-id="ff447-109">ALL</span></span>  
 <span data-ttu-id="ff447-110">指定组合多个集合并将其作为单个集合返回（包括重复项）。</span><span class="sxs-lookup"><span data-stu-id="ff447-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="ff447-111">如果未指定，则从结果集合中删除重复项。</span><span class="sxs-lookup"><span data-stu-id="ff447-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff447-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ff447-112">Return Value</span></span>  
 <span data-ttu-id="ff447-113">与 `expression`具有相同类型或属于公共基类型或派生类型的一个集合。</span><span class="sxs-lookup"><span data-stu-id="ff447-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff447-114">备注</span><span class="sxs-lookup"><span data-stu-id="ff447-114">Remarks</span></span>  
 <span data-ttu-id="ff447-115">UNION 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="ff447-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="ff447-116">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="ff447-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="ff447-117">有关优先级信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符，请参阅[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="ff447-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff447-118">示例</span><span class="sxs-lookup"><span data-stu-id="ff447-118">Example</span></span>  
 <span data-ttu-id="ff447-119">以下 Entity SQL 查询使用 UNION ALL 运算符以将两个查询的结果组合成单个集合。</span><span class="sxs-lookup"><span data-stu-id="ff447-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="ff447-120">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ff447-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ff447-121">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ff447-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ff447-122">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="ff447-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ff447-123">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ff447-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="ff447-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff447-124">See also</span></span>

- [<span data-ttu-id="ff447-125">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ff447-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
