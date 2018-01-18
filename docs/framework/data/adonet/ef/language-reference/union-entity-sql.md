---
title: UNION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 067c3fedb1e03741158209751de9a13a00c23c35
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="union-entity-sql"></a><span data-ttu-id="d97ae-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d97ae-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="d97ae-103">将两个或更多查询的结果组合成单个集合。</span><span class="sxs-lookup"><span data-stu-id="d97ae-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d97ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="d97ae-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d97ae-105">自变量</span><span class="sxs-lookup"><span data-stu-id="d97ae-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d97ae-106">返回一个集合以与该集合进行组合的任何有效查询表达式。所有表达式都必须与 `expression`一样属于同一类型或属于公共基类型或派生类型。</span><span class="sxs-lookup"><span data-stu-id="d97ae-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="d97ae-107">UNION</span><span class="sxs-lookup"><span data-stu-id="d97ae-107">UNION</span></span>  
 <span data-ttu-id="d97ae-108">指定组合多个集合并将其作为单个集合返回。</span><span class="sxs-lookup"><span data-stu-id="d97ae-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="d97ae-109">ALL</span><span class="sxs-lookup"><span data-stu-id="d97ae-109">ALL</span></span>  
 <span data-ttu-id="d97ae-110">指定组合多个集合并将其作为单个集合返回（包括重复项）。</span><span class="sxs-lookup"><span data-stu-id="d97ae-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="d97ae-111">如果未指定，则从结果集合中删除重复项。</span><span class="sxs-lookup"><span data-stu-id="d97ae-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d97ae-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d97ae-112">Return Value</span></span>  
 <span data-ttu-id="d97ae-113">与 `expression`具有相同类型或属于公共基类型或派生类型的一个集合。</span><span class="sxs-lookup"><span data-stu-id="d97ae-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d97ae-114">备注</span><span class="sxs-lookup"><span data-stu-id="d97ae-114">Remarks</span></span>  
 <span data-ttu-id="d97ae-115">UNION 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="d97ae-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d97ae-116">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="d97ae-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d97ae-117">有关优先级信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符，请参阅[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="d97ae-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d97ae-118">示例</span><span class="sxs-lookup"><span data-stu-id="d97ae-118">Example</span></span>  
 <span data-ttu-id="d97ae-119">以下 Entity SQL 查询使用 UNION ALL 运算符以将两个查询的结果组合成单个集合。</span><span class="sxs-lookup"><span data-stu-id="d97ae-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="d97ae-120">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="d97ae-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d97ae-121">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="d97ae-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d97ae-122">执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="d97ae-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d97ae-123">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="d97ae-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="d97ae-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d97ae-124">See Also</span></span>  
 [<span data-ttu-id="d97ae-125">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="d97ae-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
