---
ms.openlocfilehash: 19dcdf006de0bfa7c6b0a8127612a49a66a24802
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804585"
---
### <a name="tls-1x-by-default-passes-the-schsendauxrecord-flag-to-the-underlying-schannel-api"></a>默认情况下，TLS 1.x 将 SCH_SEND_AUX_RECORD 标记传递给基础 SCHANNEL API

|   |   |
|---|---|
|详细信息|使用 TLS 1.x 时，.NET Framework 依赖于基础 Windows SCHANNEL API。 从 .NET Framework 4.6 开始，[SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) 标记默认传递给 SCHANNEL。 这会导致 SCHANNEL 将要加密的数据拆分为两个单独的记录，第一个为 1 个字节，第二个为 <em>n</em>-1 个字节。在极少数情况下，如果假定数据驻留在一个记录中，则客户端与现有服务器之间的通信会中断。|
|建议|如果此更改中断了与现有服务器的通信，则可以将以下开关添加到应用配置文件的 [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中的 [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 元素，禁止发送 [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) 标记并还原之前不将数据拆分为单独记录的行为：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] 此设置仅用于后向兼容性。 否则不建议使用它。</blockquote> |
|范围|边缘|
|版本|4.6|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|

