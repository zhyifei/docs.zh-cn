---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252172"
---
# <a name="audienceuris"></a>\<audienceUris>
指定可接受的信赖方（RP）标识符的 Uri 集。 除非令牌的作用域是允许的受众 Uri 之一，否则不会接受令牌。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<audienceUris >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
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
|mode|一个<xref:System.IdentityModel.Selectors.AudienceUriMode>值，该值指定是否应将受众限制应用于传入令牌。 可能的值为 "始终"、"从不" 和 "BearerKeyOnly"。 默认值为 "Always"。 可选。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|`<add value=xs:string>`|将`value`属性指定的 URI 添加到 audienceUris 集合。 需要 `value` 属性。 URI 区分大小写。|  
|`<clear>`|清除 audienceUris 集合。 所有标识符都将从集合中删除。|  
|`<remove value=xs:string>`|从 audienceUris 集合中移除`value`特性指定的 URI。 需要 `value` 属性。 URI 区分大小写。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|为安全标记处理程序的集合提供配置。|  
  
## <a name="remarks"></a>备注  
 默认情况下，集合为空;使用`<add>`、 `<clear>`和`<remove>`元素可修改集合。 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>和<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>对象使用受众 uri 集合中的值来配置对象中允许的<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>受众 uri 限制。  
  
 元素由<xref:System.IdentityModel.Configuration.AudienceUriElementCollection>类表示。 `<audienceUris>` 添加到集合中的单个 URI 由<xref:System.IdentityModel.Configuration.AudienceUriElement>类表示。  
  
> [!NOTE]
> 使用`<audienceUris>`元素作为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容。 元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何配置应用程序的可接受受众 Uri。 此示例配置单个 URI。 将接受范围为此 URI 的标记，所有其他标记将被拒绝。  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
