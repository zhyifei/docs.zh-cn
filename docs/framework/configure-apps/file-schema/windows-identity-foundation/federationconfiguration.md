---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 53d6bdb34ded52e49fcc8c5de98fcd45ddabadaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942769"
---
# <a name="federationconfiguration"></a><span data-ttu-id="e822f-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e822f-101">\<federationConfiguration></span></span>
<span data-ttu-id="e822f-102">通过 WS 联合身份验证协议使用<xref:System.IdentityModel.Services.SessionAuthenticationModule>联合身份验证时配置(WSFAM)和(SAM)。<xref:System.IdentityModel.Services.WSFederationAuthenticationModule></span><span class="sxs-lookup"><span data-stu-id="e822f-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="e822f-103">当<xref:System.Security.Claims.ClaimsAuthorizationManager> 使用或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供基于声明的访问控制时, 配置。 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission></span><span class="sxs-lookup"><span data-stu-id="e822f-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
 <span data-ttu-id="e822f-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="e822f-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="e822f-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e822f-105">\<federationConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e822f-106">语法</span><span class="sxs-lookup"><span data-stu-id="e822f-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e822f-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e822f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e822f-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e822f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e822f-109">特性</span><span class="sxs-lookup"><span data-stu-id="e822f-109">Attributes</span></span>  
  
|<span data-ttu-id="e822f-110">特性</span><span class="sxs-lookup"><span data-stu-id="e822f-110">Attribute</span></span>|<span data-ttu-id="e822f-111">描述</span><span class="sxs-lookup"><span data-stu-id="e822f-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e822f-112">NAME</span><span class="sxs-lookup"><span data-stu-id="e822f-112">name</span></span>|<span data-ttu-id="e822f-113">此联合配置元素的名称。</span><span class="sxs-lookup"><span data-stu-id="e822f-113">The name of this federation configuration element.</span></span> <span data-ttu-id="e822f-114">此属性主要为未来的协议提供扩展点。</span><span class="sxs-lookup"><span data-stu-id="e822f-114">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="e822f-115">可选。</span><span class="sxs-lookup"><span data-stu-id="e822f-115">Optional.</span></span>|  
|<span data-ttu-id="e822f-116">identityConfigurationName</span><span class="sxs-lookup"><span data-stu-id="e822f-116">identityConfigurationName</span></span>|<span data-ttu-id="e822f-117">要使用的[ \<identityConfiguration >](identityconfiguration.md)元素中指定的标识配置节的名称。</span><span class="sxs-lookup"><span data-stu-id="e822f-117">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="e822f-118">如果未指定此属性, 则使用 "默认标识配置" 部分。</span><span class="sxs-lookup"><span data-stu-id="e822f-118">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="e822f-119">可选。</span><span class="sxs-lookup"><span data-stu-id="e822f-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e822f-120">子元素</span><span class="sxs-lookup"><span data-stu-id="e822f-120">Child Elements</span></span>  
  
|<span data-ttu-id="e822f-121">元素</span><span class="sxs-lookup"><span data-stu-id="e822f-121">Element</span></span>|<span data-ttu-id="e822f-122">描述</span><span class="sxs-lookup"><span data-stu-id="e822f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e822f-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="e822f-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="e822f-124">配置 SAM 使用的 cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="e822f-124">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="e822f-125">可选。</span><span class="sxs-lookup"><span data-stu-id="e822f-125">Optional.</span></span>|  
|[<span data-ttu-id="e822f-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e822f-126">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="e822f-127">配置用于加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="e822f-127">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="e822f-128">可选。</span><span class="sxs-lookup"><span data-stu-id="e822f-128">Optional.</span></span>|  
|[<span data-ttu-id="e822f-129">\<wsFederation></span><span class="sxs-lookup"><span data-stu-id="e822f-129">\<wsFederation></span></span>](wsfederation.md)|<span data-ttu-id="e822f-130">配置 WS-FEDERATION 身份验证模块 (WSFAM)。</span><span class="sxs-lookup"><span data-stu-id="e822f-130">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="e822f-131">可选。</span><span class="sxs-lookup"><span data-stu-id="e822f-131">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e822f-132">父元素</span><span class="sxs-lookup"><span data-stu-id="e822f-132">Parent Elements</span></span>  
  
|<span data-ttu-id="e822f-133">元素</span><span class="sxs-lookup"><span data-stu-id="e822f-133">Element</span></span>|<span data-ttu-id="e822f-134">描述</span><span class="sxs-lookup"><span data-stu-id="e822f-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e822f-135">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="e822f-135">\<system.identityModel.services></span></span>](system-identitymodel-services.md)|<span data-ttu-id="e822f-136">使用 WS 联合身份验证协议进行身份验证的配置节。</span><span class="sxs-lookup"><span data-stu-id="e822f-136">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e822f-137">备注</span><span class="sxs-lookup"><span data-stu-id="e822f-137">Remarks</span></span>  
 <span data-ttu-id="e822f-138">FederationConfiguration \<> 元素提供了两种不同方案中的设置:</span><span class="sxs-lookup"><span data-stu-id="e822f-138">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="e822f-139">在被动 Web 应用程序中使用 WS 联合身份验证时, 元素包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule>和 (SAM) 的设置。</span><span class="sxs-lookup"><span data-stu-id="e822f-139">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="e822f-140">它还引用了用于配置安全令牌处理程序和证书的标识配置, 以及声明授权管理器和声明身份验证管理器等组件。</span><span class="sxs-lookup"><span data-stu-id="e822f-140">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="e822f-141">当使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>或类在代码中提供基于声明的访问控制时, 元素将引用配置声明授权管理器的标识配置和用于进行授权的策略作出.</span><span class="sxs-lookup"><span data-stu-id="e822f-141">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="e822f-142">即使在非被动 Web 应用场景的情况下, 也是如此。例如, Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e822f-142">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="e822f-143">如果应用程序不是被动 Web 应用程序, `<federationConfiguration>` [ \<](claimsauthorizationmanager.md)则元素所引用的标识配置的 claimsAuthorizationManager > 元素 (及其子策略元素, 如果存在) 是唯一的设置应用.</span><span class="sxs-lookup"><span data-stu-id="e822f-143">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="e822f-144">将忽略所有其他成员。</span><span class="sxs-lookup"><span data-stu-id="e822f-144">All others are ignored.</span></span>  
  
 <span data-ttu-id="e822f-145">无论方案如何, 运行时都将加载默认的联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-145">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="e822f-146">此行为定义如下:</span><span class="sxs-lookup"><span data-stu-id="e822f-146">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="e822f-147">如果没有任何`<federationConfiguration>`元素, 则运行时将创建联合配置并使用默认值填充该配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-147">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="e822f-148">此默认的联合身份验证配置将引用默认的标识配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-148">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="e822f-149">如果存在单个`<federationConfiguration>`元素, 则它是默认的联合配置, 而不考虑它是命名还是未命名。</span><span class="sxs-lookup"><span data-stu-id="e822f-149">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="e822f-150">如果指定`identityConfiguration`其属性, 则引用命名标识配置; 否则, 将引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-150">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="e822f-151">如果存在未`<federationConfiguration>`命名的元素, 则它是默认的联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-151">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="e822f-152">如果指定`identityConfiguration`其属性, 则引用命名标识配置; 否则, 将引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-152">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="e822f-153">如果存在多`<federationConfiguration>`个命名元素, 且未`<federationConfiguration>`命名元素不存在, 则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="e822f-153">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="e822f-154">通常, 只定义了`<federationConfiguration>`一个部分。</span><span class="sxs-lookup"><span data-stu-id="e822f-154">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="e822f-155">此部分是默认的联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-155">This section is the default federation configuration.</span></span> <span data-ttu-id="e822f-156">您可以指定多个唯一命名`<federationConfiguration>`的元素; 但是, 在这种情况下, 如果要加载非命名的联合配置, 则必须为提供处理程序。</span><span class="sxs-lookup"><span data-stu-id="e822f-156">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="e822f-157"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>事件, 并将<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>处理程序中的属性设置<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>为使用配置文件中相应`<federationConfiguration>`元素的值进行初始化的对象。</span><span class="sxs-lookup"><span data-stu-id="e822f-157"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="e822f-158">元素由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>类表示。 `<federationConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="e822f-158">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="e822f-159">配置对象本身由<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>类表示。</span><span class="sxs-lookup"><span data-stu-id="e822f-159">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="e822f-160">单个<xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 实例<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>在属性上设置, 并为应用程序提供联合配置。</span><span class="sxs-lookup"><span data-stu-id="e822f-160">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e822f-161">示例</span><span class="sxs-lookup"><span data-stu-id="e822f-161">Example</span></span>  
 <span data-ttu-id="e822f-162">下面的 XML 演示一个`<federationConfiguration>`元素, 该元素指定 WSFAM 的设置, 并指定 SAM 使用默认 cookie 处理程序 ( <xref:System.IdentityModel.Services.ChunkedCookieHandler>类的实例)。</span><span class="sxs-lookup"><span data-stu-id="e822f-162">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e822f-163">在此示例中, cookie 处理程序和 WSFAM 都不需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="e822f-163">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="e822f-164">`requireHttps`这是因为`false` `<cookieHandlerElement>` `requireSsl`元素上的特性和上的特性是。 `<wsFederation>`</span><span class="sxs-lookup"><span data-stu-id="e822f-164">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="e822f-165">对于大多数生产环境, 不建议使用这些设置, 因为它们可能会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="e822f-165">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
```xml  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="e822f-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="e822f-166">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e822f-167">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e822f-167">\<identityConfiguration></span></span>](identityconfiguration.md)
