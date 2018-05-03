### <a name="multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>可能会重新排列单个 TableLayoutPanel 单元格中的多个项

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.5 中，如果多个项放置在同一 <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name> 单元格中，它们的显示顺序可能会与 .NET Framework 4.0 中的顺序不同。|
|建议|此行为已在 .NET Framework 4.5 的服务更新中还原。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，以解决此问题。 或者，避免在同一 <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name> 单元格中出现多个项的不明情况。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Forms.TableLayoutControlCollection.Add(System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32)?displayProperty=nameWithType></li></ul>|
|分析器|<ul><li>CD0098</li></ul>|

