### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>MinFreeMemoryPercentageToActiveService 现在受到遵从

|   |   |
|---|---|
|详细信息|此设置可确立激活 WCF 服务之前必须在服务器上可用的最小内存。 它旨在阻止 <xref:System.OutOfMemoryException?displayProperty=name> 异常。 在 .NET Framework 4.5 中，此设置没有效果。 在 .NET Framework 4.5.1 中，观察到该设置。|
|建议|如果 Web 服务器上的可用内存少于由配置设置定义的百分比，将引发异常。 某些成功启动并且在受约束的内存环境中运行的 WCF 服务现在可能失败。|
|范围|次要|
|版本|4.5.1|
|类型|运行时|

