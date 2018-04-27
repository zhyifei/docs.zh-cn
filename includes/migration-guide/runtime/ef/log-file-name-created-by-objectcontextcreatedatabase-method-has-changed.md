### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>ObjectContext.CreateDatabase 方法创建的日志文件名已更改，以匹配 SQL Server 规范

|   |   |
|---|---|
|详细信息|当直接调用 <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> 方法或通过使用 Code First 与 SqlClient 提供程序以及连接字符串中的 AttachDBFilename 值来调用此方法时，它将创建一个名为 filename_log.ldf 而非 filename.ldf 的日志文件（其中 filename 是 AttachDBFilename 值指定的文件的名称）。 此更改通过提供根据 SQL Server 规范命名的日志文件来改进调试。|
|建议|如果日志文件名对应用而言很重要，应更新该应用，以使用标准的 _log.ldf 文件名格式。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|

