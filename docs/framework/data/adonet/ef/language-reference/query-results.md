---
title: 查询结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
ms.openlocfilehash: 70aa2ad6385ec4791b05b202dc5dc6d4fe9e57b9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762317"
---
# <a name="query-results"></a><span data-ttu-id="7f2a4-102">查询结果</span><span class="sxs-lookup"><span data-stu-id="7f2a4-102">Query Results</span></span>
<span data-ttu-id="7f2a4-103">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 查询在转换为命令目录树执行之后，通常以下列形式之一返回查询结果：</span><span class="sxs-lookup"><span data-stu-id="7f2a4-103">After a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query is converted to command trees and executed, the query results are usually returned as one of the following:</span></span>  
  
-   <span data-ttu-id="7f2a4-104">概念模型中零个或多个类型化实体对象的集合或复杂类型的投影。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-104">A collection of zero or more typed entity objects or a projection of complex types in the conceptual model.</span></span>  
  
-   <span data-ttu-id="7f2a4-105">概念模型支持的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-105">CLR types supported by the conceptual model.</span></span>  
  
-   <span data-ttu-id="7f2a4-106">内联集合。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-106">Inline collections.</span></span>  
  
-   <span data-ttu-id="7f2a4-107">匿名类型。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-107">Anonymous types.</span></span>  
  
 <span data-ttu-id="7f2a4-108">对数据源执行查询时，结果将具体化为 CLR 类型并返回客户端。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-108">When the query has executed against the data source, the results are materialized into CLR types and returned to the client.</span></span> <span data-ttu-id="7f2a4-109">所有对象具体化均由 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 执行。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-109">All object materialization is performed by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="7f2a4-110">由于无法在 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 与 CLR 之间进行映射而导致的任何错误都将导致在对象具体化过程中引发异常。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-110">Any errors that result from an inability to map between the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] and the CLR will cause exceptions to be thrown during object materialization.</span></span>  
  
 <span data-ttu-id="7f2a4-111">如果查询执行返回基元概念模型类型，则结果由独立的且与[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]断开连接的 CLR 类型组成。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-111">If the query execution returns primitive conceptual model types, the results consist of CLR types that are stand-alone and disconnected from the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="7f2a4-112">但如果查询返回 <xref:System.Data.Objects.ObjectQuery%601> 所表示的类型化实体对象的集合，则这些类型由对象上下文进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-112">However, if the query returns a collection of typed entity objects, represented by <xref:System.Data.Objects.ObjectQuery%601>, those types are tracked by the object context.</span></span> <span data-ttu-id="7f2a4-113">所有对象行为 （如父/子集合、 更改跟踪、 多态性等） 都都中定义[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-113">All object behavior (such as child/parent collections, change tracking, polymorphism, and so on) are as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="7f2a4-114">此功能可按照[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]中的定义使用。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-114">This functionality can be used in its capacity, as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="7f2a4-115">有关详细信息，请参阅[使用对象](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-115">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="7f2a4-116">从查询返回的结构类型（如匿名类型和可以为 null 的复杂类型）可以是 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-116">Struct types returned from queries (such as anonymous types and nullable complex types) can be of `null` value.</span></span> <span data-ttu-id="7f2a4-117">返回的实体的 <xref:System.Data.Objects.DataClasses.EntityCollection%601> 属性也可以是 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-117">An <xref:System.Data.Objects.DataClasses.EntityCollection%601> property of a returned entity can also be of `null` value.</span></span> <span data-ttu-id="7f2a4-118">投影值为 `null` 的实体的集合属性会导致这种情况，例如，调用没有任何元素的 <xref:System.Linq.Queryable.FirstOrDefault%2A> 的 <xref:System.Data.Objects.ObjectQuery%601>。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-118">This can result from projecting the collection property of an entity that is of `null` value, such as calling <xref:System.Linq.Queryable.FirstOrDefault%2A> on an <xref:System.Data.Objects.ObjectQuery%601> that has no elements.</span></span>  
  
 <span data-ttu-id="7f2a4-119">在某些情况下，某个查询在其执行期间看似生成具体化结果，但该查询将在服务器上执行，实体对象绝不会在 CLR 中具体化。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-119">In certain situations, a query might appear to generate a materialized result during its execution, but the query will be executed on the server and the entity object will never be materialized in the CLR.</span></span> <span data-ttu-id="7f2a4-120">如果对象具体化的副作用对您有很大影响，这可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-120">This can cause problems if you are depending on side effects of object materialization.</span></span>  
  
 <span data-ttu-id="7f2a4-121">下面的示例包含一个自定义类 `MyContact`，该类有一个 `LastName` 属性。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-121">The following example contains a custom class, `MyContact`, with a `LastName` property.</span></span> <span data-ttu-id="7f2a4-122">如果设置 `LastName` 属性，`count` 变量就会递增。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-122">When the `LastName` property is set, a `count` variable is incremented.</span></span> <span data-ttu-id="7f2a4-123">如果执行以下两个查询，则第一个查询将使 `count` 递增，而第二个查询不会。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-123">If you execute the two following queries, the first query will increment `count` while the second query will not.</span></span> <span data-ttu-id="7f2a4-124">这是因为：在第二个查询中，将从结果中投影 `LastName` 属性，而绝不会创建 `MyContact` 类，因为这不是对存储区执行查询所必需的。</span><span class="sxs-lookup"><span data-stu-id="7f2a4-124">This is because in the second query the `LastName` property is projected from the results and the `MyContact` class is never created, because it is not required to execute the query on the store.</span></span>  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
