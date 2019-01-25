---
title: 事务和并发性
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: f5efa8f25e3cd4dedec9e5a9c99db28320a4d93e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494049"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="90985-102">事务和并发性</span><span class="sxs-lookup"><span data-stu-id="90985-102">Transactions and Concurrency</span></span>
<span data-ttu-id="90985-103">事务由作为包执行的单个命令或一组命令组成。</span><span class="sxs-lookup"><span data-stu-id="90985-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="90985-104">通过事务可以将多个操合并为单个工作单元。</span><span class="sxs-lookup"><span data-stu-id="90985-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="90985-105">如果在事务中的某一点发生故障，则所有更新都可以回滚到其事务前状态。</span><span class="sxs-lookup"><span data-stu-id="90985-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="90985-106">事务必须符合 ACID 属性（原子性、一致性、隔离和持久性）才能保证数据的一致性。</span><span class="sxs-lookup"><span data-stu-id="90985-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="90985-107">大多数关系数据库系统（例如 Microsoft SQL Server）都可在客户端应用程序执行更新、插入或删除操作时为事务提供锁定、日志记录和事务管理功能，以此来支持事务。</span><span class="sxs-lookup"><span data-stu-id="90985-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90985-108">如果锁定持续时间过长，则涉及多个资源的事务可能会降低并发性。</span><span class="sxs-lookup"><span data-stu-id="90985-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="90985-109">因此，事务应尽量保持简短。</span><span class="sxs-lookup"><span data-stu-id="90985-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="90985-110">如果一个事务涉及同一个数据库或服务器中的多个表，则存储过程中的显式事务通常可以更好地执行。</span><span class="sxs-lookup"><span data-stu-id="90985-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="90985-111">您可以通过使用 Transact-SQL `BEGIN TRANSACTION`、`COMMIT TRANSACTION` 和 `ROLLBACK TRANSACTION` 语句在 SQL Server 存储过程中创建事务。</span><span class="sxs-lookup"><span data-stu-id="90985-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="90985-112">有关更多信息，请参见 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="90985-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="90985-113">涉及不同的资源管理器，例如 SQL Server 和 Oracle 之间的事务的事务需要分布式的事务。</span><span class="sxs-lookup"><span data-stu-id="90985-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90985-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="90985-114">In This Section</span></span>  
 [<span data-ttu-id="90985-115">本地事务</span><span class="sxs-lookup"><span data-stu-id="90985-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="90985-116">演示如何对数据库执行事务。</span><span class="sxs-lookup"><span data-stu-id="90985-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="90985-117">分布式事务</span><span class="sxs-lookup"><span data-stu-id="90985-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="90985-118">描述如何在 ADO.NET 中执行分布式事务。</span><span class="sxs-lookup"><span data-stu-id="90985-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="90985-119">System.Transactions 与 SQL Server 的集成</span><span class="sxs-lookup"><span data-stu-id="90985-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="90985-120">介绍<xref:System.Transactions>与 SQL Server 的集成来使用分布式事务。</span><span class="sxs-lookup"><span data-stu-id="90985-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="90985-121">开放式并发</span><span class="sxs-lookup"><span data-stu-id="90985-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="90985-122">描述开放式并发和保守式并发，以及如何测试并发冲突。</span><span class="sxs-lookup"><span data-stu-id="90985-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90985-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="90985-123">See also</span></span>
- [<span data-ttu-id="90985-124">事务基础知识</span><span class="sxs-lookup"><span data-stu-id="90985-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)
- [<span data-ttu-id="90985-125">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="90985-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="90985-126">命令和参数</span><span class="sxs-lookup"><span data-stu-id="90985-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="90985-127">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="90985-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="90985-128">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="90985-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [<span data-ttu-id="90985-129">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="90985-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
