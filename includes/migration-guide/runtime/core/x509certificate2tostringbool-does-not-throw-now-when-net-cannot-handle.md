### <a name="x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>现在当 .NET 无法处理证书时，不会引发 X509Certificate2.ToString(bool)

|   |   |
|---|---|
|详细信息|以前如果为详细参数传递 <code>true</code>，并且安装了 .NET Framework 不支持的证书，将引发此方法。 现在，该方法将取得成功，并返回省略证书无法访问部分的有效字符串。|
|建议|应更新任何依赖 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)> 的代码，以希望返回的字符串会排除在某些情况下，API 之前曾引发的某些证书数据（例如公钥、私钥和扩展）。|
|范围|边缘|
|版本|4.6|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

