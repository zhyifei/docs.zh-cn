---
title: CASE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: df86e69684a111effc29a2663d18310b276f4b83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="case-entity-sql"></a><span data-ttu-id="9bd4f-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9bd4f-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="9bd4f-103">求出一组 `Boolean` 表达式的值以确定结果。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bd4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bd4f-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="9bd4f-105">自变量</span><span class="sxs-lookup"><span data-stu-id="9bd4f-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="9bd4f-106">一个占位符，表明可以使用多个 WHEN `Boolean_expression` THEN `result_expression` 子句。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="9bd4f-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="9bd4f-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="9bd4f-108">作为在 `Boolean_expression` 的计算结果为 `true`时返回的表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="9bd4f-109">`result expression` 是任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="9bd4f-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="9bd4f-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="9bd4f-111">比较运算的结果都不为 `true`时返回的表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="9bd4f-112">如果忽略此参数且比较运算计算的结果不为 `true`，CASE 将返回空值。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="9bd4f-113">`else_result_expression` 是任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="9bd4f-114">`else_result_expression` 及任何 `result_expression` 的数据类型必须相同或必须是隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="9bd4f-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="9bd4f-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="9bd4f-116">使用 CASE 搜索格式时所计算的 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="9bd4f-117">`Boolean_expression` 是任何有效的 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bd4f-118">返回值</span><span class="sxs-lookup"><span data-stu-id="9bd4f-118">Return Value</span></span>  
 <span data-ttu-id="9bd4f-119">从 `result_expression` 和可选 `else_result_expression`的类型集中返回优先级最高的类型。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bd4f-120">备注</span><span class="sxs-lookup"><span data-stu-id="9bd4f-120">Remarks</span></span>  
 <span data-ttu-id="9bd4f-121">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] case 表达式类似于 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case 表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="9bd4f-122">可以使用 case 表达式进行一系列条件测试，以确定哪个表达式将产生正确的结果。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="9bd4f-123">这种格式的 case 表达式应用于由一个或多个 `Boolean` 表达式组成的一组表达式，以确定正确的结果表达式。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="9bd4f-124">CASE 函数以指定的顺序为每个 WHEN 子句计算 `Boolean_expression` 的值，然后返回首个满足 `result_expression` = `Boolean_expression` 的 `true`。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="9bd4f-125">而不对剩下的表达式求值。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="9bd4f-126">如果没有任何 `Boolean_expression` 的计算结果为 `true`，则当指定了 ELSE 子句时，数据库引擎将返回 `else_result_expression` ；如果未指定 ELSE 子句，则返回空值。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="9bd4f-127">CASE 语句不会返回 multiset 类型。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bd4f-128">示例</span><span class="sxs-lookup"><span data-stu-id="9bd4f-128">Example</span></span>  
 <span data-ttu-id="9bd4f-129">以下 Entity SQL 查询使用 CASE 表达式计算一组 `Boolean` 表达式以确定结果。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="9bd4f-130">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9bd4f-131">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9bd4f-131">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9bd4f-132">按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="9bd4f-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="9bd4f-133">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="9bd4f-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="9bd4f-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bd4f-134">See Also</span></span>  
 [<span data-ttu-id="9bd4f-135">THEN</span><span class="sxs-lookup"><span data-stu-id="9bd4f-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [<span data-ttu-id="9bd4f-136">SELECT</span><span class="sxs-lookup"><span data-stu-id="9bd4f-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [<span data-ttu-id="9bd4f-137">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="9bd4f-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
