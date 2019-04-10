---
title: '> （大于）(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: e1d13fa863eb79982d239f4e2dc298f7fcd1346f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328551"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="20c13-102">> （大于） (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="20c13-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="20c13-103">比较两个表达式以确定左侧表达式的值是否大于右侧表达式的值。</span><span class="sxs-lookup"><span data-stu-id="20c13-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c13-104">语法</span><span class="sxs-lookup"><span data-stu-id="20c13-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="20c13-105">自变量</span><span class="sxs-lookup"><span data-stu-id="20c13-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="20c13-106">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="20c13-106">Any valid expression.</span></span> <span data-ttu-id="20c13-107">两个表达式都必须具有可隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="20c13-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="20c13-108">结果类型</span><span class="sxs-lookup"><span data-stu-id="20c13-108">Result Types</span></span>  
 `true` <span data-ttu-id="20c13-109">如果左侧的表达式的值大于右侧的表达式;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="20c13-109">if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20c13-110">示例</span><span class="sxs-lookup"><span data-stu-id="20c13-110">Example</span></span>  
 <span data-ttu-id="20c13-111">下面的 Entity SQL 查询使用 > 比较运算符比较两个表达式，以确定左侧表达式的值是否大于右侧表达式的值。</span><span class="sxs-lookup"><span data-stu-id="20c13-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="20c13-112">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="20c13-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="20c13-113">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="20c13-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="20c13-114">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="20c13-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="20c13-115">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="20c13-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="20c13-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="20c13-116">See also</span></span>

- [<span data-ttu-id="20c13-117">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="20c13-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
