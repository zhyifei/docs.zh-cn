---
title: '&lt;identityConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5070d9e886b8f5a8a0abf27593d40df8b5281267
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758992"
---
# <a name="ltidentityconfigurationgt"></a>&lt;identityConfiguration&gt;
指定服务级别标识设置。  
  
 \<system.identityModel>  
\<identityConfiguration>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|标识配置节的名称。 可以使用此名称以引用特定的配置节。 如果没有`name`指定属性，部分所定义的默认配置。 默认配置始终用于被动联合身份验证方案。 有关详细信息，请参阅[ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)元素。|  
|saveBootstrapContext|指定是否应在会话令牌中包含启动令牌。 值还可以设置对令牌处理程序集合通过设置`saveBootstrapContext`属性[ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)元素。 令牌处理程序集合设置一个值重写在服务上设置的值。|  
|maximumClockSkew|A <xref:System.TimeSpan> ，指定最大允许的时钟偏差。 执行具有时效性操作，例如验证登录会话的过期时间时，可以控制最大允许的时钟偏差。 默认值为 5 分钟，"00: 05:00"。 有关如何指定详细信息<xref:System.TimeSpan>值，请参阅[Timespan 值](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。 最大时钟偏差还可以设置对令牌处理程序集合通过设置`maximumClockSkew`属性[ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)元素。 令牌处理程序集合设置一个值重写在服务上设置的值。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<缓存 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|注册用于会话令牌和令牌重放检测的缓存。 可以指定在服务级别或对安全令牌处理程序集合。 可选。|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|控制令牌处理程序用来验证证书的设置。 可以指定在服务级别或对安全令牌处理程序集合。 可选。|  
|[\<claimsAuthenticationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|注册用于传入声明的声明身份验证管理器。 可选。|  
|[\<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|注册用于传入声明的声明授权管理器。 可选。|  
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|指定传入安全令牌所需的声明的集。 可选。|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|指定安全令牌处理程序的集合。 可以指定零个或多个安全令牌处理程序集合。 可选。|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|启用令牌重放检测并指定令牌的过期时间。 可以指定在服务级别或对安全令牌处理程序集合。 可选。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.identityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|提供用于启用应用程序中的 Windows Identity Foundation (WIF) 选项的配置。|  
  
## <a name="remarks"></a>备注  
 可能定义配置，每个都有一个唯一的名称的多个标识。 行为是，如下所示：  
  
1.  如果没有`<identityConfiguration>`指定元素。 默认标识配置为在运行时创建，且使用默认值填充。  
  
2.  如果某个`<identityConfiguration>`指定元素。 它是默认标识配置。 无论它是名为还是未命名的它并不重要。  
  
3.  如果选择多个`<identityConfiguration>`中指定了元素。 未命名的元素指定的默认标识配置。 当指定多个建议的`<identityConfiguration>`至少其中一个应未命名的元素。  
  
> [!WARNING]
>  如果指定多个`<identityConfiguration>`至少其中一个应未命名的元素。 未命名的元素将默认标识配置。  
  
 中指定的设置的一些`<identityConfiguration>`可以重写元素，由对安全令牌处理程序集合的设置或通过在单独的安全令牌处理程序的设置。  
  
> [!IMPORTANT]
>  使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供在代码中，引用的标识配置的基于声明的访问控制`<federationConfiguration>`元素会配置的声明授权管理器和用于使的策略授权决策。 这是为 true，即使在不是被动 Web 方案，例如 Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序的方案中。 如果应用程序不是被动的 Web 应用程序， [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)元素 （和其子策略元素，如果存在） 的引用的标识配置的应用的唯一设置。 将忽略所有其他设置。 有关详细信息，请参阅[ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)元素。  
  
 `<identityConfiguration>`元素表示由<xref:System.IdentityModel.Configuration.IdentityConfigurationElement>类。 表示一个标识配置节<xref:System.IdentityModel.Configuration.IdentityConfiguration>类。  
  
> [!IMPORTANT]
>  指定以下元素作为子元素的`<identityConfiguration>`元素已被否决，尽管行为仍支持向后兼容。 相反，应下, 指定这些元素[ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)元素。  
>   
>  -   [\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a>示例  
 下面的示例创建名为"alternateConfiguration"标识配置。 标识配置指定默认设置。  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>  
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
