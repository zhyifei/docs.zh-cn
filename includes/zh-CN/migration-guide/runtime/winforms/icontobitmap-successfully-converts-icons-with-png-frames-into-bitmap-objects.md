### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap 成功将带 PNG 帧的图标转换为位图对象

|   |   |
|---|---|
|详细信息|从面向 .NET Framework 4.6 的应用起，<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 方法成功将带 PNG 帧的图标转换为位图对象。在面向 .NET Framework 4.5.2 和更早版本的应用中，如果图标对象有 PNG 帧，则 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 方法引发 <xref:System.ArgumentOutOfRangeException> 异常。此更改影响重新编译为面向 .NET Framework 4.6 的应用以及针对图标对象具有 PNG 帧时引发的 <xref:System.ArgumentOutOfRangeException> 实施特殊处理的应用。 在.NET Framework 4.6 下运行时，转换成功，不再引发 <xref:System.ArgumentOutOfRangeException> ，因此不再调用异常处理程序。<ul><li>[X] 怪异 // 使用某种机制开启或关闭该功能，通常使用运行时目标、AppContext 或配置文件。 在某些情况下需自动开启。</li><li>[ ] 生成时中断 // 如果尝试重新编译，会导致中断</li></ul>|
|建议|如果不需要此行为，可以在 app.config 文件的 <code>&lt;runtime&gt;</code> 部分中添加下面的元素，从而保留旧行为：<pre><code>&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>如果 app.config 文件中已包含 <code>AppContextSwitchOverrides</code> 元素，则新值应与值特性合并，如下所示：<pre><code>&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.6|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|

