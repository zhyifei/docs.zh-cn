---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 9f5e0c5ded3d750a1102492c7a506e6d5643b2d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942752"
---
# <a name="identityconfiguration"></a><span data-ttu-id="5de3f-101">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5de3f-101">\<identityConfiguration></span></span>

<span data-ttu-id="5de3f-102">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-102">Specifies service-level identity settings.</span></span>

 <span data-ttu-id="5de3f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5de3f-103">\<system.identityModel></span></span>\
<span data-ttu-id="5de3f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5de3f-104">\<identityConfiguration></span></span>

## <a name="syntax"></a><span data-ttu-id="5de3f-105">语法</span><span class="sxs-lookup"><span data-stu-id="5de3f-105">Syntax</span></span>

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5de3f-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5de3f-106">Attributes and Elements</span></span>

<span data-ttu-id="5de3f-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5de3f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5de3f-108">特性</span><span class="sxs-lookup"><span data-stu-id="5de3f-108">Attributes</span></span>

|<span data-ttu-id="5de3f-109">特性</span><span class="sxs-lookup"><span data-stu-id="5de3f-109">Attribute</span></span>|<span data-ttu-id="5de3f-110">描述</span><span class="sxs-lookup"><span data-stu-id="5de3f-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="5de3f-111">NAME</span><span class="sxs-lookup"><span data-stu-id="5de3f-111">name</span></span>|<span data-ttu-id="5de3f-112">标识配置节的名称。</span><span class="sxs-lookup"><span data-stu-id="5de3f-112">The name of the identity configuration section.</span></span> <span data-ttu-id="5de3f-113">您可以使用此名称来引用特定的配置节。</span><span class="sxs-lookup"><span data-stu-id="5de3f-113">You can use this name to reference a specific configuration section.</span></span> <span data-ttu-id="5de3f-114">如果未`name`指定任何属性, 则节将定义默认配置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-114">If no `name` attribute is specified, the section defines the default configuration.</span></span> <span data-ttu-id="5de3f-115">默认配置始终用于被动联合身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="5de3f-115">The default configuration is always used for passive federation scenarios.</span></span> <span data-ttu-id="5de3f-116">有关详细信息, 请参阅[ \<federationConfiguration >](federationconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="5de3f-116">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>|
|<span data-ttu-id="5de3f-117">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="5de3f-117">saveBootstrapContext</span></span>|<span data-ttu-id="5de3f-118">指定是否应在会话令牌中包含启动令牌。</span><span class="sxs-lookup"><span data-stu-id="5de3f-118">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="5de3f-119">还可以通过在`saveBootstrapContext` [ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)元素上设置属性, 在令牌处理程序集合上设置该值。</span><span class="sxs-lookup"><span data-stu-id="5de3f-119">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="5de3f-120">标记处理程序集合上设置的值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="5de3f-120">A value set on the token handler collection overrides the value set on the service.</span></span>|
|<span data-ttu-id="5de3f-121">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="5de3f-121">maximumClockSkew</span></span>|<span data-ttu-id="5de3f-122">一个<xref:System.TimeSpan> , 它指定允许的最大时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="5de3f-122">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="5de3f-123">控制执行区分时间的操作时允许的最大时钟偏差, 如验证登录会话的过期时间。</span><span class="sxs-lookup"><span data-stu-id="5de3f-123">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="5de3f-124">默认值为5分钟 "00:05:00"。</span><span class="sxs-lookup"><span data-stu-id="5de3f-124">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="5de3f-125">有关如何指定<xref:System.TimeSpan>值的详细信息, 请参阅[Timespan 值](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5de3f-125">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="5de3f-126">还可以通过在`maximumClockSkew` [ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)元素上设置属性, 在令牌处理程序集合上设置最大时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="5de3f-126">The maximum clock skew may also be set on a token handler collection by setting the `maximumClockSkew` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="5de3f-127">标记处理程序集合上设置的值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="5de3f-127">A value set on the token handler collection overrides the value set on the service.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5de3f-128">子元素</span><span class="sxs-lookup"><span data-stu-id="5de3f-128">Child Elements</span></span>

|<span data-ttu-id="5de3f-129">元素</span><span class="sxs-lookup"><span data-stu-id="5de3f-129">Element</span></span>|<span data-ttu-id="5de3f-130">描述</span><span class="sxs-lookup"><span data-stu-id="5de3f-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5de3f-131">\<caches></span><span class="sxs-lookup"><span data-stu-id="5de3f-131">\<caches></span></span>](caches.md)|<span data-ttu-id="5de3f-132">注册用于会话令牌和令牌重播检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="5de3f-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="5de3f-133">可在服务级别或安全标记处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="5de3f-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5de3f-134">可选。</span><span class="sxs-lookup"><span data-stu-id="5de3f-134">Optional.</span></span>|
|[<span data-ttu-id="5de3f-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="5de3f-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="5de3f-136">控制标记处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="5de3f-137">可在服务级别或安全标记处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="5de3f-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5de3f-138">可选。</span><span class="sxs-lookup"><span data-stu-id="5de3f-138">Optional.</span></span>|
|[<span data-ttu-id="5de3f-139">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="5de3f-139">\<claimsAuthenticationManager></span></span>](claimsauthenticationmanager.md)|<span data-ttu-id="5de3f-140">为传入声明注册声明身份验证管理器。</span><span class="sxs-lookup"><span data-stu-id="5de3f-140">Registers a claims authentication manager for the incoming claims.</span></span> <span data-ttu-id="5de3f-141">可选。</span><span class="sxs-lookup"><span data-stu-id="5de3f-141">Optional.</span></span>|
|[<span data-ttu-id="5de3f-142">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="5de3f-142">\<claimsAuthorizationManager></span></span>](claimsauthorizationmanager.md)|<span data-ttu-id="5de3f-143">为传入声明注册声明授权管理器。</span><span class="sxs-lookup"><span data-stu-id="5de3f-143">Registers a claims authorization manager for the incoming claims.</span></span> <span data-ttu-id="5de3f-144">可选。</span><span class="sxs-lookup"><span data-stu-id="5de3f-144">Optional.</span></span>|
|[<span data-ttu-id="5de3f-145">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="5de3f-145">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="5de3f-146">指定传入安全令牌所需的声明集。</span><span class="sxs-lookup"><span data-stu-id="5de3f-146">Specifies the set of required claims for incoming security tokens.</span></span> <span data-ttu-id="5de3f-147">可选。</span><span class="sxs-lookup"><span data-stu-id="5de3f-147">Optional.</span></span>|
|[<span data-ttu-id="5de3f-148">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="5de3f-148">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="5de3f-149">指定安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="5de3f-149">Specifies a collection of security token handlers.</span></span> <span data-ttu-id="5de3f-150">可以指定零个或多个安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="5de3f-150">Zero or more collections of security token handlers can be specified.</span></span> <span data-ttu-id="5de3f-151">可选。</span><span class="sxs-lookup"><span data-stu-id="5de3f-151">Optional.</span></span>|
|[<span data-ttu-id="5de3f-152">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="5de3f-152">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="5de3f-153">启用令牌重播检测并指定令牌的过期时间。</span><span class="sxs-lookup"><span data-stu-id="5de3f-153">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="5de3f-154">可在服务级别或安全标记处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="5de3f-154">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5de3f-155">可选。</span><span class="sxs-lookup"><span data-stu-id="5de3f-155">Optional.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5de3f-156">父元素</span><span class="sxs-lookup"><span data-stu-id="5de3f-156">Parent Elements</span></span>

|<span data-ttu-id="5de3f-157">元素</span><span class="sxs-lookup"><span data-stu-id="5de3f-157">Element</span></span>|<span data-ttu-id="5de3f-158">描述</span><span class="sxs-lookup"><span data-stu-id="5de3f-158">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5de3f-159">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5de3f-159">\<system.identityModel></span></span>](system-identitymodel.md)|<span data-ttu-id="5de3f-160">为在应用程序中启用 Windows Identity Foundation (WIF) 选项提供配置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-160">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5de3f-161">备注</span><span class="sxs-lookup"><span data-stu-id="5de3f-161">Remarks</span></span>

<span data-ttu-id="5de3f-162">可以定义多个标识配置, 每个配置都具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="5de3f-162">Multiple identity configurations may be defined, each with a unique name.</span></span> <span data-ttu-id="5de3f-163">此行为如下所示:</span><span class="sxs-lookup"><span data-stu-id="5de3f-163">The behavior is as follows:</span></span>

1. <span data-ttu-id="5de3f-164">如果未`<identityConfiguration>`指定元素, 则为。</span><span class="sxs-lookup"><span data-stu-id="5de3f-164">If no `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="5de3f-165">默认标识配置是在运行时创建的, 并使用默认值进行填充。</span><span class="sxs-lookup"><span data-stu-id="5de3f-165">A default identity configuration is created at runtime and populated with default values.</span></span>

2. <span data-ttu-id="5de3f-166">如果指定单个`<identityConfiguration>`元素, 则为。</span><span class="sxs-lookup"><span data-stu-id="5de3f-166">If a single `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="5de3f-167">这是默认的标识配置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-167">It is the default identity configuration.</span></span> <span data-ttu-id="5de3f-168">这并不重要。</span><span class="sxs-lookup"><span data-stu-id="5de3f-168">It does not matter whether it is named or unnamed.</span></span>

3. <span data-ttu-id="5de3f-169">如果指定`<identityConfiguration>`了多个元素。</span><span class="sxs-lookup"><span data-stu-id="5de3f-169">If multiple `<identityConfiguration>` elements are specified.</span></span> <span data-ttu-id="5de3f-170">未命名元素指定默认标识配置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-170">The unnamed element specifies the default identity configuration.</span></span> <span data-ttu-id="5de3f-171">建议在指定多个`<identityConfiguration>`元素时, 其中一项应为未命名元素。</span><span class="sxs-lookup"><span data-stu-id="5de3f-171">It is recommended that when you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span>

> [!WARNING]
> <span data-ttu-id="5de3f-172">如果指定多个`<identityConfiguration>`元素, 则其中一个元素应该是未命名元素。</span><span class="sxs-lookup"><span data-stu-id="5de3f-172">If you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span> <span data-ttu-id="5de3f-173">未命名的元素将是默认的标识配置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-173">The unnamed element will be the default identity configuration.</span></span>

 <span data-ttu-id="5de3f-174">`<identityConfiguration>`元素中指定的某些设置可由安全令牌处理程序集合上的设置重写, 或由单个安全令牌处理程序上的设置重写。</span><span class="sxs-lookup"><span data-stu-id="5de3f-174">Some of the settings specified in the `<identityConfiguration>` element can be overridden by settings on a security token handler collection or by settings on individual security token handlers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5de3f-175">当使用<xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>或类在代码中提供基于声明的访问控制时, `<federationConfiguration>`元素引用的标识配置将配置声明授权管理器和策略, 该策略用于进行授权决定。</span><span class="sxs-lookup"><span data-stu-id="5de3f-175">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="5de3f-176">即使在非被动 Web 方案 (例如 Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序) 情况下, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="5de3f-176">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="5de3f-177">如果应用程序不是被动 Web 应用程序, [ \<](claimsauthorizationmanager.md)则仅应用所引用标识配置的 claimsAuthorizationManager > 元素 (及其子策略元素, 如果存在)。</span><span class="sxs-lookup"><span data-stu-id="5de3f-177">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="5de3f-178">将忽略所有其他设置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-178">All other settings are ignored.</span></span> <span data-ttu-id="5de3f-179">有关详细信息, 请参阅[ \<federationConfiguration >](federationconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="5de3f-179">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>

<span data-ttu-id="5de3f-180">元素由<xref:System.IdentityModel.Configuration.IdentityConfigurationElement>类表示。 `<identityConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="5de3f-180">The `<identityConfiguration>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> class.</span></span> <span data-ttu-id="5de3f-181">标识配置部分由<xref:System.IdentityModel.Configuration.IdentityConfiguration>类表示。</span><span class="sxs-lookup"><span data-stu-id="5de3f-181">An identity configuration section is represented by the <xref:System.IdentityModel.Configuration.IdentityConfiguration> class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5de3f-182">将以下元素指定为`<identityConfiguration>`元素的子元素已被弃用, 但仍支持此行为以实现向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="5de3f-182">Specifying the following elements as child elements of the `<identityConfiguration>` element has been deprecated, although the behavior is still supported for backward compatibility.</span></span> <span data-ttu-id="5de3f-183">应改为在[ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)元素下指定这些元素。</span><span class="sxs-lookup"><span data-stu-id="5de3f-183">These elements should, instead, be specified under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span>
>
> - [<span data-ttu-id="5de3f-184">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="5de3f-184">\<audienceUris></span></span>](audienceuris.md)
> - [<span data-ttu-id="5de3f-185">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="5de3f-185">\<issuerNameRegistry></span></span>](issuernameregistry.md)
> - [<span data-ttu-id="5de3f-186">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="5de3f-186">\<issuerTokenResolver></span></span>](issuertokenresolver.md)
> - [<span data-ttu-id="5de3f-187">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="5de3f-187">\<serviceTokenResolver></span></span>](servicetokenresolver.md)

## <a name="example"></a><span data-ttu-id="5de3f-188">示例</span><span class="sxs-lookup"><span data-stu-id="5de3f-188">Example</span></span>

<span data-ttu-id="5de3f-189">以下示例创建名为 "alternateConfiguration" 的标识配置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-189">The following example creates an identity configuration named "alternateConfiguration".</span></span> <span data-ttu-id="5de3f-190">标识配置指定默认设置。</span><span class="sxs-lookup"><span data-stu-id="5de3f-190">The identity configuration specifies default settings.</span></span>

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a><span data-ttu-id="5de3f-191">请参阅</span><span class="sxs-lookup"><span data-stu-id="5de3f-191">See also</span></span>

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
