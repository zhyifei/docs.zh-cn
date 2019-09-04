---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251875"
---
# <a name="securitytokenhandlers"></a>\<securityTokenHandlers>
指定注册到终结点的安全令牌处理程序的集合。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securityTokenHandlers >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|NAME|指定令牌处理程序集合的名称。 框架唯一识别的值为 "ActAs" 和 "OnBehalfOf"。 如果使用上述任一名称指定了标记处理程序集合，则会在处理 ActAs 或 OnBehalfOf 令牌时使用该集合。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](add.md)|将安全标记处理程序添加到令牌处理程序集合。|  
|[\<clear>](clear.md)|清除标记处理程序集合中的所有安全标记处理程序。|  
|[\<remove>](remove.md)|从标记处理程序集合中移除安全标记处理程序。|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|为标记处理程序的集合提供配置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|指定服务级别标识设置。|  
  
## <a name="remarks"></a>备注  
 可以在服务配置中指定安全令牌处理程序的一个或多个命名集合。 可以通过使用`name`属性来指定集合的名称。 框架处理的唯一名称为 "ActAs" 和 "OnBehalfOf"。 如果这些集合中存在处理程序，则在处理`ActAs`和`OnBehalfOf`标记时，它们由 security token service （STS）而不是默认的处理程序使用。  
  
 默认情况下，使用以下处理程序类型<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>填充集合：、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>、和<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>。 您可以使用`<add>`、 `<remove>`和`<clear>`元素来修改集合。 必须确保集合中只存在一个特定类型的处理程序。 例如，如果从<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类派生处理程序，则可以在单个集合中配置处理程序<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>或，但不能同时配置两者。  
  
 `<securityTokenHandlerConfiguration>`使用元素指定集合中处理程序的配置设置。 通过此元素指定的设置将[ \<通过 identityConfiguration >](identityconfiguration.md)元素覆盖在服务上指定的设置。 某些处理程序（包括多个内置处理程序类型）可以通过`<add>`元素的子元素支持其他配置。 在处理程序上指定的设置将重写对集合或服务指定的等效设置。
