---
ms.openlocfilehash: 122a5ab3e2def7c19d3d523881fcb15df4dbca26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236358"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>ServicePointManager.SecurityProtocol 的默认值为 SecurityProtocolType.System.Default

|   |   |
|---|---|
|详细信息|从面向 .NET Framework 4.7 的应用开始，<xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 属性的默认值为 <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>。 此更改允许基于 SslStream 的 .NET Framework 网络 API（例如 FTP、HTTPS 和 SMTP）从操作系统继承默认安全协议，而不是使用 .NET Framework 定义的硬编码值。 默认值因操作系统和系统管理员执行的任何自定义配置而异。 有关 Windows 操作系统各版本中默认 SChannel 协议的信息，请参阅 [Protocols in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-)（TLS/SSL (Schannel SSP) 中的协议）。</p>对于面向 .NET Framework 早期版本的应用程序，<xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 属性的默认值取决于所面向的 .NET Framework 版本。 请参阅[“针对 .NET Framework 4.5.2 到 4.6 迁移的重定目标更改”中的“网络”部分](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking)，了解详细信息。|
|建议|此更改会影响面向 .NET Framework 4.7 或更高版本的应用程序。 <br>如果希望使用定义协议，而不是依赖于系统默认协议，可显式设置 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 属性的值。<br>如果不需要此更改，可在应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加配置设置，从而选择弃用此更改。 以下示例显示 <code>&lt;runtime&gt;</code> 部分和 <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> 选择弃用开关：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|次要|
|版本|4.7|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|
