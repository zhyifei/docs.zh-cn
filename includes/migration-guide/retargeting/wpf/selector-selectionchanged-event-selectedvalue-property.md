### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a>选择器 SelectionChanged 事件和 SelectedValue 属性

|   |   |
|---|---|
|详细信息|自 .Net Framework 4.7.1 起，在引发 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 事件之前，<xref:System.Windows.Controls.Primitives.Selector> 始终在选择更改时更新其 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 属性值。 这使得 SelectedValue 属性与其他引发事件前更新的选择属性（<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> 和 <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>）相一致。在 .NET Framework 4.7 和更低版本中，大多情况下 SelectedValue 的更新发生在事件前，但是如果选择更改是由更改 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 属性导致的，那么它发生在事件后。|
|建议|对于面向 .NET Framework 4.7.1 或更高版本的应用，可以在应用程序配置文件的 <code>&lt;runtime&gt;</code> 部分添加以下内容，从而选择弃用此更改并启用旧版行为：<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>对于面向 .NET Framework 4.7 或更早版本，但在 .NET Framework 4.7.1 或更高版本上运行的应用，可以在应用程序配置文件的 <code>&lt;runtime&gt;</code> 部分中添加以下代码行，从而启用新的行为：<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.7.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|

