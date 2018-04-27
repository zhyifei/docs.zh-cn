### <a name="path-colon-checks-are-stricter"></a>路径冒号检查更严格

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.6.2 中，为了支持以前不受支持的路径，进行了大量更改（无论是在长度方面还是在格式方面）。 检查正确的驱动器分隔符（冒号）语法变得更加严格，这样做的副作用是阻止了少量特选路径 API 中的某些 URI 路径，这些曾经是可以容忍的。|
|建议|如果将 URI 传递给受影响的 API，请首先将该字符串修改为合法路径。<ul><li>手动从 URL 中删除该方案（例如，从 URL 中删除 <code>file://</code>）</li><li>将 URI 传递给 <xref:System.Uri> 类并使用 <xref:System.Uri.LocalPath></li></ul>或者，通过将 <code>Switch.System.IO.UseLegacyPathHandling</code> AppContext 开关设置为 true 来选择不用新路径规范化。|
|范围|边缘|
|版本|4.6.2|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|

