---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 9066f9fb68ce2c50e9523881cfa0dd930cd0b52e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319733"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="42d75-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="42d75-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="42d75-103">确定查询表达式是否为 null。</span><span class="sxs-lookup"><span data-stu-id="42d75-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42d75-104">语法</span><span class="sxs-lookup"><span data-stu-id="42d75-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="42d75-105">自变量</span><span class="sxs-lookup"><span data-stu-id="42d75-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="42d75-106">任何有效的查询表达式。</span><span class="sxs-lookup"><span data-stu-id="42d75-106">Any valid query expression.</span></span> <span data-ttu-id="42d75-107">不可以是集合，不可含有集合成员，也不可以是具有集合类型属性的记录类型。</span><span class="sxs-lookup"><span data-stu-id="42d75-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="42d75-108">NOT</span><span class="sxs-lookup"><span data-stu-id="42d75-108">NOT</span></span>  
 <span data-ttu-id="42d75-109">对 IS NULL 的 EDM.Boolean 结果取反。</span><span class="sxs-lookup"><span data-stu-id="42d75-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42d75-110">返回值</span><span class="sxs-lookup"><span data-stu-id="42d75-110">Return Value</span></span>  
 <span data-ttu-id="42d75-111">如果 `true` 返回 null，则为 `expression`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="42d75-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42d75-112">备注</span><span class="sxs-lookup"><span data-stu-id="42d75-112">Remarks</span></span>  
 <span data-ttu-id="42d75-113">使用 `IS NULL` 可确定外部联接的元素是否为 null：</span><span class="sxs-lookup"><span data-stu-id="42d75-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```sql  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="42d75-114">使用 `IS NULL` 可确定成员是否有实际值：</span><span class="sxs-lookup"><span data-stu-id="42d75-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="42d75-115">下表显示了 `IS NULL` 对于某些模式的行为。</span><span class="sxs-lookup"><span data-stu-id="42d75-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="42d75-116">所有异常都在调用提供程序之前从客户端引发：</span><span class="sxs-lookup"><span data-stu-id="42d75-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="42d75-117">模式</span><span class="sxs-lookup"><span data-stu-id="42d75-117">Pattern</span></span>|<span data-ttu-id="42d75-118">行为</span><span class="sxs-lookup"><span data-stu-id="42d75-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="42d75-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="42d75-119">null IS NULL</span></span>|<span data-ttu-id="42d75-120">返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="42d75-120">Returns `true`.</span></span>|  
|<span data-ttu-id="42d75-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="42d75-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="42d75-122">返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="42d75-122">Returns `true`.</span></span>|  
|<span data-ttu-id="42d75-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="42d75-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="42d75-124">引发错误。</span><span class="sxs-lookup"><span data-stu-id="42d75-124">Throws an error.</span></span>|  
|<span data-ttu-id="42d75-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="42d75-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="42d75-126">引发错误。</span><span class="sxs-lookup"><span data-stu-id="42d75-126">Throws an error.</span></span>|  
|<span data-ttu-id="42d75-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="42d75-127">EntityType IS NULL</span></span>|<span data-ttu-id="42d75-128">返回 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="42d75-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="42d75-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="42d75-129">ComplexType IS NULL</span></span>|<span data-ttu-id="42d75-130">引发错误。</span><span class="sxs-lookup"><span data-stu-id="42d75-130">Throws an error.</span></span>|  
|<span data-ttu-id="42d75-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="42d75-131">RowType IS NULL</span></span>|<span data-ttu-id="42d75-132">引发错误。</span><span class="sxs-lookup"><span data-stu-id="42d75-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="42d75-133">示例</span><span class="sxs-lookup"><span data-stu-id="42d75-133">Example</span></span>  
 <span data-ttu-id="42d75-134">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 IS NOT NULL 运算符来确定查询表达式是否不为 null。</span><span class="sxs-lookup"><span data-stu-id="42d75-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="42d75-135">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="42d75-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="42d75-136">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="42d75-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="42d75-137">执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="42d75-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="42d75-138">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="42d75-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="42d75-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="42d75-139">See also</span></span>

- [<span data-ttu-id="42d75-140">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="42d75-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
