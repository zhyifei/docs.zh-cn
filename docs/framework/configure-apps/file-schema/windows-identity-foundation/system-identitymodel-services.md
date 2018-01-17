---
title: '&lt;system.identityModel.services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 03c2fa7fe65650b760937ef06b848152893e023b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;system.identityModel.services&gt;
使用 WS 联合身份验证协议的身份验证的配置节。  
  
 \<system.identityModel.services >  
  
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
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) HTTP 模块。|  
  
### <a name="parent-elements"></a>父元素  
 无  
  
## <a name="remarks"></a>备注  
 添加`<system.identityModel.services>`到你的应用程序配置文件的 SAM 和 WSFAM 提供设置的部分。  
  
> [!IMPORTANT]
>  使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供在代码中，声明授权管理器的基于声明的访问控制 (<xref:System.Security.Claims.ClaimsAuthorizationManager>) 和用来进行授权决策的策略被配置通过`<identityConfiguration>`隐式或显式从引用的元素`<federationConfiguration>`本部分中的元素。 有关详细信息，请参阅**备注**下[ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)元素。  
  
 `<system.identityModel.services>`部分由<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>类。 子集合`<federationConfiguration>`节中配置的元素表示由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>类。  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何添加`<system.identityModel.services>`到配置文件的部分。 您必须首先添加两个部分声明`<system.identityModel.services>`部分和`<system.identityModel>`部分。 (当你将添加`<system.identityModel.services>`部分中，则还应添加一个声明`<system.identityModel>`部分，以确保默认`<identityConfiguration>`部分可以由运行时创建，如有必要。)已添加部分声明后，你可以配置下的联合身份验证设置`<system.identityModel.services>`元素。  
  
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
