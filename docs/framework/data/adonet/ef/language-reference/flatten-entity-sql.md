---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 75463ed622ac969eb2690c4118861823479a2caa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760565"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="e108e-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e108e-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="e108e-103">将一个由多个集合组成的集合转换为一个平展集合。</span><span class="sxs-lookup"><span data-stu-id="e108e-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="e108e-104">新集合与旧集合包含所有相同的元素，但没有嵌套结构。</span><span class="sxs-lookup"><span data-stu-id="e108e-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e108e-105">语法</span><span class="sxs-lookup"><span data-stu-id="e108e-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="e108e-106">自变量</span><span class="sxs-lookup"><span data-stu-id="e108e-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="e108e-107">任何有效的表达式，该表达式返回一个由值集合组成的集合以平展为单个集合。</span><span class="sxs-lookup"><span data-stu-id="e108e-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e108e-108">备注</span><span class="sxs-lookup"><span data-stu-id="e108e-108">Remarks</span></span>  
 <span data-ttu-id="e108e-109">`FLATTEN` 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="e108e-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="e108e-110">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="e108e-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="e108e-111">请参阅[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)有关优先级信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符。</span><span class="sxs-lookup"><span data-stu-id="e108e-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e108e-112">示例</span><span class="sxs-lookup"><span data-stu-id="e108e-112">Example</span></span>  
 <span data-ttu-id="e108e-113">以下 Entity SQL 查询使用 `FLATTEN` 运算符以将一个由多个集合组成的集合转换为一个平展集合。</span><span class="sxs-lookup"><span data-stu-id="e108e-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="e108e-114">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e108e-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e108e-115">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="e108e-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e108e-116">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="e108e-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="e108e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e108e-117">See Also</span></span>  
 [<span data-ttu-id="e108e-118">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="e108e-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
