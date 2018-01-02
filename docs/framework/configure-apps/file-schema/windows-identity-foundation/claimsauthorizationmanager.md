---
title: '&lt;claimsAuthorizationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: eb0475796a488489f4a32c820d1a92994237d7fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimsauthorizationmanagergt"></a>&lt;claimsAuthorizationManager&gt;
注册用于传入声明的声明授权管理器。  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<claimsAuthorizationManager >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|派生自的自定义类型<xref:System.Security.Claims.ClaimsAuthorizationManager>类。 有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。|  
  
### <a name="child-elements"></a>子元素  
 如果没有任何`type`属性，或者如果`type`属性引用<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthorizationManager>`元素不采用子元素; 但是，类派生自<xref:System.Security.Claims.ClaimsAuthorizationManager>可以定义子配置元素。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|指定服务级别标识设置。|  
  
## <a name="remarks"></a>备注  
 通过提供的默认行为<xref:System.Security.Claims.ClaimsAuthorizationManager>类始终授权的传入声明。 如果没有`type`指定属性或如果`type`属性指定<xref:System.Security.Claims.ClaimsAuthorizationManager>类，`<claimsAuthorizationManager>`元素不采用子元素。 你可以指定`type`特性来注册类型派生自<xref:System.Security.Claims.ClaimsAuthorizationManager>类，以实现自定义行为。 派生的类可以支持的子元素通过配置`<claimsAuthorizationManager>`通过重写元素<xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A>方法以处理这些元素。 为子元素定义的架构是最多的类设计器。  
  
> [!IMPORTANT]
>  使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供在代码中，引用的标识配置的基于声明的访问控制`<federationConfiguration>`元素会配置的声明授权管理器和用于使的策略授权决策。 这是为 true，即使在不是被动 Web 方案，例如 Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序的方案中。 如果应用程序不是被动的 Web 应用程序，`<claimsAuthorizationManager>`元素 （和其子策略元素，如果存在） 的引用的标识配置的应用的唯一设置。 将忽略所有其他设置。 有关详细信息，请参阅[ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)元素。  
  
 此元素设置<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType>属性。  
  
## <a name="example"></a>示例  
 下面的 XML 演示声明授权的配置管理器实现策略组成资源操作对其中每个指定的请求者必须具有对资源执行操作的声明的 boolean 类型的值组合。 实现声明授权管理器能够使用此策略的代码可在`ClaimsBasedAuthorization`示例。  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
