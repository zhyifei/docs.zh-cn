---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;claimsAuthenticationManager&gt;
注册用于传入声明的声明身份验证管理器。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthenticationManager >  
  
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
|类型|指定自定义类型派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>类。 有关如何指定详细信息`type`属性，请参阅 [自定义类型引用]。|  
  
### <a name="child-elements"></a>子元素  
 如果没有任何`type`属性，或者如果`type`属性引用<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不采用子元素; 但是，类派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>可以定义子配置元素。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|指定服务级别标识设置。|  
  
## <a name="remarks"></a>备注  
 通过提供的默认行为<xref:System.Security.Claims.ClaimsAuthenticationManager>类回显的传入声明。 如果没有`type`指定属性或如果`type`属性指定<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不采用子元素。 你可以指定`type`特性来注册类型派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>类，以实现自定义行为。 派生的类可以支持的子元素通过配置`<claimsAuthenticationManager>`通过重写元素<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>方法以处理这些元素。 为子元素定义的架构是最多的类设计器。  
  
 `<claimsAuthenticationManager>`元素集<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>属性。  
  
## <a name="example"></a>示例  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
