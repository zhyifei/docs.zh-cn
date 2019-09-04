---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251812"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
使用 WS 联合身份验证协议进行身份验证的配置节。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp; **\<System.identitymodel >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> （WSFAM） <xref:System.IdentityModel.Services.SessionAuthenticationModule>和（SAM） HTTP 模块的设置。|  
  
### <a name="parent-elements"></a>父元素  
 无  
  
## <a name="remarks"></a>备注  
 `<system.identityModel.services>`将部分添加到应用程序的配置文件，以提供 SAM 和 WSFAM 的设置。  
  
> [!IMPORTANT]
> 当使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.Security.Claims.ClaimsAuthorizationManager>或类在代码中提供基于声明的访问控制时，用于做出授权决定的声明授权管理器（）和策略通过`<identityConfiguration>` <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>此部分中的`<federationConfiguration>`元素隐式或显式引用的元素。 有关详细信息，请参阅[ \<federationConfiguration >](federationconfiguration.md)元素下的 "**备注**"。  
  
 部分由<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>类表示。 `<system.identityModel.services>` 在部分中配置`<federationConfiguration>`的子元素的集合由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>类表示。  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何将`<system.identityModel.services>`节添加到配置文件。 必须首先为`<system.identityModel.services>`节`<system.identityModel>`和部分添加节声明。 （添加`<system.identityModel.services>`部分时，还应为`<system.identityModel>`节添加声明，以确保运行时可以根据需要创建默认`<identityConfiguration>`节。）添加了节声明后，可以在`<system.identityModel.services>`元素下配置联合身份验证设置。  
  
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
