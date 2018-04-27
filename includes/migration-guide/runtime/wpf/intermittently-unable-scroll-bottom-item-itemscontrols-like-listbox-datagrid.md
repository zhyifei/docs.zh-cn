### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>使用自定义 DataTemplates 时，在 ItemsControls（例如 ListBox 和 DataGrid）内间歇性无法滚动到底部项目

|   |   |
|---|---|
|详细信息|在某些情况下，使用自定义 DataTemplates 时，.NET Framework 4.5 中的 bug 引起 ItemsControls（例如 <xref:System.Windows.Controls.ListBox?displayProperty=name>、<xref:System.Windows.Controls.ComboBox?displayProperty=name>、<xref:System.Windows.Controls.DataGrid?displayProperty=name> 等）无法滚动到底部项。 如果再次尝试滚动（在可重新滚动后），将可以滚动。|
|建议|此问题已在 .NET Framework 4.5.2 中解决，升级到该版本（或更高版本）的 .NET Framework 即可解决该问题。 或者，用户仍可将滚动条拖动至这些集合中的最后几个项目，但可能需要尝试两次才能成功。|
|范围|次要|
|版本|4.5|
|类型|运行时|

