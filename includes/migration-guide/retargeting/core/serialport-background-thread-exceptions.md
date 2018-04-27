### <a name="serialport-background-thread-exceptions"></a>SerialPort 后台线程异常

|   |   |
|---|---|
|详细信息|引发操作系统异常时，使用 <xref:System.IO.Ports.SerialPort> 流创建的后台线程不再终止进程。在面向 .NET Framework 4.7 及早期版本的应用程序中，当使用 <xref:System.IO.Ports.SerialPort> 流创建的后台线程上引发了操作系统异常时，进程将终止。在面向 .NET Framework 4.7.1 或更高版本的应用程序中，后台线程等待与活动串行端口相关的操作系统事件，并可能在某些情况下崩溃，例如突然删除串行端口。|
|建议|对于面向 .NET Framework 4.7.1 的应用，如果无需异常处理，可通过将以下内容添加到 <code>app.config</code> 文件的 <code>&lt;runtime&gt;</code> 部分，从而选择不用异常处理：<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>对于面向旧版 .NET Framework，但在 .NET Framework 4.7.1 或更高版本上运行的应用，可通过将以下内容添加到 <code>app.config</code> 文件的 <code>&lt;runtime&gt;</code> 部分来选择使用异常处理：<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.7.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|

