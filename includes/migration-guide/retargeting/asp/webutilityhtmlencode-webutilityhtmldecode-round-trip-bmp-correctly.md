### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode 和 WebUtility.HtmlDecode 正确往返 BMP

|   |   |
|---|---|
|详细信息|对于面向 .NET Framework 4.5 的应用程序，当基本多语言平面 (BMP) 外的字符传递给 <xref:System.Net.WebUtility.HtmlDecode(System.String)> 方法时，这些字符可正确往返。|
|建议|此更改不应影响当前应用程序，但要还原原始行为，请将 <code>&lt;httpRuntime&gt;</code> 元素的 <code>targetFramework</code> 属性设置为除 &quot;4.5&quot; 以外的字符串。 还可以设置 <code>unicodeEncodingConformance</code> 配置元素的 <code>unicodeDecodingConformance</code> 和 <code>&lt;webUtility&gt;</code> 特性以单独控制 .NET Framework 的目标版本的行为。|
|范围|边缘|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|

