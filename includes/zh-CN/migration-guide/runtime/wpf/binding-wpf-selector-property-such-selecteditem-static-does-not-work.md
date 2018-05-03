### <a name="binding-a-wpf-selector-property-such-as-selecteditem-to-a-static-property-does-not-work"></a>将 WPF 选择器属性（如‘SelectedItem’）绑定到静态属性不起作用

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.5 中，数据绑定到静态属性的 WPF 选择器属性（如 <xref:System.Windows.Controls.ListBox?displayProperty=name> 或 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 上的‘SelectedItem’）在其绑定属性更新时不会正确更新。|
|建议|此行为已在 .NET Framework 4.5 的服务更新中还原。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，以解决此问题。|
|范围|次要|
|版本|4.5|
|类型|运行时|

