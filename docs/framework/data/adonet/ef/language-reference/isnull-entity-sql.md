---
title: ISNULL (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 31e0b77e397bd4f190119a01719da185211f7715
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="044ed-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="044ed-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="044ed-103">确定查询表达式是否为 null。</span><span class="sxs-lookup"><span data-stu-id="044ed-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="044ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="044ed-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="044ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="044ed-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="044ed-106">任何有效的查询表达式。</span><span class="sxs-lookup"><span data-stu-id="044ed-106">Any valid query expression.</span></span> <span data-ttu-id="044ed-107">不可以是集合，不可含有集合成员，也不可以是具有集合类型属性的记录类型。</span><span class="sxs-lookup"><span data-stu-id="044ed-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="044ed-108">NOT</span><span class="sxs-lookup"><span data-stu-id="044ed-108">NOT</span></span>  
 <span data-ttu-id="044ed-109">对 IS NULL 的 EDM.Boolean 结果取反。</span><span class="sxs-lookup"><span data-stu-id="044ed-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="044ed-110">返回值</span><span class="sxs-lookup"><span data-stu-id="044ed-110">Return Value</span></span>  
 <span data-ttu-id="044ed-111">如果 `true` 返回 null，则为 `expression`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="044ed-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="044ed-112">备注</span><span class="sxs-lookup"><span data-stu-id="044ed-112">Remarks</span></span>  
 <span data-ttu-id="044ed-113">使用 `IS NULL` 可确定外部联接的元素是否为 null：</span><span class="sxs-lookup"><span data-stu-id="044ed-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="044ed-114">使用 `IS NULL` 可确定成员是否有实际值：</span><span class="sxs-lookup"><span data-stu-id="044ed-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="044ed-115">下表显示了 `IS NULL` 对于某些模式的行为。</span><span class="sxs-lookup"><span data-stu-id="044ed-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="044ed-116">所有异常都在调用提供程序之前从客户端引发：</span><span class="sxs-lookup"><span data-stu-id="044ed-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="044ed-117">模式</span><span class="sxs-lookup"><span data-stu-id="044ed-117">Pattern</span></span>|<span data-ttu-id="044ed-118">行为</span><span class="sxs-lookup"><span data-stu-id="044ed-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="044ed-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="044ed-119">null IS NULL</span></span>|<span data-ttu-id="044ed-120">返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="044ed-120">Returns `true`.</span></span>|  
|<span data-ttu-id="044ed-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="044ed-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="044ed-122">返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="044ed-122">Returns `true`.</span></span>|  
|<span data-ttu-id="044ed-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="044ed-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="044ed-124">引发错误。</span><span class="sxs-lookup"><span data-stu-id="044ed-124">Throws an error.</span></span>|  
|<span data-ttu-id="044ed-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="044ed-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="044ed-126">引发错误。</span><span class="sxs-lookup"><span data-stu-id="044ed-126">Throws an error.</span></span>|  
|<span data-ttu-id="044ed-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="044ed-127">EntityType IS NULL</span></span>|<span data-ttu-id="044ed-128">返回 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="044ed-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="044ed-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="044ed-129">ComplexType IS NULL</span></span>|<span data-ttu-id="044ed-130">引发错误。</span><span class="sxs-lookup"><span data-stu-id="044ed-130">Throws an error.</span></span>|  
|<span data-ttu-id="044ed-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="044ed-131">RowType IS NULL</span></span>|<span data-ttu-id="044ed-132">引发错误。</span><span class="sxs-lookup"><span data-stu-id="044ed-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="044ed-133">示例</span><span class="sxs-lookup"><span data-stu-id="044ed-133">Example</span></span>  
 <span data-ttu-id="044ed-134">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 IS NOT NULL 运算符来确定查询表达式是否不为 null。</span><span class="sxs-lookup"><span data-stu-id="044ed-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="044ed-135">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="044ed-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="044ed-136">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="044ed-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="044ed-137">执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="044ed-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="044ed-138">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="044ed-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="044ed-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="044ed-139">See Also</span></span>  
 [<span data-ttu-id="044ed-140">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="044ed-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
