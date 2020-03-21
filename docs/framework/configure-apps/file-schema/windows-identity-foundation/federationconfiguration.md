---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152731"
---
# <a name="federationconfiguration"></a><span data-ttu-id="2ded3-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="2ded3-101">\<federationConfiguration></span></span>
<span data-ttu-id="2ded3-102">通过 WS-联合协议使用联合身份验证时配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>（WSFAM） 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>（SAM）。</span><span class="sxs-lookup"><span data-stu-id="2ded3-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="2ded3-103">配置<xref:System.Security.Claims.ClaimsAuthorizationManager>使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类时提供基于声明的访问控制。</span><span class="sxs-lookup"><span data-stu-id="2ded3-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
<span data-ttu-id="2ded3-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ded3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ded3-105">&nbsp;&nbsp;[**\<系统.身份模型.服务>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="2ded3-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="2ded3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<联合配置>**</span><span class="sxs-lookup"><span data-stu-id="2ded3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ded3-107">语法</span><span class="sxs-lookup"><span data-stu-id="2ded3-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ded3-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2ded3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2ded3-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2ded3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ded3-110">属性</span><span class="sxs-lookup"><span data-stu-id="2ded3-110">Attributes</span></span>  
  
|<span data-ttu-id="2ded3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2ded3-111">Attribute</span></span>|<span data-ttu-id="2ded3-112">说明</span><span class="sxs-lookup"><span data-stu-id="2ded3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ded3-113">name</span><span class="sxs-lookup"><span data-stu-id="2ded3-113">name</span></span>|<span data-ttu-id="2ded3-114">此联合配置元素的名称。</span><span class="sxs-lookup"><span data-stu-id="2ded3-114">The name of this federation configuration element.</span></span> <span data-ttu-id="2ded3-115">此属性主要为未来的协议提供扩展点。</span><span class="sxs-lookup"><span data-stu-id="2ded3-115">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="2ded3-116">可选。</span><span class="sxs-lookup"><span data-stu-id="2ded3-116">Optional.</span></span>|  
|<span data-ttu-id="2ded3-117">标识配置名称</span><span class="sxs-lookup"><span data-stu-id="2ded3-117">identityConfigurationName</span></span>|<span data-ttu-id="2ded3-118">标识配置中指定的标识配置部分的名称>要使用的元素。 [ \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2ded3-118">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="2ded3-119">如果未指定此属性，则使用默认标识配置部分。</span><span class="sxs-lookup"><span data-stu-id="2ded3-119">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="2ded3-120">可选。</span><span class="sxs-lookup"><span data-stu-id="2ded3-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ded3-121">子元素</span><span class="sxs-lookup"><span data-stu-id="2ded3-121">Child Elements</span></span>  
  
|<span data-ttu-id="2ded3-122">元素</span><span class="sxs-lookup"><span data-stu-id="2ded3-122">Element</span></span>|<span data-ttu-id="2ded3-123">说明</span><span class="sxs-lookup"><span data-stu-id="2ded3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ded3-124">\<饼干汉德勒></span><span class="sxs-lookup"><span data-stu-id="2ded3-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="2ded3-125">配置 SAM 使用的 Cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="2ded3-125">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="2ded3-126">可选。</span><span class="sxs-lookup"><span data-stu-id="2ded3-126">Optional.</span></span>|  
|[<span data-ttu-id="2ded3-127">\<服务证书></span><span class="sxs-lookup"><span data-stu-id="2ded3-127">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="2ded3-128">配置用于加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="2ded3-128">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="2ded3-129">可选。</span><span class="sxs-lookup"><span data-stu-id="2ded3-129">Optional.</span></span>|  
|[<span data-ttu-id="2ded3-130">\<ws联邦></span><span class="sxs-lookup"><span data-stu-id="2ded3-130">\<wsFederation></span></span>](wsfederation.md)|<span data-ttu-id="2ded3-131">配置 WS-联合身份验证模块 （WSFAM）。</span><span class="sxs-lookup"><span data-stu-id="2ded3-131">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="2ded3-132">可选。</span><span class="sxs-lookup"><span data-stu-id="2ded3-132">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ded3-133">父元素</span><span class="sxs-lookup"><span data-stu-id="2ded3-133">Parent Elements</span></span>  
  
|<span data-ttu-id="2ded3-134">元素</span><span class="sxs-lookup"><span data-stu-id="2ded3-134">Element</span></span>|<span data-ttu-id="2ded3-135">说明</span><span class="sxs-lookup"><span data-stu-id="2ded3-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ded3-136">\<系统.身份模型.服务></span><span class="sxs-lookup"><span data-stu-id="2ded3-136">\<system.identityModel.services></span></span>](system-identitymodel-services.md)|<span data-ttu-id="2ded3-137">使用 WS-联合协议进行身份验证的配置部分。</span><span class="sxs-lookup"><span data-stu-id="2ded3-137">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ded3-138">备注</span><span class="sxs-lookup"><span data-stu-id="2ded3-138">Remarks</span></span>  
 <span data-ttu-id="2ded3-139">联合\<配置>元素在两种不同的方案中提供设置：</span><span class="sxs-lookup"><span data-stu-id="2ded3-139">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="2ded3-140">在被动 Web 应用程序中使用 WS-联合时，元素包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>（WSFAM） 和 （SAM） 的<xref:System.IdentityModel.Services.SessionAuthenticationModule>设置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-140">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="2ded3-141">它还引用用于配置安全令牌处理程序和证书的标识配置，以及声明授权管理器和声明身份验证管理器等组件。</span><span class="sxs-lookup"><span data-stu-id="2ded3-141">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="2ded3-142">当使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类在代码中提供基于声明的访问控制时，元素引用标识配置，该配置用于做出授权决策的声明授权管理器和策略。</span><span class="sxs-lookup"><span data-stu-id="2ded3-142">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="2ded3-143">这是事实，即使在不是被动 Web 方案的情况下也是如此;例如，Windows 通信基础 （WCF） 应用程序或非基于 Web 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ded3-143">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="2ded3-144">如果应用程序不是被动 Web 应用程序，则`<federationConfiguration>`该元素引用的标识配置[\<的声明授权管理器>](claimsauthorizationmanager.md)元素（及其子策略元素（如果存在）是应用的唯一设置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-144">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="2ded3-145">将忽略所有其他成员。</span><span class="sxs-lookup"><span data-stu-id="2ded3-145">All others are ignored.</span></span>  
  
 <span data-ttu-id="2ded3-146">无论方案如何，运行时都会加载默认联合身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-146">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="2ded3-147">行为的定义如下：</span><span class="sxs-lookup"><span data-stu-id="2ded3-147">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="2ded3-148">如果没有`<federationConfiguration>`元素存在，运行时将创建联合配置，并将其填充为默认值。</span><span class="sxs-lookup"><span data-stu-id="2ded3-148">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="2ded3-149">此默认联合身份验证配置将引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-149">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="2ded3-150">如果存在单个`<federationConfiguration>`元素，则无论它是命名还是未命名，它都是默认的联合配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-150">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="2ded3-151">如果指定`identityConfiguration`了其属性，则引用命名标识配置;如果指定标识配置被引用。否则，将引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-151">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="2ded3-152">如果存在未命名的`<federationConfiguration>`元素，则它是默认的联合配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-152">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="2ded3-153">如果指定`identityConfiguration`了其属性，则引用命名标识配置;如果指定标识配置被引用。否则，将引用默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-153">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="2ded3-154">如果存在多个命名`<federationConfiguration>`元素，并且不存在未命名`<federationConfiguration>`元素，则引发异常。</span><span class="sxs-lookup"><span data-stu-id="2ded3-154">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="2ded3-155">通常，只定义单个`<federationConfiguration>`节。</span><span class="sxs-lookup"><span data-stu-id="2ded3-155">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="2ded3-156">此部分是默认联合配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-156">This section is the default federation configuration.</span></span> <span data-ttu-id="2ded3-157">您可以指定多个唯一命名的元素;`<federationConfiguration>`但是，您可以指定多个唯一命名的元素。但是，在这种情况下，如果要加载非命名配置以外的联合配置，则必须为 提供处理程序。</span><span class="sxs-lookup"><span data-stu-id="2ded3-157">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="2ded3-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>事件，并将处理程序<xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>内的属性设置为使用配置文件中<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>相应元素中的值`<federationConfiguration>`初始化的对象。</span><span class="sxs-lookup"><span data-stu-id="2ded3-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="2ded3-159">元素`<federationConfiguration>`由类<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement>表示。</span><span class="sxs-lookup"><span data-stu-id="2ded3-159">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="2ded3-160">配置对象本身由类<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>表示。</span><span class="sxs-lookup"><span data-stu-id="2ded3-160">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="2ded3-161">在<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>属性上设置单个实例<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>，并为应用程序提供联合配置。</span><span class="sxs-lookup"><span data-stu-id="2ded3-161">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ded3-162">示例</span><span class="sxs-lookup"><span data-stu-id="2ded3-162">Example</span></span>  
 <span data-ttu-id="2ded3-163">以下 XML 显示了`<federationConfiguration>`一个元素，该元素指定 WSFAM 的设置，并指定 SAM 使用<xref:System.IdentityModel.Services.ChunkedCookieHandler>默认 Cookie 处理程序（类的实例）。</span><span class="sxs-lookup"><span data-stu-id="2ded3-163">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="2ded3-164">在此示例中，不需要 Cookie 处理程序和 WSFAM 使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="2ded3-164">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="2ded3-165">这是因为`requireHttps``<wsFederation>`元素上的属性和`requireSsl`上的属性`<cookieHandlerElement>`是`false`。</span><span class="sxs-lookup"><span data-stu-id="2ded3-165">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="2ded3-166">不建议大多数生产环境使用这些设置，因为它们可能会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="2ded3-166">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ded3-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ded3-167">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2ded3-168">\<身份配置></span><span class="sxs-lookup"><span data-stu-id="2ded3-168">\<identityConfiguration></span></span>](identityconfiguration.md)
