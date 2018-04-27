### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>现在，WCF 消息安全性能够使用 TLS1.1 和 TLS1.2

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.7 开始，除 SSL3.0 和 TLS1.0 之外，客户还可通过应用程序配置设置在 WCF 消息安全性中配置 TLS1.1 或 TLS1.2。|
|建议|在 .NET Framework 4.7 中，默认情况下禁用 WCF 消息安全性中对 TLS1.1 和 TLS1.2 的支持。 可通过将以下行添加到 app.config 或 web.config 文件的 <code>&lt;runtime&gt;</code> 部分来启用支持：<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|版本|4.7|
|类型|重定目标|

