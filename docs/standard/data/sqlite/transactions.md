---
title: 事务
ms.date: 12/13/2019
description: 了解如何使用事务。
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450380"
---
# <a name="transactions"></a><span data-ttu-id="30077-103">事务</span><span class="sxs-lookup"><span data-stu-id="30077-103">Transactions</span></span>

<span data-ttu-id="30077-104">通过事务可以将多个 SQL 语句组合成单个工作单元，并将其作为一个原子单元提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="30077-104">Transactions let you group multiple SQL statements into a single unit of work that is committed to the database as one atomic unit.</span></span> <span data-ttu-id="30077-105">如果事务中的任何语句失败，则可以回滚前面语句所做的更改。</span><span class="sxs-lookup"><span data-stu-id="30077-105">If any statement in the transaction fails, changes made by the previous statements can be rolled back.</span></span> <span data-ttu-id="30077-106">当事务开始时，数据库的初始状态为 "已启动"。</span><span class="sxs-lookup"><span data-stu-id="30077-106">The initial state of the database when the transaction was started is preserved.</span></span> <span data-ttu-id="30077-107">如果对数据库进行了大量更改，则使用事务还可以提高 SQLite 的性能。</span><span class="sxs-lookup"><span data-stu-id="30077-107">Using a transaction can also improve performance on SQLite when making numerous changes to the database at once.</span></span>

## <a name="concurrency"></a><span data-ttu-id="30077-108">并发</span><span class="sxs-lookup"><span data-stu-id="30077-108">Concurrency</span></span>

<span data-ttu-id="30077-109">在 SQLite 中，一次只允许一个事务在数据库中具有挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="30077-109">In SQLite, only one transaction is allowed to have changes pending in the database at a time.</span></span> <span data-ttu-id="30077-110">因此，如果另一个事务需要很长时间才能完成，则对 <xref:Microsoft.Data.Sqlite.SqliteCommand> 的调用 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> 和 `Execute` 方法可能会超时。</span><span class="sxs-lookup"><span data-stu-id="30077-110">Because of this, calls to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> and the `Execute` methods on <xref:Microsoft.Data.Sqlite.SqliteCommand> may time out if another transaction takes too long to complete.</span></span>

<span data-ttu-id="30077-111">有关锁定、重试和超时的详细信息，请参阅[数据库错误](database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="30077-111">For more information about locking, retries, and timeouts, see [Database errors](database-errors.md).</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="30077-112">隔离级别</span><span class="sxs-lookup"><span data-stu-id="30077-112">Isolation levels</span></span>

<span data-ttu-id="30077-113">默认情况下，在 SQLite 中**可序列化**事务。</span><span class="sxs-lookup"><span data-stu-id="30077-113">Transactions are **serializable** by default in SQLite.</span></span> <span data-ttu-id="30077-114">此隔离级别保证在事务中所做的任何更改都是完全隔离的。</span><span class="sxs-lookup"><span data-stu-id="30077-114">This isolation level guarantees that any changes made within a transaction are completely isolated.</span></span> <span data-ttu-id="30077-115">在事务之外执行的其他语句不受事务更改的影响。</span><span class="sxs-lookup"><span data-stu-id="30077-115">Other statements executed outside of the transaction aren't affected by the transaction's changes.</span></span>

<span data-ttu-id="30077-116">SQLite 还支持使用共享缓存时**未提交读**。</span><span class="sxs-lookup"><span data-stu-id="30077-116">SQLite also supports **read uncommitted** when using a shared cache.</span></span> <span data-ttu-id="30077-117">此级别允许脏读、不可重复读取和幻像：</span><span class="sxs-lookup"><span data-stu-id="30077-117">This level allows dirty reads, nonrepeatable reads, and phantoms:</span></span>

- <span data-ttu-id="30077-118">当事务外部的查询返回一个事务中的挂起的更改，但该事务中的更改将回滚时，将发生*脏读*。</span><span class="sxs-lookup"><span data-stu-id="30077-118">A *dirty read* occurs when changes pending in one transaction are returned by a query outside of the transaction, but the changes in the transaction are rolled back.</span></span> <span data-ttu-id="30077-119">结果包含从不实际提交到数据库的数据。</span><span class="sxs-lookup"><span data-stu-id="30077-119">The results contain data that was never actually committed to the database.</span></span>

- <span data-ttu-id="30077-120">当事务两次查询相同的行时，将发生*不可重复读取*，但结果不同，因为它在两个查询之间由另一个事务更改。</span><span class="sxs-lookup"><span data-stu-id="30077-120">A *nonrepeatable read* occurs when a transaction queries same row twice, but the results are different because it was changed between the two queries by another transaction.</span></span>

- <span data-ttu-id="30077-121">*幻像*是在事务期间更改或添加以满足查询的 where 子句的行。</span><span class="sxs-lookup"><span data-stu-id="30077-121">*Phantoms* are rows that get changed or added to meet the where clause of a query during a transaction.</span></span> <span data-ttu-id="30077-122">如果允许，同一查询在同一事务中执行两次时，可能返回不同的行。</span><span class="sxs-lookup"><span data-stu-id="30077-122">If allowed, the same query could return different rows when executed twice in the same transaction.</span></span>

<span data-ttu-id="30077-123">IsolationLevel 将传递给 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> 的视为最低级别。</span><span class="sxs-lookup"><span data-stu-id="30077-123">Microsoft.Data.Sqlite treats the IsolationLevel passed to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> as a minimum level.</span></span> <span data-ttu-id="30077-124">实际隔离级别将提升为读取未提交或可序列化。</span><span class="sxs-lookup"><span data-stu-id="30077-124">The actual isolation level will be promoted to either read uncommitted or serializable.</span></span>

<span data-ttu-id="30077-125">下面的代码模拟脏读。</span><span class="sxs-lookup"><span data-stu-id="30077-125">The following code simulates a dirty read.</span></span> <span data-ttu-id="30077-126">请注意，连接字符串必须包括 `Cache=Shared`。</span><span class="sxs-lookup"><span data-stu-id="30077-126">Note, the connection string must include `Cache=Shared`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
