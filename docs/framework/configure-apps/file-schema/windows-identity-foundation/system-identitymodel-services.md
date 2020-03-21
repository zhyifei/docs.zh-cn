---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152499"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
使用 WS-联合协议进行身份验证的配置部分。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;**\<系统.身份模型.服务>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<联合配置>](federationconfiguration.md)|包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>（WSFAM） 和 （SAM） <xref:System.IdentityModel.Services.SessionAuthenticationModule> HTTP 模块的设置。|  
  
### <a name="parent-elements"></a>父元素  
 无  
  
## <a name="remarks"></a>备注  
 向应用程序的`<system.identityModel.services>`配置文件添加一节，以提供 SAM 和 WSFAM 的设置。  
  
> [!IMPORTANT]
> 当使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类在代码中提供基于声明的访问控制时，用于做出授权决策的声明授权<xref:System.Security.Claims.ClaimsAuthorizationManager>管理器 （ ） 和策略通过从本节中`<identityConfiguration>``<federationConfiguration>`的元素隐式或显式引用的元素进行配置。 有关详细信息，请参阅[\<联合配置>](federationconfiguration.md)元素下的**备注**。  
  
 该`<system.identityModel.services>`节由类<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>表示。 在节中配置的`<federationConfiguration>`子元素的集合由类<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>表示。  
  
## <a name="example"></a>示例  
 以下 XML 演示如何向配置文件添加`<system.identityModel.services>`节。 必须首先为`<system.identityModel.services>`节和`<system.identityModel>`节添加节声明。 （添加`<system.identityModel.services>`节时，还应为`<system.identityModel>`节添加声明，以确保运行时在必要时可以创建默认`<identityConfiguration>`节。添加节声明后，可以在`<system.identityModel.services>`元素下配置联合身份验证设置。  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
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
  
</configuration>  
```
