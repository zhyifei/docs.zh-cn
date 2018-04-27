### <a name="entity-framework-version-must-match-the-net-framework-version"></a>Entity Framework 版本必须与 .NET Framework 版本匹配

|   |   |
|---|---|
|详细信息|Entity Framework 版本应与 .NET Framework 版本匹配。 Entity Framework 5 推荐用于 .NET 4.5。 .NET 4.5 项目中围绕着 <xref:System.ComponentModel.DataAnnotations>EF 4.x 存在一些已知问题。 在 .NET 4.5 中，这些问题被移动到不同的程序集中，所以在确定使用哪些注释时存在问题。|
|建议|对于 .NET Framework 4.5 升级到 Entity Framework 5|
|范围|主要|
|版本|4.5|
|类型|重定目标|

