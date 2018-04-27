### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng 现在可正确加载非标准密钥大小的 RSA 密钥

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.6.2 之前的版本中，使用非标准密钥大小的 RSA 证书的客户无法通过 <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> 和 <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> 扩展方法访问这些密钥。  引发 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>，并附带“不支持请求的密钥大小”消息。 .NET Framework 4.6.2 中已修复此问题。 同样，<xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> 和 <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> 现在可以处理非标准密钥大小，而不会引发 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>。|
|建议|如果处理依赖于先前行为的逻辑时有任何异常 - 使用非标准密钥大小时引发 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>，请考虑删除该逻辑。|
|范围|边缘|
|版本|4.6.2|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|

