---
title: '&lt;wsFederation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7fd4e12d77380942204d37b59644c46aed3a0148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltwsfederationgt"></a>&lt;wsFederation&gt;
提供有关配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM)。  
  
\<system.identityModel.services >  
\<federationConfiguration >  
\<wsFederation >  
  
## <a name="syntax"></a>语法  
  
```xml
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
                  freshness=xs:decimal  
                  homerealm=xs:string (URI)  
                  issuer=xs:string (URI)  
                  persistentCookiesOnPassiveRedirects=xs:boolean  
                  passiveRedirectEnabled=xs:boolean  
                  policy=xs:string (URI)  
                  realm=xs:string (URI)  
                  reply=xs:string (URI)  
                  request=xs:string (URI)  
                  requestPtr=xs:string (URI)  
                  requireHttps=xs:boolean  
                  resource=xs:string (URI)  
                  signInQueryString=xs:string  
                  signOutQueryString=xs:string  
                  signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|AuthenticationType|一个 URI，指定身份验证类型。 设置的 WS 联合身份验证登录请求 wauth 参数。 可选。 默认值为空字符串，它指定 wauth 参数未包含在请求中。|  
|新鲜度|所需的最长时间身份验证请求，以分钟为单位。 设置的 WS 联合身份验证登录请求 wfresh 参数。 可选。 默认值为零。 可选。 **警告：**中下一个版本的.NET Framework 4.5、`freshness`属性的类型将为`xs:string`，其默认值将为`null`。|  
|homeRealm|要用于身份验证标识提供程序 (IP) 主领域。 设置的 WS 联合身份验证登录请求 whr 参数。 可选。 默认值为空字符串，它指定 whr 参数未包含在请求中。|  
|issuer|预期的令牌颁发者的 URI。 设置登录请求的基 URL 的 WS 联合身份验证和所需的注销请求。|  
|persistentCookiesOnPassiveRedirects|指定是否在身份验证颁发了永久 cookie。 可选。 默认值为"false"，不发送 cookie。|  
|passiveRedirectEnabled|指定是否启用 WSFAM 自动将未经授权的请求重定向到 STS。 可选。 默认值为"true"，未经授权的请求自动重定向。|  
|策略|指定的位置相关的策略用于登录请求的 URL。 默认值为一个空字符串。 设置的 WS 联合身份验证登录请求 wp 参数。 可选。 默认值为空字符串，它指定 wp 参数未包含在请求中。|  
|realm|请求的领域的 URI。 (一个 URI，为安全令牌服务 (STS) 中标识信赖方 (RP)。)设置请求 wtrealm WS 联合身份验证登录请求参数。 必须的。|  
|答复|标识从该处信赖方 (RP) 应用程序希望接收安全令牌服务 (STS) 从的答复地址 URL。 设置的 WS 联合身份验证登录请求 wreply 参数。 可选。 默认值为空字符串，它指定 wreply 参数未包含在请求中。|  
|请求|令牌颁发请求。 设置的 WS 联合身份验证登录请求 wreq 参数。 可选。 默认值为空字符串，它指定 wreq 参数未包含在请求中。 不在请求中包括 wreq 或 wreqptr 参数意味着 STS，了解哪种类型的令牌颁发。|  
|requestPtr|指定令牌颁发请求的位置的 URL。 设置请求 wreqptr 参数。 可选。 默认值为空字符串，它指定 wreqptr 参数未包含在请求中。 不在请求中包括 wreq 或 wreqptr 参数意味着 STS，了解哪种类型的令牌颁发。|  
|requireHttps|指定与安全令牌服务 (STS) 的通信是否必须使用 HTTPS 协议。 可选。 默认值为"true"时，必须使用 HTTPS。|  
|Resource — 资源|一个 URI，标识要访问的资源的信赖方 (RP) 到到安全令牌服务 (STS)。 可选。 设置的 WS 联合身份验证登录请求 wres 参数。 可选。 默认值为空字符串，它指定 wres 参数未包含在请求中。 **注意：** wres 是旧的参数。 指定`realm`属性以改为使用 wtrealm 参数。|  
|signInQueryString|提供一个扩展性点，以便在 WS 联合身份验证登录请求 URL 中指定应用程序定义查询参数。 可选。 默认值为空字符串，指定应在请求中包含任何其他参数。 参数指定为使用以下形式的查询字符串片段： `"param1=value1&param2=value2&param3=value3"` ，依此类推。 **注意：**配置文件中 &"必须使用其实体引用，指定查询字符串中的字符`&`。|  
|signOutQueryString|提供一个扩展性点，以便在 WS 联合身份验证登录请求 URL 中指定应用程序定义查询参数。 可选。 默认值为空字符串，指定应在请求中包含任何其他参数。 参数指定为使用以下形式的查询字符串片段： `"param1=value1&param2=value2&param3=value3"` ，依此类推。 **注意：**配置文件中 &"必须使用其实体引用，指定查询字符串中的字符`&`。|  
|signOutReply|在被动注销通过 WS 联合身份验证协议期间指定的客户端应被重定向到由安全令牌服务 (STS) 的 URL。 WS 联合身份验证的注销请求上设置 wreply 参数。 可选。 默认值为空字符串，指定应在请求中包含任何其他参数。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。|  
  
## <a name="remarks"></a>备注  
 你可以使用`<wsFederation>`元素为 WSFAM 配置默认 WS 联合身份验证参数设置和默认行为。 WS 联合身份验证参数设置下定义`<wsFederation>`元素设置公开的等效属性<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>类。 这些属性中保持不变由 WSFAM 颁发的每个请求。 你可以添加由 WSFAM; 公开的事件的事件处理程序处理请求的过程动态更改的 WS 联合身份验证参数例如，<xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>事件。 有关详细信息，请参阅的文档<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>类。  
  
 `<wsFederation>`元素表示由<xref:System.IdentityModel.Services.Configuration.WSFederationElement>类。 配置对象本身由<xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration>类。 单个<xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration>实例上设置<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>通过访问的对象<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性并为 WSFAM 提供配置。  
  
## <a name="example"></a>示例  
 下面的 XML 演示`<wsFederation>`指定 WSFAM 设置的元素。  
  
> [!WARNING]
>  在此示例中，WSFAM 不需要使用 HTTPS。 这是因为`requireHttps`属性`<wsFederation>`元素设置`false`。 对于大多数生产环境不被建议此设置，因为它可能存在安全风险。  
  
```xml
<wsFederation passiveRedirectEnabled="true"   
              issuer="http://localhost:15839/wsFederationSTS/Issue"   
              realm="http://localhost:50969/"   
              reply="http://localhost:50969/"   
              requireHttps="false"   
              signOutReply="http://localhost:50969/SignedOutPage.html"   
              signOutQueryString="Param1=value2&Param2=value2"   
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
