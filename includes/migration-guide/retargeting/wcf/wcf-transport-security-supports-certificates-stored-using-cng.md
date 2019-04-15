---
ms.openlocfilehash: b57e0acb03a99f33460a7b6c880280b37e01a17b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234881"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>WCF 传输安全性支持使用 CNG 存储的证书

|   |   |
|---|---|
|详细信息|从面向 .NET Framework 4.6.2 的应用起，WCF 传输安全性支持使用 Windows 加密库 (CNG) 存储的证书。 此支持仅限于将证书与指数长度不超过 32 位的公钥结合使用。 当应用程序面向 .NET Framework 4.6.2 时，此功能默认启用。在旧版 .NET framework 中，尝试将 X509 证书与 CSG 密钥存储提供程序结合使用会引发异常。|
|建议|应用如果面向 .NET Framework 4.6.1 和更早版本，但在 .NET Framework 4.6.2 上运行，则可通过将以下行添加到 app.config 或 web.config 文件的 <code>&lt;runtime&gt;</code> 部分来启用对 CNG 证书的支持：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableCngCertificates=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>也可以使用以下代码以编程方式完成此操作：<pre><code class="lang-cs">private const string DisableCngCertificates = @&quot;Switch.System.ServiceModel.DisableCngCertificate&quot;;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, false);&#13;&#10;</code></pre><pre><code class="lang-vb">Const DisableCngCertificates As String = &quot;Switch.System.ServiceModel.DisableCngCertificates&quot;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, False)&#13;&#10;</code></pre>请注意，鉴于有此更改，将不再执行任何依赖无法尝试使用 CNG 证书启动安全通信的异常处理代码。|
|范围|次要|
|版本|4.6.2|
|类型|重定目标|
