---
title: 缓解：池阻止时间段
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1021cf66c7091e699efac72fc9e614f30910398b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645101"
---
# <a name="mitigation-pool-blocking-period"></a><span data-ttu-id="d54e2-102">缓解：池阻止时间段</span><span class="sxs-lookup"><span data-stu-id="d54e2-102">Mitigation: Pool Blocking Period</span></span>
<span data-ttu-id="d54e2-103">与 Azure SQL 数据库的连接已删除连接池阻止时间段。</span><span class="sxs-lookup"><span data-stu-id="d54e2-103">The connection pool blocking period has been removed for connections to Azure SQL databases.</span></span>  
  
## <a name="additional-description"></a><span data-ttu-id="d54e2-104">其他说明</span><span class="sxs-lookup"><span data-stu-id="d54e2-104">Additional description</span></span>  
 <span data-ttu-id="d54e2-105">在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 和早期版本中，当应用在连接到数据库过程中遇到暂时性连接失败时，无法快速重试连接，因为连接池会缓存错误，并在 5 秒至 1 分钟后重新引发该错误。有关详细信息，请参阅 [SQL Server 连接池 (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md)。</span><span class="sxs-lookup"><span data-stu-id="d54e2-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, when an app encounters a transient connection failure when connecting to a database, the connection attempt cannot be retried quickly, because the connection pool caches the error and re-throws it for 5 seconds to 1 min. For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span> <span data-ttu-id="d54e2-106">这种行为会给 Azure SQL 数据库连接带来问题，因为经常会因暂时性错误而导致连接失败，这些错误通常在几秒内便会恢复。</span><span class="sxs-lookup"><span data-stu-id="d54e2-106">This behavior is problematic for connections to Azure SQL databases, which often fail with transient errors that are typically recovered from within a few seconds.</span></span> <span data-ttu-id="d54e2-107">连接池阻止功能意味着，应用在很长一段时间内都无法连接到数据库，即使数据库可用也不行。</span><span class="sxs-lookup"><span data-stu-id="d54e2-107">The connection pool blocking feature means that the app cannot connect to the database for an extensive period, even though the database is available.</span></span> <span data-ttu-id="d54e2-108">对于连接到 Azure SQL 数据库以及需要在几秒内呈现的 Web 应用，这种行为带来的问题尤为明显。</span><span class="sxs-lookup"><span data-stu-id="d54e2-108">This behavior is particularly problematic for web apps that connect to Azure SQL databases and that need to render within a few seconds.</span></span>  
  
 <span data-ttu-id="d54e2-109">对于发送到已知 Azure SQL 数据库（\*.database.windows.net、\*.database.chinacloudapi.cn、\*.database.usgovcloudapi.net、\*.database.cloudapi.de）的打开连接请求（开头为 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]），将不会缓存打开连接错误。</span><span class="sxs-lookup"><span data-stu-id="d54e2-109">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], for connection open requests to known Azure SQL databases (\*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), connection open errors are not cached.</span></span> <span data-ttu-id="d54e2-110">对于其他所有连接尝试，连接池阻止时间段还会继续强制执行。</span><span class="sxs-lookup"><span data-stu-id="d54e2-110">For all other connection attempts, the connection pool blocking period continues to be enforced.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d54e2-111">影响</span><span class="sxs-lookup"><span data-stu-id="d54e2-111">Impact</span></span>  
 <span data-ttu-id="d54e2-112">此更改允许立即重新尝试打开 Azure SQL 数据库的连接，从而改进了已启用云的应用的性能。</span><span class="sxs-lookup"><span data-stu-id="d54e2-112">This change allows the connection open attempt to be retried immediately for Azure SQL databases, thereby improving the performance of cloud-enabled apps.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d54e2-113">缓解</span><span class="sxs-lookup"><span data-stu-id="d54e2-113">Mitigation</span></span>  
 <span data-ttu-id="d54e2-114">对于受到此更改不利影响的应用，连接池阻止时间段可通过设置新 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> 属性进行配置。</span><span class="sxs-lookup"><span data-stu-id="d54e2-114">For apps that are adversely affected by this change, the connection pool blocking period can be configured by setting the new <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property.</span></span>  <span data-ttu-id="d54e2-115">该属性的值属于 <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> 枚举，可采用以下三个值中的任意一个：</span><span class="sxs-lookup"><span data-stu-id="d54e2-115">The value of the property is a member of the <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> enumeration that can take either of three values:</span></span>  
  
-   `PoolBlockingPeriod.AlwaysBlock` 
  
-   `PoolBlockingPeriod.Auto`  
  
-   `PoolBlockingPeriod.NeverBlock` 
  
 <span data-ttu-id="d54e2-116">可以通过将 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> 属性设置为 `PoolBlockingPeriod.AlwaysBlock` 来还原以前的行为。</span><span class="sxs-lookup"><span data-stu-id="d54e2-116">The previous behavior can be restored by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property to `PoolBlockingPeriod.AlwaysBlock`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54e2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d54e2-117">See also</span></span>
- [<span data-ttu-id="d54e2-118">运行时更改</span><span class="sxs-lookup"><span data-stu-id="d54e2-118">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
