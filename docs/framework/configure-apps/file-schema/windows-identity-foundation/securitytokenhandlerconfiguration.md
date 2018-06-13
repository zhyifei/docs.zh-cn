---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 168bdc4fbf640b201ebc61462d04727c23f838f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758420"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="43c93-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="43c93-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="43c93-103">提供配置令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="43c93-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="43c93-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="43c93-104">\<system.identityModel></span></span>  
<span data-ttu-id="43c93-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="43c93-105">\<identityConfiguration></span></span>  
<span data-ttu-id="43c93-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="43c93-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="43c93-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="43c93-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c93-108">语法</span><span class="sxs-lookup"><span data-stu-id="43c93-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43c93-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="43c93-109">Attributes and Elements</span></span>  
 <span data-ttu-id="43c93-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="43c93-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43c93-111">特性</span><span class="sxs-lookup"><span data-stu-id="43c93-111">Attributes</span></span>  
  
|<span data-ttu-id="43c93-112">特性</span><span class="sxs-lookup"><span data-stu-id="43c93-112">Attribute</span></span>|<span data-ttu-id="43c93-113">描述</span><span class="sxs-lookup"><span data-stu-id="43c93-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43c93-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="43c93-114">saveBootstrapContext</span></span>|<span data-ttu-id="43c93-115">指定是否应在会话令牌中包含启动令牌。</span><span class="sxs-lookup"><span data-stu-id="43c93-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="43c93-116">值还可以设置对令牌处理程序集合通过设置`saveBootstrapContext`属性[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="43c93-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="43c93-117">令牌处理程序集合设置一个值重写在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="43c93-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="43c93-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="43c93-118">maximumClockSkew</span></span>|<span data-ttu-id="43c93-119">A <xref:System.TimeSpan> ，指定最大允许的时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="43c93-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="43c93-120">执行具有时效性操作，例如验证登录会话的过期时间时，可以控制最大允许的时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="43c93-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="43c93-121">默认值为 5 分钟，"00: 05:00"。</span><span class="sxs-lookup"><span data-stu-id="43c93-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="43c93-122">有关如何指定详细信息<xref:System.TimeSpan>值，请参阅[Timespan 值](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="43c93-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="43c93-123">最大时钟偏差还可以设置在服务级别通过设置`maximumClockSkew`属性[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="43c93-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="43c93-124">令牌处理程序集合设置一个值重写在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="43c93-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43c93-125">子元素</span><span class="sxs-lookup"><span data-stu-id="43c93-125">Child Elements</span></span>  
  
|<span data-ttu-id="43c93-126">元素</span><span class="sxs-lookup"><span data-stu-id="43c93-126">Element</span></span>|<span data-ttu-id="43c93-127">描述</span><span class="sxs-lookup"><span data-stu-id="43c93-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43c93-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="43c93-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="43c93-129">指定是可接受此信赖方标识符的 Uri 的集。</span><span class="sxs-lookup"><span data-stu-id="43c93-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="43c93-130">可选。</span><span class="sxs-lookup"><span data-stu-id="43c93-130">Optional.</span></span>|  
|[<span data-ttu-id="43c93-131">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="43c93-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="43c93-132">注册用于会话令牌和令牌重放检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="43c93-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="43c93-133">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="43c93-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="43c93-134">可选。</span><span class="sxs-lookup"><span data-stu-id="43c93-134">Optional.</span></span>|  
|[<span data-ttu-id="43c93-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="43c93-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="43c93-136">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="43c93-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="43c93-137">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="43c93-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="43c93-138">如果使用自己的验证程序配置特定的处理程序，则将重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="43c93-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="43c93-139">可选。</span><span class="sxs-lookup"><span data-stu-id="43c93-139">Optional.</span></span>|  
|[<span data-ttu-id="43c93-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="43c93-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="43c93-141">配置的颁发者名称注册表，由标记处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="43c93-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="43c93-142">可选。</span><span class="sxs-lookup"><span data-stu-id="43c93-142">Optional.</span></span>|  
|[<span data-ttu-id="43c93-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="43c93-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="43c93-144">注册的颁发者令牌解析程序由标记处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="43c93-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="43c93-145">颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="43c93-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="43c93-146">可选。</span><span class="sxs-lookup"><span data-stu-id="43c93-146">Optional.</span></span>|  
|[<span data-ttu-id="43c93-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="43c93-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="43c93-148">注册的服务令牌解析程序由标记处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="43c93-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="43c93-149">服务的标记解析程序用于解析在传入令牌和消息上的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="43c93-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="43c93-150">可选。</span><span class="sxs-lookup"><span data-stu-id="43c93-150">Optional.</span></span>|  
|[<span data-ttu-id="43c93-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="43c93-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="43c93-152">启用令牌重放检测并指定令牌的过期时间。</span><span class="sxs-lookup"><span data-stu-id="43c93-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="43c93-153">可以指定在服务级别或对安全令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="43c93-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="43c93-154">可选。</span><span class="sxs-lookup"><span data-stu-id="43c93-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43c93-155">父元素</span><span class="sxs-lookup"><span data-stu-id="43c93-155">Parent Elements</span></span>  
  
|<span data-ttu-id="43c93-156">元素</span><span class="sxs-lookup"><span data-stu-id="43c93-156">Element</span></span>|<span data-ttu-id="43c93-157">描述</span><span class="sxs-lookup"><span data-stu-id="43c93-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43c93-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="43c93-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="43c93-159">指定与终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="43c93-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43c93-160">备注</span><span class="sxs-lookup"><span data-stu-id="43c93-160">Remarks</span></span>  
 <span data-ttu-id="43c93-161">本部分提供的属性值<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>对象。</span><span class="sxs-lookup"><span data-stu-id="43c93-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="43c93-162">此节中配置的设置会覆盖的服务上配置。</span><span class="sxs-lookup"><span data-stu-id="43c93-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="43c93-163">其中某些设置可以反过来，重写由处理程序添加到安全令牌的处理程序集合时指定的设置。</span><span class="sxs-lookup"><span data-stu-id="43c93-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43c93-164">示例</span><span class="sxs-lookup"><span data-stu-id="43c93-164">Example</span></span>  
  
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
