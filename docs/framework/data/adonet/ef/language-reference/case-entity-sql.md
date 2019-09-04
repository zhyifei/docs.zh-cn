---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 79544f4180313a008669c56c4f2740c889043c6d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251255"
---
# <a name="case-entity-sql"></a><span data-ttu-id="482cc-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="482cc-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="482cc-103">求出一组 `Boolean` 表达式的值以确定结果。</span><span class="sxs-lookup"><span data-stu-id="482cc-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="482cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="482cc-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="482cc-105">自变量</span><span class="sxs-lookup"><span data-stu-id="482cc-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="482cc-106">一个占位符，表明可以使用多个 WHEN `Boolean_expression` THEN `result_expression` 子句。</span><span class="sxs-lookup"><span data-stu-id="482cc-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="482cc-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="482cc-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="482cc-108">作为在 `Boolean_expression` 的计算结果为 `true`时返回的表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="482cc-109">`result expression` 是任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="482cc-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="482cc-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="482cc-111">比较运算的结果都不为 `true`时返回的表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="482cc-112">如果忽略此参数且比较运算计算的结果不为 `true`，CASE 将返回空值。</span><span class="sxs-lookup"><span data-stu-id="482cc-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="482cc-113">`else_result_expression` 是任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="482cc-114">`else_result_expression` 及任何 `result_expression` 的数据类型必须相同或必须是隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="482cc-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="482cc-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="482cc-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="482cc-116">使用 CASE 搜索格式时所计算的 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="482cc-117">`Boolean_expression` 是任何有效的 `Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="482cc-118">返回值</span><span class="sxs-lookup"><span data-stu-id="482cc-118">Return Value</span></span>  
 <span data-ttu-id="482cc-119">从 `result_expression` 和可选 `else_result_expression`的类型集中返回优先级最高的类型。</span><span class="sxs-lookup"><span data-stu-id="482cc-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="482cc-120">备注</span><span class="sxs-lookup"><span data-stu-id="482cc-120">Remarks</span></span>  
 <span data-ttu-id="482cc-121">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] Case 表达式类似于 transact-sql case 表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the Transact-SQL case expression.</span></span> <span data-ttu-id="482cc-122">可以使用 case 表达式进行一系列条件测试，以确定哪个表达式将产生正确的结果。</span><span class="sxs-lookup"><span data-stu-id="482cc-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="482cc-123">这种格式的 case 表达式应用于由一个或多个 `Boolean` 表达式组成的一组表达式，以确定正确的结果表达式。</span><span class="sxs-lookup"><span data-stu-id="482cc-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="482cc-124">CASE 函数以指定的顺序为每个 WHEN 子句计算 `Boolean_expression` 的值，然后返回首个满足 `result_expression` = `Boolean_expression` 的 `true`。</span><span class="sxs-lookup"><span data-stu-id="482cc-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="482cc-125">而不对剩下的表达式求值。</span><span class="sxs-lookup"><span data-stu-id="482cc-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="482cc-126">如果没有任何 `Boolean_expression` 的计算结果为 `true`，则当指定了 ELSE 子句时，数据库引擎将返回 `else_result_expression` ；如果未指定 ELSE 子句，则返回空值。</span><span class="sxs-lookup"><span data-stu-id="482cc-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="482cc-127">CASE 语句不会返回 multiset 类型。</span><span class="sxs-lookup"><span data-stu-id="482cc-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="482cc-128">示例</span><span class="sxs-lookup"><span data-stu-id="482cc-128">Example</span></span>  
 <span data-ttu-id="482cc-129">以下 Entity SQL 查询使用 CASE 表达式计算一组 `Boolean` 表达式以确定结果。</span><span class="sxs-lookup"><span data-stu-id="482cc-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="482cc-130">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="482cc-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="482cc-131">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="482cc-131">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="482cc-132">[按照如何：执行返回 PrimitiveType 结果](../how-to-execute-a-query-that-returns-primitivetype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="482cc-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="482cc-133">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="482cc-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="482cc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="482cc-134">See also</span></span>

- [<span data-ttu-id="482cc-135">THEN</span><span class="sxs-lookup"><span data-stu-id="482cc-135">THEN</span></span>](then-entity-sql.md)
- [<span data-ttu-id="482cc-136">SELECT</span><span class="sxs-lookup"><span data-stu-id="482cc-136">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="482cc-137">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="482cc-137">Entity SQL Reference</span></span>](entity-sql-reference.md)
