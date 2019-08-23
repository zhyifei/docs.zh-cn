---
title: 如何：调用数据库函数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: dd440be3f73eb2f02a269a8cad29f0fe30920836
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936027"
---
# <a name="how-to-call-database-functions"></a><span data-ttu-id="cb85c-102">如何：调用数据库函数</span><span class="sxs-lookup"><span data-stu-id="cb85c-102">How to: Call Database Functions</span></span>
<span data-ttu-id="cb85c-103"><xref:System.Data.Objects.SqlClient.SqlFunctions> 类包含公开要在 LINQ to Entities 查询中使用的 SQL Server 函数的方法。</span><span class="sxs-lookup"><span data-stu-id="cb85c-103">The <xref:System.Data.Objects.SqlClient.SqlFunctions> class contains methods that expose SQL Server functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="cb85c-104">当您在 LINQ to Entities 查询中使用 <xref:System.Data.Objects.SqlClient.SqlFunctions> 方法时，将在数据库中执行相应的数据库函数。</span><span class="sxs-lookup"><span data-stu-id="cb85c-104">When you use <xref:System.Data.Objects.SqlClient.SqlFunctions> methods in LINQ to Entities queries, the corresponding database functions are executed in the database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb85c-105">可以直接调用对一组值执行计算并返回单个值的数据库函数（也称为聚合数据库函数）。</span><span class="sxs-lookup"><span data-stu-id="cb85c-105">Database functions that perform a calculation on a set of values and return a single value (also known as aggregate database functions) can be directly invoked.</span></span> <span data-ttu-id="cb85c-106">其他规范函数只能作为 LINQ to Entities 查询的一部分调用。</span><span class="sxs-lookup"><span data-stu-id="cb85c-106">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="cb85c-107">若要直接调用聚合函数，必须将 <xref:System.Data.Objects.ObjectQuery%601> 传递到此函数。</span><span class="sxs-lookup"><span data-stu-id="cb85c-107">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="cb85c-108">有关更多信息，请参见下面的第二个示例。</span><span class="sxs-lookup"><span data-stu-id="cb85c-108">For more information, see the second example below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb85c-109"><xref:System.Data.Objects.SqlClient.SqlFunctions> 类中的方法特定于 SQL Server 函数。</span><span class="sxs-lookup"><span data-stu-id="cb85c-109">The methods in the <xref:System.Data.Objects.SqlClient.SqlFunctions> class are specific to SQL Server functions.</span></span> <span data-ttu-id="cb85c-110">通过其他提供程序可能能够提供公开数据库函数的相似类。</span><span class="sxs-lookup"><span data-stu-id="cb85c-110">Similar classes that expose database functions may be available through other providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb85c-111">示例</span><span class="sxs-lookup"><span data-stu-id="cb85c-111">Example</span></span>  
 <span data-ttu-id="cb85c-112">下面的示例使用[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)。</span><span class="sxs-lookup"><span data-stu-id="cb85c-112">The following example uses the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples).</span></span> <span data-ttu-id="cb85c-113">此示例执行一个 LINQ to Entities 查询，该查询使用 <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> 方法返回其姓氏以“Si”开头的所有联系人：</span><span class="sxs-lookup"><span data-stu-id="cb85c-113">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> method to return all contacts whose last name starts with "Si":</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="cb85c-114">示例</span><span class="sxs-lookup"><span data-stu-id="cb85c-114">Example</span></span>  
 <span data-ttu-id="cb85c-115">下面的示例使用[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)。</span><span class="sxs-lookup"><span data-stu-id="cb85c-115">The following example uses the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples).</span></span> <span data-ttu-id="cb85c-116">此示例直接调用聚合 <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="cb85c-116">The example calls the aggregate <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> method directly.</span></span> <span data-ttu-id="cb85c-117">请注意，应将 <xref:System.Data.Objects.ObjectQuery%601> 传递给此函数，这样，就可以调用它而不需要使它成为 LINQ to Entities 查询的一部分。</span><span class="sxs-lookup"><span data-stu-id="cb85c-117">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cb85c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb85c-118">See also</span></span>

- [<span data-ttu-id="cb85c-119">在 LINQ to Entities 查询中调用函数</span><span class="sxs-lookup"><span data-stu-id="cb85c-119">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="cb85c-120">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="cb85c-120">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
