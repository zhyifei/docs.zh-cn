---
title: "WIF 会话管理 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98bce126-18a9-401b-b20d-67ee462a5f8a
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# WIF 会话管理
当客户端首先尝试访问由一个依赖方承载受保护的资源时，客户端必须首先验证为该依赖方信任的安全标记服务\(STS\)。  STS然后发出安全标记传递到客户端。  客户端将此标记为依赖方，然后授予对受保护资源的客户端访问。  但是，特别是，因为甚至可能不在同一台计算机上或字段和该依赖方同名，则不希望客户端必须重新进行身份为每个请求的STS。  相反，Windows标识基础\(WIF\)使该客户端和依赖方生成客户端使用一个会话安全标记验证到所有请求的依赖方，在第一个请求后的会话。  该依赖方可以使用此会话安全标记，存储在cookie中，重新生成客户端的 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>。  
  
 STS定义哪些身份验证客户端必须提供。  但是，客户端可以有它可以验证。STS的多个凭据。  例如，可能会从活动状态的Windows中的标记，用户名和密码、证书和smartkey。  在这种情况下，STS授予客户端多个标识，为每个标识与客户端存在的一凭据对应。  该依赖方可以使用一个或多个标识，在决定时授予客户端访问的级别。  
  
 <xref:System.IdentityModel.Tokens.SessionSecurityToken?displayProperty=fullName> 用于重新生成客户端的 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>，在 <xref:System.Security.Claims.ClaimsPrincipal.Identities%2A>包含所有客户端的标识。  集合中的每 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 包含与该标识的引导标记。  
  
 如果一个新的会话标记问题与原始标记会话的会话ID，<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler?displayProperty=fullName> 不在标记缓存更新会话标记。  应始终实例化唯一的会话ID.的一个会话标记  
  
> [!NOTE]
>  如果它接收到无效的输入，Session.SecurityTokenHandler.ReadToken引发异常; <xref:System.Xml.XmlException> 例如，因此，如果包含会话标记的cookie已损坏。  建议您捕捉此异常并提供特定于应用程序的行为。  
  
 如果受保护的网页包含或受保护字段的诸多资源\(例如小图像\)，客户端必须重新验证本身即可该依赖方下载这些资源中的每一。  对会话身份验证令牌的使用无需验证为每个请求的STS，但是，仍然意味着许多发送cookie。  您可能希望将网页，以便重要数据和资源受保护的字段存储，当次项目在未受保护的字段存储和与主网页中链接。  另外，通过设置cookie路径引用仅受保护字段。  
  
 若要运行引用模式，Microsoft建议提供处理程序为 **global.asax.cs** 文件的 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SessionSecurityTokenCreated> 事件和设置 **IsReferenceMode** 属性在 <xref:System.IdentityModel.Services.SessionSecurityTokenCreatedEventArgs.SessionToken%2A> 属性传递到的标记。  这些更新确保标记会话运行引用每个请求的模式和支持在仅将会话身份验证模块的 <xref:System.IdentityModel.Services.SessionAuthenticationModule.IsReferenceMode%2A> 属性。  
  
## 扩展性  
 可以扩展会话管理机制。  其中一个原因是提高性能。  例如，可以创建转换或优化在其内存状态之间的会话安全标记的自定义cookie处理程序，以及访问cookie。  为此，可以配置 <xref:System.IdentityModel.Services.SessionAuthenticationModule?displayProperty=fullName> 的 <xref:System.IdentityModel.Services.SessionAuthenticationModule.CookieHandler%2A?displayProperty=fullName> 属性使用从 <xref:System.IdentityModel.Services.CookieHandler?displayProperty=fullName>派生的自定义cookie处理程序。  <xref:System.IdentityModel.Services.ChunkedCookieHandler?displayProperty=fullName> 是默认cookie处理程序，因为cookie超过超文本传输协议\(HTTP\)允许的范围;如果您使用自定义cookie处理程序，则必须实现多级组块。  
  
 有关更多信息，请参见 [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) http:\/\/go.microsoft.com\/fwlink\/?LinkID\=248408\) \(示例。  此示例演示场就绪的会话缓存\(与tokenreplycache\)，以便可以使用会话引用而不是交换大cookie;此示例在场还演示保护cookie的一种简便方法。  会话缓存WCF根据。  有关保护会话，示例演示在cookie的WIF 4.5的新功能转换基于MachineKey，可将其粘贴到该web.config的相应代码段激活。  该示例“没有网络”，但是，它演示了您提供使您的应用程序需要场准备就绪。