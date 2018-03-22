---
title: INTERSECT (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 38814d3f4e8bca6a3a20d14c41d7674a205e30d2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="ff68c-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ff68c-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="ff68c-103">返回 INTERSECT 操作数左右两边的两个查询表达式均返回的所有非重复值的集合。</span><span class="sxs-lookup"><span data-stu-id="ff68c-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="ff68c-104">所有表达式都必须与 `expression`一样属于同一类型或属于公共基类型或派生类型。</span><span class="sxs-lookup"><span data-stu-id="ff68c-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff68c-105">语法</span><span class="sxs-lookup"><span data-stu-id="ff68c-105">Syntax</span></span>  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff68c-106">自变量</span><span class="sxs-lookup"><span data-stu-id="ff68c-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ff68c-107">返回一个集合以与从其他查询表达式返回的集合进行比较的任何有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="ff68c-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff68c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ff68c-108">Return Value</span></span>  
 <span data-ttu-id="ff68c-109">与 `expression`具有相同类型或属于公共基类型或派生类型的一个集合。</span><span class="sxs-lookup"><span data-stu-id="ff68c-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff68c-110">备注</span><span class="sxs-lookup"><span data-stu-id="ff68c-110">Remarks</span></span>  
 <span data-ttu-id="ff68c-111">INTERSECT 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="ff68c-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="ff68c-112">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="ff68c-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="ff68c-113">有关优先级信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符，请参阅[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="ff68c-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff68c-114">示例</span><span class="sxs-lookup"><span data-stu-id="ff68c-114">Example</span></span>  
 <span data-ttu-id="ff68c-115">以下 Entity SQL 查询使用 INTERSECT 运算符以返回 INTERSECT 操作数左右两边的两个查询表达式均返回的所有非重复值的集合。</span><span class="sxs-lookup"><span data-stu-id="ff68c-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="ff68c-116">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ff68c-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ff68c-117">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ff68c-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ff68c-118">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="ff68c-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ff68c-119">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ff68c-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="ff68c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff68c-120">See Also</span></span>  
 [<span data-ttu-id="ff68c-121">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ff68c-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
