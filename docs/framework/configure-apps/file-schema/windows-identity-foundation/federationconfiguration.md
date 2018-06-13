---
title: '&lt;federationConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 44014d620dcd03e055eb58b50a1428b8e1b41186
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759382"
---
# <a name="ltfederationconfigurationgt"></a><span data-ttu-id="5534b-102">&lt;federationConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="5534b-102">&lt;federationConfiguration&gt;</span></span>
<span data-ttu-id="5534b-103">配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) 时使用联合身份验证通过 WS 联合身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="5534b-103">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="5534b-104">配置<xref:System.Security.Claims.ClaimsAuthorizationManager>时使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类以提供基于声明的访问控制。</span><span class="sxs-lookup"><span data-stu-id="5534b-104">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
 <span data-ttu-id="5534b-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="5534b-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="5534b-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5534b-106">\<federationConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5534b-107">语法</span><span class="sxs-lookup"><span data-stu-id="5534b-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5534b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5534b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5534b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5534b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5534b-110">特性</span><span class="sxs-lookup"><span data-stu-id="5534b-110">Attributes</span></span>  
  
|<span data-ttu-id="5534b-111">特性</span><span class="sxs-lookup"><span data-stu-id="5534b-111">Attribute</span></span>|<span data-ttu-id="5534b-112">描述</span><span class="sxs-lookup"><span data-stu-id="5534b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5534b-113">name</span><span class="sxs-lookup"><span data-stu-id="5534b-113">name</span></span>|<span data-ttu-id="5534b-114">此联合身份验证配置元素的名称。</span><span class="sxs-lookup"><span data-stu-id="5534b-114">The name of this federation configuration element.</span></span> <span data-ttu-id="5534b-115">此属性主要将来协议提供一个扩展点。</span><span class="sxs-lookup"><span data-stu-id="5534b-115">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="5534b-116">可选。</span><span class="sxs-lookup"><span data-stu-id="5534b-116">Optional.</span></span>|  
|<span data-ttu-id="5534b-117">identityConfigurationName</span><span class="sxs-lookup"><span data-stu-id="5534b-117">identityConfigurationName</span></span>|<span data-ttu-id="5534b-118">中指定的标识配置节名称[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素使用。</span><span class="sxs-lookup"><span data-stu-id="5534b-118">The name of the identity configuration section as specified in an [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element to use.</span></span> <span data-ttu-id="5534b-119">如果未指定此属性，则使用默认标识配置节。</span><span class="sxs-lookup"><span data-stu-id="5534b-119">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="5534b-120">可选。</span><span class="sxs-lookup"><span data-stu-id="5534b-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5534b-121">子元素</span><span class="sxs-lookup"><span data-stu-id="5534b-121">Child Elements</span></span>  
  
|<span data-ttu-id="5534b-122">元素</span><span class="sxs-lookup"><span data-stu-id="5534b-122">Element</span></span>|<span data-ttu-id="5534b-123">描述</span><span class="sxs-lookup"><span data-stu-id="5534b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5534b-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="5534b-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="5534b-125">配置使用 SAM 的 cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="5534b-125">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="5534b-126">可选。</span><span class="sxs-lookup"><span data-stu-id="5534b-126">Optional.</span></span>|  
|[<span data-ttu-id="5534b-127">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="5534b-127">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="5534b-128">配置用来加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="5534b-128">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="5534b-129">可选。</span><span class="sxs-lookup"><span data-stu-id="5534b-129">Optional.</span></span>|  
|[<span data-ttu-id="5534b-130">\<wsFederation ></span><span class="sxs-lookup"><span data-stu-id="5534b-130">\<wsFederation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|<span data-ttu-id="5534b-131">配置 WS 联合身份验证模块 (WSFAM)。</span><span class="sxs-lookup"><span data-stu-id="5534b-131">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="5534b-132">可选。</span><span class="sxs-lookup"><span data-stu-id="5534b-132">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5534b-133">父元素</span><span class="sxs-lookup"><span data-stu-id="5534b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="5534b-134">元素</span><span class="sxs-lookup"><span data-stu-id="5534b-134">Element</span></span>|<span data-ttu-id="5534b-135">描述</span><span class="sxs-lookup"><span data-stu-id="5534b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5534b-136">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="5534b-136">\<system.identityModel.services></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|<span data-ttu-id="5534b-137">使用 WS 联合身份验证协议的身份验证的配置节。</span><span class="sxs-lookup"><span data-stu-id="5534b-137">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5534b-138">备注</span><span class="sxs-lookup"><span data-stu-id="5534b-138">Remarks</span></span>  
 <span data-ttu-id="5534b-139">\<FederationConfiguration > 元素提供两种不同方案中的设置：</span><span class="sxs-lookup"><span data-stu-id="5534b-139">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
-   <span data-ttu-id="5534b-140">在使用 WS 联合被动 Web 应用程序中时，该元素包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。</span><span class="sxs-lookup"><span data-stu-id="5534b-140">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="5534b-141">它还引用标识配置要用于配置安全标记处理程序和证书，以及如声明授权管理器和声明身份验证管理器的组件。</span><span class="sxs-lookup"><span data-stu-id="5534b-141">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
-   <span data-ttu-id="5534b-142">使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供代码中的基于声明的访问控制中，元素引用配置的声明授权管理器和策略用于进行授权的标识配置决策。</span><span class="sxs-lookup"><span data-stu-id="5534b-142">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="5534b-143">这是为 true，即使在被动 Web 情况; 不是方案中例如，Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5534b-143">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="5534b-144">如果应用程序不是被动的 Web 应用程序， [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)元素 （和其子策略元素，如果存在） 的引用的标识配置`<federationConfiguration>`元素将应用的唯一的设置。</span><span class="sxs-lookup"><span data-stu-id="5534b-144">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="5534b-145">将忽略所有其他成员。</span><span class="sxs-lookup"><span data-stu-id="5534b-145">All others are ignored.</span></span>  
  
 <span data-ttu-id="5534b-146">而不考虑此方案中，则运行时加载默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-146">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="5534b-147">是，如下所示定义了此行为：</span><span class="sxs-lookup"><span data-stu-id="5534b-147">The behavior is defined as follows:</span></span>  
  
1.  <span data-ttu-id="5534b-148">如果没有任何`<federationConfiguration>`元素不存在，运行时创建的联合身份验证配置，并使用默认值填充它。</span><span class="sxs-lookup"><span data-stu-id="5534b-148">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="5534b-149">此默认联合身份验证配置将引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-149">This default federation configuration will reference the default identity configuration.</span></span>  
  
2.  <span data-ttu-id="5534b-150">如果某个`<federationConfiguration>`元素存在，它是无论它是名为还是未命名的默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-150">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="5534b-151">如果其`identityConfiguration`指定属性，引用已命名的标识配置; 否则，引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-151">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3.  <span data-ttu-id="5534b-152">如果未命名`<federationConfiguration>`元素存在，它是默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-152">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="5534b-153">如果其`identityConfiguration`指定属性，引用已命名的标识配置; 否则，引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-153">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4.  <span data-ttu-id="5534b-154">如果多个名为`<federationConfiguration>`元素是否存在以及是否未命名`<federationConfiguration>`元素存在，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="5534b-154">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="5534b-155">通常情况下，只有一个`<federationConfiguration>`定义部分。</span><span class="sxs-lookup"><span data-stu-id="5534b-155">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="5534b-156">本部分是默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-156">This section is the default federation configuration.</span></span> <span data-ttu-id="5534b-157">你可以指定多个唯一地命名`<federationConfiguration>`元素; 但是，在这种情况下，如果你想要加载未命名以外的联合身份验证配置，则必须提供的处理程序。</span><span class="sxs-lookup"><span data-stu-id="5534b-157">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="5534b-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> 事件并设置<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>到处理程序内的属性<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>对象从相应的值初始化`<federationConfiguration>`配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="5534b-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="5534b-159">`<federationConfiguration>`元素表示由<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>类。</span><span class="sxs-lookup"><span data-stu-id="5534b-159">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="5534b-160">配置对象本身由<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>类。</span><span class="sxs-lookup"><span data-stu-id="5534b-160">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="5534b-161">单个<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>实例上设置<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性，并提供应用程序的联合的配置。</span><span class="sxs-lookup"><span data-stu-id="5534b-161">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5534b-162">示例</span><span class="sxs-lookup"><span data-stu-id="5534b-162">Example</span></span>  
 <span data-ttu-id="5534b-163">下面的 XML 演示`<federationConfiguration>`指定 WSFAM 设置和指定的元素的默认 cookie 处理程序 (实例<xref:System.IdentityModel.Services.ChunkedCookieHandler>类) 由 SAM。</span><span class="sxs-lookup"><span data-stu-id="5534b-163">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5534b-164">在此示例中，cookie 处理程序和 WSFAM 都不需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="5534b-164">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="5534b-165">这是因为`requireHttps`属性`<wsFederation>`元素和`requireSsl`属性`<cookieHandlerElement>`是`false`。</span><span class="sxs-lookup"><span data-stu-id="5534b-165">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="5534b-166">对于大多数生产环境不被建议这些设置，因为它们可能存在安全风险。</span><span class="sxs-lookup"><span data-stu-id="5534b-166">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5534b-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="5534b-167">See Also</span></span>  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="5534b-168">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5534b-168">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
