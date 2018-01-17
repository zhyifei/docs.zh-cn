---
title: "SQL Server 中的数据库镜像"
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
ms.assetid: 89befaff-bb46-4290-8382-e67cdb0e3de9
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6956d48163f9b9da66258c0dbb3452beab5420d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="database-mirroring-in-sql-server"></a>SQL Server 中的数据库镜像
通过 SQL Server 中的数据库镜像，可以在备用服务器上保留 SQL Server 数据库的副本（即镜像）。 镜像可以确保数据始终存在两个独立的副本，从而提供高可用性和完整的数据冗余。 用于 SQL Server 的 .NET 数据提供程序提供了数据库镜像的隐式支持，这样，在为 SQL Server 数据库配置了镜像之后，开发人员无需采取任何措施或编写任何代码。 此外，<xref:System.Data.SqlClient.SqlConnection> 对象支持显式连接模式，该模式允许在 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> 中提供故障转移合作伙伴服务器的名称。  
  
 对于连接目标为某个配置为镜像的数据库的 <xref:System.Data.SqlClient.SqlConnection> 对象将发生以下简化的事件序列：  
  
1.  客户端应用程序成功连接到主体数据库上，服务器发送回合作伙伴服务器的名称，然后将该名称缓存在客户端上。  
  
2.  如果包含主体数据库的服务器失败或连接中断，连接和事务状态将丢失。 客户端应用程序尝试重新建立与主体数据库的连接，但是失败。  
  
3.  然后，客户端应用程序透明地尝试与合作伙伴服务器上的镜像数据库建立连接。 如果成功，连接将重定向到镜像数据库，而该镜像数据库将成为新的主体数据库。  
  
## <a name="specifying-the-failover-partner-in-the-connection-string"></a>在连接字符串中指定故障转移合作伙伴  
 如果在连接字符串中提供故障转移合作伙伴服务器的名称，当客户端应用程序初次连接时，主体数据库不可用，客户端将直接尝试与故障转移合作伙伴建立连接。  
  
```  
";Failover Partner=PartnerServerName"  
```  
  
 如果省略故障转移合作伙伴服务器的名称且客户端应用程序初次连接时主体数据库不可用，则引发 <xref:System.Data.SqlClient.SqlException>。  
  
 成功打开 <xref:System.Data.SqlClient.SqlConnection> 后，故障转移合作伙伴名称由服务器返回，取代连接字符串中提供的任何值。  
  
> [!NOTE]
>  您必须在连接字符串中显式指定数据库镜像方案的初始编录或数据库名称。 如果客户端收到没有显式指定初始编录或数据库的连接的故障转移信息，故障转移信息不会缓存，应用程序也不会在主体服务器出现故障时尝试进行故障转移。 如果连接字符串包含故障转移合作伙伴的值，但是没有包含初始编录或数据库的值，则会引发 `InvalidArgumentException`。  
  
## <a name="retrieving-the-current-server-name"></a>检索当前服务器名称  
 如果进行故障转移，可以使用 <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> 对象的 <xref:System.Data.SqlClient.SqlConnection> 属性来检索当前连接实际连接到的服务器的名称。 以下代码段检索活动服务器的名称，假定连接变量引用打开的 <xref:System.Data.SqlClient.SqlConnection>。  
  
 当发生故障转移事件并且连接切换到镜像服务器**数据源**属性更新以反映镜像名称。  
  
```vb  
Dim activeServer As String = connection.DataSource  
```  
  
```csharp  
string activeServer = connection.DataSource;  
```  
  
## <a name="sqlclient-mirroring-behavior"></a>SqlClient 镜像行为  
 客户端总是尝试连接当前的主体服务器。 如果失败，将尝试连接故障转移合作伙伴。 如果镜像数据库已切换为合作伙伴服务器上的主体角色，连接将成功，新的主体/镜像映射将发送到客户端，并在调用 <xref:System.AppDomain> 的生存期期间进行缓存。 它不会存储在持久性存储区并不是可用于在不同的后续连接**AppDomain**或进程。 但是，它是可用于在同一个后续连接**AppDomain**。 请注意，另一个**AppDomain**或始终在相同或另一台计算机上运行的进程具有自己的连接，池，这些连接不会重置。 在这种情况下，如果主数据库发生故障后，每个进程或**AppDomain**失败一次，并且该池将自动清除。  
  
> [!NOTE]
>  每个数据库都要在服务器上配置镜像支持。 如果对不在主体/镜像数据库集中的其他数据库执行数据操作，那么无论使用多部分名称还是更改当前数据库，在失败时都不会传播对这些数据库的更改。 修改未镜像的数据库中的数据时，不会生成错误。 开发人员必须评估此类操作可能产生的影响。  
  
## <a name="database-mirroring-resources"></a>数据库镜像资源  
 有关配置、部署和管理镜像的概念性文档及信息，请参见“SQL Server 联机丛书”中的下列资源。  
  
|资源|描述|  
|--------------|-----------------|  
|[数据库镜像](http://msdn.microsoft.com/library/bb934127.aspx)SQL Server 联机丛书中|说明如何在 SQL Server 中设置和配置镜像。|  
  
## <a name="see-also"></a>请参阅  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
