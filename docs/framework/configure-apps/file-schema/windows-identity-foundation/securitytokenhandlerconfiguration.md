---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793274"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="5a547-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="5a547-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="5a547-103">提供的令牌处理程序集合的配置。</span><span class="sxs-lookup"><span data-stu-id="5a547-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="5a547-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5a547-104">\<system.identityModel></span></span>  
<span data-ttu-id="5a547-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5a547-105">\<identityConfiguration></span></span>  
<span data-ttu-id="5a547-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="5a547-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="5a547-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5a547-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a547-108">语法</span><span class="sxs-lookup"><span data-stu-id="5a547-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a547-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5a547-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5a547-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5a547-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a547-111">特性</span><span class="sxs-lookup"><span data-stu-id="5a547-111">Attributes</span></span>  
  
|<span data-ttu-id="5a547-112">特性</span><span class="sxs-lookup"><span data-stu-id="5a547-112">Attribute</span></span>|<span data-ttu-id="5a547-113">描述</span><span class="sxs-lookup"><span data-stu-id="5a547-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a547-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="5a547-114">saveBootstrapContext</span></span>|<span data-ttu-id="5a547-115">指定是否应在会话令牌中包含启动令牌。</span><span class="sxs-lookup"><span data-stu-id="5a547-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="5a547-116">值还可以设置标记处理程序集合上设置`saveBootstrapContext`特性，可以在[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="5a547-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="5a547-117">令牌处理程序集合上设置值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="5a547-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="5a547-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="5a547-118">maximumClockSkew</span></span>|<span data-ttu-id="5a547-119">一个<xref:System.TimeSpan>指定最大允许的时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="5a547-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="5a547-120">执行时间敏感操作，如验证登录会话的过期时间时，控制最大允许的时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="5a547-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="5a547-121">默认为 5 分钟"00: 05:00"。</span><span class="sxs-lookup"><span data-stu-id="5a547-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="5a547-122">有关如何指定详细信息<xref:System.TimeSpan>值，请参阅[Timespan 值](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5a547-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="5a547-123">最大时钟偏差还可以设置在服务级别通过设置`maximumClockSkew`特性，可以在[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="5a547-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="5a547-124">令牌处理程序集合上设置值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="5a547-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a547-125">子元素</span><span class="sxs-lookup"><span data-stu-id="5a547-125">Child Elements</span></span>  
  
|<span data-ttu-id="5a547-126">元素</span><span class="sxs-lookup"><span data-stu-id="5a547-126">Element</span></span>|<span data-ttu-id="5a547-127">描述</span><span class="sxs-lookup"><span data-stu-id="5a547-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a547-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="5a547-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="5a547-129">指定 Uri 是可接受此信赖方标识符的集。</span><span class="sxs-lookup"><span data-stu-id="5a547-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="5a547-130">可选。</span><span class="sxs-lookup"><span data-stu-id="5a547-130">Optional.</span></span>|  
|[<span data-ttu-id="5a547-131">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="5a547-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="5a547-132">注册用于会话令牌和令牌重放检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="5a547-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="5a547-133">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="5a547-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5a547-134">可选。</span><span class="sxs-lookup"><span data-stu-id="5a547-134">Optional.</span></span>|  
|[<span data-ttu-id="5a547-135">\<certificatevalidation 设置 ></span><span class="sxs-lookup"><span data-stu-id="5a547-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="5a547-136">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="5a547-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="5a547-137">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="5a547-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5a547-138">如果特定的处理程序配置了其自己的验证程序，则将重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="5a547-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="5a547-139">可选。</span><span class="sxs-lookup"><span data-stu-id="5a547-139">Optional.</span></span>|  
|[<span data-ttu-id="5a547-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="5a547-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="5a547-141">配置颁发者名称注册的标记处理程序集合中的处理程序使用。</span><span class="sxs-lookup"><span data-stu-id="5a547-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5a547-142">可选。</span><span class="sxs-lookup"><span data-stu-id="5a547-142">Optional.</span></span>|  
|[<span data-ttu-id="5a547-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="5a547-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="5a547-144">注册令牌处理程序集合中的处理程序使用的颁发者令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="5a547-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5a547-145">颁发者令牌解析程序用于解决签名令牌对传入令牌和消息。</span><span class="sxs-lookup"><span data-stu-id="5a547-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="5a547-146">可选。</span><span class="sxs-lookup"><span data-stu-id="5a547-146">Optional.</span></span>|  
|[<span data-ttu-id="5a547-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="5a547-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="5a547-148">注册的服务令牌解析程序使用的令牌处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="5a547-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5a547-149">服务标记解析器用于解析传入的令牌和消息中的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="5a547-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="5a547-150">可选。</span><span class="sxs-lookup"><span data-stu-id="5a547-150">Optional.</span></span>|  
|[<span data-ttu-id="5a547-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="5a547-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="5a547-152">启用令牌重放检测并指定令牌的到期时间。</span><span class="sxs-lookup"><span data-stu-id="5a547-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="5a547-153">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="5a547-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5a547-154">可选。</span><span class="sxs-lookup"><span data-stu-id="5a547-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a547-155">父元素</span><span class="sxs-lookup"><span data-stu-id="5a547-155">Parent Elements</span></span>  
  
|<span data-ttu-id="5a547-156">元素</span><span class="sxs-lookup"><span data-stu-id="5a547-156">Element</span></span>|<span data-ttu-id="5a547-157">描述</span><span class="sxs-lookup"><span data-stu-id="5a547-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a547-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="5a547-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="5a547-159">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="5a547-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a547-160">备注</span><span class="sxs-lookup"><span data-stu-id="5a547-160">Remarks</span></span>  
 <span data-ttu-id="5a547-161">本部分提供的属性值<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>对象。</span><span class="sxs-lookup"><span data-stu-id="5a547-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="5a547-162">在本部分中配置的设置会覆盖服务上配置。</span><span class="sxs-lookup"><span data-stu-id="5a547-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="5a547-163">其中某些设置可以反过来，重写由一个处理程序添加到安全标记处理程序集合时指定的设置。</span><span class="sxs-lookup"><span data-stu-id="5a547-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a547-164">示例</span><span class="sxs-lookup"><span data-stu-id="5a547-164">Example</span></span>  
  
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
