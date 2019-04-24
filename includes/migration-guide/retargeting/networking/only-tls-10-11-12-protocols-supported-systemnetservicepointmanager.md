---
ms.openlocfilehash: 8438341d6fcc5cf0415a2cae059bc76477a5c5e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803331"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>System.Net.ServicePointManager 和 System.Net.Security.SslStream 中仅支持 Tls 1.0、1.1 和 1.2 协议

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.6 开始，<xref:System.Net.ServicePointManager> 和 <xref:System.Net.Security.SslStream> 类仅可使用以下三种协议之一：Tls1.0、Tls1.1 或 Tls1.2。 不支持 SSL3.0 协议和 RC4 密码。|
|建议|建议的缓解操作是将服务器端应用升级到 Tls1.0、Tls1.1 或 Tls1.2。 如果这不可行或者如果客户端应用被中断，则可以使用 <xref:System.AppContext?displayProperty=name> 类并采用如两种方式中的一种来选择退出此功能：<ol><li>以编程方式在 <xref:System.AppContext?displayProperty=name> 上设置兼容性开关，如[此处](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46)所述</li><li>通过将以下行添加到 app.config 文件的 <code>&lt;runtime&gt;</code> 部分：<code>&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSchUseStrongCrypto=true&quot;/&gt;</code>；</li></ol>|
|范围|次要|
|版本|4.6|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType></li></ul>|
