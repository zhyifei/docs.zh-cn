### <a name="non-pooled-sql-connections-will-leak-memory-if-not-explicitly-disposed"></a>如果不是显式释放，非池化 SQL 连接将会泄漏内存

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.5 中，非显式公开（通过“释放”、“关闭”或使用）的非池化 SQL 连接会泄漏内存|
|建议|此问题已在 .NET Framework 4.5 服务更新中修复。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，以解决此问题。 或者，可通过以下方式避免此问题：在“使用”模式下使用 <xref:System.Data.SqlClient.SqlConnection?displayProperty=name>（这是最佳做法）或在不需要连接时显式调用“释放”或“关闭”。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String%2CSystem.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

