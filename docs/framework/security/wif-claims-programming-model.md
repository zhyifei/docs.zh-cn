---
title: "WIF 声明编程模型 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 149cb875-9b1c-4695-b88a-fbf1725a02f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# WIF 声明编程模型
ASP。NET 和 Windows 资格） 开发人员通常使用的空间和 IPrincipal 接口处理用户的标识信息。  中。NET 4.5、 Windows 标识基础 \(WIF\) 已经集成的声明是现在始终存在的任何主体中，如下图所示：  
  
 ![WIF 声明编程模型](../../../docs/framework/security/media/wifclaimsprogrammingmodel.png "WIFClaimsProgrammingModel")  
  
 中。NET 4.5，System.Security.Claims 包含新的 ClaimsPrincipal 和 ClaimsIdentity 类 （参见上图）。  中的所有承担者。NET 现在从 ClaimsPrincipal 派生。  内置的标识的所有类，都如 FormsIdentity asp。NET 和 WindowsIdentity 现在从 ClaimsIdentity 派生。  同样，从 ClaimsPrincipal 派生出所有内置的主体类 （如 GenericPrincipal 和 WindowsPrincipal。  
  
 报销申请由<xref:System.Security.Claims.Claim>类。  此类具有以下重要属性：  
  
-   <xref:System.Security.Claims.Claim.Type%2A>表示的类型声明的通常是一个 URI。  例如，电子邮件地址声明表示为`http://schemas.microsoft.com/ws/2008/06/identity/claims/email`。  
  
-   <xref:System.Security.Claims.Claim.Value%2A>包含声明的值，表示为字符串。  例如，电子邮件地址可以表示为"someone@contoso.com"。  
  
-   <xref:System.Security.Claims.Claim.ValueType%2A>表示该声明值的类型，通常是一个 URI。  例如，字符串类型表示为`http://www.w3.org/2001/XMLSchema#string`。  值类型必须是 QName XML 架构。  该值的格式应为`namespace#format`启用 WIF 输出 QName 有效值。  如果命名空间不是明确定义的命名空间，生成的 XML 可能不能是架构验证，因为不会针对该命名空间已发布的 XSD 文件。  默认值类型是`http://www.w3.org/2001/XMLSchema#string`。  请参阅[http:\/\/www.w3.org\/2001\/XMLSchema](http://go.microsoft.com/fwlink/?LinkId=209155)的已知值类型，您可以安全地使用。  
  
-   <xref:System.Security.Claims.Claim.Issuer%2A>是的安全令牌服务 \(STS\) 发出声明的标识符。  这可以表示为 URL 的 STS 或一个名称，如表示 STS， `https://sts1.contoso.com/sts`。  
  
-   <xref:System.Security.Claims.Claim.OriginalIssuer%2A>是在最初发布的报销申请，无论多少 STSs STS 的标识符是链中。  就像它表示<xref:System.Security.Claims.Claim.Issuer%2A>。  
  
-   <xref:System.Security.Claims.Claim.Subject%2A>是所要检查其身份的主题。  该方法包含 <xref:System.Security.Claims.ClaimsIdentity>。  
  
-   <xref:System.Security.Claims.Claim.Properties%2A>是一个字典，其中允许开发人员提供特定于应用程序的其他属性，以及网络上传输的数据，并可用于自定义验证。  
  
## 标识委派  
 一个重要的属性<xref:System.Security.Claims.ClaimsIdentity>是<xref:System.Security.Claims.ClaimsIdentity.Actor%2A>。  此属性使委派的凭据在多层中间层作为要对后端服务发出请求的客户端系统中。  
  
### Thread.CurrentPrincipal 通过访问声明  
 若要访问当前用户的组声明 RP 应用程序中，使用`Thread.CurrentPrincipal`。  
  
 下面的代码示例演示此方法获取 System.Security.Claims.ClaimsIdentity 的用法：  
  
```  
ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
```  
  
 有关更多信息，请参见 <xref:System.Security.Claims>。  
  
### 角色的声明类型  
 配置 RP 应用程序的部分是确定您的角色声明类型应为。  System.Security.Claims.ClaimsPrincipal.IsInRole\(System.String\) 使用此声明类型。  默认的声明类型是`http://schemas.microsoft.com/ws/2008/06/identity/claims/role`。  
  
### 通过从不同的标记类型的 Windows 标识基础提取的报销申请  
 WIF 支持多个组合框中的身份验证机制。  下表列出了 WIF 提取从不同的标记类型的声明。  
  
||||  
|-|-|-|  
|标记类型|生成的报销申请|映射到 Windows 访问令牌|  
|SAML 1.1|1.  来自 System.IdentityModel.SecurityTokenService.GetOutputClaimsIdentity\(System.Security.Claims.ClaimsPrincipal,System.IdentityModel.Protocols.WSTrust.RequestSecurityToken,System.IdentityModel.Scope\) 的所有声明。<br />2.  `http://schemas.microsoft.com/ws/2008/06/identity/claims/confirmationkey`包含 XML 序列化的确认码中，如果该标记包含证明令牌的报销申请。<br />3.  `http://schemas.microsoft.com/ws/2008/06/identity/claims/samlissuername`从颁发者的元素声明。<br />4.  AuthenticationMethod 和 AuthenticationInstant 索赔，如果该标记包含验证语句。|除了声明列入"SAML 1.1"，除声明类型的`http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`，将添加声明和身份将由 WindowsClaimsIdentity 相关的 Windows 身份验证。|  
|SAML 2.0|同"SAML 1.1"。|同"SAML 1.1 映射到 Windows 帐户"。|  
|X509|1.  With 的索赔可分辨名称、 电子邮件名、 SimpleName、 UpnName、 UrlName，dnsName，指纹，RsaKey （这可以提取使用 RSACryptoServiceProvider.ExportParameters 方法中的 X509Certificate2.PublicKey.Key 属性）、 DsaKey （这可以提取使用 DSACryptoServiceProvider.ExportParameters 方法中的 X509Certificate2.PublicKey.Key 属性），序列号属性从 x509 证书。<br />2.  AuthenticationMethod 声明值`http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/x509`。  此处提及的 AuthenticationInstant XmlSchema 日期时间格式验证证书的时间的值。|1.  它使用 Windows 帐户的完全合格的域名名为`http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`声明值。  .<br />2.  来自 x509 证书没有映射到 Windows、 声明和来自获得通过将证书映射到 Windows 的 windows 帐户声明。|  
|UPN|1.  声明是类似于 Windows 身份验证部分中的声明。<br />2.  AuthenticationMethod 声明值`http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password`。  AuthenticationInstant 声称 XmlSchema 日期时间格式时验证密码的时间的值。||  
|Windows （Kerberos 或 NTLM）|1.  生成的访问令牌中如索赔： PrimarySID，DenyOnlyPrimarySID，PrimaryGroupSID，DenyOnlyPrimaryGroupSID，GroupSID，DenyOnlySID，和名称<br />2.  值的 AuthenticationMethod `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/windows`。  创建的 Windows 访问令牌时的时间值的 AuthenticationInstant XMLSchema 日期时间格式。||  
|RSA 密钥对|1.  `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/rsa` RSAKeyValue 的值来声明。<br />2.  AuthenticationMethod 的值的报销申请`http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/signature`。  AuthenticationInstant 报销申请的 RSA 密钥进行了身份验证时的时间值 （即，签名已经过验证） 以 XMLSchema 日期时间格式。||  
  
|||  
|-|-|  
|身份验证类型|在"AuthenticationMethod"声明中发出的 URI|  
|密码|`urn:oasis:names:tc:SAML:1.0:am:password`|  
|Kerberos|`urn:ietf:rfc:1510`|  
|SecureRemotePassword|`urn:ietf:rfc:2945`|  
|TLSClient|`urn:ietf:rfc:2246`|  
|X509|`urn:oasis:names:tc:SAML:1.0:am:X509-PKI`|  
|PGP|`urn:oasis:names:tc:SAML:1.0:am:PGP`|  
|Spki|`urn:oasis:names:tc:SAML:1.0:am:SPKI`|  
|XmlDSig|`urn:ietf:rfc:3075`|  
|Unspecified|`urn:oasis:names:tc:SAML:1.0:am:unspecified`|