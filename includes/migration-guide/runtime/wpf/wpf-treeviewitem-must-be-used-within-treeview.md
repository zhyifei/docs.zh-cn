### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a>WPF TreeViewItem 必须在 TreeView 内使用

|   |   |
|---|---|
|详细信息|4.5 中引入了一项更改，即限制在 <xref:System.Windows.Controls.TreeView?displayProperty=name> 外使用 <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> 元素。 在下列条件下，可能会出现这种情况：<ul><li><xref:System.Windows.Controls.TreeViewItem?displayProperty=name> 的视觉父级不是面板。 （为 <xref:System.Windows.Controls.TreeView?displayProperty=name> 生成的 <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> 将有一个面板作为其父级）</li><li><xref:System.Windows.Controls.TreeViewItem?displayProperty=name> 是充当列表控件（ListBox、DataGrid、ListView 等）“项目主机”的 <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> 的后代。 无需启用虚拟化。</li><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> 进行项滚动 (<code>ScrollUnit=&quot;Item&quot;</code>)。</li><li>有些用户调用 <code>VirtualizingStackPanel.MakeVisible(v)</code> 以将元素 <code>v</code> 滚动至视图。 这可通过许多方法显式或隐式实现；或许最常见的方法是，只需单击 <code>v</code> 即可为其提供键盘焦点。</li><li>视觉父链贯穿整个 <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>，范围从 <code>v</code> 到 <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name>。</li></ul>换言之，在 <xref:System.Windows.Controls.TreeView?displayProperty=name> 之外使用 <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>，并且用户单击 <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> 的某个后代以显示它后，便可显示。 如果 <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> 的后代都没有焦点，将永远不会遇到此问题。 例如，如果 <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> 是 DataTemplate 的根，则会出现此问题。 发生此问题时，WPF 框架中将引发 InvalidCastException。|
|建议|将向此问题提供修补程序。|
|范围|次要|
|版本|4.5|
|类型|运行时|

