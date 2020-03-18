---
ms.openlocfilehash: e6b0387d9d04aa979de289ea0c5caa6c76f4d1be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802656"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>ASP.NET 多部分处理不正确可能会导致丢失窗体数据。

|   |   |
|---|---|
|详细信息|在面向 .NET Framework 4.7.2 及更低版本的应用程序中，ASP.Net 可能会错误地解析多部分边界值，从而导致窗体数据在请求执行期间不可用。 面向 .NET Framework 4.8 或更高版本的应用程序正确解析多部分数据，因此在请求执行期间可以使用窗体值。|
|建议|从运行 .NET Framework 4.8 的应用程序开始，在面向 .NET Framework 4.8 或更高版本时使用 <code>targetFrameworkVersion</code> 元素，默认行为将更改为竖线分隔符。 在面向上述框架版本或不使用 <code>targetFrameworkVersion</code> 时，仍会返回一些值的尾随分隔符。此行为也可以通过 <code>appSetting</code> 显式控制：<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|范围|未知|
|Version|4.8|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.HttpRequest.Form?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.Files?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
