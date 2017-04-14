---
title: "WIF 3.5 和 WIF 4.5 之间的命名空间映射 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# WIF 3.5 和 WIF 4.5 之间的命名空间映射
从.NET 4.5开始，Windows标识基础\(WIF\)完全集成.NET Framework。  此集成造成的名称更改和WIF命名空间的某些组合和API图面。  本主题提供某些指南和泛型映射在WIF 3.5命名空间和WIF 4.5命名空间之间。  在位置的不打算详尽说明，而是提供一些一般信息有关查找在WIF 4.5的熟悉WIF 3.5选件类。  有关WIF WIF 3.5和4.5之间的差异的更多信息，请参见 [Windows Identity Foundation 4.5 中的新增功能](../../../docs/framework/security/whats-new-in-wif.md)。  有关实现中如何迁移使用WIF 3.5到WIF生成的应用程序4.5，请参见 [使用 WIF 3.5 至 WIF 4.5 构建的应用程序迁移指南](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)。  
  
## WIF 3.5到WIF 4.5命名空间映射  
 WIF选件类，集合在WIF 3.5的 `Microsoft.IdentityModel` 命名空间下，在以下命名空间中现在分配: `System.Security.Claims`、 `System.ServiceModel.Security`和 `System.IdentityModel` 命名空间WIF 4.5。  另外\+某个WIF 3.5命名空间WIF 4.5合并了或完全被删除。  
  
> [!IMPORTANT]
>  下面 `System.IdentityModel` 命名空间包含实现WCF基于声明的标识模型的选件类: <xref:System.IdentityModel.Claims?displayProperty=fullName>、 <xref:System.IdentityModel.Policy?displayProperty=fullName>和 <xref:System.IdentityModel.Selectors?displayProperty=fullName>。  WCF基于声明的标识模型由WIF取代。  在生成基于WIF时，的解决方法在这三个命名空间不应使用选件类。  
  
 下表提供的WIF 3.5选件类可以在WIF 4.5中的信息。  
  
||||  
|-|-|-|  
|**WIF 3.5命名空间**|**WIF 4.5命名空间**|**注释**|  
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=fullName>|-   表示常数的大多数选件类未实现。<br />-   用于生成安全标记服务的选件类从 `Microsoft.IdentityModel.SecurityTokenService` 已移动到 <xref:System.IdentityModel?displayProperty=fullName>。<br />-   在 `Microsoft.IdentityModel.Threading` 的选件类已移动到 <xref:System.IdentityModel?displayProperty=fullName>。<br />-   `ExceptionMapper` 和 `MruSecurityTokenCache` 选件类未实现。|  
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=fullName>|-   `IClaimsPrincipal` 和 `IClaimsIdentity` 接口在WIF 4.5未实现。  相反 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> 和 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 现在是大多数.NET主体和标识选件类派生的基类。  这意味着不会对专用的声明主体和标识选件类的需要。`Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` 和 `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` 在WIF 4.5，请使用 <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> 和 <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName>。  上述情况同样适用于其他存在于WIF 3.5的其他专用的声明主体和标识选件类的。<br />-   `Microsoft.IdentityModel.Claims.ClaimsCollection` 选件类在WIF 4.5未实现。  相反，声明的集合公开为类型 <xref:System.Security.Claims.Claim?displayProperty=fullName>的可枚举集合。<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> 和 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 提供现在完全支持LINQ的方法。|  
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=fullName>|这些元素和选件类执行了名称更改，而某些WIF 4.5放置的;例如 `Microsoft.IdentityModel.Configuraiton.ServiceConfiguration` 现在是 <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=fullName>。|  
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSIdentity`|未实现在WIF 4.5|在WIF 3.5包含选件类支持CardSpace，未实现在WIF 4.5。|  
|`Microsoft.IdentityModel.Protocols.WSTrust`|在 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> 和 <xref:System.ServiceModel.Security?displayProperty=fullName> 命名空间之间拆分。|表示ws\-discovery信任项目的选件类在 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> 命名空间;例如，<xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken> 选件类。  表示WCF服务协定、服务主机和通道使WCF服务通信使用ws\-discovery信任协议的选件类在 <xref:System.ServiceModel.Security?displayProperty=fullName> 命名空间;例如，<xref:System.ServiceModel.Security.WSTrustServiceHost> 选件类。|  
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|未实现在WIF 4.5|\-|  
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|未实现在WIF 4.5|表示XML在WIF 3.5的加密常数包含的选件类。  这些常数在WIF 4.5未实现。|  
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=fullName>|表示常数的 `EnvelopingSignature` 选件类和选件类未实现。|  
|`Microsoft.IdentityModel.SecurityTokenService`|可在 <xref:System.IdentityModel?displayProperty=fullName>、 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>和 <xref:System.IdentityModel.Tokens?displayProperty=fullName> 命名空间之间。|\-|  
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>|为被动的选件类\(ws\-discovery联邦\)方案提供配置主已移动到 <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>;但是，在某些选件类在 <xref:System.IdentityModel.Services?displayProperty=fullName>。|  
|`Microsoft.IdentityModel.Web.Controls`|未实现在WIF 4.5|在 `Microsoft.IdentityModel.Web.Controls` 的选件类实现了联合的被动登录控件，不存在WIF 4.5。|  
|`Microsoft.IdentityModel.WindowsTokenService`|未实现在WIF 4.5|\-|  
  
## 请参阅  
 [Windows Identity Foundation 4.5 中的新增功能](../../../docs/framework/security/whats-new-in-wif.md)   
 [使用 WIF 3.5 至 WIF 4.5 构建的应用程序迁移指南](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)