### <a name="typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>Type.IsAssignableFrom 会针对具有约束的泛型变量返回错误结果

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.5 中，<xref:System.Type.IsAssignableFrom(System.Type)> 在所有情况下会针对具有约束的某些泛型类型错误地返回 <code>false</code>。|
|建议|此问题已在服务更新中得到解决。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，以解决此问题。 或者，避免将 IsAssignableFrom 与对泛型参数拥有约束的泛型类型一起使用。 反射 API 可用作解决方法。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Type.IsAssignableFrom(System.Type)?displayProperty=nameWithType></li></ul>|
|分析器|<ul><li>CD0089</li></ul>|

