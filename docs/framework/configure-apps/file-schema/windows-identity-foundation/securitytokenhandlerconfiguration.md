---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152562"
---
# <a name="securitytokenhandlerconfiguration"></a>\<安全令牌处理程序配置>
提供令牌处理程序集合的配置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<安全令牌处理程序配置>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|保存引导上下文|指定是否应在会话令牌中包括引导标记。 还可以通过在`saveBootstrapContext`[\<标识配置>](identityconfiguration.md)元素上设置属性，在令牌处理程序集合上设置该值。 令牌处理程序集合上设置的值将覆盖服务上设置的值。|  
|最大时钟|指定<xref:System.TimeSpan>允许的最大时钟偏斜的 。 控制执行时间敏感操作（如验证登录会话的过期时间）时允许的最大时钟偏差。 默认值为 5 分钟，"00：05：00"。 有关如何指定<xref:System.TimeSpan>值的详细信息，请参阅[时间跨度值](../windows-workflow-foundation/index.md)。 还可以通过在`maximumClockSkew`[\<标识配置>](identityconfiguration.md)元素上设置属性，在服务级别设置最大时钟偏斜。 令牌处理程序集合上设置的值将覆盖服务上设置的值。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<观众尤里斯·>](audienceuris.md)|指定此依赖方可接受的标识符的 URI 集。 可选。|  
|[\<缓存>](caches.md)|注册用于会话令牌和令牌重播检测的缓存。 可以在服务级别或安全令牌处理程序集合上指定。 可选。|  
|[\<证书验证>](certificatevalidation.md)|控制令牌处理程序用于验证证书的设置。 可以在服务级别或安全令牌处理程序集合上指定。 如果特定处理程序配置了自己的验证器，则这些设置将被覆盖。 可选。|  
|[\<发行人名称注册>](issuernameregistry.md)|配置令牌处理程序集合中处理程序使用的颁发者名称注册表。 可选。|  
|[\<颁发者令牌解析器>](issuertokenresolver.md)|注册令牌处理程序集合中处理程序使用的颁发者令牌解析器。 颁发者令牌解析器用于解析传入令牌和消息上的签名令牌。 可选。|  
|[\<服务令牌解析器>](servicetokenresolver.md)|注册令牌处理程序集合中处理程序使用的服务令牌解析器。 服务令牌解析器用于解析传入令牌和消息上的加密令牌。 可选。|  
|[\<令牌回放检测>](tokenreplaydetection.md)|启用令牌重播检测并指定令牌的过期时间。 可以在服务级别或安全令牌处理程序集合上指定。 可选。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<安全令牌处理程序>](securitytokenhandlers.md)|指定向终结点注册的安全令牌处理程序的集合。|  
  
## <a name="remarks"></a>备注  
 本节提供<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>对象的属性值。 本节中配置的设置将覆盖服务上配置的设置。 反过来，其中一些设置可以被在将处理程序添加到安全令牌处理程序集合时指定的设置覆盖。  
  
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
