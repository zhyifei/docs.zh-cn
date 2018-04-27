### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a>Enumerable.Empty&lt;TResult&gt; 始终返回缓存的实例

|   |   |
|---|---|
|详细信息|从 .NET 4.5 开始，<xref:System.Linq.Enumerable.Empty%60%601> 始终返回缓存的内部实例 <xref:System.Collections.Generic.IEnumerable%601>。以前，在调用 API 时，<xref:System.Linq.Enumerable.Empty%60%601> 将缓存空 <xref:System.Collections.Generic.IEnumerable%601>，这意味着在同时快速调用 <xref:System.Linq.Enumerable.Empty%60%601> 的某些情况下，针对 API 的不同调用将返回不同的类型实例。|
|建议|因为以前的行为不确定，所以代码不太可能依赖它。 但是，如果出现需要比较空枚举并希望它们有时不相等这一罕见情形，应创建显式空数组 (<code>new T[0]</code>)，而非使用 <xref:System.Linq.Enumerable.Empty%60%601>。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|

