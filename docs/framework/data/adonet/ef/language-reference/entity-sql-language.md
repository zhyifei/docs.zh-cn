---
title: Entity SQL 语言
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 0c698f04c3b95ffb204a20d41e91ef3f6210c5d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494090"
---
# <a name="entity-sql-language"></a><span data-ttu-id="3f2dd-102">Entity SQL 语言</span><span class="sxs-lookup"><span data-stu-id="3f2dd-102">Entity SQL Language</span></span>
<span data-ttu-id="3f2dd-103">Entity SQL 是类似于 SQL 的与存储无关的查询语言。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="3f2dd-104">通过 Entity SQL，可以将实体数据作为对象或以表格形式进行查询。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="3f2dd-105">在以下情况下，应考虑使用 Entity SQL：</span><span class="sxs-lookup"><span data-stu-id="3f2dd-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="3f2dd-106">当查询必须在运行时动态构造时。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="3f2dd-107">在这种情况下，还应考虑使用 <xref:System.Data.Objects.ObjectQuery%601> 的查询生成器方法，而不是在运行时构造 Entity SQL 查询字符串。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="3f2dd-108">当您要将查询定义为模型定义的一部分时。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="3f2dd-109">在数据模型中只支持 Entity SQL。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="3f2dd-110">有关详细信息，请参阅[QueryView 元素 (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="3f2dd-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
-   <span data-ttu-id="3f2dd-111">当使用 EntityClient，通过 <xref:System.Data.EntityClient.EntityDataReader> 将只读实体数据返回为行集时。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="3f2dd-112">有关详细信息，请参阅[针对实体框架的 EntityClient Provider](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="3f2dd-113">如果您已经是基于 SQL 的查询语言的专家，Entity SQL 可能对您而言是最简单不过了。</span><span class="sxs-lookup"><span data-stu-id="3f2dd-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="3f2dd-114">将 Entity SQL 与 EntityClient 提供程序结合使用</span><span class="sxs-lookup"><span data-stu-id="3f2dd-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="3f2dd-115">如果您要将 Entity SQL 与 EntityClient 提供程序结合使用，有关更多信息请参见下列主题：</span><span class="sxs-lookup"><span data-stu-id="3f2dd-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="3f2dd-116">用于实体框架的 EntityClient 提供程序</span><span class="sxs-lookup"><span data-stu-id="3f2dd-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="3f2dd-117">如何：生成 EntityConnection 连接字符串</span><span class="sxs-lookup"><span data-stu-id="3f2dd-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="3f2dd-118">如何：执行返回 PrimitiveType 结果的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="3f2dd-119">如何：执行返回 StructuralType 结果的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="3f2dd-120">如何：执行返回 RefType 结果的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="3f2dd-121">如何：执行返回复杂类型的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="3f2dd-122">如何：执行返回嵌套的集合的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="3f2dd-123">如何：执行参数化的 Entity SQL 查询使用 EntityCommand</span><span class="sxs-lookup"><span data-stu-id="3f2dd-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="3f2dd-124">如何：执行参数化存储的过程使用 EntityCommand</span><span class="sxs-lookup"><span data-stu-id="3f2dd-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="3f2dd-125">如何：执行多态查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="3f2dd-126">如何：使用导航关系导航运算符</span><span class="sxs-lookup"><span data-stu-id="3f2dd-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="3f2dd-127">将 Entity SQL 与对象查询结合使用</span><span class="sxs-lookup"><span data-stu-id="3f2dd-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="3f2dd-128">如果您要将 Entity SQL 与对象查询结合使用，有关更多信息请参见下列主题：</span><span class="sxs-lookup"><span data-stu-id="3f2dd-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="3f2dd-129">如何：执行返回实体类型对象的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](https://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [<span data-ttu-id="3f2dd-130">如何：执行参数化的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-130">How to: Execute a Parameterized Query</span></span>](https://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [<span data-ttu-id="3f2dd-131">如何：使用导航属性导航关系</span><span class="sxs-lookup"><span data-stu-id="3f2dd-131">How to: Navigate Relationships Using Navigation Properties</span></span>](https://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [<span data-ttu-id="3f2dd-132">如何：调用用户定义函数</span><span class="sxs-lookup"><span data-stu-id="3f2dd-132">How to: Call a User-Defined Function</span></span>](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [<span data-ttu-id="3f2dd-133">如何：筛选数据</span><span class="sxs-lookup"><span data-stu-id="3f2dd-133">How to: Filter Data</span></span>](https://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [<span data-ttu-id="3f2dd-134">如何：对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="3f2dd-134">How to: Sort Data</span></span>](https://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [<span data-ttu-id="3f2dd-135">如何：对数据进行分组</span><span class="sxs-lookup"><span data-stu-id="3f2dd-135">How to: Group Data</span></span>](https://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [<span data-ttu-id="3f2dd-136">如何：聚合数据</span><span class="sxs-lookup"><span data-stu-id="3f2dd-136">How to: Aggregate Data</span></span>](https://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [<span data-ttu-id="3f2dd-137">如何：执行返回匿名类型对象的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](https://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [<span data-ttu-id="3f2dd-138">如何：执行返回基元类型的集合的查询</span><span class="sxs-lookup"><span data-stu-id="3f2dd-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](https://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [<span data-ttu-id="3f2dd-139">如何：查询在 EntityCollection 中的相关的对象</span><span class="sxs-lookup"><span data-stu-id="3f2dd-139">How to: Query Related Objects in an EntityCollection</span></span>](https://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [<span data-ttu-id="3f2dd-140">如何：两个查询的联合排序</span><span class="sxs-lookup"><span data-stu-id="3f2dd-140">How to: Order the Union of Two Queries</span></span>](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [<span data-ttu-id="3f2dd-141">如何：页查看查询结果</span><span class="sxs-lookup"><span data-stu-id="3f2dd-141">How to: Page Through Query Results</span></span>](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a><span data-ttu-id="3f2dd-142">本节内容</span><span class="sxs-lookup"><span data-stu-id="3f2dd-142">In This Section</span></span>  
 [<span data-ttu-id="3f2dd-143">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="3f2dd-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="3f2dd-144">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="3f2dd-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="3f2dd-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f2dd-145">See also</span></span>
- [<span data-ttu-id="3f2dd-146">ADO.NET 实体框架</span><span class="sxs-lookup"><span data-stu-id="3f2dd-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
- [<span data-ttu-id="3f2dd-147">语言参考</span><span class="sxs-lookup"><span data-stu-id="3f2dd-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
