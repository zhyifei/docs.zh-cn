---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 53f3943524c45a43ddb60553b8ff45f19df66b14
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152458"
---
# <a name="wsfederation"></a>\<ws联邦>
为<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>（WSFAM） 提供配置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型.服务>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<联合配置>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws联邦>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|authenticationType|一个认证类型的 URI。 设置 WS-联合登录请求 wauth 参数。 可选。 默认值为空字符串，它指定请求中不包括 wauth 参数。|  
|新鲜|身份验证请求所需的最大生存期（以分钟为单位）。 设置 WS-Federation 登录请求 wfresh 参数。 可选。 默认值为 0。 可选。 **警告：** 在下一个版本 .NET Framework 4.5`freshness`中，属性将的类型`xs:string`，其默认值将为`null`。|  
|首页王国|用于身份验证的标识提供程序 （IdP） 的主要领域。 设置 WS-Federation 登录请求 whr 参数。 可选。 默认值为空字符串，它指定请求中不包括 whr 参数。|  
|颁发者|预期令牌颁发器的 URI。 设置 WS-联合登录请求和需要注销请求的基本 URL。|  
|持久性 CookieOn 被动重定向|指定是否在身份验证时发出持久性 Cookie。 可选。 默认值为"false"，未发出 Cookie。|  
|被动重定向启用|指定是否启用 WSFAM 自动将未经授权的请求重定向到 STS。 可选。 默认值为"true"，未经授权的请求将自动重定向。|  
|policy|指定要在登录请求上使用的相关策略的位置的 URL。 默认值为空字符串。 设置 WS-Federation 登录请求 wp 参数。 可选。 默认值为空字符串，它指定请求中不包括 wp 参数。|  
|realm|请求域的 URI。 （标识安全令牌服务 （STS） 的依赖方 （RP） 的 URI。设置请求 wtrealm WS-联合登录请求参数。 必需。|  
|答复|标识依赖方 (RP) 应用程序的地址的 URL 要接受来自安全标志服务 (STS) 的回复。 设置 WS-联合登录请求 wreply 参数。 可选。 默认值为空字符串，它指定请求中不包括 wreply 参数。|  
|请求|令牌颁发请求。 设置 WS-Federation 登录请求 wreq 参数。 可选。 默认值为空字符串，它指定 wreq 参数不包括在请求中。 不包括请求中的 wreq 或 wreqptr 参数意味着 STS 知道要发出哪种令牌。|  
|请求Ptr|一个指定令牌颁发请求位置的 URI。 设置请求 wreqptr 参数。 可选。 默认值为空字符串，它指定请求中不包括 wreqptr 参数。 不包括请求中的 wreq 或 wreqptr 参数意味着 STS 知道要发出哪种令牌。|  
|需要 Https|指定与安全令牌服务 （STS） 的通信是否必须使用 HTTPS 协议。 可选。 默认值为"true"，必须使用 HTTPS。|  
|resource|标识访问的资源、依赖方 (RP)和对安全标志服务 (STS) 的 URI。 可选。 设置 WS-联合登录请求 wres 参数。 可选。 默认值为空字符串，它指定请求中不包括 wres 参数。 **注意：wrs**是一个旧参数。 指定要`realm`改用 wtrealm 参数的属性。|  
|符号在查询字符串|提供扩展点，用于在 WS-联合登录请求 URL 中指定应用程序定义的查询参数。 可选。 默认值为空字符串，它指定请求中不应包含其他参数。 参数使用以下形式指定为查询字符串片段：`"param1=value1&param2=value2&param3=value3"`等。 **注：** 在配置文件中，必须使用其实体引用指定查询字符串中的"&"字符`&`。|  
|注销查询字符串|提供扩展点，用于在 WS-联合登录请求 URL 中指定应用程序定义的查询参数。 可选。 默认值为空字符串，它指定请求中不应包含其他参数。 参数使用以下形式指定为查询字符串片段：`"param1=value1&param2=value2&param3=value3"`等。 **注：** 在配置文件中，必须使用其实体引用指定查询字符串中的"&"字符`&`。|  
|符号退出回复|指定在通过 WS-联合协议进行被动注销期间，安全令牌服务 （STS） 应重定向客户端的 URL。 在 WS-联合注销请求上设置 wreply 参数。 可选。 默认值为空字符串，它指定请求中不应包含其他参数。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<联合配置>](federationconfiguration.md)|包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>（WSFAM） 和 （SAM）<xref:System.IdentityModel.Services.SessionAuthenticationModule>的设置。|  
  
## <a name="remarks"></a>备注  
 可以使用 该`<wsFederation>`元素为 WSFAM 配置默认 WS-联合参数设置和默认行为。 在元素集下`<wsFederation>`定义的 WS-联合参数设置，<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>该属性公开了等效属性。 对于 WSFAM 发出的每个请求，这些属性保持不变。 通过在请求处理期间为 WSFAM 公开的事件添加事件处理程序，可以动态更改 WS-联合参数;例如，事件<xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>。 有关详细信息，请参阅<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>类的文档。  
  
 元素`<wsFederation>`由类<xref:System.IdentityModel.Services.Configuration.WSFederationElement>表示。 配置对象本身由类<xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration>表示。 在通过<xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration><xref:System.IdentityModel.Services.Configuration.FederationConfiguration><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性访问的对象上设置单个实例，并为 WSFAM 提供配置。  
  
## <a name="example"></a>示例  
 以下 XML 显示了`<wsFederation>`指定 WSFAM 设置的元素。  
  
> [!WARNING]
> 在此示例中，WSFAM 不需要使用 HTTPS。 这是因为`requireHttps``<wsFederation>`元素上的属性被设置`false`。 对于大多数生产环境，不建议此设置，因为它可能会带来安全风险。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
