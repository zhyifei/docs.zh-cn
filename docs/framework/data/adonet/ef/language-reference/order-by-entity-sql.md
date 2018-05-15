---
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 5cffd7a696496f92ae83822faff2f08e325eea93
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="97c01-102">ORDER BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="97c01-102">ORDER BY (Entity SQL)</span></span>
<span data-ttu-id="97c01-103">指定用于 SELECT 语句所返回的对象的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="97c01-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c01-104">语法</span><span class="sxs-lookup"><span data-stu-id="97c01-104">Syntax</span></span>  
  
```  
[ ORDER BY   
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]   
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="97c01-105">自变量</span><span class="sxs-lookup"><span data-stu-id="97c01-105">Arguments</span></span>  
 `order_by_expression`  
 <span data-ttu-id="97c01-106">指定作为排序依据的属性的任何有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="97c01-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="97c01-107">可以指定多个排序表达式。</span><span class="sxs-lookup"><span data-stu-id="97c01-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="97c01-108">ORDER BY 子句中排序表达式的顺序将决定排序后结果集的结构。</span><span class="sxs-lookup"><span data-stu-id="97c01-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="97c01-109">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="97c01-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="97c01-110">指定应根据 `collation_name`中所指定的排序规则执行 ORDER BY 运算。</span><span class="sxs-lookup"><span data-stu-id="97c01-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="97c01-111">COLLATE 仅适用于字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="97c01-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="97c01-112">ASC</span><span class="sxs-lookup"><span data-stu-id="97c01-112">ASC</span></span>  
 <span data-ttu-id="97c01-113">指定所指定属性中的值应按升序排序，即从最低值往最高值排序。</span><span class="sxs-lookup"><span data-stu-id="97c01-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="97c01-114">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="97c01-114">This is the default.</span></span>  
  
 <span data-ttu-id="97c01-115">DESC</span><span class="sxs-lookup"><span data-stu-id="97c01-115">DESC</span></span>  
 <span data-ttu-id="97c01-116">指定所指定属性中的值应按降序排序，即从最高值往最低值排序。</span><span class="sxs-lookup"><span data-stu-id="97c01-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="97c01-117">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="97c01-117">LIMIT `n`</span></span>  
 <span data-ttu-id="97c01-118">仅选择前 `n` 个项。</span><span class="sxs-lookup"><span data-stu-id="97c01-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="97c01-119">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="97c01-119">SKIP `n`</span></span>  
 <span data-ttu-id="97c01-120">跳过前 `n` 个项。</span><span class="sxs-lookup"><span data-stu-id="97c01-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97c01-121">备注</span><span class="sxs-lookup"><span data-stu-id="97c01-121">Remarks</span></span>  
 <span data-ttu-id="97c01-122">ORDER BY 子句在逻辑上应用于 SELECT 子句的结果。</span><span class="sxs-lookup"><span data-stu-id="97c01-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="97c01-123">ORDER BY 子句可以使用选择列表中各项的别名来引用这些项。</span><span class="sxs-lookup"><span data-stu-id="97c01-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="97c01-124">ORDER BY 子句也可引用当前处于作用域内的其他变量。</span><span class="sxs-lookup"><span data-stu-id="97c01-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="97c01-125">但如果用 DISTINCT 修饰符指定了 SELECT 子句，则 ORDER BY 子句只能引用 SELECT 子句中的别名。</span><span class="sxs-lookup"><span data-stu-id="97c01-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="97c01-126">ORDER BY 子句中的每个表达式的计算结果都必须是可按顺序比较是否不等（小于或大于，等等）的某一类型。</span><span class="sxs-lookup"><span data-stu-id="97c01-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="97c01-127">这些类型通常为标量基元类型，如数字、字符串和日期。</span><span class="sxs-lookup"><span data-stu-id="97c01-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="97c01-128">可比较类型的 RowTypes 也可按顺序比较。</span><span class="sxs-lookup"><span data-stu-id="97c01-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="97c01-129">如果代码循环访问一个有序集（顶级投影除外），则不能确保输出会保持其顺序。</span><span class="sxs-lookup"><span data-stu-id="97c01-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  
  
```  
-- In the following sample, order is guaranteed to be preserved:  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="97c01-130">若要执行有序的 UNION、UNION ALL、EXCEPT 或 INTERSECT 运算，请使用以下模式：</span><span class="sxs-lookup"><span data-stu-id="97c01-130">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="97c01-131">受限制的关键字</span><span class="sxs-lookup"><span data-stu-id="97c01-131">Restricted keywords</span></span>  
 <span data-ttu-id="97c01-132">下列关键字在 `ORDER BY` 子句中使用时，必须用引号括起：</span><span class="sxs-lookup"><span data-stu-id="97c01-132">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
-   <span data-ttu-id="97c01-133">CROSS</span><span class="sxs-lookup"><span data-stu-id="97c01-133">CROSS</span></span>  
  
-   <span data-ttu-id="97c01-134">FULL</span><span class="sxs-lookup"><span data-stu-id="97c01-134">FULL</span></span>  
  
-   <span data-ttu-id="97c01-135">KEY</span><span class="sxs-lookup"><span data-stu-id="97c01-135">KEY</span></span>  
  
-   <span data-ttu-id="97c01-136">LEFT</span><span class="sxs-lookup"><span data-stu-id="97c01-136">LEFT</span></span>  
  
-   <span data-ttu-id="97c01-137">ORDER</span><span class="sxs-lookup"><span data-stu-id="97c01-137">ORDER</span></span>  
  
-   <span data-ttu-id="97c01-138">OUTER</span><span class="sxs-lookup"><span data-stu-id="97c01-138">OUTER</span></span>  
  
-   <span data-ttu-id="97c01-139">RIGHT</span><span class="sxs-lookup"><span data-stu-id="97c01-139">RIGHT</span></span>  
  
-   <span data-ttu-id="97c01-140">ROW</span><span class="sxs-lookup"><span data-stu-id="97c01-140">ROW</span></span>  
  
-   <span data-ttu-id="97c01-141">VALUE</span><span class="sxs-lookup"><span data-stu-id="97c01-141">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="97c01-142">嵌套查询排序</span><span class="sxs-lookup"><span data-stu-id="97c01-142">Ordering Nested Queries</span></span>  
 <span data-ttu-id="97c01-143">在实体框架中，嵌套表达式可以放在查询的任何位置，不保留嵌套查询的顺序。</span><span class="sxs-lookup"><span data-stu-id="97c01-143">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="97c01-144">示例</span><span class="sxs-lookup"><span data-stu-id="97c01-144">Example</span></span>  
 <span data-ttu-id="97c01-145">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 ORDER BY 运算符来指定用于 SELECT 语句所返回的对象的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="97c01-145">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="97c01-146">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="97c01-146">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="97c01-147">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="97c01-147">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="97c01-148">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="97c01-148">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="97c01-149">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="97c01-149">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ORDERBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="97c01-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="97c01-150">See Also</span></span>  
 [<span data-ttu-id="97c01-151">查询表达式</span><span class="sxs-lookup"><span data-stu-id="97c01-151">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [<span data-ttu-id="97c01-152">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="97c01-152">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="97c01-153">SKIP</span><span class="sxs-lookup"><span data-stu-id="97c01-153">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [<span data-ttu-id="97c01-154">LIMIT</span><span class="sxs-lookup"><span data-stu-id="97c01-154">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [<span data-ttu-id="97c01-155">TOP</span><span class="sxs-lookup"><span data-stu-id="97c01-155">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
