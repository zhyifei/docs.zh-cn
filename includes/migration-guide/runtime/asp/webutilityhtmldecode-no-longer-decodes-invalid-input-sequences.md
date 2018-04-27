### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>WebUtility.HtmlDecode 不再对无效的输入序列进行解码

|   |   |
|---|---|
|详细信息|默认情况下，解码方法不再将无效的输入序列解码为无效的 UTF-16 字符串。 相反，它们将返回原始的输入。|
|建议|仅当你存储二进制数据而不是字符串中的 UTF-16 数据时，解码器输出中的更改才会起作用。 要显式控制此行为，请将 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) 元素的 <code>aspnet:AllowRelaxedUnicodeDecoding</code> 特性设置为 <code>true</code> 以启用旧行为，或设置为 <code>false</code> 以启用当前行为。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|

