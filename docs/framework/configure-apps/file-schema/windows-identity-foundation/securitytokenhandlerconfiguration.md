---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360402"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="f72ac-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f72ac-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="f72ac-102">提供的令牌处理程序集合的配置。</span><span class="sxs-lookup"><span data-stu-id="f72ac-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="f72ac-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f72ac-103">\<system.identityModel></span></span>  
<span data-ttu-id="f72ac-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f72ac-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f72ac-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f72ac-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f72ac-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f72ac-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72ac-107">语法</span><span class="sxs-lookup"><span data-stu-id="f72ac-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f72ac-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f72ac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f72ac-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f72ac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f72ac-110">特性</span><span class="sxs-lookup"><span data-stu-id="f72ac-110">Attributes</span></span>  
  
|<span data-ttu-id="f72ac-111">特性</span><span class="sxs-lookup"><span data-stu-id="f72ac-111">Attribute</span></span>|<span data-ttu-id="f72ac-112">描述</span><span class="sxs-lookup"><span data-stu-id="f72ac-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f72ac-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="f72ac-113">saveBootstrapContext</span></span>|<span data-ttu-id="f72ac-114">指定是否应在会话令牌中包含启动令牌。</span><span class="sxs-lookup"><span data-stu-id="f72ac-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="f72ac-115">值还可以设置标记处理程序集合上设置`saveBootstrapContext`特性，可以在[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f72ac-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="f72ac-116">令牌处理程序集合上设置值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="f72ac-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="f72ac-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="f72ac-117">maximumClockSkew</span></span>|<span data-ttu-id="f72ac-118">一个<xref:System.TimeSpan>指定最大允许的时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="f72ac-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="f72ac-119">执行时间敏感操作，如验证登录会话的过期时间时，控制最大允许的时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="f72ac-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="f72ac-120">默认为 5 分钟"00: 05:00"。</span><span class="sxs-lookup"><span data-stu-id="f72ac-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="f72ac-121">有关如何指定详细信息<xref:System.TimeSpan>值，请参阅[Timespan 值](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f72ac-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="f72ac-122">最大时钟偏差还可以设置在服务级别通过设置`maximumClockSkew`特性，可以在[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f72ac-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="f72ac-123">令牌处理程序集合上设置值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="f72ac-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f72ac-124">子元素</span><span class="sxs-lookup"><span data-stu-id="f72ac-124">Child Elements</span></span>  
  
|<span data-ttu-id="f72ac-125">元素</span><span class="sxs-lookup"><span data-stu-id="f72ac-125">Element</span></span>|<span data-ttu-id="f72ac-126">描述</span><span class="sxs-lookup"><span data-stu-id="f72ac-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f72ac-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="f72ac-127">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="f72ac-128">指定 Uri 是可接受此信赖方标识符的集。</span><span class="sxs-lookup"><span data-stu-id="f72ac-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="f72ac-129">可选。</span><span class="sxs-lookup"><span data-stu-id="f72ac-129">Optional.</span></span>|  
|[<span data-ttu-id="f72ac-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="f72ac-130">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="f72ac-131">注册用于会话令牌和令牌重放检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="f72ac-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="f72ac-132">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="f72ac-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f72ac-133">可选。</span><span class="sxs-lookup"><span data-stu-id="f72ac-133">Optional.</span></span>|  
|[<span data-ttu-id="f72ac-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="f72ac-134">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="f72ac-135">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="f72ac-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="f72ac-136">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="f72ac-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f72ac-137">如果特定的处理程序配置了其自己的验证程序，则将重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="f72ac-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="f72ac-138">可选。</span><span class="sxs-lookup"><span data-stu-id="f72ac-138">Optional.</span></span>|  
|[<span data-ttu-id="f72ac-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="f72ac-139">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="f72ac-140">配置颁发者名称注册的标记处理程序集合中的处理程序使用。</span><span class="sxs-lookup"><span data-stu-id="f72ac-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f72ac-141">可选。</span><span class="sxs-lookup"><span data-stu-id="f72ac-141">Optional.</span></span>|  
|[<span data-ttu-id="f72ac-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="f72ac-142">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="f72ac-143">注册令牌处理程序集合中的处理程序使用的颁发者令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="f72ac-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f72ac-144">颁发者令牌解析程序用于解决签名令牌对传入令牌和消息。</span><span class="sxs-lookup"><span data-stu-id="f72ac-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="f72ac-145">可选。</span><span class="sxs-lookup"><span data-stu-id="f72ac-145">Optional.</span></span>|  
|[<span data-ttu-id="f72ac-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="f72ac-146">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="f72ac-147">注册的服务令牌解析程序使用的令牌处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="f72ac-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f72ac-148">服务标记解析器用于解析传入的令牌和消息中的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="f72ac-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="f72ac-149">可选。</span><span class="sxs-lookup"><span data-stu-id="f72ac-149">Optional.</span></span>|  
|[<span data-ttu-id="f72ac-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="f72ac-150">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="f72ac-151">启用令牌重放检测并指定令牌的到期时间。</span><span class="sxs-lookup"><span data-stu-id="f72ac-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="f72ac-152">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="f72ac-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f72ac-153">可选。</span><span class="sxs-lookup"><span data-stu-id="f72ac-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f72ac-154">父元素</span><span class="sxs-lookup"><span data-stu-id="f72ac-154">Parent Elements</span></span>  
  
|<span data-ttu-id="f72ac-155">元素</span><span class="sxs-lookup"><span data-stu-id="f72ac-155">Element</span></span>|<span data-ttu-id="f72ac-156">描述</span><span class="sxs-lookup"><span data-stu-id="f72ac-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f72ac-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f72ac-157">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="f72ac-158">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="f72ac-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f72ac-159">备注</span><span class="sxs-lookup"><span data-stu-id="f72ac-159">Remarks</span></span>  
 <span data-ttu-id="f72ac-160">本部分提供的属性值<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>对象。</span><span class="sxs-lookup"><span data-stu-id="f72ac-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="f72ac-161">在本部分中配置的设置会覆盖服务上配置。</span><span class="sxs-lookup"><span data-stu-id="f72ac-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="f72ac-162">其中某些设置可以反过来，重写由一个处理程序添加到安全标记处理程序集合时指定的设置。</span><span class="sxs-lookup"><span data-stu-id="f72ac-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f72ac-163">示例</span><span class="sxs-lookup"><span data-stu-id="f72ac-163">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
