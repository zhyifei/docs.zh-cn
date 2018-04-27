### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>Sql_variant 数据使用 sql_variant 排序规则而不是数据库排序规则

|   |   |
|---|---|
|详细信息|<code>sql_variant</code> 数据使用 <code>sql_variant</code> 排序规则而不是数据库排序规则。|
|建议|如果数据库排序规则与 <code>sql_variant</code> 排序规则不同，则此更改将解决可能的数据损坏。 依赖损坏的数据的应用程序可能会失败。|
|范围|透明|
|版本|4.5|
|类型|运行时|

