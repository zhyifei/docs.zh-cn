---
title: 用于 SQL Server 的提供程序统计信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: d52c6bfdadf0a53ac4c5f62c37f1056c6702a82c
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032252"
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="c308b-102">用于 SQL Server 的提供程序统计信息</span><span class="sxs-lookup"><span data-stu-id="c308b-102">Provider Statistics for SQL Server</span></span>
<span data-ttu-id="c308b-103">从 .NET Framework 2.0 版开始，适用于 SQL Server 的 .NET Framework 数据提供程序支持运行时统计信息。</span><span class="sxs-lookup"><span data-stu-id="c308b-103">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="c308b-104">必须在创建了有效的连接对象后将 <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> 对象的 <xref:System.Data.SqlClient.SqlConnection> 属性设置为 `True`，以启用统计信息。</span><span class="sxs-lookup"><span data-stu-id="c308b-104">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="c308b-105">启用了统计信息之后，可以通过 <xref:System.Collections.IDictionary> 对象的 <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> 方法检索 <xref:System.Data.SqlClient.SqlConnection> 引用，以将统计信息作为“实时快照”查看。</span><span class="sxs-lookup"><span data-stu-id="c308b-105">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="c308b-106">通过列表作为一组名称/值对字典条目进行枚举。</span><span class="sxs-lookup"><span data-stu-id="c308b-106">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="c308b-107">这些名称/值对不排序。</span><span class="sxs-lookup"><span data-stu-id="c308b-107">These name/value pairs are unordered.</span></span> <span data-ttu-id="c308b-108">可以随时调用 <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> 对象的 <xref:System.Data.SqlClient.SqlConnection> 方法，以重置计数器。</span><span class="sxs-lookup"><span data-stu-id="c308b-108">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="c308b-109">如果尚未启用统计信息收集功能，则不会生成异常。</span><span class="sxs-lookup"><span data-stu-id="c308b-109">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="c308b-110">此外，如果调用 <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> 之前没有先调用 <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A>，检索到的值是每个条目的初始值。</span><span class="sxs-lookup"><span data-stu-id="c308b-110">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="c308b-111">如果启用了统计信息，运行应用程序一段时间，然后禁用统计信息，检索到的值将反映在禁用统计信息之前收集的值。</span><span class="sxs-lookup"><span data-stu-id="c308b-111">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="c308b-112">所有统计信息值按照连接进行收集。</span><span class="sxs-lookup"><span data-stu-id="c308b-112">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="c308b-113">可用的统计信息值</span><span class="sxs-lookup"><span data-stu-id="c308b-113">Statistical Values Available</span></span>  
 <span data-ttu-id="c308b-114">当前，Microsoft SQL Server 提供程序中共有 18 个不同的可用项。</span><span class="sxs-lookup"><span data-stu-id="c308b-114">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="c308b-115">可以通过访问可用的项的数目**计数**的属性<xref:System.Collections.IDictionary>接口引用返回<xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>。</span><span class="sxs-lookup"><span data-stu-id="c308b-115">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="c308b-116">所有提供程序统计信息计数器使用公共语言运行时<xref:System.Int64>类型 (**长**C# 和 Visual Basic 中)，其宽度为 64 位。</span><span class="sxs-lookup"><span data-stu-id="c308b-116">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="c308b-117">最大值**int64**数据类型，如由定义**int64。MaxValue**字段中，为 ((2^63) 1))。</span><span class="sxs-lookup"><span data-stu-id="c308b-117">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="c308b-118">计数器的值达到此最大值时，应不再将这些值作为准确的值。</span><span class="sxs-lookup"><span data-stu-id="c308b-118">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="c308b-119">这意味着， **int64。MaxValue**-1((2^63)-2) 实际上是任何统计信息的最大有效值。</span><span class="sxs-lookup"><span data-stu-id="c308b-119">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c308b-120">字典用于返回提供程序统计信息，因为以后可能会更改返回的统计信息的数目、名称和顺序。</span><span class="sxs-lookup"><span data-stu-id="c308b-120">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="c308b-121">应用程序不应依靠字典中找到的特定值，而应检查该值是否存在并相应进行分支。</span><span class="sxs-lookup"><span data-stu-id="c308b-121">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="c308b-122">下表说明当前可用的统计信息值。</span><span class="sxs-lookup"><span data-stu-id="c308b-122">The following table describes the current statistical values available.</span></span> <span data-ttu-id="c308b-123">注意，在 Microsoft .NET Framework 的地区版本中，各个值的键名未本地化。</span><span class="sxs-lookup"><span data-stu-id="c308b-123">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="c308b-124">键名</span><span class="sxs-lookup"><span data-stu-id="c308b-124">Key Name</span></span>|<span data-ttu-id="c308b-125">描述</span><span class="sxs-lookup"><span data-stu-id="c308b-125">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="c308b-126">返回在应用程序使用提供程序启动并启用了统计信息之后，提供程序从 SQL Server 接收的表格格式数据流 (TDS) 数据包数。</span><span class="sxs-lookup"><span data-stu-id="c308b-126">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="c308b-127">返回在启用了统计信息之后，由提供程序发送到 SQL Server 的 TDS 数据包数。</span><span class="sxs-lookup"><span data-stu-id="c308b-127">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="c308b-128">大命令可能需要多个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c308b-128">Large commands can require multiple buffers.</span></span> <span data-ttu-id="c308b-129">例如，如果某个大命令发送到服务器，并且需要六个数据包，`ServerRoundtrips` 将以 1 递增，`BuffersSent` 将以 6 递增。</span><span class="sxs-lookup"><span data-stu-id="c308b-129">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="c308b-130">返回在应用程序使用提供程序启动并启用了统计信息之后，提供程序从 SQL Server 接收的 TDS 数据包中的数据字节数。</span><span class="sxs-lookup"><span data-stu-id="c308b-130">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="c308b-131">返回在应用程序使用提供程序启动并启用了统计信息之后，在 TDS 数据包中发送到 SQL Server 的数据字节数。</span><span class="sxs-lookup"><span data-stu-id="c308b-131">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="c308b-132">连接在统计信息启用之后已打开的时间（单位为毫秒；如果在打开连接之前就启用了统计信息，则为总连接时间）。</span><span class="sxs-lookup"><span data-stu-id="c308b-132">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="c308b-133">返回在应用程序使用提供程序启动并启用了统计信息之后，通过连接打开游标的次数。</span><span class="sxs-lookup"><span data-stu-id="c308b-133">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="c308b-134">注意，SELECT 语句返回的只读/只进结果不属于游标，所以不影响此计数器。</span><span class="sxs-lookup"><span data-stu-id="c308b-134">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="c308b-135">返回在启用统计信息之后提供程序用于处理的累计时间（以毫秒为单位），包括等待服务器答复所用的时间以及执行提供程序本身的代码所用的时间。</span><span class="sxs-lookup"><span data-stu-id="c308b-135">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="c308b-136">包含计时代码的类如下：</span><span class="sxs-lookup"><span data-stu-id="c308b-136">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="c308b-137">SqlConnection</span><span class="sxs-lookup"><span data-stu-id="c308b-137">SqlConnection</span></span><br /><br /> <span data-ttu-id="c308b-138">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="c308b-138">SqlCommand</span></span><br /><br /> <span data-ttu-id="c308b-139">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="c308b-139">SqlDataReader</span></span><br /><br /> <span data-ttu-id="c308b-140">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="c308b-140">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="c308b-141">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="c308b-141">SqlTransaction</span></span><br /><br /> <span data-ttu-id="c308b-142">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="c308b-142">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="c308b-143">为了保持对性能要求很高的成员尽可能小，下列成员不计时：</span><span class="sxs-lookup"><span data-stu-id="c308b-143">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="c308b-144">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="c308b-144">SqlDataReader</span></span><br /><br /> <span data-ttu-id="c308b-145">this[] 运算符（所有重载）</span><span class="sxs-lookup"><span data-stu-id="c308b-145">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="c308b-146">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="c308b-146">GetBoolean</span></span><br /><br /> <span data-ttu-id="c308b-147">GetChar</span><span class="sxs-lookup"><span data-stu-id="c308b-147">GetChar</span></span><br /><br /> <span data-ttu-id="c308b-148">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="c308b-148">GetDateTime</span></span><br /><br /> <span data-ttu-id="c308b-149">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="c308b-149">GetDecimal</span></span><br /><br /> <span data-ttu-id="c308b-150">GetDouble</span><span class="sxs-lookup"><span data-stu-id="c308b-150">GetDouble</span></span><br /><br /> <span data-ttu-id="c308b-151">GetFloat</span><span class="sxs-lookup"><span data-stu-id="c308b-151">GetFloat</span></span><br /><br /> <span data-ttu-id="c308b-152">GetGuid</span><span class="sxs-lookup"><span data-stu-id="c308b-152">GetGuid</span></span><br /><br /> <span data-ttu-id="c308b-153">GetInt16</span><span class="sxs-lookup"><span data-stu-id="c308b-153">GetInt16</span></span><br /><br /> <span data-ttu-id="c308b-154">GetInt32</span><span class="sxs-lookup"><span data-stu-id="c308b-154">GetInt32</span></span><br /><br /> <span data-ttu-id="c308b-155">GetInt64</span><span class="sxs-lookup"><span data-stu-id="c308b-155">GetInt64</span></span><br /><br /> <span data-ttu-id="c308b-156">GetName</span><span class="sxs-lookup"><span data-stu-id="c308b-156">GetName</span></span><br /><br /> <span data-ttu-id="c308b-157">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="c308b-157">GetOrdinal</span></span><br /><br /> <span data-ttu-id="c308b-158">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="c308b-158">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="c308b-159">GetSqlBoolean </span><span class="sxs-lookup"><span data-stu-id="c308b-159">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="c308b-160">GetSqlByte </span><span class="sxs-lookup"><span data-stu-id="c308b-160">GetSqlByte</span></span><br /><br /> <span data-ttu-id="c308b-161">GetSqlDateTime </span><span class="sxs-lookup"><span data-stu-id="c308b-161">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="c308b-162">GetSqlDecimal </span><span class="sxs-lookup"><span data-stu-id="c308b-162">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="c308b-163">GetSqlDouble </span><span class="sxs-lookup"><span data-stu-id="c308b-163">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="c308b-164">GetSqlGuid </span><span class="sxs-lookup"><span data-stu-id="c308b-164">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="c308b-165">GetSqlInt16 </span><span class="sxs-lookup"><span data-stu-id="c308b-165">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="c308b-166">GetSqlInt32 </span><span class="sxs-lookup"><span data-stu-id="c308b-166">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="c308b-167">GetSqlInt64 </span><span class="sxs-lookup"><span data-stu-id="c308b-167">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="c308b-168">GetSqlMoney </span><span class="sxs-lookup"><span data-stu-id="c308b-168">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="c308b-169">GetSqlSingle </span><span class="sxs-lookup"><span data-stu-id="c308b-169">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="c308b-170">GetSqlString </span><span class="sxs-lookup"><span data-stu-id="c308b-170">GetSqlString</span></span><br /><br /> <span data-ttu-id="c308b-171">GetString</span><span class="sxs-lookup"><span data-stu-id="c308b-171">GetString</span></span><br /><br /> <span data-ttu-id="c308b-172">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="c308b-172">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="c308b-173">返回在应用程序使用提供程序启动并启用了统计信息之后，通过连接执行的 INSERT、DELETE 和 UPDATE 语句的总数。</span><span class="sxs-lookup"><span data-stu-id="c308b-173">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="c308b-174">返回在应用程序使用提供程序启动并启用了统计信息之后，受到通过连接执行的 INSERT、DELETE 和 UPDATE 语句影响的行的总数。</span><span class="sxs-lookup"><span data-stu-id="c308b-174">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="c308b-175">返回在应用程序使用提供程序启动并启用了统计信息之后，提供程序等待服务器答复所用的累计时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="c308b-175">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="c308b-176">返回在应用程序使用提供程序启动并启用了统计信息之后，通过连接执行的已准备命令数。</span><span class="sxs-lookup"><span data-stu-id="c308b-176">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="c308b-177">返回在应用程序使用提供程序启动并启用了统计信息之后，通过连接准备的语句数。</span><span class="sxs-lookup"><span data-stu-id="c308b-177">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="c308b-178">返回在应用程序使用提供程序启动并启用了统计信息之后，通过连接执行的 SELECT 语句数。</span><span class="sxs-lookup"><span data-stu-id="c308b-178">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="c308b-179">其中包括用于从游标检索行的 FETCH 语句，SELECT 语句的计数在到达 <xref:System.Data.SqlClient.SqlDataReader> 的结尾时更新。</span><span class="sxs-lookup"><span data-stu-id="c308b-179">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="c308b-180">返回在应用程序使用提供程序启动并启用了统计信息之后所选的行数。</span><span class="sxs-lookup"><span data-stu-id="c308b-180">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="c308b-181">此计数器反映 SQL 语句生成的所有行，即使是调用方没有真正使用的行。</span><span class="sxs-lookup"><span data-stu-id="c308b-181">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="c308b-182">例如，如果在读取整个结果集之前关闭数据读取器，不会影响该计数。</span><span class="sxs-lookup"><span data-stu-id="c308b-182">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="c308b-183">其中包括通过 FETCH 语句从游标检索的行。</span><span class="sxs-lookup"><span data-stu-id="c308b-183">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="c308b-184">返回在应用程序使用提供程序启动并启用了统计信息之后，连接向服务器发送命令并收到回复的次数。</span><span class="sxs-lookup"><span data-stu-id="c308b-184">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="c308b-185">返回在应用程序使用提供程序启动并启用了统计信息之后使用过的结果集数。</span><span class="sxs-lookup"><span data-stu-id="c308b-185">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="c308b-186">例如，此值可能包括返回到客户端的任何结果集。</span><span class="sxs-lookup"><span data-stu-id="c308b-186">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="c308b-187">对于光标，每个获取或块获取操作都属于独立的结果集。</span><span class="sxs-lookup"><span data-stu-id="c308b-187">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="c308b-188">返回在应用程序使用提供程序启动并启用了统计信息之后启动的用户事务数（包括回滚）。</span><span class="sxs-lookup"><span data-stu-id="c308b-188">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="c308b-189">如果连接在启用自动提交的情况下运行，则每个命令都属于一个事务。</span><span class="sxs-lookup"><span data-stu-id="c308b-189">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="c308b-190">只要执行了 BEGIN TRAN 语句，无论事务是提交还是以后回滚，此计数器都会使事务计数递增。</span><span class="sxs-lookup"><span data-stu-id="c308b-190">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="c308b-191">返回在应用程序使用提供程序启动并启用了统计信息之后，通过连接执行的非准备语句数。</span><span class="sxs-lookup"><span data-stu-id="c308b-191">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="c308b-192">检索值</span><span class="sxs-lookup"><span data-stu-id="c308b-192">Retrieving a Value</span></span>  
 <span data-ttu-id="c308b-193">以下控制台应用程序显示如何在连接上启用统计信息，如何分别检索四个统计信息值，以及如何将统计信息输出到控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="c308b-193">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c308b-194">下面的示例使用示例**AdventureWorks** SQL Server 中包含的数据库。</span><span class="sxs-lookup"><span data-stu-id="c308b-194">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="c308b-195">示例代码中提供的连接字符串假定数据库在本地计算机上已安装并且可用。</span><span class="sxs-lookup"><span data-stu-id="c308b-195">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="c308b-196">根据环境的需要修改连接字符串。</span><span class="sxs-lookup"><span data-stu-id="c308b-196">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =   
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="c308b-197">检索所有值</span><span class="sxs-lookup"><span data-stu-id="c308b-197">Retrieving All Values</span></span>  
 <span data-ttu-id="c308b-198">以下控制台应用程序显示如何在连接上启用统计信息，如何使用枚举器检索所有可用统计信息值，以及如何将统计信息输出到控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="c308b-198">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c308b-199">下面的示例使用示例**AdventureWorks** SQL Server 中包含的数据库。</span><span class="sxs-lookup"><span data-stu-id="c308b-199">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="c308b-200">示例代码中提供的连接字符串假定数据库在本地计算机上已安装并且可用。</span><span class="sxs-lookup"><span data-stu-id="c308b-200">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="c308b-201">根据环境的需要修改连接字符串。</span><span class="sxs-lookup"><span data-stu-id="c308b-201">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c308b-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="c308b-202">See Also</span></span>  
 [<span data-ttu-id="c308b-203">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c308b-203">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="c308b-204">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="c308b-204">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
