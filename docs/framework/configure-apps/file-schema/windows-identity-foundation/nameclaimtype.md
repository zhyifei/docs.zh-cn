---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e403667f16e316004f766b8476e20eca9bd1c988
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltnameclaimtypegt"></a>&lt;nameClaimType&gt;
设置指定的声明类型<xref:System.Security.Principal.IIdentity.Name%2A>属性。 声明类型用于搜索<xref:System.Security.Claims.Claim>的集合中<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>此令牌处理程序方法。 然后，将匹配声明的值设置为的名称<xref:System.Security.Principal.IIdentity>生成从此令牌处理程序。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<samlSecurityTokenRequirement >  
\<nameClaimType >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|值|一个字符串，指定表示要用于声明的声明类型的 URI<xref:System.Security.Principal.IIdentity.Name%2A>属性。 必须的。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|提供有关配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类之一的派生的类。|  
  
## <a name="remarks"></a>备注  
 `<nameClaimType>`元素集<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>属性时<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>从配置初始化对象。  
  
## <a name="example"></a>示例  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
