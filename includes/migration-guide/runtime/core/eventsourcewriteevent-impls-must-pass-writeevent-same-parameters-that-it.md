### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>EventSource.WriteEvent impls 必须传递它接收的相同参数 WriteEvent（以及 ID）

|   |   |
|---|---|
|详细信息|运行时现在强制执行用于指定以下内容的协定：从 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 派生的用于定义 ETW 事件方法的类必须使用事件 ID（后跟 ETW 事件方法已传递的相同参数）调用基类 <code>EventSource.WriteEvent</code> 方法。|
|建议|如果 <xref:System.IndexOutOfRangeException?displayProperty=name> 读取违反此协定的事件源进程中的 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> 数据，则将引发 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 异常。|
|范围|次要|
|版本|4.5.1|
|类型|运行时|

