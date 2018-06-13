---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ca108d7dd0498b0d7c08bb632ab45c7229ff58c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757042"
---
# <a name="ltsystemidentitymodelservicesgt"></a><span data-ttu-id="6f9b9-102">&lt;system.identityModel.services&gt;</span><span class="sxs-lookup"><span data-stu-id="6f9b9-102">&lt;system.identityModel.services&gt;</span></span>
<span data-ttu-id="6f9b9-103">使用 WS 联合身份验证协议的身份验证的配置节。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="6f9b9-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="6f9b9-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f9b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="6f9b9-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f9b9-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6f9b9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6f9b9-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f9b9-108">特性</span><span class="sxs-lookup"><span data-stu-id="6f9b9-108">Attributes</span></span>  
 <span data-ttu-id="6f9b9-109">无</span><span class="sxs-lookup"><span data-stu-id="6f9b9-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6f9b9-110">子元素</span><span class="sxs-lookup"><span data-stu-id="6f9b9-110">Child Elements</span></span>  
  
|<span data-ttu-id="6f9b9-111">元素</span><span class="sxs-lookup"><span data-stu-id="6f9b9-111">Element</span></span>|<span data-ttu-id="6f9b9-112">描述</span><span class="sxs-lookup"><span data-stu-id="6f9b9-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f9b9-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="6f9b9-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="6f9b9-114">包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) HTTP 模块。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f9b9-115">父元素</span><span class="sxs-lookup"><span data-stu-id="6f9b9-115">Parent Elements</span></span>  
 <span data-ttu-id="6f9b9-116">无</span><span class="sxs-lookup"><span data-stu-id="6f9b9-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f9b9-117">备注</span><span class="sxs-lookup"><span data-stu-id="6f9b9-117">Remarks</span></span>  
 <span data-ttu-id="6f9b9-118">添加`<system.identityModel.services>`到你的应用程序配置文件的 SAM 和 WSFAM 提供设置的部分。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f9b9-119">使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供在代码中，声明授权管理器的基于声明的访问控制 (<xref:System.Security.Claims.ClaimsAuthorizationManager>) 和用来进行授权决策的策略被配置通过`<identityConfiguration>`隐式或显式从引用的元素`<federationConfiguration>`本部分中的元素。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="6f9b9-120">有关详细信息，请参阅**备注**下[ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="6f9b9-121">`<system.identityModel.services>`部分由<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>类。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="6f9b9-122">子集合`<federationConfiguration>`节中配置的元素表示由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>类。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f9b9-123">示例</span><span class="sxs-lookup"><span data-stu-id="6f9b9-123">Example</span></span>  
 <span data-ttu-id="6f9b9-124">下面的 XML 演示如何添加`<system.identityModel.services>`到配置文件的部分。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="6f9b9-125">您必须首先添加两个部分声明`<system.identityModel.services>`部分和`<system.identityModel>`部分。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="6f9b9-126">(当你将添加`<system.identityModel.services>`部分中，则还应添加一个声明`<system.identityModel>`部分，以确保默认`<identityConfiguration>`部分可以由运行时创建，如有必要。)已添加部分声明后，你可以配置下的联合身份验证设置`<system.identityModel.services>`元素。</span><span class="sxs-lookup"><span data-stu-id="6f9b9-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
