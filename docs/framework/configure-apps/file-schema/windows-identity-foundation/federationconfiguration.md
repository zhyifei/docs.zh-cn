---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152731"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
通过 WS-联合协议使用联合身份验证时配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>（WSFAM） 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>（SAM）。 配置<xref:System.Security.Claims.ClaimsAuthorizationManager>使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类时提供基于声明的访问控制。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型.服务>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<联合配置>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|name|此联合配置元素的名称。 此属性主要为未来的协议提供扩展点。 可选。|  
|标识配置名称|标识配置中指定的标识配置部分的名称>要使用的元素。 [ \<](identityconfiguration.md) 如果未指定此属性，则使用默认标识配置部分。 可选。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<饼干汉德勒>](cookiehandler.md)|配置 SAM 使用的 Cookie 处理程序。 可选。|  
|[\<服务证书>](servicecertificate.md)|配置用于加密和解密令牌的证书。 可选。|  
|[\<ws联邦>](wsfederation.md)|配置 WS-联合身份验证模块 （WSFAM）。 可选。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<系统.身份模型.服务>](system-identitymodel-services.md)|使用 WS-联合协议进行身份验证的配置部分。|  
  
## <a name="remarks"></a>备注  
 联合\<配置>元素在两种不同的方案中提供设置：  
  
- 在被动 Web 应用程序中使用 WS-联合时，元素包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>（WSFAM） 和 （SAM） 的<xref:System.IdentityModel.Services.SessionAuthenticationModule>设置。 它还引用用于配置安全令牌处理程序和证书的标识配置，以及声明授权管理器和声明身份验证管理器等组件。  
  
- 当使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类在代码中提供基于声明的访问控制时，元素引用标识配置，该配置用于做出授权决策的声明授权管理器和策略。 这是事实，即使在不是被动 Web 方案的情况下也是如此;例如，Windows 通信基础 （WCF） 应用程序或非基于 Web 的应用程序。 如果应用程序不是被动 Web 应用程序，则`<federationConfiguration>`该元素引用的标识配置[\<的声明授权管理器>](claimsauthorizationmanager.md)元素（及其子策略元素（如果存在）是应用的唯一设置。 将忽略所有其他成员。  
  
 无论方案如何，运行时都会加载默认联合身份验证配置。 行为的定义如下：  
  
1. 如果没有`<federationConfiguration>`元素存在，运行时将创建联合配置，并将其填充为默认值。 此默认联合身份验证配置将引用默认标识配置。  
  
2. 如果存在单个`<federationConfiguration>`元素，则无论它是命名还是未命名，它都是默认的联合配置。 如果指定`identityConfiguration`了其属性，则引用命名标识配置;如果指定标识配置被引用。否则，将引用默认标识配置。  
  
3. 如果存在未命名的`<federationConfiguration>`元素，则它是默认的联合配置。 如果指定`identityConfiguration`了其属性，则引用命名标识配置;如果指定标识配置被引用。否则，将引用默认标识配置。  
  
4. 如果存在多个命名`<federationConfiguration>`元素，并且不存在未命名`<federationConfiguration>`元素，则引发异常。  
  
 通常，只定义单个`<federationConfiguration>`节。 此部分是默认联合配置。 您可以指定多个唯一命名的元素;`<federationConfiguration>`但是，您可以指定多个唯一命名的元素。但是，在这种情况下，如果要加载非命名配置以外的联合配置，则必须为 提供处理程序。 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>事件，并将处理程序<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>内的属性设置为使用配置文件中<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>相应元素中的值`<federationConfiguration>`初始化的对象。  
  
 元素`<federationConfiguration>`由类<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>表示。 配置对象本身由类<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>表示。 在<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>属性上设置单个实例<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>，并为应用程序提供联合配置。  
  
## <a name="example"></a>示例  
 以下 XML 显示了`<federationConfiguration>`一个元素，该元素指定 WSFAM 的设置，并指定 SAM 使用<xref:System.IdentityModel.Services.ChunkedCookieHandler>默认 Cookie 处理程序（类的实例）。  
  
> [!WARNING]
> 在此示例中，不需要 Cookie 处理程序和 WSFAM 使用 HTTPS。 这是因为`requireHttps``<wsFederation>`元素上的属性和`requireSsl`上的属性`<cookieHandlerElement>`是`false`。 不建议大多数生产环境使用这些设置，因为它们可能会带来安全风险。  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"
      issuer="http://localhost:15839/wsFederationSTS/Issue"
      realm="http://localhost:50969/" reply="http://localhost:50969/"
      requireHttps="false"
      signOutReply="http://localhost:50969/SignedOutPage.html"
      signOutQueryString="Param1=value2&Param2=value2"
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<身份配置>](identityconfiguration.md)
