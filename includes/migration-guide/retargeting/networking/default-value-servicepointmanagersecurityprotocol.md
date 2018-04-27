### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>ServicePointManager.SecurityProtocol 的默认值为 SecurityProtocolType.System.Default

|   |   |
|---|---|
|详细信息|从面向 .NET Framework 4.7 的应用开始，<xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 属性的默认值为 <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>。 此更改允许基于 SslStream 的 .NET Framework 网络 API（例如 FTP、HTTPS 和 SMTP）从操作系统继承默认安全协议，而不是使用 .NET Framework 定义的硬编码值。 默认值因操作系统和系统管理员执行的任何自定义配置而异。 有关每个版本的 Windows 操作系统中的默认 SChannel 协议的信息，请参阅 [TLS/SSL (Schannel SSP) 中的协议](https://msdn.microsoft.com/library/windows/desktop/mt808159.aspx)。对于面向早期版本 .NET Framework 的应用程序，<xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 属性的默认值取决于所面向的 .NET Framework 版本。 请参阅[“针对 .NET Framework 4.5.2 到 4.6 迁移的重定目标更改”中的“网络”部分](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking)，了解详细信息。|
|建议|此更改影响面向 .NET Framework 4.7 或更高版本的应用程序。如果希望使用定义的协议而不是依赖系统默认协议，则可显式设置 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 属性的值。如果无需此更改，可通过将配置设置添加到应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分来选择弃用此更改。 以下示例显示 <code>&lt;runtime&gt;</code> 部分和 <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> 选择弃用开关：<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.7|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|

