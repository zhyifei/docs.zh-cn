---
title: 启用多个活动结果集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
ms.openlocfilehash: 633aaa4a9540d0895252e56dbeabd97200081fc9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877677"
---
# <a name="enabling-multiple-active-result-sets"></a><span data-ttu-id="ee472-102">启用多个活动结果集</span><span class="sxs-lookup"><span data-stu-id="ee472-102">Enabling Multiple Active Result Sets</span></span>
<span data-ttu-id="ee472-103">多个活动结果集 (MARS) 是一项用于 SQL Server 的功能，可用来对单个连接执行多个批处理。</span><span class="sxs-lookup"><span data-stu-id="ee472-103">Multiple Active Result Sets (MARS) is a feature that works with SQL Server to allow the execution of multiple batches on a single connection.</span></span> <span data-ttu-id="ee472-104">如果对 SQL Server 启用了 MARS，使用的每个命令对象将向该连接添加一个会话。</span><span class="sxs-lookup"><span data-stu-id="ee472-104">When MARS is enabled for use with SQL Server, each command object used adds a session to the connection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee472-105">一个 MARS 会话打开一个逻辑连接以供 MARS 使用，然后为每个活动命令打开一个逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="ee472-105">A single MARS session opens one logical connection for MARS to use and then one logical connection for each active command.</span></span>  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a><span data-ttu-id="ee472-106">在连接字符串中启用和禁用 MARS</span><span class="sxs-lookup"><span data-stu-id="ee472-106">Enabling and Disabling MARS in the Connection String</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee472-107">以下连接字符串使用示例**AdventureWorks** SQL Server 中包含的数据库。</span><span class="sxs-lookup"><span data-stu-id="ee472-107">The following connection strings use the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="ee472-108">提供的连接字符串假定数据库安装在名为 MSSQL1 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="ee472-108">The connection strings provided assume that the database is installed on a server named MSSQL1.</span></span> <span data-ttu-id="ee472-109">根据环境的需要修改连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ee472-109">Modify the connection string as necessary for your environment.</span></span>  
  
 <span data-ttu-id="ee472-110">默认情况下禁用 MARS 功能。</span><span class="sxs-lookup"><span data-stu-id="ee472-110">The MARS feature is disabled by default.</span></span> <span data-ttu-id="ee472-111">可以通过在连接字符串中添加“MultipleActiveResultSets=True”关键字对来启用此功能。</span><span class="sxs-lookup"><span data-stu-id="ee472-111">It can be enabled by adding the "MultipleActiveResultSets=True" keyword pair to your connection string.</span></span> <span data-ttu-id="ee472-112">“True”是启用 MARS 的唯一有效值。</span><span class="sxs-lookup"><span data-stu-id="ee472-112">"True" is the only valid value for enabling MARS.</span></span> <span data-ttu-id="ee472-113">以下示例演示如何连接到 SQL Server 实例以及如何指定应启用 MARS。</span><span class="sxs-lookup"><span data-stu-id="ee472-113">The following example demonstrates how to connect to an instance of SQL Server and how to specify that MARS should be enabled.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 <span data-ttu-id="ee472-114">可以通过在连接字符串中添加“MultipleActiveResultSets=False”关键字对来禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="ee472-114">You can disable MARS by adding the "MultipleActiveResultSets=False" keyword pair to your connection string.</span></span> <span data-ttu-id="ee472-115">“False”是禁用 MARS 的唯一有效值。</span><span class="sxs-lookup"><span data-stu-id="ee472-115">"False" is the only valid value for disabling MARS.</span></span> <span data-ttu-id="ee472-116">以下连接字符串演示如何禁用 MARS。</span><span class="sxs-lookup"><span data-stu-id="ee472-116">The following connection string demonstrates how to disable MARS.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a><span data-ttu-id="ee472-117">使用 MARS 时的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="ee472-117">Special Considerations When Using MARS</span></span>  
 <span data-ttu-id="ee472-118">通常情况下，现有的应用程序不需要修改，即可使用启用 MARS 的连接。</span><span class="sxs-lookup"><span data-stu-id="ee472-118">In general, existing applications should not need modification to use a MARS-enabled connection.</span></span> <span data-ttu-id="ee472-119">但是，如果要在应用程序中使用 MARS 功能，应了解下列特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="ee472-119">However, if you wish to use MARS features in your applications, you should understand the following special considerations.</span></span>  
  
### <a name="statement-interleaving"></a><span data-ttu-id="ee472-120">语句交替</span><span class="sxs-lookup"><span data-stu-id="ee472-120">Statement Interleaving</span></span>  
 <span data-ttu-id="ee472-121">MARS 操作在服务器上同步执行。</span><span class="sxs-lookup"><span data-stu-id="ee472-121">MARS operations execute synchronously on the server.</span></span> <span data-ttu-id="ee472-122">允许 SELECT 和 BULK INSERT 语句的语句交替。</span><span class="sxs-lookup"><span data-stu-id="ee472-122">Statement interleaving of SELECT and BULK INSERT statements is allowed.</span></span> <span data-ttu-id="ee472-123">但是，数据操作语言 (DML) 和数据定义语言 (DDL) 语句会自动执行。</span><span class="sxs-lookup"><span data-stu-id="ee472-123">However, data manipulation language (DML) and data definition language (DDL) statements execute atomically.</span></span> <span data-ttu-id="ee472-124">将阻止任何在执行原子批处理时尝试执行的语句。</span><span class="sxs-lookup"><span data-stu-id="ee472-124">Any statements attempting to execute while an atomic batch is executing are blocked.</span></span> <span data-ttu-id="ee472-125">服务器上的并行执行不是 MARS 功能。</span><span class="sxs-lookup"><span data-stu-id="ee472-125">Parallel execution at the server is not a MARS feature.</span></span>  
  
 <span data-ttu-id="ee472-126">如果在 MARS 连接下提交两个批处理，其中一个批处理包含 SELECT 语句，另一个包含 DML 语句，DML 可以在 SELECT 语句执行过程中开始执行。</span><span class="sxs-lookup"><span data-stu-id="ee472-126">If two batches are submitted under a MARS connection, one of them containing a SELECT statement, the other containing a DML statement, the DML can begin execution within execution of the SELECT statement.</span></span> <span data-ttu-id="ee472-127">但是，DML 语句必须运行完成，SELECT 语句才可以继续执行。</span><span class="sxs-lookup"><span data-stu-id="ee472-127">However, the DML statement must run to completion before the SELECT statement can make progress.</span></span> <span data-ttu-id="ee472-128">如果两个语句在相同事务下运行，读取操作将看不到 DML 语句在 SELECT 语句开始执行后所作的任何更改。</span><span class="sxs-lookup"><span data-stu-id="ee472-128">If both statements are running under the same transaction, any changes made by a DML statement after the SELECT statement has started execution are not visible to the read operation.</span></span>  
  
 <span data-ttu-id="ee472-129">SELECT 语句中的 WAITFOR 语句在等待时不生成事务，即直到生成第一行时才生成事务。</span><span class="sxs-lookup"><span data-stu-id="ee472-129">A WAITFOR statement inside a SELECT statement does not yield the transaction while it is waiting, that is, until the first row is produced.</span></span> <span data-ttu-id="ee472-130">这意味着在 WAITFOR 语句等待时，无法在相同连接内执行任何其他批处理。</span><span class="sxs-lookup"><span data-stu-id="ee472-130">This implies that no other batches can execute within the same connection while a WAITFOR statement is waiting.</span></span>  
  
### <a name="mars-session-cache"></a><span data-ttu-id="ee472-131">MARS 会话缓存</span><span class="sxs-lookup"><span data-stu-id="ee472-131">MARS Session Cache</span></span>  
 <span data-ttu-id="ee472-132">如果打开启用了 MARS 的连接，将创建一个逻辑会话，这样会增加系统开销。</span><span class="sxs-lookup"><span data-stu-id="ee472-132">When a connection is opened with MARS enabled, a logical session is created, which adds additional overhead.</span></span> <span data-ttu-id="ee472-133">若要尽量减少开销并提高性能， **SqlClient**缓存 MARS 会话在一个连接。</span><span class="sxs-lookup"><span data-stu-id="ee472-133">To minimize overhead and enhance performance, **SqlClient** caches the MARS session within a connection.</span></span> <span data-ttu-id="ee472-134">缓存最多可以包含 10 个 MARS 会话。</span><span class="sxs-lookup"><span data-stu-id="ee472-134">The cache contains at most 10 MARS sessions.</span></span> <span data-ttu-id="ee472-135">用户不可调整此值。</span><span class="sxs-lookup"><span data-stu-id="ee472-135">This value is not user adjustable.</span></span> <span data-ttu-id="ee472-136">如果达到会话限制，将创建一个新会话 — 不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ee472-136">If the session limit is reached, a new session is created—an error is not generated.</span></span> <span data-ttu-id="ee472-137">缓存及其包含的会话针对特定连接；不在连接之间共享。</span><span class="sxs-lookup"><span data-stu-id="ee472-137">The cache and sessions contained in it are per-connection; they are not shared across connections.</span></span> <span data-ttu-id="ee472-138">会话释放后，除非已达到池的上限，否则，将返回池中。</span><span class="sxs-lookup"><span data-stu-id="ee472-138">When a session is released, it is returned to the pool unless the pool's upper limit has been reached.</span></span> <span data-ttu-id="ee472-139">如果缓存池已满，会话将关闭。</span><span class="sxs-lookup"><span data-stu-id="ee472-139">If the cache pool is full, the session is closed.</span></span> <span data-ttu-id="ee472-140">MARS 会话不会过期。</span><span class="sxs-lookup"><span data-stu-id="ee472-140">MARS sessions do not expire.</span></span> <span data-ttu-id="ee472-141">只在连接对象断开后才进行清理。</span><span class="sxs-lookup"><span data-stu-id="ee472-141">They are only cleaned up when the connection object is disposed.</span></span> <span data-ttu-id="ee472-142">MARS 会话缓存不会预加载。</span><span class="sxs-lookup"><span data-stu-id="ee472-142">The MARS session cache is not preloaded.</span></span> <span data-ttu-id="ee472-143">如果应用程序需要更多的会话，将加载该会话。</span><span class="sxs-lookup"><span data-stu-id="ee472-143">It is loaded as the application requires more sessions.</span></span>  
  
### <a name="thread-safety"></a><span data-ttu-id="ee472-144">线程安全</span><span class="sxs-lookup"><span data-stu-id="ee472-144">Thread Safety</span></span>  
 <span data-ttu-id="ee472-145">MARS 操作不是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="ee472-145">MARS operations are not thread-safe.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="ee472-146">连接池</span><span class="sxs-lookup"><span data-stu-id="ee472-146">Connection Pooling</span></span>  
 <span data-ttu-id="ee472-147">启用 MARS 的连接像任何其他连接一样建立池连接。</span><span class="sxs-lookup"><span data-stu-id="ee472-147">MARS-enabled connections are pooled like any other connection.</span></span> <span data-ttu-id="ee472-148">如果应用程序打开两个连接，一个启用了 MARS，一个禁用了 MARS，这两个连接将位于独立的池中。</span><span class="sxs-lookup"><span data-stu-id="ee472-148">If an application opens two connections, one with MARS enabled and one with MARS disabled, the two connections are in separate pools.</span></span> <span data-ttu-id="ee472-149">有关详细信息，请参阅 [SQL Server 连接池 (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)。</span><span class="sxs-lookup"><span data-stu-id="ee472-149">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
### <a name="sql-server-batch-execution-environment"></a><span data-ttu-id="ee472-150">SQL Server 批处理执行环境</span><span class="sxs-lookup"><span data-stu-id="ee472-150">SQL Server Batch Execution Environment</span></span>  
 <span data-ttu-id="ee472-151">打开连接时，将定义默认的环境。</span><span class="sxs-lookup"><span data-stu-id="ee472-151">When a connection is opened, a default environment is defined.</span></span> <span data-ttu-id="ee472-152">然后，将此环境复制到逻辑 MARS 会话中。</span><span class="sxs-lookup"><span data-stu-id="ee472-152">This environment is then copied into a logical MARS session.</span></span>  
  
 <span data-ttu-id="ee472-153">批处理执行环境包括下列组件：</span><span class="sxs-lookup"><span data-stu-id="ee472-153">The batch execution environment includes the following components:</span></span>  
  
- <span data-ttu-id="ee472-154">设置选项（例如 ANSI_NULLS、DATE_FORMAT、LANGUAGE、TEXTSIZE）</span><span class="sxs-lookup"><span data-stu-id="ee472-154">Set options (for example, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span></span>  
  
- <span data-ttu-id="ee472-155">安全上下文（用户/应用程序角色）</span><span class="sxs-lookup"><span data-stu-id="ee472-155">Security context (user/application role)</span></span>  
  
- <span data-ttu-id="ee472-156">数据库上下文（当前数据库）</span><span class="sxs-lookup"><span data-stu-id="ee472-156">Database context (current database)</span></span>  
  
- <span data-ttu-id="ee472-157">执行状态变量 (例如，@@ERROR，@@ROWCOUNT，@@FETCH_STATUS @@IDENTITY)</span><span class="sxs-lookup"><span data-stu-id="ee472-157">Execution state variables (for example, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span></span>  
  
- <span data-ttu-id="ee472-158">顶级临时表</span><span class="sxs-lookup"><span data-stu-id="ee472-158">Top-level temporary tables</span></span>  
  
 <span data-ttu-id="ee472-159">使用 MARS，默认的执行环境将与连接关联。</span><span class="sxs-lookup"><span data-stu-id="ee472-159">With MARS, a default execution environment is associated to a connection.</span></span> <span data-ttu-id="ee472-160">在给定连接下开始执行的每个新的批处理会接收默认环境的副本。</span><span class="sxs-lookup"><span data-stu-id="ee472-160">Every new batch that starts executing under a given connection receives a copy of the default environment.</span></span> <span data-ttu-id="ee472-161">只要代码在给定的批处理下执行，对环境所作的所有更改将作用于特定的批处理。</span><span class="sxs-lookup"><span data-stu-id="ee472-161">Whenever code is executed under a given batch, all changes made to the environment are scoped to the specific batch.</span></span> <span data-ttu-id="ee472-162">执行完成后，执行设置将复制到默认环境中。</span><span class="sxs-lookup"><span data-stu-id="ee472-162">Once execution finishes, the execution settings are copied into the default environment.</span></span> <span data-ttu-id="ee472-163">如果单个批处理发出的多个命令要在相同事务下顺序执行，语义与通过与早期客户端或服务器有关的连接公开的语义相同。</span><span class="sxs-lookup"><span data-stu-id="ee472-163">In the case of a single batch issuing several commands to be executed sequentially under the same transaction, semantics are the same as those exposed by connections involving earlier clients or servers.</span></span>  
  
### <a name="parallel-execution"></a><span data-ttu-id="ee472-164">并行执行</span><span class="sxs-lookup"><span data-stu-id="ee472-164">Parallel Execution</span></span>  
 <span data-ttu-id="ee472-165">使用 MARS 后，并非不再需要在应用程序中使用多个连接。</span><span class="sxs-lookup"><span data-stu-id="ee472-165">MARS is not designed to remove all requirements for multiple connections in an application.</span></span> <span data-ttu-id="ee472-166">如果应用程序需要对服务器真正地并行执行命令，应使用多个连接。</span><span class="sxs-lookup"><span data-stu-id="ee472-166">If an application needs true parallel execution of commands against a server, multiple connections should be used.</span></span>  
  
 <span data-ttu-id="ee472-167">例如，考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="ee472-167">For example, consider the following scenario.</span></span> <span data-ttu-id="ee472-168">创建了两个命令对象，一个用于处理结果集，另一个用于更新数据；这两个命令对象通过 MARS 共享公共连接。</span><span class="sxs-lookup"><span data-stu-id="ee472-168">Two command objects are created, one for processing a result set and another for updating data; they share a common connection via MARS.</span></span> <span data-ttu-id="ee472-169">在此方案中， `Transaction`。`Commit`</span><span class="sxs-lookup"><span data-stu-id="ee472-169">In this scenario, the `Transaction`.`Commit`</span></span> <span data-ttu-id="ee472-170">在更新时失败，直到在第一个命令对象，并生成以下异常上读取了所有结果：</span><span class="sxs-lookup"><span data-stu-id="ee472-170">fails on the update until all the results have been read on the first command object, yielding the following exception:</span></span>  
  
 <span data-ttu-id="ee472-171">消息:其他会话正在使用事务的上下文。</span><span class="sxs-lookup"><span data-stu-id="ee472-171">Message: Transaction context in use by another session.</span></span>  
  
 <span data-ttu-id="ee472-172">源：.NET SqlClient 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="ee472-172">Source: .NET SqlClient Data Provider</span></span>  
  
 <span data-ttu-id="ee472-173">要求：(null)</span><span class="sxs-lookup"><span data-stu-id="ee472-173">Expected: (null)</span></span>  
  
 <span data-ttu-id="ee472-174">接收到：System.Data.SqlClient.SqlException</span><span class="sxs-lookup"><span data-stu-id="ee472-174">Received: System.Data.SqlClient.SqlException</span></span>  
  
 <span data-ttu-id="ee472-175">可以通过三种方式处理此方案：</span><span class="sxs-lookup"><span data-stu-id="ee472-175">There are three options for handling this scenario:</span></span>  
  
1. <span data-ttu-id="ee472-176">在创建读取器之后开始事务，使读取器不是事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="ee472-176">Start the transaction after the reader is created, so that it is not part of the transaction.</span></span> <span data-ttu-id="ee472-177">每次更新将变为读取器自己的事务。</span><span class="sxs-lookup"><span data-stu-id="ee472-177">Every update then becomes its own transaction.</span></span>  
  
2. <span data-ttu-id="ee472-178">在读取器关闭之后提交所有工作。</span><span class="sxs-lookup"><span data-stu-id="ee472-178">Commit all work after the reader is closed.</span></span> <span data-ttu-id="ee472-179">对于大量的更新批处理，可能会这样做。</span><span class="sxs-lookup"><span data-stu-id="ee472-179">This has the potential for a substantial batch of updates.</span></span>  
  
3. <span data-ttu-id="ee472-180">不使用 MARS；而是对每个命令对象使用独立的连接，就像在 MARS 之前一样。</span><span class="sxs-lookup"><span data-stu-id="ee472-180">Don't use MARS; instead use a separate connection for each command object as you would have before MARS.</span></span>  
  
### <a name="detecting-mars-support"></a><span data-ttu-id="ee472-181">检测 MARS 支持</span><span class="sxs-lookup"><span data-stu-id="ee472-181">Detecting MARS Support</span></span>  
 <span data-ttu-id="ee472-182">应用程序可以通过读取 `SqlConnection.ServerVersion` 值来检查 MARS 支持。</span><span class="sxs-lookup"><span data-stu-id="ee472-182">An application can check for MARS support by reading the `SqlConnection.ServerVersion` value.</span></span> <span data-ttu-id="ee472-183"> SQL Server 2005 的主版本号应为 9，SQL Server 2008 的主版本号应为 10。</span><span class="sxs-lookup"><span data-stu-id="ee472-183">The major number should be 9 for SQL Server 2005 and 10 for SQL Server 2008.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee472-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee472-184">See also</span></span>

- [<span data-ttu-id="ee472-185">多重活动结果集 (MARS)</span><span class="sxs-lookup"><span data-stu-id="ee472-185">Multiple Active Result Sets (MARS)</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)
- [<span data-ttu-id="ee472-186">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ee472-186">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
