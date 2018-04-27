### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>WPF 文本框选定文本在文本框处于非活动状态时，将显示其他颜色

|   |   |
|---|---|
|详细信息|在 .NET 4.5 中，当 WPF 文本框控件处于非活动状态（该控件没有焦点）时，文本框中选定文本所显示的颜色与该控件处于活动状态时所显示的颜色不同。|
|建议|可以通过将 <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> 属性设置为 <code>false</code> 来还原以前的 (.NET 4.0) 行为。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

