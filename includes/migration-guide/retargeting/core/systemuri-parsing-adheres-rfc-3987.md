### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>System.Uri 分析符合 RFC 3987

|   |   |
|---|---|
|详细信息|URI 分析在 .NET 4.5 中做了几方面的更改。 但请注意，这些更改仅影响面向 .NET 4.5 的代码。 如果二进制文件面向 .NET 4.0，将遵守旧行为。 .NET 4.5 中对 URI 分析所做的更改包括：<ul><li>URI 分析将根据 RFC 3987 中的最新 IRI 规则执行规范化和字符检查。</li><li>将仅对 URI 的主机部分执行 Unicode 范式 C。</li><li>无效的 mailto: URI 现在会引发异常。</li><li>现在将保留路径段末尾的尾随点。</li><li><code>file://</code> URI 不会转义 <code>?</code> 字符。</li><li>不支持从 <code>U+0080</code> 到 <code>U+009F</code> 的 Unicode 控制字符。</li><li>逗号字符 <code>,</code> 或 <code>%2c</code> 不会自动取消转义。</li></ul>|
|建议|如果需要使用旧的 .NET 4.0 URI 分析语义（通常不需要），可通过面向 .NET 4.0 使用它们。 这可通过在程序集上使用 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> 来实现，也可以通过“项目属性”页中 Visual Studio 的项目系统 UI 来实现。|
|范围|主要|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Uri.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.UriKind)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.Uri,System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li></ul>|

