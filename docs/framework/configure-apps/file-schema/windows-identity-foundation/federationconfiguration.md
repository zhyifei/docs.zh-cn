---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: e0ac3b663b2a65e00524fe0fba7997125721487c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297482"
---
# <a name="federationconfiguration"></a><span data-ttu-id="21353-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="21353-101">\<federationConfiguration></span></span>
<span data-ttu-id="21353-102">配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) 时使用联合身份验证通过 WS 联合身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="21353-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="21353-103">配置<xref:System.Security.Claims.ClaimsAuthorizationManager>使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类以提供基于声明的访问控制。</span><span class="sxs-lookup"><span data-stu-id="21353-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
 <span data-ttu-id="21353-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="21353-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="21353-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="21353-105">\<federationConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21353-106">语法</span><span class="sxs-lookup"><span data-stu-id="21353-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21353-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="21353-107">Attributes and Elements</span></span>  
 <span data-ttu-id="21353-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="21353-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21353-109">特性</span><span class="sxs-lookup"><span data-stu-id="21353-109">Attributes</span></span>  
  
|<span data-ttu-id="21353-110">特性</span><span class="sxs-lookup"><span data-stu-id="21353-110">Attribute</span></span>|<span data-ttu-id="21353-111">描述</span><span class="sxs-lookup"><span data-stu-id="21353-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21353-112">name</span><span class="sxs-lookup"><span data-stu-id="21353-112">name</span></span>|<span data-ttu-id="21353-113">此联合身份验证配置元素的名称。</span><span class="sxs-lookup"><span data-stu-id="21353-113">The name of this federation configuration element.</span></span> <span data-ttu-id="21353-114">此属性主要用于将来的协议提供一个扩展点。</span><span class="sxs-lookup"><span data-stu-id="21353-114">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="21353-115">可选。</span><span class="sxs-lookup"><span data-stu-id="21353-115">Optional.</span></span>|  
|<span data-ttu-id="21353-116">identityConfigurationName</span><span class="sxs-lookup"><span data-stu-id="21353-116">identityConfigurationName</span></span>|<span data-ttu-id="21353-117">中指定的标识配置节的名称[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素使用。</span><span class="sxs-lookup"><span data-stu-id="21353-117">The name of the identity configuration section as specified in an [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element to use.</span></span> <span data-ttu-id="21353-118">如果未指定此属性，则使用默认标识配置节。</span><span class="sxs-lookup"><span data-stu-id="21353-118">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="21353-119">可选。</span><span class="sxs-lookup"><span data-stu-id="21353-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21353-120">子元素</span><span class="sxs-lookup"><span data-stu-id="21353-120">Child Elements</span></span>  
  
|<span data-ttu-id="21353-121">元素</span><span class="sxs-lookup"><span data-stu-id="21353-121">Element</span></span>|<span data-ttu-id="21353-122">描述</span><span class="sxs-lookup"><span data-stu-id="21353-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21353-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="21353-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="21353-124">配置由 SAM 使用的 cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="21353-124">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="21353-125">可选。</span><span class="sxs-lookup"><span data-stu-id="21353-125">Optional.</span></span>|  
|[<span data-ttu-id="21353-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="21353-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="21353-127">配置用于加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="21353-127">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="21353-128">可选。</span><span class="sxs-lookup"><span data-stu-id="21353-128">Optional.</span></span>|  
|[<span data-ttu-id="21353-129">\<wsFederation></span><span class="sxs-lookup"><span data-stu-id="21353-129">\<wsFederation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|<span data-ttu-id="21353-130">配置 WS 联合身份验证模块 (WSFAM)。</span><span class="sxs-lookup"><span data-stu-id="21353-130">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="21353-131">可选。</span><span class="sxs-lookup"><span data-stu-id="21353-131">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21353-132">父元素</span><span class="sxs-lookup"><span data-stu-id="21353-132">Parent Elements</span></span>  
  
|<span data-ttu-id="21353-133">元素</span><span class="sxs-lookup"><span data-stu-id="21353-133">Element</span></span>|<span data-ttu-id="21353-134">描述</span><span class="sxs-lookup"><span data-stu-id="21353-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21353-135">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="21353-135">\<system.identityModel.services></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|<span data-ttu-id="21353-136">使用 WS 联合身份验证协议进行身份验证的配置节。</span><span class="sxs-lookup"><span data-stu-id="21353-136">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21353-137">备注</span><span class="sxs-lookup"><span data-stu-id="21353-137">Remarks</span></span>  
 <span data-ttu-id="21353-138">\<FederationConfiguration > 元素提供了两种不同方案中的设置：</span><span class="sxs-lookup"><span data-stu-id="21353-138">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
-   <span data-ttu-id="21353-139">元素时使用 WS 联合被动 Web 应用程序中，包含配置设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。</span><span class="sxs-lookup"><span data-stu-id="21353-139">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="21353-140">它还引用了要用来配置安全令牌处理程序和证书，以及声明授权管理器和声明身份验证管理器等组件的标识配置。</span><span class="sxs-lookup"><span data-stu-id="21353-140">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
-   <span data-ttu-id="21353-141">使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类来提供基于声明的访问控制在代码中，元素引用配置的声明授权管理器和使用进行授权策略的标识配置决策。</span><span class="sxs-lookup"><span data-stu-id="21353-141">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="21353-142">这是为 true，即使在不是被动 Web 方案; 的方案中例如，Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="21353-142">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="21353-143">如果应用程序不是被动的 Web 应用程序， [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)元素 （和其子策略元素，如果存在） 的引用的标识配置`<federationConfiguration>`元素应用的唯一设置。</span><span class="sxs-lookup"><span data-stu-id="21353-143">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="21353-144">将忽略所有其他成员。</span><span class="sxs-lookup"><span data-stu-id="21353-144">All others are ignored.</span></span>  
  
 <span data-ttu-id="21353-145">无论何种方案，在运行时加载默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="21353-145">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="21353-146">行为定义，如下所示：</span><span class="sxs-lookup"><span data-stu-id="21353-146">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="21353-147">如果没有任何`<federationConfiguration>`元素不存在，运行时创建的联合身份验证配置，并使用默认值填充它。</span><span class="sxs-lookup"><span data-stu-id="21353-147">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="21353-148">这种默认联合身份验证配置将引用的默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="21353-148">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="21353-149">如果某个`<federationConfiguration>`元素存在，它是无论它是名为还是未命名的默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="21353-149">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="21353-150">如果其`identityConfiguration`指定属性，引用名为的标识配置; 否则，引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="21353-150">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="21353-151">如果未命名`<federationConfiguration>`元素存在，它是默认的联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="21353-151">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="21353-152">如果其`identityConfiguration`指定属性，引用名为的标识配置; 否则，引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="21353-152">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="21353-153">如果多个名为`<federationConfiguration>`元素是否存在以及是否未命名`<federationConfiguration>`元素存在，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="21353-153">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="21353-154">通常情况下，只有一个`<federationConfiguration>`定义部分。</span><span class="sxs-lookup"><span data-stu-id="21353-154">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="21353-155">本部分是默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="21353-155">This section is the default federation configuration.</span></span> <span data-ttu-id="21353-156">你可以指定多个唯一命名`<federationConfiguration>`元素; 但是，在这种情况下，如果你想要加载而未命名的联合身份验证配置，则必须提供的处理程序。</span><span class="sxs-lookup"><span data-stu-id="21353-156">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="21353-157"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> 事件并设置<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>属性的处理程序内<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>对象从相应的值初始化`<federationConfiguration>`配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="21353-157"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="21353-158">`<federationConfiguration>`元素表示由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>类。</span><span class="sxs-lookup"><span data-stu-id="21353-158">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="21353-159">表示配置对象本身<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>类。</span><span class="sxs-lookup"><span data-stu-id="21353-159">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="21353-160">将单个<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>上设置实例<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性，并提供应用程序的联合的配置。</span><span class="sxs-lookup"><span data-stu-id="21353-160">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21353-161">示例</span><span class="sxs-lookup"><span data-stu-id="21353-161">Example</span></span>  
 <span data-ttu-id="21353-162">下面的 XML 演示`<federationConfiguration>`元素指定 WSFAM 设置，并指定默认 cookie 处理程序 (实例<xref:System.IdentityModel.Services.ChunkedCookieHandler>类) 由 SAM 使用。</span><span class="sxs-lookup"><span data-stu-id="21353-162">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="21353-163">在此示例中，cookie 处理程序和 WSFAM 都不需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="21353-163">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="21353-164">这是因为`requireHttps`特性，可以在`<wsFederation>`元素并`requireSsl`特性，可以在`<cookieHandlerElement>`是`false`。</span><span class="sxs-lookup"><span data-stu-id="21353-164">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="21353-165">因为它们可能会存在安全风险，这些设置不会建议用于大多数生产环境。</span><span class="sxs-lookup"><span data-stu-id="21353-165">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21353-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="21353-166">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="21353-167">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="21353-167">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
