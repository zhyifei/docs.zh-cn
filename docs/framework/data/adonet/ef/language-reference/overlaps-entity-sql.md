---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: 9d909fb7efbb29619351cfc866b0f84381d0b80b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319633"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="1b355-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1b355-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="1b355-103">确定两个集合是否具有公共元素。</span><span class="sxs-lookup"><span data-stu-id="1b355-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b355-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b355-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b355-105">自变量</span><span class="sxs-lookup"><span data-stu-id="1b355-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1b355-106">返回一个集合以与从其他查询表达式返回的集合进行比较的任何有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="1b355-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="1b355-107">所有表达式都必须与 `expression`一样属于同一类型或属于公共基类型或派生类型。</span><span class="sxs-lookup"><span data-stu-id="1b355-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b355-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1b355-108">Return Value</span></span>  
 <span data-ttu-id="1b355-109">如果两个集合具有公共元素，则为`true` ；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1b355-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b355-110">备注</span><span class="sxs-lookup"><span data-stu-id="1b355-110">Remarks</span></span>  
 <span data-ttu-id="1b355-111">OVERLAPS 提供的功能等效于以下：</span><span class="sxs-lookup"><span data-stu-id="1b355-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="1b355-112">OVERLAPS 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="1b355-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="1b355-113">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="1b355-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="1b355-114">有关优先级信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符，请参阅[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="1b355-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b355-115">示例</span><span class="sxs-lookup"><span data-stu-id="1b355-115">Example</span></span>  
 <span data-ttu-id="1b355-116">以下 Entity SQL 查询使用 OVERLAPS 运算符以确定两个集合是否具有公共值。</span><span class="sxs-lookup"><span data-stu-id="1b355-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="1b355-117">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="1b355-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1b355-118">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="1b355-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="1b355-119">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="1b355-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1b355-120">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="1b355-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="1b355-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b355-121">See also</span></span>

- [<span data-ttu-id="1b355-122">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="1b355-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
