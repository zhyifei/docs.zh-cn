---
title: '&amp;&amp; （和）（实体 SQL）'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: be6e7120e6c19714f151aa38a8b9a1355de29d1a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039956"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="459b6-102">&amp;&amp; （和）（实体 SQL）</span><span class="sxs-lookup"><span data-stu-id="459b6-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="459b6-103">如果两个表达式均为 `true` ，则返回 `true`；否则，返回 `false` 或 `NULL`。</span><span class="sxs-lookup"><span data-stu-id="459b6-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="459b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="459b6-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```
 
<span data-ttu-id="459b6-105">或</span><span class="sxs-lookup"><span data-stu-id="459b6-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="459b6-106">自变量</span><span class="sxs-lookup"><span data-stu-id="459b6-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="459b6-107">返回 Boolean 的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="459b6-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="459b6-108">备注</span><span class="sxs-lookup"><span data-stu-id="459b6-108">Remarks</span></span>  
 <span data-ttu-id="459b6-109">双“与”符号 (&&) 与 AND 运算符具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="459b6-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="459b6-110">下表显示可能的输入值和返回类型。</span><span class="sxs-lookup"><span data-stu-id="459b6-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="459b6-111">true</span><span class="sxs-lookup"><span data-stu-id="459b6-111">TRUE</span></span>|<span data-ttu-id="459b6-112">false</span><span class="sxs-lookup"><span data-stu-id="459b6-112">FALSE</span></span>|<span data-ttu-id="459b6-113">NULL</span><span class="sxs-lookup"><span data-stu-id="459b6-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="459b6-114">false</span><span class="sxs-lookup"><span data-stu-id="459b6-114">FALSE</span></span>|<span data-ttu-id="459b6-115">false</span><span class="sxs-lookup"><span data-stu-id="459b6-115">FALSE</span></span>|<span data-ttu-id="459b6-116">false</span><span class="sxs-lookup"><span data-stu-id="459b6-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="459b6-117">NULL</span><span class="sxs-lookup"><span data-stu-id="459b6-117">NULL</span></span>|<span data-ttu-id="459b6-118">false</span><span class="sxs-lookup"><span data-stu-id="459b6-118">FALSE</span></span>|<span data-ttu-id="459b6-119">NULL</span><span class="sxs-lookup"><span data-stu-id="459b6-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="459b6-120">示例</span><span class="sxs-lookup"><span data-stu-id="459b6-120">Example</span></span>  
 <span data-ttu-id="459b6-121">以下 Entity SQL 查询演示如何使用 AND 运算符。</span><span class="sxs-lookup"><span data-stu-id="459b6-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="459b6-122">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="459b6-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="459b6-123">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="459b6-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="459b6-124">执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="459b6-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="459b6-125">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="459b6-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="459b6-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="459b6-126">See also</span></span>

- [<span data-ttu-id="459b6-127">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="459b6-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
