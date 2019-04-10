---
title: < （小于） (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 1ca1cbdf1282782295b659393e8f54aae3ec5649
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320439"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="f1cd7-102">\<（小于）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f1cd7-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="f1cd7-103">比较两个表达式以确定左侧表达式的值是否小于右侧表达式的值。</span><span class="sxs-lookup"><span data-stu-id="f1cd7-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1cd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1cd7-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1cd7-105">自变量</span><span class="sxs-lookup"><span data-stu-id="f1cd7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f1cd7-106">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="f1cd7-106">Any valid expression.</span></span> <span data-ttu-id="f1cd7-107">两个表达式都必须具有可隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f1cd7-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f1cd7-108">结果类型</span><span class="sxs-lookup"><span data-stu-id="f1cd7-108">Result Types</span></span>  
 `true` <span data-ttu-id="f1cd7-109">如果左侧的表达式的值小于右侧表达式;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f1cd7-109">if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1cd7-110">示例</span><span class="sxs-lookup"><span data-stu-id="f1cd7-110">Example</span></span>  
 <span data-ttu-id="f1cd7-111">下面的 Entity SQL 查询使用 < 比较运算符比较两个表达式，以确定左侧表达式的值是否小于右侧表达式的值。</span><span class="sxs-lookup"><span data-stu-id="f1cd7-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="f1cd7-112">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="f1cd7-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f1cd7-113">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="f1cd7-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f1cd7-114">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="f1cd7-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f1cd7-115">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="f1cd7-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="f1cd7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1cd7-116">See also</span></span>

- [<span data-ttu-id="f1cd7-117">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="f1cd7-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
