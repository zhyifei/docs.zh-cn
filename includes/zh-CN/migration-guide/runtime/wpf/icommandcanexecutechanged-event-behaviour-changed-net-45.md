### <a name="icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>ICommand.CanExecuteChanged 事件行为已在 .NET 4.5 中更改

|   |   |
|---|---|
|详细信息|.NET Framework 4.5 中已忽略 <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name>，除非事件的发送程序与引发事件的对象是同一个对象。 此 bug 已在 .NET Framework 4.5 服务更新中修复。|
|建议|此 bug 已在 .NET Framework 4.5 服务版本中修复，因此确保 .NET Framework 处于最新状态或升级到 .NET Framework 4.5.1 可避免此问题出现。 或者，可修改使用 <xref:System.Windows.Input.ICommand?displayProperty=name> 的应用程序代码，确保引发 <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name> 命令的发送程序与引发该事件的对象是同一对象。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=nameWithType></li></ul>|
|分析器|<ul><li>CD0084</li></ul>|

