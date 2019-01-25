---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: e66a09276f40ab6d9ff7c11bb160385b4c1efb48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542552"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="09c75-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="09c75-102">NAVIGATE (Entity SQL)</span></span>
<span data-ttu-id="09c75-103">导航实体之间建立的关系。</span><span class="sxs-lookup"><span data-stu-id="09c75-103">Navigates over the relationship established between entities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09c75-104">语法</span><span class="sxs-lookup"><span data-stu-id="09c75-104">Syntax</span></span>  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a><span data-ttu-id="09c75-105">自变量</span><span class="sxs-lookup"><span data-stu-id="09c75-105">Arguments</span></span>  
 `instance-expresssion`  
 <span data-ttu-id="09c75-106">一个实体的实例。</span><span class="sxs-lookup"><span data-stu-id="09c75-106">An instance of an entity.</span></span>  
  
 `relationship-type`  
 <span data-ttu-id="09c75-107">关系的类型名称，取自概念架构定义语言 (CSDL) 文件。</span><span class="sxs-lookup"><span data-stu-id="09c75-107">The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="09c75-108">`relationship-type`是作为限定\<命名空间 >。\<关系类型名称 >。</span><span class="sxs-lookup"><span data-stu-id="09c75-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>  
  
 `to`  
 <span data-ttu-id="09c75-109">关系的结束端。</span><span class="sxs-lookup"><span data-stu-id="09c75-109">The end of the relationship.</span></span>  
  
 `from`  
 <span data-ttu-id="09c75-110">关系的起始端。</span><span class="sxs-lookup"><span data-stu-id="09c75-110">The beginning of the relationship.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09c75-111">返回值</span><span class="sxs-lookup"><span data-stu-id="09c75-111">Return Value</span></span>  
 <span data-ttu-id="09c75-112">如果结束端的基数为 1，返回值将为 `Ref<T>`。</span><span class="sxs-lookup"><span data-stu-id="09c75-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="09c75-113">如果结束端的基数为 n，返回值将为 `Collection<Ref<T>>`。</span><span class="sxs-lookup"><span data-stu-id="09c75-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09c75-114">备注</span><span class="sxs-lookup"><span data-stu-id="09c75-114">Remarks</span></span>  
 <span data-ttu-id="09c75-115">关系是 [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM) 中的一类构造。</span><span class="sxs-lookup"><span data-stu-id="09c75-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="09c75-116">可以在两个或更多实体类型之间建立关系，用户可以通过关系从一端（实体）导航到另一端。</span><span class="sxs-lookup"><span data-stu-id="09c75-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="09c75-117">当关系中的名称解析没有歧义时，`from` 和 `to` 为有条件可选。</span><span class="sxs-lookup"><span data-stu-id="09c75-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>  
  
 <span data-ttu-id="09c75-118">NAVIGATE 在 O 和 C 空间中有效。</span><span class="sxs-lookup"><span data-stu-id="09c75-118">NAVIGATE is valid in O and C space.</span></span>  
  
 <span data-ttu-id="09c75-119">导航构造的常规形式如下：</span><span class="sxs-lookup"><span data-stu-id="09c75-119">The general form of a navigation construct is the following:</span></span>  
  
 <span data-ttu-id="09c75-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="09c75-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>  
  
 <span data-ttu-id="09c75-121">例如：</span><span class="sxs-lookup"><span data-stu-id="09c75-121">For example:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="09c75-122">其中 OrderCustomer 为 `relationship`，Customer 和 Order 为关系的 `to-end` （客户）和 `from-end` （订单）。</span><span class="sxs-lookup"><span data-stu-id="09c75-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="09c75-123">如果 ordercustomer 为 n:1 关系，则导航表达式的结果类型是 Ref\<客户 >。</span><span class="sxs-lookup"><span data-stu-id="09c75-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>  
  
 <span data-ttu-id="09c75-124">此表达式的简单形式如下：</span><span class="sxs-lookup"><span data-stu-id="09c75-124">The simpler form of this expression is the following:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="09c75-125">同样，在以下形式的查询中，导航表达式将生成一组 < Ref\<顺序 >>。</span><span class="sxs-lookup"><span data-stu-id="09c75-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 <span data-ttu-id="09c75-126">实例表达式必须为 entity/ref 类型。</span><span class="sxs-lookup"><span data-stu-id="09c75-126">The instance-expression must be an entity/ref type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09c75-127">示例</span><span class="sxs-lookup"><span data-stu-id="09c75-127">Example</span></span>  
 <span data-ttu-id="09c75-128">下面的 Entity SQL 查询使用 NAVIGATE 运算符来导航建立在 Address 和 SalesOrderHeader 实体类型之间的关系。</span><span class="sxs-lookup"><span data-stu-id="09c75-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="09c75-129">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="09c75-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="09c75-130">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="09c75-130">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="09c75-131">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="09c75-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="09c75-132">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="09c75-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a><span data-ttu-id="09c75-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="09c75-133">See also</span></span>
- [<span data-ttu-id="09c75-134">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="09c75-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="09c75-135">如何：导航与关系导航运算符</span><span class="sxs-lookup"><span data-stu-id="09c75-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
