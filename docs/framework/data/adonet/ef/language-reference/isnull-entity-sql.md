---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: aaecce3ff74d64b8e07b31329ced5b5e581fca5b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295089"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="d93f1-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d93f1-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="d93f1-103">确定查询表达式是否为 null。</span><span class="sxs-lookup"><span data-stu-id="d93f1-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d93f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="d93f1-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="d93f1-105">自变量</span><span class="sxs-lookup"><span data-stu-id="d93f1-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d93f1-106">任何有效的查询表达式。</span><span class="sxs-lookup"><span data-stu-id="d93f1-106">Any valid query expression.</span></span> <span data-ttu-id="d93f1-107">不可以是集合，不可含有集合成员，也不可以是具有集合类型属性的记录类型。</span><span class="sxs-lookup"><span data-stu-id="d93f1-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="d93f1-108">NOT</span><span class="sxs-lookup"><span data-stu-id="d93f1-108">NOT</span></span>  
 <span data-ttu-id="d93f1-109">对 IS NULL 的 EDM.Boolean 结果取反。</span><span class="sxs-lookup"><span data-stu-id="d93f1-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d93f1-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d93f1-110">Return Value</span></span>  
 <span data-ttu-id="d93f1-111">如果 `true` 返回 null，则为 `expression`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="d93f1-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d93f1-112">备注</span><span class="sxs-lookup"><span data-stu-id="d93f1-112">Remarks</span></span>  
 <span data-ttu-id="d93f1-113">使用 `IS NULL` 可确定外部联接的元素是否为 null：</span><span class="sxs-lookup"><span data-stu-id="d93f1-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="d93f1-114">使用 `IS NULL` 可确定成员是否有实际值：</span><span class="sxs-lookup"><span data-stu-id="d93f1-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="d93f1-115">下表显示了 `IS NULL` 对于某些模式的行为。</span><span class="sxs-lookup"><span data-stu-id="d93f1-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="d93f1-116">所有异常都在调用提供程序之前从客户端引发：</span><span class="sxs-lookup"><span data-stu-id="d93f1-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="d93f1-117">模式</span><span class="sxs-lookup"><span data-stu-id="d93f1-117">Pattern</span></span>|<span data-ttu-id="d93f1-118">行为</span><span class="sxs-lookup"><span data-stu-id="d93f1-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="d93f1-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="d93f1-119">null IS NULL</span></span>|<span data-ttu-id="d93f1-120">返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="d93f1-120">Returns `true`.</span></span>|  
|<span data-ttu-id="d93f1-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d93f1-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="d93f1-122">返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="d93f1-122">Returns `true`.</span></span>|  
|<span data-ttu-id="d93f1-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d93f1-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="d93f1-124">引发错误。</span><span class="sxs-lookup"><span data-stu-id="d93f1-124">Throws an error.</span></span>|  
|<span data-ttu-id="d93f1-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d93f1-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="d93f1-126">引发错误。</span><span class="sxs-lookup"><span data-stu-id="d93f1-126">Throws an error.</span></span>|  
|<span data-ttu-id="d93f1-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d93f1-127">EntityType IS NULL</span></span>|<span data-ttu-id="d93f1-128">返回 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="d93f1-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="d93f1-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d93f1-129">ComplexType IS NULL</span></span>|<span data-ttu-id="d93f1-130">引发错误。</span><span class="sxs-lookup"><span data-stu-id="d93f1-130">Throws an error.</span></span>|  
|<span data-ttu-id="d93f1-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d93f1-131">RowType IS NULL</span></span>|<span data-ttu-id="d93f1-132">引发错误。</span><span class="sxs-lookup"><span data-stu-id="d93f1-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d93f1-133">示例</span><span class="sxs-lookup"><span data-stu-id="d93f1-133">Example</span></span>  
 <span data-ttu-id="d93f1-134">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 IS NOT NULL 运算符来确定查询表达式是否不为 null。</span><span class="sxs-lookup"><span data-stu-id="d93f1-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="d93f1-135">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="d93f1-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d93f1-136">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="d93f1-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d93f1-137">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d93f1-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d93f1-138">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="d93f1-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="d93f1-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="d93f1-139">See also</span></span>

- [<span data-ttu-id="d93f1-140">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="d93f1-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
