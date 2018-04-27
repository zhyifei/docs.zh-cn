### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection 可以不再连接到 SQL Server 1997 或使用 VIA 适配器的数据库

|   |   |
|---|---|
|详细信息|不再支持使用[虚拟接口适配器 (VIA) 协议](https://technet.microsoft.com/library/ms191229%28v=sql.105%29.aspx)连接到 SQL Server 数据库。 连接字符串中可以见到用于连接到 SQL Server 数据库的协议。 VIA 连接将包含 via:&lt;servername&gt;。 如果此应用通过协议而不是 VIA （例如 tcp: 或 np:）连接到 SQL，则不会遇到中断的更改。此外，也不再支持连接到 SQL Server 7 (1997)。|
|建议|VIA 协议已弃用，因此，应使用备用协议连接到 SQL 数据库。 使用的最常见的协议是 TCP/IP。 在[此处](https://msdn.microsoft.com/library/bb909712.aspx)可以找到有关启用 TCP/IP 协议的说明。 如果只能从 Intranet 访问数据库，在网络速度慢时，共享的管道协议可能会提供更好的性能。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

