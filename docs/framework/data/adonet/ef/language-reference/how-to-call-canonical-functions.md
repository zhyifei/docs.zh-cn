---
title: 如何：调用规范函数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
ms.openlocfilehash: 6e555b3d896862db491b34e11564e70bbe2d15eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213150"
---
# <a name="how-to-call-canonical-functions"></a><span data-ttu-id="016d0-102">如何：调用规范函数</span><span class="sxs-lookup"><span data-stu-id="016d0-102">How to: Call Canonical Functions</span></span>
<span data-ttu-id="016d0-103"><xref:System.Data.Objects.EntityFunctions> 类包含公开要在 LINQ to Entities 查询中使用的规范函数的方法。</span><span class="sxs-lookup"><span data-stu-id="016d0-103">The <xref:System.Data.Objects.EntityFunctions> class contains methods that expose canonical functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="016d0-104">有关规范函数的信息，请参阅[规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="016d0-104">For information about canonical functions, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="016d0-105"><xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> 类中的 <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> 和 <xref:System.Data.Objects.EntityFunctions> 方法不具有规范函数等效性。</span><span class="sxs-lookup"><span data-stu-id="016d0-105">The <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> and <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> methods in the <xref:System.Data.Objects.EntityFunctions> class do not have canonical function equivalents.</span></span>  
  
 <span data-ttu-id="016d0-106">可以直接调用对一组值执行计算并返回单个值的规范函数（也成为聚合规范函数）。</span><span class="sxs-lookup"><span data-stu-id="016d0-106">Canonical functions that perform a calculation on a set of values and return a single value (also known as aggregate canonical functions) can be directly invoked.</span></span> <span data-ttu-id="016d0-107">其他规范函数只能作为 LINQ to Entities 查询的一部分调用。</span><span class="sxs-lookup"><span data-stu-id="016d0-107">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="016d0-108">若要直接调用聚合函数，必须将 <xref:System.Data.Objects.ObjectQuery%601> 传递到此函数。</span><span class="sxs-lookup"><span data-stu-id="016d0-108">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="016d0-109">有关更多信息，请参见下面的第二个示例。</span><span class="sxs-lookup"><span data-stu-id="016d0-109">For more information, see the second example below.</span></span>  
  
 <span data-ttu-id="016d0-110">可以在 LINQ to Entities 查询中使用公共语言运行时 (CLR) 方法调用某些规范函数。</span><span class="sxs-lookup"><span data-stu-id="016d0-110">You can call some canonical functions by using common language runtime (CLR) methods in LINQ to Entities queries.</span></span> <span data-ttu-id="016d0-111">有关 CLR 方法映射到规范函数的列表，请参阅[CLR 方法至规范函数映射](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="016d0-111">For a list of CLR methods that map to canonical functions, see [CLR Method to Canonical Function Mapping](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="016d0-112">示例</span><span class="sxs-lookup"><span data-stu-id="016d0-112">Example</span></span>  
 <span data-ttu-id="016d0-113">下面的示例使用[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)。</span><span class="sxs-lookup"><span data-stu-id="016d0-113">The following example uses the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples).</span></span> <span data-ttu-id="016d0-114">此示例执行一个 LINQ to Entities 查询，该查询使用 <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> 方法返回 `SellEndDate` 与 `SellStartDate` 之间相差小于 365 天的所有产品：</span><span class="sxs-lookup"><span data-stu-id="016d0-114">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> method to return all products for which the difference between `SellEndDate` and `SellStartDate` is less than 365 days:</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="016d0-115">示例</span><span class="sxs-lookup"><span data-stu-id="016d0-115">Example</span></span>  
 <span data-ttu-id="016d0-116">下面的示例使用[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)。</span><span class="sxs-lookup"><span data-stu-id="016d0-116">The following example uses the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples).</span></span> <span data-ttu-id="016d0-117">此示例直接调用聚合 <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> 方法，以返回 `SalesOrderHeader` 小计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="016d0-117">The example calls the aggregate <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> method directly to return the standard deviation of `SalesOrderHeader` subtotals.</span></span> <span data-ttu-id="016d0-118">请注意，应将 <xref:System.Data.Objects.ObjectQuery%601> 传递给此函数，这样，就可以调用它而不需要使它成为 LINQ to Entities 查询的一部分。</span><span class="sxs-lookup"><span data-stu-id="016d0-118">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="016d0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="016d0-119">See also</span></span>

- [<span data-ttu-id="016d0-120">在 LINQ to Entities 查询中调用函数</span><span class="sxs-lookup"><span data-stu-id="016d0-120">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="016d0-121">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="016d0-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
