### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>HttpRequest.ContentEncoding 属性禁止使用 UTF7

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，<xref:System.Web.HttpRequest?displayProperty=name> 正文禁止使用 UTF-7 编码。 在某些情况下，取决于传入的 UTF-7 数据的应用程序数据将不会正确解码。|
|建议|理想情况下，应更新应用程序，使其在 <xref:System.Web.HttpRequest?displayProperty=name> 中不使用 UTF-7 编码。 或者，可以使用 [appSettings](https://msdn.microsoft.com/library/hh975440(v=vs.110).aspx) 元素的 <code>aspnet:AllowUtf7RequestContentEncoding</code> 属性还原旧行为。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|

