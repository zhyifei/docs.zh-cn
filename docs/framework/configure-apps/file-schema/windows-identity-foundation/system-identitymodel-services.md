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
# <a name="systemidentitymodelservices"></a><span data-ttu-id="85056-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="85056-102">\<system.identityModel.services></span></span>
<span data-ttu-id="85056-103">使用 WS 联合身份验证协议进行身份验证的配置节。</span><span class="sxs-lookup"><span data-stu-id="85056-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="85056-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="85056-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="85056-105">&nbsp;&nbsp; **\<System.identitymodel >**</span><span class="sxs-lookup"><span data-stu-id="85056-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85056-106">语法</span><span class="sxs-lookup"><span data-stu-id="85056-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85056-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="85056-107">Attributes and Elements</span></span>  
 <span data-ttu-id="85056-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="85056-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85056-109">特性</span><span class="sxs-lookup"><span data-stu-id="85056-109">Attributes</span></span>  
 <span data-ttu-id="85056-110">无</span><span class="sxs-lookup"><span data-stu-id="85056-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="85056-111">子元素</span><span class="sxs-lookup"><span data-stu-id="85056-111">Child Elements</span></span>  
  
|<span data-ttu-id="85056-112">元素</span><span class="sxs-lookup"><span data-stu-id="85056-112">Element</span></span>|<span data-ttu-id="85056-113">描述</span><span class="sxs-lookup"><span data-stu-id="85056-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85056-114">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="85056-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="85056-115">包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> （WSFAM） <xref:System.IdentityModel.Services.SessionAuthenticationModule>和（SAM） HTTP 模块的设置。</span><span class="sxs-lookup"><span data-stu-id="85056-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85056-116">父元素</span><span class="sxs-lookup"><span data-stu-id="85056-116">Parent Elements</span></span>  
 <span data-ttu-id="85056-117">无</span><span class="sxs-lookup"><span data-stu-id="85056-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85056-118">备注</span><span class="sxs-lookup"><span data-stu-id="85056-118">Remarks</span></span>  
 <span data-ttu-id="85056-119">`<system.identityModel.services>`将部分添加到应用程序的配置文件，以提供 SAM 和 WSFAM 的设置。</span><span class="sxs-lookup"><span data-stu-id="85056-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="85056-120">当使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.Security.Claims.ClaimsAuthorizationManager>或类在代码中提供基于声明的访问控制时，用于做出授权决定的声明授权管理器（）和策略通过`<identityConfiguration>` <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>此部分中的`<federationConfiguration>`元素隐式或显式引用的元素。</span><span class="sxs-lookup"><span data-stu-id="85056-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="85056-121">有关详细信息，请参阅[ \<federationConfiguration >](federationconfiguration.md)元素下的 "**备注**"。</span><span class="sxs-lookup"><span data-stu-id="85056-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="85056-122">部分由<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>类表示。 `<system.identityModel.services>`</span><span class="sxs-lookup"><span data-stu-id="85056-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="85056-123">在部分中配置`<federationConfiguration>`的子元素的集合由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>类表示。</span><span class="sxs-lookup"><span data-stu-id="85056-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85056-124">示例</span><span class="sxs-lookup"><span data-stu-id="85056-124">Example</span></span>  
 <span data-ttu-id="85056-125">下面的 XML 演示如何将`<system.identityModel.services>`节添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="85056-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="85056-126">必须首先为`<system.identityModel.services>`节`<system.identityModel>`和部分添加节声明。</span><span class="sxs-lookup"><span data-stu-id="85056-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="85056-127">（添加`<system.identityModel.services>`部分时，还应为`<system.identityModel>`节添加声明，以确保运行时可以根据需要创建默认`<identityConfiguration>`节。）添加了节声明后，可以在`<system.identityModel.services>`元素下配置联合身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="85056-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
