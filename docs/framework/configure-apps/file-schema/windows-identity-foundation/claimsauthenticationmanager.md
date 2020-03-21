---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152744"
---
# <a name="claimsauthenticationmanager"></a>\<声明身份验证管理器>
注册传入声明的声明身份验证管理器。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<声明身份验证管理器>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|type|指定派生自类的<xref:System.Security.Claims.ClaimsAuthenticationManager>自定义类型。 有关如何指定属性的详细信息，`type`请参阅 [自定义类型引用]。|  
  
### <a name="child-elements"></a>子元素  
 如果没有`type`属性，或者该`type`属性引用该<xref:System.Security.Claims.ClaimsAuthenticationManager>类，则`<claimsAuthenticationManager>`元素不会采用子元素;如果该属性引用该类，则元素不会采用子元素。但是，派生自的<xref:System.Security.Claims.ClaimsAuthenticationManager>类可以定义子配置元素。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<身份配置>](identityconfiguration.md)|指定服务级别标识设置。|  
  
## <a name="remarks"></a>备注  
 通过<xref:System.Security.Claims.ClaimsAuthenticationManager>类提供的默认行为与传入的声明相呼应。 如果未`type`指定属性或`type`属性指定类，<xref:System.Security.Claims.ClaimsAuthenticationManager>则`<claimsAuthenticationManager>`元素不会采用子元素。 可以指定属性`type`以注册从<xref:System.Security.Claims.ClaimsAuthenticationManager>类派生的类型以实现自定义行为。 派生类可以通过重写`<claimsAuthenticationManager>`<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>处理这些元素的方法来支持通过元素的子元素进行配置。 为子元素定义的架构由类的设计器决定。  
  
 元素`<claimsAuthenticationManager>`设置<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>属性。  
  
## <a name="example"></a>示例  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
