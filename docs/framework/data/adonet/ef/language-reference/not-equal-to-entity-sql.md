---
title: '!=（不等于）(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: 3d6e391e708b81c45af82280f200aebdaef41421
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130959"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="ed7fb-102">!=（不等于）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ed7fb-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="ed7fb-103">比较两个表达式以确定左侧表达式是否不等于右侧表达式。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="ed7fb-104">!=（不等于）运算符在功能上等效于 <> 运算符。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7fb-105">语法</span><span class="sxs-lookup"><span data-stu-id="ed7fb-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ed7fb-106">自变量</span><span class="sxs-lookup"><span data-stu-id="ed7fb-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ed7fb-107">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-107">Any valid expression.</span></span> <span data-ttu-id="ed7fb-108">两个表达式都必须具有可隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ed7fb-109">结果类型</span><span class="sxs-lookup"><span data-stu-id="ed7fb-109">Result Types</span></span>  
 `true` <span data-ttu-id="ed7fb-110">如果左侧的表达式是否不等于右侧表达式;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-110">if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed7fb-111">示例</span><span class="sxs-lookup"><span data-stu-id="ed7fb-111">Example</span></span>  
 <span data-ttu-id="ed7fb-112">下面的 Entity SQL 查询使用 != 运算符比较两个表达式，以确定左侧表达式是否不等于右侧表达式。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="ed7fb-113">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ed7fb-114">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ed7fb-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ed7fb-115">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7fb-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ed7fb-116">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ed7fb-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="ed7fb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed7fb-117">See also</span></span>

- [<span data-ttu-id="ed7fb-118">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ed7fb-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
