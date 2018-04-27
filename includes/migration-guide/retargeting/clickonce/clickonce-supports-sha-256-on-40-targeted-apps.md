### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce 支持面向 4.0 的应用上的 SHA-256

|   |   |
|---|---|
|详细信息|以前，如果 ClickOnce 应用具有使用 SHA-256 签名的证书，即使应用面向 4.0 版本，也需要 .NET 4.5 或更高版本。 现在，即使使用 SHA-256 签名，面向 4.0 版本的 ClickOnce 应用也可以在 4.0 版上运行。|
|建议|此更改删除了该依赖项，允许将 SHA-256 证书用于为面向 .NET Framework 4 或更早版本的 ClickOnce 应用签名。|
|范围|次要|
|版本|4.6|
|类型|重定目标|

