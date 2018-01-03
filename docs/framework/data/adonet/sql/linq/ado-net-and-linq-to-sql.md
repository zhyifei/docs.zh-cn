---
title: "ADO.NET 和 LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ae0b5aeb658b67434cea187839833e24007ee77e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="64fe7-102">ADO.NET 和 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="64fe7-102">ADO.NET and LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="64fe7-103">是的一部分[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]系列技术。</span><span class="sxs-lookup"><span data-stu-id="64fe7-103"> is part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies.</span></span> <span data-ttu-id="64fe7-104">它基于由 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 提供程序模型提供的服务。</span><span class="sxs-lookup"><span data-stu-id="64fe7-104">It is based on services provided by the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] provider model.</span></span> <span data-ttu-id="64fe7-105">因此，您可以将 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 代码与现有的 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 应用程序混合在一起，将当前 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 解决方案迁移到 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="64fe7-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] applications and migrate current [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="64fe7-106">下图高度概括了这种关系。</span><span class="sxs-lookup"><span data-stu-id="64fe7-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="64fe7-107">![LINQ to SQL 以及 ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="64fe7-107">![LINQ to SQL and ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="64fe7-108">连接</span><span class="sxs-lookup"><span data-stu-id="64fe7-108">Connections</span></span>  
 <span data-ttu-id="64fe7-109">在创建 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 时，可以提供现有 <xref:System.Data.Linq.DataContext> 连接。</span><span class="sxs-lookup"><span data-stu-id="64fe7-109">You can supply an existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="64fe7-110">对 <xref:System.Data.Linq.DataContext> 的所有操作（包括查询）都使用所提供的这个连接。</span><span class="sxs-lookup"><span data-stu-id="64fe7-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="64fe7-111">如果此连接已经打开，则在您使用完此连接时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会保持它的打开状态不变。</span><span class="sxs-lookup"><span data-stu-id="64fe7-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="64fe7-112">您始终可以访问此连接，并可以使用 <xref:System.Data.Linq.DataContext.Connection%2A> 属性自行关闭它，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="64fe7-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="64fe7-113">事务</span><span class="sxs-lookup"><span data-stu-id="64fe7-113">Transactions</span></span>  
 <span data-ttu-id="64fe7-114">当您的应用程序已经启动了您自己的数据库事务并且您希望您的 <xref:System.Data.Linq.DataContext> 包含在内时，您可以向您的 <xref:System.Data.Linq.DataContext> 提供此事务。</span><span class="sxs-lookup"><span data-stu-id="64fe7-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="64fe7-115">通过 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 创建事务的首选方法是使用 <xref:System.Transactions.TransactionScope> 对象。</span><span class="sxs-lookup"><span data-stu-id="64fe7-115">The preferred method of doing transactions with the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="64fe7-116">通过使用此方法，你可以创建跨数据库及其他驻留在内存中的资源管理器执行的分布式事务。</span><span class="sxs-lookup"><span data-stu-id="64fe7-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="64fe7-117">事务范围几乎不需要资源就可以启动。</span><span class="sxs-lookup"><span data-stu-id="64fe7-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="64fe7-118">它们仅在事务范围内存在多个连接时才将自身提升为分布式事务。</span><span class="sxs-lookup"><span data-stu-id="64fe7-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="64fe7-119">不能将此方法用于所有数据库。</span><span class="sxs-lookup"><span data-stu-id="64fe7-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="64fe7-120">例如，SqlClient 连接在针对 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] 服务器使用时无法提升系统事务。</span><span class="sxs-lookup"><span data-stu-id="64fe7-120">For example, the SqlClient connection cannot promote system transactions when it works against a [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] server.</span></span> <span data-ttu-id="64fe7-121">它采取的方法是，只要它发现有使用事务范围的情况，它就会自动向完整的分布式事务登记。</span><span class="sxs-lookup"><span data-stu-id="64fe7-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="64fe7-122">直接 SQL 命令</span><span class="sxs-lookup"><span data-stu-id="64fe7-122">Direct SQL Commands</span></span>  
 <span data-ttu-id="64fe7-123">有时您可能会遇到这样的情况：<xref:System.Data.Linq.DataContext> 查询或提交更改的能力不足以满足您需要执行的专门任务的需要。</span><span class="sxs-lookup"><span data-stu-id="64fe7-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="64fe7-124">在这些情况下，您可以使用 <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 方法向数据库发出 SQL 命令，将查询结果转换成对象。</span><span class="sxs-lookup"><span data-stu-id="64fe7-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="64fe7-125">例如，假定 `Customer` 类的数据分布在两个表（customer1 和 customer2）中。</span><span class="sxs-lookup"><span data-stu-id="64fe7-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="64fe7-126">下面的查询将返回 `Customer` 对象的序列：</span><span class="sxs-lookup"><span data-stu-id="64fe7-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="64fe7-127">只要表格结果中的列名与您的实体类的列属性匹配，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 就会为您创建不在任何 SQL 查询范围之内的对象。</span><span class="sxs-lookup"><span data-stu-id="64fe7-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="64fe7-128">参数</span><span class="sxs-lookup"><span data-stu-id="64fe7-128">Parameters</span></span>  
 <span data-ttu-id="64fe7-129"><xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 方法接受参数。</span><span class="sxs-lookup"><span data-stu-id="64fe7-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="64fe7-130">下面的代码执行参数化查询：</span><span class="sxs-lookup"><span data-stu-id="64fe7-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="64fe7-131">在查询文本中使用 `Console.WriteLine()` 和 `String.Format()` 所用的大括号表示法来表示参数。</span><span class="sxs-lookup"><span data-stu-id="64fe7-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="64fe7-132">`String.Format()` 获取您提供的查询字符串，然后将括在大括号内的参数替换为所生成的参数名，如 `@p0`、`@p1` …… `@p(n)`。</span><span class="sxs-lookup"><span data-stu-id="64fe7-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64fe7-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="64fe7-133">See Also</span></span>  
 [<span data-ttu-id="64fe7-134">背景信息</span><span class="sxs-lookup"><span data-stu-id="64fe7-134">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="64fe7-135">如何：重复使用 ADO.NET 命令和 DataContext 之间的连接</span><span class="sxs-lookup"><span data-stu-id="64fe7-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
