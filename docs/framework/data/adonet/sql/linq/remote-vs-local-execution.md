---
title: 远程查询执行与本地执行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: 02d0417bc05f8585dc469d365089c8123d395f64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164510"
---
# <a name="remote-vs-local-execution"></a><span data-ttu-id="d6df1-102">远程查询执行与本地执行</span><span class="sxs-lookup"><span data-stu-id="d6df1-102">Remote vs. Local Execution</span></span>
<span data-ttu-id="d6df1-103">您可以决定以远程方式（即数据库引擎对数据库执行查询）或在本地（[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对本地缓存执行查询）执行您的查询。</span><span class="sxs-lookup"><span data-stu-id="d6df1-103">You can decide to execute your queries either remotely (that is, the database engine executes the query against the database) or locally ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] executes the query against a local cache).</span></span>  
  
## <a name="remote-execution"></a><span data-ttu-id="d6df1-104">远程执行</span><span class="sxs-lookup"><span data-stu-id="d6df1-104">Remote Execution</span></span>  
 <span data-ttu-id="d6df1-105">请考虑下面的查询：</span><span class="sxs-lookup"><span data-stu-id="d6df1-105">Consider the following query:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 <span data-ttu-id="d6df1-106">如果数据库有数千行订单，则在处理其中很小一部分时您不需要将它们全都检索出来。</span><span class="sxs-lookup"><span data-stu-id="d6df1-106">If your database has thousands of rows of orders, you do not want to retrieve them all to process a small subset.</span></span> <span data-ttu-id="d6df1-107">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Data.Linq.EntitySet%601> 类实现了 <xref:System.Linq.IQueryable> 接口。</span><span class="sxs-lookup"><span data-stu-id="d6df1-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.EntitySet%601> class implements the <xref:System.Linq.IQueryable> interface.</span></span> <span data-ttu-id="d6df1-108">这种方式确保了可以以远程方式执行此类查询。</span><span class="sxs-lookup"><span data-stu-id="d6df1-108">This approach makes sure that such queries can be executed remotely.</span></span> <span data-ttu-id="d6df1-109">利用此技术有两大优点：</span><span class="sxs-lookup"><span data-stu-id="d6df1-109">Two major benefits flow from this technique:</span></span>  
  
-   <span data-ttu-id="d6df1-110">不会检索到不需要的数据。</span><span class="sxs-lookup"><span data-stu-id="d6df1-110">Unnecessary data is not retrieved.</span></span>  
  
-   <span data-ttu-id="d6df1-111">由于利用了数据库索引，由数据库引擎执行的查询通常更为高效。</span><span class="sxs-lookup"><span data-stu-id="d6df1-111">A query executed by the database engine is often more efficient because of the database indexes.</span></span>  
  
## <a name="local-execution"></a><span data-ttu-id="d6df1-112">本地执行</span><span class="sxs-lookup"><span data-stu-id="d6df1-112">Local Execution</span></span>  
 <span data-ttu-id="d6df1-113">在其他一些情况下，您可能需要在本地缓存中保留完整的相关实体集。</span><span class="sxs-lookup"><span data-stu-id="d6df1-113">In other situations, you might want to have the complete set of related entities in the local cache.</span></span> <span data-ttu-id="d6df1-114">为此，<xref:System.Data.Linq.EntitySet%601> 提供了 <xref:System.Data.Linq.EntitySet%601.Load%2A> 方法，用于显式加载 <xref:System.Data.Linq.EntitySet%601> 的所有成员。</span><span class="sxs-lookup"><span data-stu-id="d6df1-114">For this purpose, <xref:System.Data.Linq.EntitySet%601> provides the <xref:System.Data.Linq.EntitySet%601.Load%2A> method to explicitly load all the members of the <xref:System.Data.Linq.EntitySet%601>.</span></span>  
  
 <span data-ttu-id="d6df1-115">如果 <xref:System.Data.Linq.EntitySet%601> 已经加载，则后续查询将在本地执行。</span><span class="sxs-lookup"><span data-stu-id="d6df1-115">If an <xref:System.Data.Linq.EntitySet%601> is already loaded, subsequent queries are executed locally.</span></span> <span data-ttu-id="d6df1-116">这种方式在两个方面起到帮助作用：</span><span class="sxs-lookup"><span data-stu-id="d6df1-116">This approach helps in two ways:</span></span>  
  
-   <span data-ttu-id="d6df1-117">如果此完整集必须在本地使用或使用多次，则您可以避免远程查询和与之相关的延迟。</span><span class="sxs-lookup"><span data-stu-id="d6df1-117">If the complete set must be used locally or multiple times, you can avoid remote queries and associated latencies.</span></span>  
  
-   <span data-ttu-id="d6df1-118">实体可以序列化为完整的实体。</span><span class="sxs-lookup"><span data-stu-id="d6df1-118">The entity can be serialized as a complete entity.</span></span>  
  
 <span data-ttu-id="d6df1-119">下面的代码段演示了如何实现本地执行：</span><span class="sxs-lookup"><span data-stu-id="d6df1-119">The following code fragment illustrates how local execution can be obtained:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a><span data-ttu-id="d6df1-120">比较</span><span class="sxs-lookup"><span data-stu-id="d6df1-120">Comparison</span></span>  
 <span data-ttu-id="d6df1-121">这两项功能提供了强大的选项组合：大型集合采用以远程方式执行，小型集合或在需要完整集的情况下在本地执行。</span><span class="sxs-lookup"><span data-stu-id="d6df1-121">These two capabilities provide a powerful combination of options: remote execution for large collections and local execution for small collections or where the complete collection is needed.</span></span> <span data-ttu-id="d6df1-122">您需要通过 <xref:System.Linq.IQueryable> 进行远程执行，对于本地执行，则需要对内存中的 <xref:System.Collections.Generic.IEnumerable%601> 集合执行。</span><span class="sxs-lookup"><span data-stu-id="d6df1-122">You implement remote execution through <xref:System.Linq.IQueryable>, and local execution against an in-memory <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="d6df1-123">若要强制在本地执行 (即<xref:System.Collections.Generic.IEnumerable%601>)，请参阅[将一种类型转换为泛型 IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)。</span><span class="sxs-lookup"><span data-stu-id="d6df1-123">To force local execution (that is, <xref:System.Collections.Generic.IEnumerable%601>), see [Convert a Type to a Generic IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span></span>  
  
### <a name="queries-against-unordered-sets"></a><span data-ttu-id="d6df1-124">针对无序集的查询</span><span class="sxs-lookup"><span data-stu-id="d6df1-124">Queries Against Unordered Sets</span></span>  
 <span data-ttu-id="d6df1-125">请注意实现的本地集合之间的重要区别<xref:System.Collections.Generic.List%601>并提供了执行的远程查询的集合*无序集*关系数据库中。</span><span class="sxs-lookup"><span data-stu-id="d6df1-125">Note the important difference between a local collection that implements <xref:System.Collections.Generic.List%601> and a collection that provides remote queries executed against *unordered sets* in a relational database.</span></span> <xref:System.Collections.Generic.List%601> <span data-ttu-id="d6df1-126">如使用索引值的方法需要列表语义，列表语义通常无法通过针对无序集的远程查询获得。</span><span class="sxs-lookup"><span data-stu-id="d6df1-126">methods such as those that use index values require list semantics, which typically cannot be obtained through a remote query against an unordered set.</span></span> <span data-ttu-id="d6df1-127">因此，此类方法隐式加载 <xref:System.Data.Linq.EntitySet%601>，以允许本地执行。</span><span class="sxs-lookup"><span data-stu-id="d6df1-127">For this reason, such methods implicitly load the <xref:System.Data.Linq.EntitySet%601> to allow local execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6df1-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6df1-128">See also</span></span>

- [<span data-ttu-id="d6df1-129">查询概念</span><span class="sxs-lookup"><span data-stu-id="d6df1-129">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
