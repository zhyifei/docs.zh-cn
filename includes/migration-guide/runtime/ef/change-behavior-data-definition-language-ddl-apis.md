### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>数据定义语言 (DDL) API 行为的更改

|   |   |
|---|---|
|详细信息|指定 AttachDBFilename 时，DDL API 的行为已更改，具体如下：<ul><li>连接字符串不需要指定 Initial Catalog 值。 以前，需要 AttachDBFilename 和 Initial Catalog。</li><li>如果指定了 AttachDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，ObjectContext.DatabaseExists 方法将返回 true。 以前，它会返回 false。</li><li>如果指定了 AttachDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，则调用 ObjectContext.DeleteDatabase 方法会删除文件。</li><li>如果在连接字符串指定某个 AttachDBFilename 值，且不存在 MDF 和 Initial Catalog 时调用 ObjectContext.DeleteDatabase，该方法将引发 InvalidOperationException 异常。 以前，它会引发 SqlException 异常。</li></ul>|
|建议|利用这些更改，可以更轻松地生成使用 DDL API 的工具和应用程序。 这些更改会影响以下方案中的应用程序兼容性：<ul><li>如果 ObjectContext.DatabaseExists 返回 true，用户将编写直接执行 DROP DATABASE 命令的代码，而不是调用 ObjectContext.DeleteDatabase。 如果未附加数据库但存在 MDF 文件，则会中断现有代码。</li><li>用户编写希望 ObjectContext.DeleteDatabase 方法在 Initial Catalog 和 MDF 文件不存在时引发 SqlException 异常而非 InvalidOperationException 异常的代码。</li></ul>|
|范围|次要|
|版本|4.5|
|类型|运行时|

