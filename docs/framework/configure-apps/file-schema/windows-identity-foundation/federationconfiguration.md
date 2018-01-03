---
title: '&lt;federationConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0014e0224221cd5143709ba0a5b38f10e457b494
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) 时使用联合身份验证通过 WS 联合身份验证协议。 配置<xref:System.Security.Claims.ClaimsAuthorizationManager>时使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类以提供基于声明的访问控制。  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|此联合身份验证配置元素的名称。 此属性主要将来协议提供一个扩展点。 可选。|  
|identityConfigurationName|中指定的标识配置节名称[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素使用。 如果未指定此属性，则使用默认标识配置节。 可选。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|配置使用 SAM 的 cookie 处理程序。 可选。|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|配置用来加密和解密令牌的证书。 可选。|  
|[\<wsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|配置 WS 联合身份验证模块 (WSFAM)。 可选。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|使用 WS 联合身份验证协议的身份验证的配置节。|  
  
## <a name="remarks"></a>备注  
 \<FederationConfiguration > 元素提供两种不同方案中的设置：  
  
-   在使用 WS 联合被动 Web 应用程序中时，该元素包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。 它还引用标识配置要用于配置安全标记处理程序和证书，以及如声明授权管理器和声明身份验证管理器的组件。  
  
-   使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供代码中的基于声明的访问控制中，元素引用配置的声明授权管理器和策略用于进行授权的标识配置决策。 这是为 true，即使在被动 Web 情况; 不是方案中例如，Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序。 如果应用程序不是被动的 Web 应用程序， [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)元素 （和其子策略元素，如果存在） 的引用的标识配置`<federationConfiguration>`元素将应用的唯一的设置。 将忽略所有其他成员。  
  
 而不考虑此方案中，则运行时加载默认联合身份验证配置。 是，如下所示定义了此行为：  
  
1.  如果没有任何`<federationConfiguration>`元素不存在，运行时创建的联合身份验证配置，并使用默认值填充它。 此默认联合身份验证配置将引用默认标识配置。  
  
2.  如果某个`<federationConfiguration>`元素存在，它是无论它是名为还是未命名的默认联合身份验证配置。 如果其`identityConfiguration`指定属性，引用已命名的标识配置; 否则，引用默认标识配置。  
  
3.  如果未命名`<federationConfiguration>`元素存在，它是默认联合身份验证配置。 如果其`identityConfiguration`指定属性，引用已命名的标识配置; 否则，引用默认标识配置。  
  
4.  如果多个名为`<federationConfiguration>`元素是否存在以及是否未命名`<federationConfiguration>`元素存在，将引发异常。  
  
 通常情况下，只有一个`<federationConfiguration>`定义部分。 本部分是默认联合身份验证配置。 你可以指定多个唯一地命名`<federationConfiguration>`元素; 但是，在这种情况下，如果你想要加载未命名以外的联合身份验证配置，则必须提供的处理程序。 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>事件并设置<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>到处理程序内的属性<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>对象从相应的值初始化`<federationConfiguration>`配置文件中的元素。  
  
 `<federationConfiguration>`元素表示由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>类。 配置对象本身由<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>类。 单个<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>实例上设置<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性，并提供应用程序的联合的配置。  
  
## <a name="example"></a>示例  
 下面的 XML 演示`<federationConfiguration>`指定 WSFAM 设置和指定的元素的默认 cookie 处理程序 (实例<xref:System.IdentityModel.Services.ChunkedCookieHandler>类) 由 SAM。  
  
> [!WARNING]
>  在此示例中，cookie 处理程序和 WSFAM 都不需要使用 HTTPS。 这是因为`requireHttps`属性`<wsFederation>`元素和`requireSsl`属性`<cookieHandlerElement>`是`false`。 对于大多数生产环境不被建议这些设置，因为它们可能存在安全风险。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
