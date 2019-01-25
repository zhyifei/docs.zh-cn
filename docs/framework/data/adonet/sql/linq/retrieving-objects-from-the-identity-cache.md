---
title: 从实体缓存检索对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: dceda9dce794e0a08cc9cd7905cf3cd0685898d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569149"
---
# <a name="retrieving-objects-from-the-identity-cache"></a><span data-ttu-id="f94fb-102">从实体缓存检索对象</span><span class="sxs-lookup"><span data-stu-id="f94fb-102">Retrieving Objects from the Identity Cache</span></span>
<span data-ttu-id="f94fb-103">本主题介绍从 <xref:System.Data.Linq.DataContext> 管理的标识缓存中返回对象的 LINQ to SQL 查询类型。</span><span class="sxs-lookup"><span data-stu-id="f94fb-103">This topic describes the types of LINQ to SQL queries that return an object from the identity cache that is managed by the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="f94fb-104">在 LINQ to SQL 中，<xref:System.Data.Linq.DataContext> 管理对象的一种方法是在执行查询时将对象标识记录到标识缓存中。</span><span class="sxs-lookup"><span data-stu-id="f94fb-104">In LINQ to SQL, one of the ways in which the <xref:System.Data.Linq.DataContext> manages objects is by logging object identities in an identity cache as queries are executed.</span></span> <span data-ttu-id="f94fb-105">在有些情况下，LINQ to SQL 将先尝试从标识缓存中检索对象，然后再在数据库中执行查询。</span><span class="sxs-lookup"><span data-stu-id="f94fb-105">In some cases, LINQ to SQL will attempt to retrieve an object from the identity cache before executing a query in the database.</span></span>  
  
 <span data-ttu-id="f94fb-106">通常，如果 LINQ to SQL 查询要从标识缓存中返回对象，该查询必须基于对象的主键，并且必须返回单一对象。</span><span class="sxs-lookup"><span data-stu-id="f94fb-106">In general, for a LINQ to SQL query to return an object from the identity cache, the query must be based on the primary key of an object and must return a single object.</span></span> <span data-ttu-id="f94fb-107">特别是，该查询必须具有下面显示的常规形式之一。</span><span class="sxs-lookup"><span data-stu-id="f94fb-107">In particular, the query must be in one of the general forms shown below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f94fb-108">预编译的查询不会从标识缓存中返回对象。</span><span class="sxs-lookup"><span data-stu-id="f94fb-108">Pre-compiled queries will not return objects from the identity cache.</span></span> <span data-ttu-id="f94fb-109">有关预编译查询的详细信息，请参阅<xref:System.Data.Linq.CompiledQuery>和[如何：存储和重用查询](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="f94fb-109">For more information about pre-compiled queries, see <xref:System.Data.Linq.CompiledQuery> and [How to: Store and Reuse Queries](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span></span>  
  
 <span data-ttu-id="f94fb-110">查询必须具有以下常规形式之一，才能从标识缓存中检索对象：</span><span class="sxs-lookup"><span data-stu-id="f94fb-110">A query must be in one of the following general forms to retrieve an object from the identity cache:</span></span>  
  
-   <span data-ttu-id="f94fb-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span><span class="sxs-lookup"><span data-stu-id="f94fb-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span></span>  
  
-   <span data-ttu-id="f94fb-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span><span class="sxs-lookup"><span data-stu-id="f94fb-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span></span>  
  
 <span data-ttu-id="f94fb-113">在这些常规形式中，`Function1`、`Function2` 和 `predicate` 定义如下。</span><span class="sxs-lookup"><span data-stu-id="f94fb-113">In these general forms, `Function1`, `Function2`, and `predicate` are defined as follows.</span></span>  
  
 <span data-ttu-id="f94fb-114">`Function1` 可以是以下任意形式：</span><span class="sxs-lookup"><span data-stu-id="f94fb-114">`Function1` can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.Where%2A>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="f94fb-115">`Function2` 可以是以下任意形式：</span><span class="sxs-lookup"><span data-stu-id="f94fb-115">`Function2` can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="f94fb-116">`predicate` 必须是一个表达式，并且其中对象的主键属性必须设置为常量值。</span><span class="sxs-lookup"><span data-stu-id="f94fb-116">`predicate` must be an expression in which the object's primary key property is set to a constant value.</span></span> <span data-ttu-id="f94fb-117">如果对象的主键由多个属性定义，则每个主键属性都必须设置为常量值。</span><span class="sxs-lookup"><span data-stu-id="f94fb-117">If an object has a primary key defined by more than one property, each primary key property must be set to a constant value.</span></span> <span data-ttu-id="f94fb-118">下面的示例是 `predicate` 必须采用的形式：</span><span class="sxs-lookup"><span data-stu-id="f94fb-118">The following are examples of the form `predicate` must take:</span></span>  
  
-   `c => c.PK == constant_value`  
  
-   `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a><span data-ttu-id="f94fb-119">示例</span><span class="sxs-lookup"><span data-stu-id="f94fb-119">Example</span></span>  
 <span data-ttu-id="f94fb-120">下面的代码提供了从标识缓存中检索对象的 LINQ to SQL 查询类型的示例。</span><span class="sxs-lookup"><span data-stu-id="f94fb-120">The following code provides examples of the types of LINQ to SQL queries that retrieve an object from the identity cache.</span></span>  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f94fb-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f94fb-121">See also</span></span>
- [<span data-ttu-id="f94fb-122">查询概念</span><span class="sxs-lookup"><span data-stu-id="f94fb-122">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="f94fb-123">对象标识</span><span class="sxs-lookup"><span data-stu-id="f94fb-123">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
- [<span data-ttu-id="f94fb-124">背景信息</span><span class="sxs-lookup"><span data-stu-id="f94fb-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="f94fb-125">对象标识</span><span class="sxs-lookup"><span data-stu-id="f94fb-125">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
