---
ms.openlocfilehash: 707d26865114729cd6cec46735baa8ba6266834f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760969"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>ZipArchiveEntry 对象的 FullName 属性中的路径分隔符更改

|   |   |
|---|---|
|详细信息|对于面向 .NET Framework 4.6.1 及更高版本的应用，在通过重载 <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> 方法创建的 <xref:System.IO.Compression.ZipArchiveEntry> 对象的 <xref:System.IO.Compression.ZipArchiveEntry.FullName> 属性中，路径分隔符已从反斜杠 (&quot;&quot;) 更改为正斜杠 (&quot;/&quot;)。 该更改使 .NET 实现遵循 [.ZIP 文件格式规范](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)的 4.4.17.1 部分，还允许 .ZIP 存档在非 Windows 系统上进行解压缩。<br />对于面向非 Windows 操作系统（如 Macintosh）上旧版 .NET Framework 的应用程序，解压缩其创建的 zip 文件将无法保留目录结构。 例如，在 Macintosh 上，该应用创建一组文件，它们的文件名与目录路径相连，还与任何反斜杠 (&quot;&quot;) 字符和文件名相连。 因此，不会保留解压缩的文件的目录结构。|
|建议|对于在 Windows 操作系统上由 .NET Framework<xref:System.IO?displayProperty=nameWithType> 命名空间中的 API 解压缩的 .ZIP 文件，此更改造成的影响应该是最小的，因为这些 API 可以无缝地将正斜杠（“`/`”） 或反斜杠（“`\`”）处理为路径分隔符。<br />如果不需要此更改，可在应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加配置设置，从而选择弃用此更改。 以下示例显示 <code>&lt;runtime&gt;</code> 部分和 <code>Switch.System.IO.Compression.ZipFile.UseBackslash</code> 选择弃用开关：<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>此外，对于面向先前版本的 .NET Framework，但在 .NET Framework 4.6.1 及更高版本上运行的应用，可通过将配置设置添加到应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中来选择启用此行为。 以下展示了 <code>&lt;runtime&gt;</code> 部分和 <code>Switch.System.IO.Compression.ZipFile.UseBackslash</code> 选择弃用开关。<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|版本|4.6.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType></li></ul>|

