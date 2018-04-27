### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>从 DataGrid 的 UnloadingRow 事件的处理程序访问 WPF DataGrid 的选定项可能会导致 NullReferenceException

|   |   |
|---|---|
|详细信息|由于 .NET Framework 4.5 中的 bug，涉及删除行的 <xref:System.Windows.Controls.DataGrid> 事件的事件处理程序如果访问 <xref:System.Windows.Controls.DataGrid> 的 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> 或 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> 属性，可能会导致引发 <xref:System.NullReferenceException?displayProperty=name>。|
|建议|此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|

