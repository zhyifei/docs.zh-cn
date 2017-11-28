---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: be98c93452c9c7a37ecad5b03f5160ea08f2c82e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a>&lt;securityTokenHandlerConfiguration&gt;
提供配置令牌处理程序的集合。  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|saveBootstrapContext|指定是否应在会话令牌中包含启动令牌。 值还可以设置对令牌处理程序集合通过设置`saveBootstrapContext`属性[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。 令牌处理程序集合设置一个值重写在服务上设置的值。|  
|maximumClockSkew|A <xref:System.TimeSpan> ，指定最大允许的时钟偏差。 执行具有时效性操作，例如验证登录会话的过期时间时，可以控制最大允许的时钟偏差。 默认值为 5 分钟，"00: 05:00"。 有关如何指定详细信息<xref:System.TimeSpan>值，请参阅[Timespan 值](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。 最大时钟偏差还可以设置在服务级别通过设置`maximumClockSkew`属性[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。 令牌处理程序集合设置一个值重写在服务上设置的值。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|指定是可接受此信赖方标识符的 Uri 的集。 可选。|  
|[\<缓存 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|注册用于会话令牌和令牌重放检测的缓存。 可以指定在服务级别或对安全令牌处理程序集合。 可选。|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|控制令牌处理程序用来验证证书的设置。 可以指定在服务级别或对安全令牌处理程序集合。 如果使用自己的验证程序配置特定的处理程序，则将重写这些设置。 可选。|  
|[\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|配置的颁发者名称注册表，由标记处理程序集合中的处理程序。 可选。|  
|[\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|注册的颁发者令牌解析程序由标记处理程序集合中的处理程序。 颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。 可选。|  
|[\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|注册的服务令牌解析程序由标记处理程序集合中的处理程序。 服务的标记解析程序用于解析在传入令牌和消息上的加密令牌。 可选。|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|启用令牌重放检测并指定令牌的过期时间。 可以指定在服务级别或对安全令牌处理程序集合。 可选。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|指定与终结点注册的安全令牌处理程序的集合。|  
  
## <a name="remarks"></a>备注  
 本部分提供的属性值<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>对象。 此节中配置的设置会覆盖的服务上配置。 其中某些设置可以反过来，重写由处理程序添加到安全令牌的处理程序集合时指定的设置。  
  
## <a name="example"></a>示例  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
