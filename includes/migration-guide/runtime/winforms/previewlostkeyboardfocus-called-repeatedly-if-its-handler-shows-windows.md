### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>如果 PreviewLostKeyboardFocus 的处理程序显示 Windows 窗体消息框，将重复调用它

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，在消息框关闭时，从 <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> 处理程序中调用 <code>System.Windows.Forms.MessageBox.Show</code> 将重新触发该处理程序，从而可能会导致消息框无限循环出现。|
|建议|有两种选项可以解决此问题：<ol><li>调用 <code>System.Windows.MessageBox.Show</code>（而非 <code>System.Windows.Forms.MessageBox.Show</code>）可避免此问题出现。</li><li>在 <xref:System.Windows.UIElement.LostKeyboardFocus> 事件处理程序中显示消息框可避免此问题出现（这与 <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=name> 事件处理程序的情况不同）。</li></ol>|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|

