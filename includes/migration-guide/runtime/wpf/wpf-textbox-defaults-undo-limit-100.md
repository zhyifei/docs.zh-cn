### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>WPF 文本框默认撤消限制是 100

|   |   |
|---|---|
|详细信息|在 .NET 4.5 中，WPF 文本框的默认撤消限制是 100（.NET 4.0 则没有限制）|
|建议|如果 100 的撤消限制过低，可使用 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> 显式设置该限制|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

