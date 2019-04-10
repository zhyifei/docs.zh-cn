---
ms.openlocfilehash: e86542cbf96025247a29a860bfd44db5383c9d16
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760156"
---
### <a name="sslstream-supports-tls-alerts"></a>SslStream 支持 TLS 警报

|   |   |
|---|---|
|详细信息|TLS 握手失败后，第一个 I/O 读取/写入操作将引发带有内部 <xref:System.ComponentModel.Win32Exception?displayProperty=name> 异常的 <xref:System.IO.IOException?displayProperty=name>。 可以使用 [TLS 和 SSL 警报的 Schannel 错误代码](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts)将 <xref:System.ComponentModel.Win32Exception?displayProperty=name> 的 <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=name> 代码从远程方映射到 TLS 警报。 有关详细信息，请参阅 [RFC 2246：第 7.2.2 节错误警报](https://tools.ietf.org/html/rfc2246#section-7.2.2)。 <br/>.NET Framework 4.6.2 及更早版本中的行为是：如果另一方握手失败然后立即拒绝连接，则传输通道（通常为 TCP 连接）将在写入或读取时超时。|
|建议|调用网络 I/O API（例如 <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>）的应用程序应处理 <xref:System.IO.IOException> 或 <xref:System.TimeoutException?displayProperty=name>。<br/>从 .NET Framework 4.7 开始，TLS 警报功能将默认启用。 在 .NET Framework 4.7 或更高系统上运行的面向 .NET Framework 4.0 到 4.6.2 版本的应用程序将禁用该功能以保留兼容性。 <br/>以下配置 API 用于为在 .NET Framework 4.7 或更高版本上运行的 .NET Framework 4.6 和更高版本应用程序启用或禁用该功能。<ul><li>以编程方式：</li></ul>必须是应用程序执行的第一件事，因为 ServicePointManager 将只初始化一次：<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;TestSwitch.LocalAppContext.DisableCaching&quot;, true);&#13;&#10;AppContext.SetSwitch(&quot;Switch.System.Net.DontEnableTlsAlerts&quot;, true); // Set to &#39;false&#39; to enable the feature in .NET Framework 4.6 - 4.6.2.&#13;&#10;</code></pre><ul><li>AppConfig：</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableTlsAlerts=true&quot;/&gt;&#13;&#10;&lt;!-- Set to &#39;false&#39; to enable the feature in .NET Framework 4.6 - 4.6.2. --&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><ul><li>注册表项（计算机全局）：</p>将值设置为 <code>false</code> 以在 .NET Framework 4.6 - 4.6.2 中启用该功能。<ul><li>>键：HKLM\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts</li><li>类型：String</li><li>值：&quot;true&quot</li></ul></ul> |
|范围|边缘|
|Version|4.7|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.WebRequest?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.Http?displayProperty=nameWithType></li></ul>|
