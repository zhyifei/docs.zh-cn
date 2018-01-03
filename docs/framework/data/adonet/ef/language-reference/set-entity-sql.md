---
title: SET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 12ce6c47db89fe91fd11a94aa10a47b57b45d736
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="set-entity-sql"></a><span data-ttu-id="fedcc-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fedcc-102">SET (Entity SQL)</span></span>
<span data-ttu-id="fedcc-103">SET 表达式用于通过生成一个新集合（其中移除了所有重复元素）将对象集合转换为一个集。</span><span class="sxs-lookup"><span data-stu-id="fedcc-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fedcc-104">语法</span><span class="sxs-lookup"><span data-stu-id="fedcc-104">Syntax</span></span>  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="fedcc-105">自变量</span><span class="sxs-lookup"><span data-stu-id="fedcc-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="fedcc-106">任何返回集合的有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="fedcc-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fedcc-107">备注</span><span class="sxs-lookup"><span data-stu-id="fedcc-107">Remarks</span></span>  
 <span data-ttu-id="fedcc-108">SET 表达式 `SET(c)` 在逻辑上等效于以下 select 语句：</span><span class="sxs-lookup"><span data-stu-id="fedcc-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="fedcc-109">`SET` 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="fedcc-109">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="fedcc-110">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="fedcc-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="fedcc-111">请参阅[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)有关优先级信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符。</span><span class="sxs-lookup"><span data-stu-id="fedcc-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fedcc-112">示例</span><span class="sxs-lookup"><span data-stu-id="fedcc-112">Example</span></span>  
 <span data-ttu-id="fedcc-113">以下 Entity SQL 查询使用 SET 表达式将一个对象集合转换为一个集。</span><span class="sxs-lookup"><span data-stu-id="fedcc-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="fedcc-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="fedcc-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fedcc-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="fedcc-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="fedcc-116">按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="fedcc-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="fedcc-117">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="fedcc-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a><span data-ttu-id="fedcc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="fedcc-118">See Also</span></span>  
 [<span data-ttu-id="fedcc-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="fedcc-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
