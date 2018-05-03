### <a name="unexpected-invalidcastexception-from-invokemethod-activity-in-wf4"></a>来自 WF4 中 InvokeMethod 活动的意外 InvalidCastException

|   |   |
|---|---|
|详细信息|使用 <xref:System.Activities.Statements.InvokeMethod>（针对具有可以为 null 的参数的方法）会引发 <xref:System.InvalidCastException?displayProperty=name>。|
|建议|此行为已在 .NET Framework 4.5 的服务发布中还原。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，解决此问题。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Activities.Statements.InvokeMethod.Parameters?displayProperty=nameWithType></li></ul>|
|分析器|<ul><li>CD0088</li></ul>|

