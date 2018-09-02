---
title: SqlClient 对高可用性的支持，灾难恢复
ms.date: 03/30/2017
ms.assetid: 61e0b396-09d7-4e13-9711-7dcbcbd103a0
ms.openlocfilehash: 258922a1541c4594ce2b4673d4d68c279087aef2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395850"
---
# <a name="sqlclient-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="6f8f2-102">SqlClient 对高可用性的支持，灾难恢复</span><span class="sxs-lookup"><span data-stu-id="6f8f2-102">SqlClient Support for High Availability, Disaster Recovery</span></span>
<span data-ttu-id="6f8f2-103">本主题介绍对高可用性、灾难恢复（AlwaysOn 可用性组）的 SqlClient支持（[!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] 中的新功能）。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-103">This topic discusses SqlClient support (added in [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]) for high-availability, disaster recovery -- AlwaysOn Availability Groups.</span></span>  <span data-ttu-id="6f8f2-104">AlwaysOn 可用性组功能已添加到 SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-104">AlwaysOn Availability Groups feature was added to SQL Server 2012.</span></span> <span data-ttu-id="6f8f2-105">有关 AlwaysOn 可用性组的详细信息，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-105">For more information about AlwaysOn Availability Groups, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="6f8f2-106">现在，您可以指定的可用性组侦听器 （高可用性、 灾难恢复） 可用性组 (AG) 或连接属性中的 SQL Server 2012 故障转移群集实例。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-106">You can now specify the availability group listener of a (high-availability, disaster-recovery) availability group (AG) or SQL Server 2012 Failover Cluster Instance in the connection property.</span></span> <span data-ttu-id="6f8f2-107">如果 SqlClient 应用程序连接到发生故障转移的 AlwaysOn 数据库，原始连接会中断，而且应用程序必须打开一个新连接以在故障转移之后继续工作。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-107">If a SqlClient application is connected to an AlwaysOn database that fails over, the original connection is broken and the application must open a new connection to continue work after the failover.</span></span>  
  
 <span data-ttu-id="6f8f2-108">如果您未连接到可用性组侦听器或 SQL Server 2012 故障转移群集实例，并且多个 IP 地址与主机名相关联，SqlClient 将按顺序遍历与 DNS 条目关联的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-108">If you are not connecting to an availability group listener or SQL Server 2012 Failover Cluster Instance, and if multiple IP addresses are associated with a hostname, SqlClient will iterate sequentially through all IP addresses associated with DNS entry.</span></span> <span data-ttu-id="6f8f2-109">如果 DNS 服务器返回的第一个 IP 地址未绑定到到任何网络接口卡 (NIC)，这可能非常耗时。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-109">This can be time consuming if the first IP address returned by DNS server is not bound to any network interface card (NIC).</span></span> <span data-ttu-id="6f8f2-110">连接到可用性组侦听器或 SQL Server 2012 故障转移群集实例时，SqlClient 尝试并行建立与所有 IP 地址的连接，如果连接尝试成功，则驱动程序将丢弃所有挂起的连接尝试次数。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-110">When connecting to an availability group listener or SQL Server 2012 Failover Cluster Instance, SqlClient attempts to establish connections to all IP addresses in parallel and if a connection attempt succeeds, the driver will discard any pending connection attempts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f8f2-111">增加连接超时值和实现连接重试逻辑会增加应用程序连接到可用性组的概率。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-111">Increasing connection timeout and implementing connection retry logic will increase the probability that an application will connect to an availability group.</span></span> <span data-ttu-id="6f8f2-112">此外，由于故障转移，连接可能失败，所以您应当实现连接重试逻辑，重试失败的连接，直到它重新连接。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-112">Also, because a connection can fail because of a failover, you should implement connection retry logic, retrying a failed connection until it reconnects.</span></span>  
  
 <span data-ttu-id="6f8f2-113">以下连接属性已添加到 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] 中的 SqlClient：</span><span class="sxs-lookup"><span data-stu-id="6f8f2-113">The following connection properties were added to SqlClient in [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]:</span></span>  
  
-   `ApplicationIntent`  
  
-   `MultiSubnetFailover`  
  
 <span data-ttu-id="6f8f2-114">您可通过编程方式修改这些连接字符串关键字：</span><span class="sxs-lookup"><span data-stu-id="6f8f2-114">You can programmatically modify these connection string keywords with:</span></span>  
  
1.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ApplicationIntent%2A>  
  
2.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>  

> [!NOTE]
>  <span data-ttu-id="6f8f2-115">设置`MultiSubnetFailover`到`true`不需要[!INCLUDE[net_v461](../../../../../includes/net-v461-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-115">Setting `MultiSubnetFailover` to `true` isn't required with [!INCLUDE[net_v461](../../../../../includes/net-v461-md.md)] or later versions.</span></span>
  
## <a name="connecting-with-multisubnetfailover"></a><span data-ttu-id="6f8f2-116">使用 MultiSubnetFailover 连接</span><span class="sxs-lookup"><span data-stu-id="6f8f2-116">Connecting With MultiSubnetFailover</span></span>  
 <span data-ttu-id="6f8f2-117">始终指定`MultiSubnetFailover=True`连接到 SQL Server 2012 可用性组侦听器或 SQL Server 2012 故障转移群集实例时。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-117">Always specify `MultiSubnetFailover=True` when connecting to a SQL Server 2012 availability group listener or SQL Server 2012 Failover Cluster Instance.</span></span> <span data-ttu-id="6f8f2-118">`MultiSubnetFailover` 启用更快故障转移的所有可用性组或故障转移群集实例在 SQL Server 2012 和将显著缩短单子网和多子网 AlwaysOn 拓扑的故障转移时间。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-118">`MultiSubnetFailover` enables faster failover for all Availability Groups and or Failover Cluster Instance in SQL Server 2012 and will significantly reduce failover time for single and multi-subnet AlwaysOn topologies.</span></span> <span data-ttu-id="6f8f2-119">在多子网故障转移期间，客户端将尝试并行连接。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-119">During a multi-subnet failover, the client will attempt connections in parallel.</span></span> <span data-ttu-id="6f8f2-120">在子网故障转移期间，将积极重试 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-120">During a subnet failover, will aggressively retry the TCP connection.</span></span>  
  
 <span data-ttu-id="6f8f2-121">`MultiSubnetFailover`连接属性指示可用性组或 SQL Server 2012 故障转移群集实例中部署应用程序和 SqlClient 将尝试通过尝试连接到主 SQL Server 实例上的数据库连接到所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-121">The `MultiSubnetFailover` connection property indicates that the application is being deployed in an availability group or SQL Server 2012 Failover Cluster Instance and that SqlClient will try to connect to the database on the primary SQL Server instance by trying to connect to all the IP addresses.</span></span> <span data-ttu-id="6f8f2-122">为连接指定 `MultiSubnetFailover=True` 时，客户端尝试 TCP 连接的频率比操作系统的默认 TCP 重新传输间隔快。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-122">When `MultiSubnetFailover=True` is specified for a connection, the client retries TCP connection attempts faster than the operating system’s default TCP retransmit intervals.</span></span> <span data-ttu-id="6f8f2-123">这使得在 AlwaysOn 可用性组或 AlwaysOn 故障转移群集实例进行故障转移后更快地重新连接，它同时适用于单子网/多子网可用性组和故障转移群集实例。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-123">This enables faster reconnection after failover of either an AlwaysOn Availability Group or an AlwaysOn Failover Cluster Instance, and is applicable to both single- and multi-subnet Availability Groups and Failover Cluster Instances.</span></span>  
  
 <span data-ttu-id="6f8f2-124">有关 SqlClient 中的连接字符串关键字的更多信息，请参见 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-124">For more information about connection string keywords in SqlClient, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="6f8f2-125">指定`MultiSubnetFailover=True`时连接到的内容，而不是可用性组侦听器或 SQL Server 2012 故障转移群集实例可能会导致性能下降，和不受支持。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-125">Specifying `MultiSubnetFailover=True` when connecting to something other than a availability group listener or SQL Server 2012 Failover Cluster Instance may result in a negative performance impact, and is not supported.</span></span>  
  
 <span data-ttu-id="6f8f2-126">使用以下准则来连接到可用性组中的服务器或 SQL Server 2012 故障转移群集实例：</span><span class="sxs-lookup"><span data-stu-id="6f8f2-126">Use the following guidelines to connect to a server in an availability group or SQL Server 2012 Failover Cluster Instance:</span></span>  
  
-   <span data-ttu-id="6f8f2-127">连接到单子网或多子网时使用 `MultiSubnetFailover` 连接属性，这样可提高它们的性能。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-127">Use the `MultiSubnetFailover` connection property when connecting to a single subnet or multi-subnet; it will improve performance for both.</span></span>  
  
-   <span data-ttu-id="6f8f2-128">要连接到可用性组，请在连接字符串中指定作为服务器的可用性组的可用性组侦听器。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-128">To connect to an availability group, specify the availability group listener of the availability group as the server in your connection string.</span></span>  
  
-   <span data-ttu-id="6f8f2-129">连接到 SQL Server 实例配置有 64 个以上的 IP 地址将导致连接失败。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-129">Connecting to a SQL Server instance configured with more than 64 IP addresses will cause a connection failure.</span></span>  
  
-   <span data-ttu-id="6f8f2-130">使用的应用程序的行为`MultiSubnetFailover`连接属性不受影响的身份验证的类型： SQL Server 身份验证、 Kerberos 身份验证或 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-130">Behavior of an application that uses the `MultiSubnetFailover` connection property is not affected based on the type of authentication: SQL Server Authentication, Kerberos Authentication, or Windows Authentication.</span></span>  
  
-   <span data-ttu-id="6f8f2-131">增加 `Connect Timeout` 的值以延长故障转移时间并减少应用程序连接重试次数。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-131">Increase the value of `Connect Timeout` to accommodate for failover time and reduce application connection retry attempts.</span></span>  
  
-   <span data-ttu-id="6f8f2-132">不支持分布式事务。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-132">Distributed transactions are not supported.</span></span>  
  
 <span data-ttu-id="6f8f2-133">如果只读路由无效，在下列情况下连接到辅助副本位置将失败：</span><span class="sxs-lookup"><span data-stu-id="6f8f2-133">If read-only routing is not in effect, connecting to a secondary replica location will fail in the following situations:</span></span>  
  
1.  <span data-ttu-id="6f8f2-134">如果未配置辅助副本位置以接受连接。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-134">If the secondary replica location is not configured to accept connections.</span></span>  
  
2.  <span data-ttu-id="6f8f2-135">如果应用程序使用 `ApplicationIntent=ReadWrite`（将在下文讨论），并且辅助副本位置配置为只读访问。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-135">If an application uses `ApplicationIntent=ReadWrite` (discussed below) and the secondary replica location is configured for read-only access.</span></span>  
  
 <span data-ttu-id="6f8f2-136">在只读辅助副本上不支持 <xref:System.Data.SqlClient.SqlDependency>。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-136"><xref:System.Data.SqlClient.SqlDependency> is not supported on read-only secondary replicas.</span></span>  
  
 <span data-ttu-id="6f8f2-137">如果主副本配置为拒绝只读工作负荷并且连接字符串包含 `ApplicationIntent=ReadOnly`，连接将失败。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-137">A connection will fail if a primary replica is configured to reject read-only workloads and the connection string contains `ApplicationIntent=ReadOnly`.</span></span>  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a><span data-ttu-id="6f8f2-138">从数据库镜像升级到使用多子网群集</span><span class="sxs-lookup"><span data-stu-id="6f8f2-138">Upgrading to Use Multi-Subnet Clusters from Database Mirroring</span></span>  
 <span data-ttu-id="6f8f2-139">如果 <xref:System.ArgumentException> 和 `MultiSubnetFailover` 连接关键字在连接字符串中存在，或者使用 `Failover Partner` 和 TCP 以外的其他协议，则会出现连接错误 (`MultiSubnetFailover=True`)。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-139">A connection error (<xref:System.ArgumentException>) will occur if the `MultiSubnetFailover` and `Failover Partner` connection keywords are present in the connection string, or if `MultiSubnetFailover=True` and a protocol other than TCP is used.</span></span> <span data-ttu-id="6f8f2-140">错误 (<xref:System.Data.SqlClient.SqlException>) 也会出现如果`MultiSubnetFailover`使用和 SQL Server 将返回一个故障转移伙伴响应指示它数据库镜像对的一部分。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-140">An error (<xref:System.Data.SqlClient.SqlException>) will also occur if `MultiSubnetFailover` is used and the SQL Server returns a failover partner response indicating it is part of a database mirroring pair.</span></span>  
  
 <span data-ttu-id="6f8f2-141">如果您将当前使用数据库镜像的 SqlClient 应用程序升级到多子网方案，应删除 `Failover Partner` 连接属性并使用 `MultiSubnetFailover` 设置为 `True` 的属性替换它，同时使用可用性组侦听器替换连接字符串中的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-141">If you upgrade a SqlClient application that currently uses database mirroring to a multi-subnet scenario, you should remove the `Failover Partner` connection property and replace it with `MultiSubnetFailover` set to `True` and replace the server name in the connection string with an availability group listener.</span></span> <span data-ttu-id="6f8f2-142">如果连接字符串使用 `Failover Partner` 和 `MultiSubnetFailover=True`，驱动程序将生成错误。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-142">If a connection string uses `Failover Partner` and `MultiSubnetFailover=True`, the driver will generate an error.</span></span> <span data-ttu-id="6f8f2-143">但是，如果连接字符串使用 `Failover Partner` 和 `MultiSubnetFailover=False`（或 `ApplicationIntent=ReadWrite`），应用程序将使用数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-143">However, if a connection string uses `Failover Partner` and `MultiSubnetFailover=False` (or `ApplicationIntent=ReadWrite`), the application will use database mirroring.</span></span>  
  
 <span data-ttu-id="6f8f2-144">如果在 AG 的主数据库上使用数据库镜像，并且如果 `MultiSubnetFailover=True` 被用于连接到主数据库而非可用性组侦听器的连接字符串中，驱动程序将返回错误。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-144">The driver will return an error if database mirroring is used on the primary database in the AG, and if `MultiSubnetFailover=True` is used in the connection string that connects to a primary database instead of to an availability group listener.</span></span>  
  
## <a name="specifying-application-intent"></a><span data-ttu-id="6f8f2-145">指定应用程序意向</span><span class="sxs-lookup"><span data-stu-id="6f8f2-145">Specifying Application Intent</span></span>  
 <span data-ttu-id="6f8f2-146">当 `ApplicationIntent=ReadOnly` 时，客户端在连接到启用 AlwaysOn 的数据库时请求读工作负荷。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-146">When `ApplicationIntent=ReadOnly`, the client requests a read workload when connecting to an AlwaysOn enabled database.</span></span> <span data-ttu-id="6f8f2-147">服务器将在连接时和 USE 数据库语句期间执行该意向，但是仅针对启用 Always On 的数据库。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-147">The server will enforce the intent at connection time and during a USE database statement but only to an Always On enabled database.</span></span>  
  
 <span data-ttu-id="6f8f2-148">`ApplicationIntent` 关键字不适用于旧的只读数据库。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-148">The `ApplicationIntent` keyword does not work with legacy, read-only databases.</span></span>  
  
 <span data-ttu-id="6f8f2-149">数据库可以允许或不允许针对的 AlwaysOn 数据库上的读工作负荷。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-149">A database can allow or disallow read workloads on the targeted AlwaysOn database.</span></span> <span data-ttu-id="6f8f2-150">（使用 `ALLOW_CONNECTIONS` 和 `PRIMARY_ROLE``SECONDARY_ROLE` 语句的 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 子句可做到这点。）</span><span class="sxs-lookup"><span data-stu-id="6f8f2-150">(This is done with the `ALLOW_CONNECTIONS` clause of the `PRIMARY_ROLE` and `SECONDARY_ROLE`[!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements.)</span></span>  
  
 <span data-ttu-id="6f8f2-151">`ApplicationIntent` 关键字用于启用只读路由。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-151">The `ApplicationIntent` keyword is used to enable read-only routing.</span></span>  
  
## <a name="read-only-routing"></a><span data-ttu-id="6f8f2-152">只读路由</span><span class="sxs-lookup"><span data-stu-id="6f8f2-152">Read-Only Routing</span></span>  
 <span data-ttu-id="6f8f2-153">只读路由是一种可以确保数据库只读副本的可用性的功能。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-153">Read-only routing is a feature that can ensure the availability of a read only replica of a database.</span></span> <span data-ttu-id="6f8f2-154">要启用只读路由：</span><span class="sxs-lookup"><span data-stu-id="6f8f2-154">To enable read-only routing:</span></span>  
  
1.  <span data-ttu-id="6f8f2-155">您必须连接到 Always On 可用性组的可用性组侦听器。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-155">You must connect to an Always On Availability Group availability group listener.</span></span>  
  
2.  <span data-ttu-id="6f8f2-156">`ApplicationIntent` 连接字符串关键字必须设置为 `ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-156">The `ApplicationIntent` connection string keyword must be set to `ReadOnly`.</span></span>  
  
3.  <span data-ttu-id="6f8f2-157">可用性组必须由数据库管理员配置以启用只读路由。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-157">The Availability Group must be configured by the database administrator to enable read-only routing.</span></span>  
  
 <span data-ttu-id="6f8f2-158">使用只读路由的多个连接并非连接到相同的只读副本。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-158">It is possible that multiple connections using read-only routing will not all connect to the same read-only replica.</span></span> <span data-ttu-id="6f8f2-159">数据库同步的更改或服务器路由配置的更改可能导致客户端连接到不同的只读副本。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-159">Changes in database synchronization or changes in the server's routing configuration can result in client connections to different read-only replicas.</span></span> <span data-ttu-id="6f8f2-160">为确保所有只读请求连接到相同的只读副本，请不要将可用性组侦听器传递给 `Data Source` 连接字符串关键字。 </span><span class="sxs-lookup"><span data-stu-id="6f8f2-160">To ensure that all read-only requests connect to the same read-only replica, do not pass an availability group listener to the `Data Source` connection string keyword.</span></span> <span data-ttu-id="6f8f2-161">请指定只读实例的名称。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-161">Instead, specify the name of the read-only instance.</span></span>  
  
 <span data-ttu-id="6f8f2-162">只读路由可能需要比连接到主副本更长的时间，因为只读路由要先连接到主副本，然后查找最可能可用的可读辅助副本。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-162">Read-only routing may take longer than connecting to the primary because read only routing first connects to the primary and then looks for the best available readable secondary.</span></span> <span data-ttu-id="6f8f2-163">为此，您应增加您的登录超时值。</span><span class="sxs-lookup"><span data-stu-id="6f8f2-163">Because of this, you should increase your login timeout.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f8f2-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f8f2-164">See Also</span></span>  
 [<span data-ttu-id="6f8f2-165">SQL Server 功能和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6f8f2-165">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [<span data-ttu-id="6f8f2-166">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="6f8f2-166">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
