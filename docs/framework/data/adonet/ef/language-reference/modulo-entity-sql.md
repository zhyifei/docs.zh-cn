---
title: （取模）（实体 SQL）
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: b08689b6f5b17950738c557e02f995fa85aeb35e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160480"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="124f1-102">（取模）（实体 SQL）</span><span class="sxs-lookup"><span data-stu-id="124f1-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="124f1-103">返回两个表达式相除后的余数。</span><span class="sxs-lookup"><span data-stu-id="124f1-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="124f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="124f1-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="124f1-105">自变量</span><span class="sxs-lookup"><span data-stu-id="124f1-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="124f1-106">被除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="124f1-106">The numeric expression to divide.</span></span> `dividend` <span data-ttu-id="124f1-107">为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="124f1-107">is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="124f1-108">除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="124f1-108">The numeric expression to divide the dividend by.</span></span> `divisor` <span data-ttu-id="124f1-109">为任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="124f1-109">is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="124f1-110">结果类型</span><span class="sxs-lookup"><span data-stu-id="124f1-110">Result Types</span></span>  
 <span data-ttu-id="124f1-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="124f1-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="124f1-112">示例</span><span class="sxs-lookup"><span data-stu-id="124f1-112">Example</span></span>  
 <span data-ttu-id="124f1-113">以下 Entity SQL 查询使用 % 算数运算符以返回两个表达式相除后的余数。</span><span class="sxs-lookup"><span data-stu-id="124f1-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="124f1-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="124f1-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="124f1-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="124f1-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="124f1-116">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="124f1-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="124f1-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="124f1-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="124f1-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="124f1-118">See also</span></span>

- [<span data-ttu-id="124f1-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="124f1-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
