### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims 考虑到所有 claimTypes

|   |   |
|---|---|
|详细信息|在面向 .NET Framework 4.6.1 的应用中，如果从 SAN 字段拥有多个 DNS 条目的证书初始化 X509 声明集，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> 方法会尝试将 claimType 自变量与所有 DNS 条目进行匹配。对于面向以前版本的 .NET Framework 的应用，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> 方法会尝试仅将 claimType 自变量与最后一个 DNS 条目进行匹配。|
|建议|此更改仅影响面向 .NET Framework 4.6.1 的应用程序。 在 [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) 兼容性开关中，可能会禁用此更改（如果面向 4.6.1 之前的版本，将启用此更改）。|
|范围|次要|
|版本|4.6.1|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType></li></ul>|

