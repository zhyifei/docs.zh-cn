---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252093"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager>
为传入声明注册声明身份验证管理器。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthenticationManager >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|type|指定从<xref:System.Security.Claims.ClaimsAuthenticationManager>类派生的自定义类型。 有关如何指定`type`属性的详细信息，请参阅 [自定义类型引用]。|  
  
### <a name="child-elements"></a>子元素  
 <xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager>如果没有`type`属性，或者如果特性引用类，则元素不采用子元素; 但是，从派生的类可以定义子配置元素。 `type`  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|指定服务级别标识设置。|  
  
## <a name="remarks"></a>备注  
 通过<xref:System.Security.Claims.ClaimsAuthenticationManager>类提供的默认行为会回显传入声明。 如果未`type`指定任何特性或`type`特性指定了<xref:System.Security.Claims.ClaimsAuthenticationManager>类，则`<claimsAuthenticationManager>`元素不采用子元素。 可以指定`type`用于注册派生<xref:System.Security.Claims.ClaimsAuthenticationManager>自类的类型的属性，以实现自定义行为。 派生类可以通过`<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>重写方法来处理这些元素，从而支持通过元素的子元素进行的配置。 为子元素定义的架构位于类的设计器中。  
  
 `<claimsAuthenticationManager>` 元素<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>设置属性。  
  
## <a name="example"></a>示例  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
