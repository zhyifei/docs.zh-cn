### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>不支持对具有非公共资源库的属性的双向数据绑定

|   |   |
|---|---|
|详细信息|尝试将数据绑定到没有公共资源库的方案从未受支持。 从 .NET Framework 4.5.1 开始，此方案将引发 <xref:System.InvalidOperationException?displayProperty=name>。 请注意，仅专门面向 .NET Framework 4.5.1 的应用会引发此新异常。 如果应用面向 .NET Framework 4.5，将允许该调用。 如果应用不面向特定 .NET Framework 版本，绑定将视为单向绑定。|
|建议|应更新应用以使用单向绑定，或公开公布属性的资源库。 或者，面向 .NET Framework 4.5 将使应用展示旧行为。|
|范围|次要|
|版本|4.5.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType></li></ul>|

