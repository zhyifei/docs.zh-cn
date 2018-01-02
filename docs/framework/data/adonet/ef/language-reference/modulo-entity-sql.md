---
title: "（取模）（实体 SQL）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a04b2972c80aff654331aeb319390b6f817374bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="65672-102">（取模）（实体 SQL）</span><span class="sxs-lookup"><span data-stu-id="65672-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="65672-103">返回两个表达式相除后的余数。</span><span class="sxs-lookup"><span data-stu-id="65672-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65672-104">语法</span><span class="sxs-lookup"><span data-stu-id="65672-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="65672-105">自变量</span><span class="sxs-lookup"><span data-stu-id="65672-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="65672-106">被除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="65672-106">The numeric expression to divide.</span></span> <span data-ttu-id="65672-107">`dividend` 为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="65672-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="65672-108">除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="65672-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="65672-109">`divisor` 为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="65672-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="65672-110">结果类型</span><span class="sxs-lookup"><span data-stu-id="65672-110">Result Types</span></span>  
 <span data-ttu-id="65672-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="65672-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="65672-112">示例</span><span class="sxs-lookup"><span data-stu-id="65672-112">Example</span></span>  
 <span data-ttu-id="65672-113">以下 Entity SQL 查询使用 % 算数运算符以返回两个表达式相除后的余数。</span><span class="sxs-lookup"><span data-stu-id="65672-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="65672-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="65672-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="65672-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="65672-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="65672-116">执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="65672-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="65672-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="65672-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="65672-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="65672-118">See Also</span></span>  
 [<span data-ttu-id="65672-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="65672-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
