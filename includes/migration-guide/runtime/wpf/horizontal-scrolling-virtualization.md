### <a name="horizontal-scrolling-and-virtualization"></a>水平滚动和虚拟化

|   |   |
|---|---|
|详细信息|此更改适用于按与主滚动方向正交的方向自行执行虚拟化的 <xref:System.Windows.Controls.ItemsControl?displayProperty=name>（主要示例是 EnableColumnVirtualization=&quot;True&quot; 的 <xref:System.Windows.Controls.DataGrid?displayProperty=name>）。  特定水平滚动操作的结果已更改为产生更直观且更类似于可类比垂直操作的结果。操作包括“滚动到此处”和“滚动到右边缘”，以使用右键单击水平滚动条所获得的菜单中的名称。  这两种方法都能计算候选偏移和调用 <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>。滚动到新偏移后，“滚动到此处”或“滚动到右边缘”的定义可能会发生变化，因为新反虚拟化的内容已更改 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> 的值。在低于 .Net 4.6.2 的版本中，滚动操作仅使用候选偏移，即使不再位于“此处”或“右边缘”也一样。  这会导致滚动翻阅出现“退回”等效果，最好是用举例来说明。 假设 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 有 ExtentWidth=1000 和 Width=200。  “滚动到右边缘”使用候选偏移 1000 - 200 = 800。  在滚动到此偏移时，新列会进行反虚拟化；假设这些列都非常宽，这样就可以将 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> 更改为 2000。  滚动结束于 HorizontalOffset=800，而翻阅“退回”到滚动条中间位置附近，刚好在 800/2000 = 40%。此更改将在发生这种情况时重新计算新的候选偏移并重试&quot;&quot;。 （垂直滚动已采用这样的做法。）此更改为最终用户提供了更易于预测的直观体验，但还可能会影响依赖水平滚动后的 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> 确切值的所有应用，不论水平滚动是由最终用户触发，还是由显式调用 <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)> 所触发。|
|建议|应将使用 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> 预测值的应用更改为：在由于反虚拟化而可能更改 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> 的任何水平滚动发生后提取实际值（和 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> 值）。|
|范围|次要|
|版本|4.6.2|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.Primitives.IScrollInfo?displayProperty=nameWithType></li></ul>|

