---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 44f128a292b013fd3a3a80efdd2d10a63e3cfb07
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833839"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="66177-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="66177-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="66177-103">确定集合是否为空。</span><span class="sxs-lookup"><span data-stu-id="66177-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66177-104">语法</span><span class="sxs-lookup"><span data-stu-id="66177-104">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="66177-105">参数</span><span class="sxs-lookup"><span data-stu-id="66177-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="66177-106">返回集合的任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="66177-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="66177-107">NOT</span><span class="sxs-lookup"><span data-stu-id="66177-107">NOT</span></span>  
 <span data-ttu-id="66177-108">指定对 EXISTS 的结果取反。</span><span class="sxs-lookup"><span data-stu-id="66177-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66177-109">返回值</span><span class="sxs-lookup"><span data-stu-id="66177-109">Return Value</span></span>  
 <span data-ttu-id="66177-110">如果集合不为空，则为 `true`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="66177-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66177-111">备注</span><span class="sxs-lookup"><span data-stu-id="66177-111">Remarks</span></span>  
 <span data-ttu-id="66177-112">EXISTS 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="66177-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="66177-113">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="66177-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="66177-114">有关 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符的优先级信息，请参阅[EXCEPT](except-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="66177-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66177-115">示例</span><span class="sxs-lookup"><span data-stu-id="66177-115">Example</span></span>  
 <span data-ttu-id="66177-116">以下 Entity SQL 查询使用 EXISTS 运算符以确定集合是否为空。</span><span class="sxs-lookup"><span data-stu-id="66177-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="66177-117">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="66177-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="66177-118">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="66177-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="66177-119">按照 [How 中的过程执行以下操作：执行返回 StructuralType Results @ no__t-0 的查询。</span><span class="sxs-lookup"><span data-stu-id="66177-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="66177-120">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="66177-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="66177-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="66177-121">See also</span></span>

- [<span data-ttu-id="66177-122">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="66177-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
