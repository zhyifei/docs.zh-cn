---
title: 类型系统 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: 1831028f9e659dab90ca3c8689d7ff2d5c0ee36a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554330"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="ba570-102">类型系统 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ba570-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="ba570-103">支持多种类型：</span><span class="sxs-lookup"><span data-stu-id="ba570-103">supports a number of types:</span></span>  
  
-   <span data-ttu-id="ba570-104">基元（简单）类型，如 `Int32` 和 `String.`。</span><span class="sxs-lookup"><span data-stu-id="ba570-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
-   <span data-ttu-id="ba570-105">在架构中定义的名义类型，如 <xref:System.Data.Metadata.Edm.EntityType>、<xref:System.Data.Metadata.Edm.ComplexType> 和 <xref:System.Data.Metadata.Edm.RelationshipType>。</span><span class="sxs-lookup"><span data-stu-id="ba570-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
-   <span data-ttu-id="ba570-106">架构中未显式定义的匿名类型：<xref:System.Data.Metadata.Edm.CollectionType>、<xref:System.Data.Metadata.Edm.RowType> 和 <xref:System.Data.Metadata.Edm.RefType>。</span><span class="sxs-lookup"><span data-stu-id="ba570-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="ba570-107">本节讨论在架构中未显式定义但受 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 支持的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="ba570-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="ba570-108">有关基元类型和名义类型的信息，请参阅[概念模型类型 (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)。</span><span class="sxs-lookup"><span data-stu-id="ba570-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="ba570-109">行</span><span class="sxs-lookup"><span data-stu-id="ba570-109">Rows</span></span>  
 <span data-ttu-id="ba570-110">行的结构取决于该行所包含的类型化以命名成员的序列。</span><span class="sxs-lookup"><span data-stu-id="ba570-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="ba570-111">行类型没有标识，不能被继承。</span><span class="sxs-lookup"><span data-stu-id="ba570-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="ba570-112">如果同一行类型的实例的成员分别等效，则这些实例是等效的。</span><span class="sxs-lookup"><span data-stu-id="ba570-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="ba570-113">行不具有超出其结构等效项的行为，在公共语言运行库中没有等效项。</span><span class="sxs-lookup"><span data-stu-id="ba570-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="ba570-114">查询可产生包含行或行的集合的结构。</span><span class="sxs-lookup"><span data-stu-id="ba570-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="ba570-115">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询和主机语言之间的 API 绑定定义行在产生结果的查询中的实现方式。</span><span class="sxs-lookup"><span data-stu-id="ba570-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="ba570-116">有关如何构造行实例的信息，请参阅[构造类型](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="ba570-116">For information on how to construct a row instance, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="ba570-117">集合</span><span class="sxs-lookup"><span data-stu-id="ba570-117">Collections</span></span>  
 <span data-ttu-id="ba570-118">集合类型表示其他对象的零个或零个以上的实例。</span><span class="sxs-lookup"><span data-stu-id="ba570-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="ba570-119">有关如何构造集合的信息，请参阅[构造类型](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="ba570-119">For information on how to construct collection, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="ba570-120">参考资料</span><span class="sxs-lookup"><span data-stu-id="ba570-120">References</span></span>  
 <span data-ttu-id="ba570-121">引用是指向特定实体集中的特定实体的逻辑指针。</span><span class="sxs-lookup"><span data-stu-id="ba570-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="ba570-122">支持使用以下运算符对引用进行构造、解构和导航：</span><span class="sxs-lookup"><span data-stu-id="ba570-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
-   [<span data-ttu-id="ba570-123">REF</span><span class="sxs-lookup"><span data-stu-id="ba570-123">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
-   [<span data-ttu-id="ba570-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="ba570-124">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
-   [<span data-ttu-id="ba570-125">KEY</span><span class="sxs-lookup"><span data-stu-id="ba570-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
-   [<span data-ttu-id="ba570-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="ba570-126">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 <span data-ttu-id="ba570-127">可以使用成员访问（点）运算符 (`.`) 对引用进行导航。</span><span class="sxs-lookup"><span data-stu-id="ba570-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="ba570-128">下面的代码段通过对 r（引用）属性进行导航提取 Order 的 Id 属性。</span><span class="sxs-lookup"><span data-stu-id="ba570-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="ba570-129">如果引用值为 null，或引用的目标不存在，则结果为 null。</span><span class="sxs-lookup"><span data-stu-id="ba570-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba570-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba570-130">See also</span></span>
- [<span data-ttu-id="ba570-131">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="ba570-131">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="ba570-132">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ba570-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="ba570-133">CAST</span><span class="sxs-lookup"><span data-stu-id="ba570-133">CAST</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)
- [<span data-ttu-id="ba570-134">CSDL、SSDL 和 MSL 规范</span><span class="sxs-lookup"><span data-stu-id="ba570-134">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
