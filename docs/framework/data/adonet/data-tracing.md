---
title: ADO.NET 中的数据跟踪
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: f92a17374cf3df1281e51d54bae1a1dcf9e5ea03
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937632"
---
# <a name="data-tracing-in-adonet"></a>ADO.NET 中的数据跟踪

ADO.NET 功能内置数据跟踪功能，适用于 SQL Server、Oracle、OLE DB 和 ODBC 的 .NET 数据提供程序，以及 ADO.NET <xref:System.Data.DataSet>和 SQL Server 网络协议。

跟踪数据访问 API 调用可以帮助诊断以下问题：

- 客户端程序和数据库之间的架构不匹配。

- 数据库不可用或网络库问题。

- 不正确的 SQL，无论是硬编码还是由应用程序生成。

- 不正确的编程逻辑。

- 多个 ADO.NET 组件之间或 ADO.NET 与您自己的组件之间的交互引发的问题。

为了支持不同的跟踪技术，跟踪是可扩展的，这样，开发人员可以在任何应用程序堆栈级别上跟踪问题。 尽管跟踪不属于纯 ADO.NET 功能，但是，Microsoft 提供程序利用通用的跟踪和规范 API。

有关在 ADO.NET 中设置和配置托管跟踪的详细信息，请参阅[跟踪数据访问](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10))。

## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>访问扩展事件日志中的诊断信息

在用于 SQL Server 的 .NET Framework 数据提供程序中，数据访问跟踪（[数据访问跟踪](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10))）已更新，以便更轻松地将客户端事件与诊断信息关联，如连接失败、从服务器的连接环形缓冲区和扩展事件日志中的应用程序性能信息。 有关读取扩展事件日志的信息，请参阅[查看事件会话数据](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh710068(v=sql.110))。

对于连接操作，ADO.NET 将发送一个客户端连接 ID。 如果连接失败，您可以访问连接环形缓冲区（[使用连接环形缓冲区 SQL Server 2008 中的连接性故障排除](https://docs.microsoft.com/archive/blogs/sql_protocols/connectivity-troubleshooting-in-sql-server-2008-with-the-connectivity-ring-buffer)）并查找 `ClientConnectionID` 字段并获取有关连接失败的诊断信息。 如果出现错误，则将客户端连接 ID 记录在环形缓冲区中。 （如果在发送预登录数据包之前连接失败，将不会生成客户端连接 ID。）客户端连接 ID 是16字节的 GUID。 如果 `client_connection_id` 操作已添加到扩展事件会话中的事件，则还可以在扩展事件目标输出中找到查找客户端连接 ID。 如果需要进一步的客户端驱动程序诊断帮助，可以启用数据访问跟踪并重新运行连接命令，然后观察 `ClientConnectionID` 字段。

还可以通过使用 `SqlConnection.ClientConnectionID` 属性以编程方式获取客户端连接 ID。

`ClientConnectionID` 可用于成功建立连接的 <xref:System.Data.SqlClient.SqlConnection> 对象。 如果连接尝试失败，则 `ClientConnectionID` 可通过 `SqlException.ToString` 提供。

ADO.NET 还会发送一个特定于线程的活动 ID。 如果在启用了 TRACK_CAUSALITY 选项的情况启动会话，则会在扩展事件会话中捕获活动 ID。 有关活动连接的性能问题，可以从客户端的数据访问跟踪获取活动 ID（`ActivityID` 字段），然后查找扩展事件输出中的活动 ID。 扩展事件中的活动 ID 是一个 16 字节 GUID（与客户端连接 ID 的 GUID 不同），附有一个四字节的序列号。 序列号表示请求在线程中的顺序，并指示线程的批处理和 RPC 语句的相对顺序。 启用数据访问跟踪以及数据访问跟踪配置字中的第 18 位处于打开状态时，当前可以针对 SQL 批处理语句和 RPC 请求选择发送 `ActivityID`。

下面的示例使用 Transact-sql 来启动扩展事件会话，该会话将存储在环形缓冲区中并记录从客户端在 RPC 和批处理操作上发送的活动 ID。

```sql
create event session MySession on server
add event connectivity_ring_buffer_recorded,
add event sql_statement_starting (action (client_connection_id)),
add event sql_statement_completed (action (client_connection_id)),
add event rpc_starting (action (client_connection_id)),
add event rpc_completed (action (client_connection_id))
add target ring_buffer with (track_causality=on)
```

## <a name="see-also"></a>另请参阅

- [.NET Framework 中的网络跟踪](../../network-programming/network-tracing.md)
- [跟踪应用程序和在应用程序中插入检测点](../../debug-trace-profile/tracing-and-instrumenting-applications.md)
- [ADO.NET 概述](ado-net-overview.md)
