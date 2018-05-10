### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase 不传播 OnStart 异常

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.7 和更早版本中，服务启动时引发的异常不会传播到 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> 的调用方。<br/>从面向.NET Framework 4.7.1 的应用程序开始，针对启动失败的服务，运行时会将异常传播到 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>。|
|建议|服务启动时，如果出现异常，将传播该异常。 这有助于诊断服务启动失败的事例。 <br/>如果不需要此行为，可在应用程序配置文件的 <runtime> 部分中添加以下 <AppContextSwitchOverrides> 元素，从而选择弃用此行为：<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>如果应用程序面向早于 4.7.1 的版本，但你需要此行为，请将以下 <AppContextSwitchOverrides> 元素添加到应用程序配置文件的 <runtime> 部分：<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.7.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|

