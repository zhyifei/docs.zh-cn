---
title: "&amp;&amp;（和）(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e7255110a9118c3a31c84e3262fd5b1490d546e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="ae2f3-102">&amp;&amp;（和）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ae2f3-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="ae2f3-103">如果两个表达式均为 `true` ，则返回 `true`；否则，返回 `false` 或 `NULL`。</span><span class="sxs-lookup"><span data-stu-id="ae2f3-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae2f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae2f3-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae2f3-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ae2f3-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="ae2f3-106">返回 Boolean 的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="ae2f3-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae2f3-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae2f3-107">Remarks</span></span>  
 <span data-ttu-id="ae2f3-108">双“与”符号 (&&) 与 AND 运算符具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ae2f3-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="ae2f3-109">下表显示可能的输入值和返回类型。</span><span class="sxs-lookup"><span data-stu-id="ae2f3-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="ae2f3-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="ae2f3-110">TRUE</span></span>|<span data-ttu-id="ae2f3-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="ae2f3-111">FALSE</span></span>|<span data-ttu-id="ae2f3-112">NULL</span><span class="sxs-lookup"><span data-stu-id="ae2f3-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="ae2f3-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="ae2f3-113">FALSE</span></span>|<span data-ttu-id="ae2f3-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="ae2f3-114">FALSE</span></span>|<span data-ttu-id="ae2f3-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="ae2f3-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="ae2f3-116">NULL</span><span class="sxs-lookup"><span data-stu-id="ae2f3-116">NULL</span></span>|<span data-ttu-id="ae2f3-117">false</span><span class="sxs-lookup"><span data-stu-id="ae2f3-117">FALSE</span></span>|<span data-ttu-id="ae2f3-118">NULL</span><span class="sxs-lookup"><span data-stu-id="ae2f3-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ae2f3-119">示例</span><span class="sxs-lookup"><span data-stu-id="ae2f3-119">Example</span></span>  
 <span data-ttu-id="ae2f3-120">以下 Entity SQL 查询演示如何使用 AND 运算符。</span><span class="sxs-lookup"><span data-stu-id="ae2f3-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="ae2f3-121">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ae2f3-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ae2f3-122">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ae2f3-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ae2f3-123">执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="ae2f3-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ae2f3-124">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ae2f3-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="ae2f3-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae2f3-125">See Also</span></span>  
 [<span data-ttu-id="ae2f3-126">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ae2f3-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
