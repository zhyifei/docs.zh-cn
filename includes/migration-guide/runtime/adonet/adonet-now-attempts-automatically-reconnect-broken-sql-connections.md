### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a>ADO.NET 现在尝试自动重连已中断的 SQL 连接

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5.1 开始，.NET Framework 将尝试自动重新连接已中断的 SQL 连接。 虽然这通常会使应用更可靠，但在少数情况下，应用需要知道连接已断开，以便重新连接时可采取一些操作。|
|建议|如果由于兼容性问题而不希望使用此功能，则可通过将连接字符串（或 <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=name>）的 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=name> 属性设置为 0 来禁用此功能。|
|范围|边缘|
|版本|4.5.1|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)?displayProperty=nameWithType></li></ul>|

