### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>WCF PipeConnection.GetHashAlgorithm 现在使用 SHA256

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.7.1 开始，Windows Communication Foundation 使用 SHA256 哈希为命名管道生成随机名称。 在 .NET Framework 4.7 和更早版本中，它使用 SHA1 哈希。|
|建议|如果在 .NET Framework 4.7.1 或更高版本中遇到此更改的兼容性问题，则可以通过将以下行添加到 app.config 文件的 <code>&lt;runtime&gt;</code> 部分选择弃用此更改：<pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.7.1|
|类型|运行时|

