---
title: "!=（不等于）(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 81643b9a4a1cd49e950010c0023b27108d34180c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="ec484-102">!=（不等于）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ec484-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="ec484-103">比较两个表达式以确定左侧表达式是否不等于右侧表达式。</span><span class="sxs-lookup"><span data-stu-id="ec484-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="ec484-104">!=（不等于）运算符在功能上等效于 <> 运算符。</span><span class="sxs-lookup"><span data-stu-id="ec484-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec484-105">语法</span><span class="sxs-lookup"><span data-stu-id="ec484-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec484-106">自变量</span><span class="sxs-lookup"><span data-stu-id="ec484-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ec484-107">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="ec484-107">Any valid expression.</span></span> <span data-ttu-id="ec484-108">两个表达式都必须具有可隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ec484-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ec484-109">结果类型</span><span class="sxs-lookup"><span data-stu-id="ec484-109">Result Types</span></span>  
 <span data-ttu-id="ec484-110">如果左侧表达式不等于右侧表达式，则为`true` ；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ec484-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec484-111">示例</span><span class="sxs-lookup"><span data-stu-id="ec484-111">Example</span></span>  
 <span data-ttu-id="ec484-112">下面的 Entity SQL 查询使用 != 运算符比较两个表达式，以确定左侧表达式是否不等于右侧表达式。</span><span class="sxs-lookup"><span data-stu-id="ec484-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="ec484-113">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ec484-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ec484-114">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ec484-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ec484-115">执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="ec484-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ec484-116">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ec484-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="ec484-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec484-117">See Also</span></span>  
 [<span data-ttu-id="ec484-118">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ec484-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
