---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152562"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="80320-101">\<安全令牌处理程序配置></span><span class="sxs-lookup"><span data-stu-id="80320-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="80320-102">提供令牌处理程序集合的配置。</span><span class="sxs-lookup"><span data-stu-id="80320-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="80320-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80320-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80320-104">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="80320-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="80320-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="80320-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="80320-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="80320-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="80320-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<安全令牌处理程序配置>**</span><span class="sxs-lookup"><span data-stu-id="80320-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80320-108">语法</span><span class="sxs-lookup"><span data-stu-id="80320-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80320-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="80320-109">Attributes and Elements</span></span>  
 <span data-ttu-id="80320-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="80320-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80320-111">属性</span><span class="sxs-lookup"><span data-stu-id="80320-111">Attributes</span></span>  
  
|<span data-ttu-id="80320-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="80320-112">Attribute</span></span>|<span data-ttu-id="80320-113">说明</span><span class="sxs-lookup"><span data-stu-id="80320-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80320-114">保存引导上下文</span><span class="sxs-lookup"><span data-stu-id="80320-114">saveBootstrapContext</span></span>|<span data-ttu-id="80320-115">指定是否应在会话令牌中包括引导标记。</span><span class="sxs-lookup"><span data-stu-id="80320-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="80320-116">还可以通过在`saveBootstrapContext`[\<标识配置>](identityconfiguration.md)元素上设置属性，在令牌处理程序集合上设置该值。</span><span class="sxs-lookup"><span data-stu-id="80320-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="80320-117">令牌处理程序集合上设置的值将覆盖服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="80320-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="80320-118">最大时钟</span><span class="sxs-lookup"><span data-stu-id="80320-118">maximumClockSkew</span></span>|<span data-ttu-id="80320-119">指定<xref:System.TimeSpan>允许的最大时钟偏斜的 。</span><span class="sxs-lookup"><span data-stu-id="80320-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="80320-120">控制执行时间敏感操作（如验证登录会话的过期时间）时允许的最大时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="80320-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="80320-121">默认值为 5 分钟，"00：05：00"。</span><span class="sxs-lookup"><span data-stu-id="80320-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="80320-122">有关如何指定<xref:System.TimeSpan>值的详细信息，请参阅[时间跨度值](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="80320-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="80320-123">还可以通过在`maximumClockSkew`[\<标识配置>](identityconfiguration.md)元素上设置属性，在服务级别设置最大时钟偏斜。</span><span class="sxs-lookup"><span data-stu-id="80320-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="80320-124">令牌处理程序集合上设置的值将覆盖服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="80320-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80320-125">子元素</span><span class="sxs-lookup"><span data-stu-id="80320-125">Child Elements</span></span>  
  
|<span data-ttu-id="80320-126">元素</span><span class="sxs-lookup"><span data-stu-id="80320-126">Element</span></span>|<span data-ttu-id="80320-127">说明</span><span class="sxs-lookup"><span data-stu-id="80320-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80320-128">\<观众尤里斯·></span><span class="sxs-lookup"><span data-stu-id="80320-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="80320-129">指定此依赖方可接受的标识符的 URI 集。</span><span class="sxs-lookup"><span data-stu-id="80320-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="80320-130">可选。</span><span class="sxs-lookup"><span data-stu-id="80320-130">Optional.</span></span>|  
|[<span data-ttu-id="80320-131">\<缓存></span><span class="sxs-lookup"><span data-stu-id="80320-131">\<caches></span></span>](caches.md)|<span data-ttu-id="80320-132">注册用于会话令牌和令牌重播检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="80320-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="80320-133">可以在服务级别或安全令牌处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="80320-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="80320-134">可选。</span><span class="sxs-lookup"><span data-stu-id="80320-134">Optional.</span></span>|  
|[<span data-ttu-id="80320-135">\<证书验证></span><span class="sxs-lookup"><span data-stu-id="80320-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="80320-136">控制令牌处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="80320-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="80320-137">可以在服务级别或安全令牌处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="80320-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="80320-138">如果特定处理程序配置了自己的验证器，则这些设置将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="80320-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="80320-139">可选。</span><span class="sxs-lookup"><span data-stu-id="80320-139">Optional.</span></span>|  
|[<span data-ttu-id="80320-140">\<发行人名称注册></span><span class="sxs-lookup"><span data-stu-id="80320-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="80320-141">配置令牌处理程序集合中处理程序使用的颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="80320-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="80320-142">可选。</span><span class="sxs-lookup"><span data-stu-id="80320-142">Optional.</span></span>|  
|[<span data-ttu-id="80320-143">\<颁发者令牌解析器></span><span class="sxs-lookup"><span data-stu-id="80320-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="80320-144">注册令牌处理程序集合中处理程序使用的颁发者令牌解析器。</span><span class="sxs-lookup"><span data-stu-id="80320-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="80320-145">颁发者令牌解析器用于解析传入令牌和消息上的签名令牌。</span><span class="sxs-lookup"><span data-stu-id="80320-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="80320-146">可选。</span><span class="sxs-lookup"><span data-stu-id="80320-146">Optional.</span></span>|  
|[<span data-ttu-id="80320-147">\<服务令牌解析器></span><span class="sxs-lookup"><span data-stu-id="80320-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="80320-148">注册令牌处理程序集合中处理程序使用的服务令牌解析器。</span><span class="sxs-lookup"><span data-stu-id="80320-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="80320-149">服务令牌解析器用于解析传入令牌和消息上的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="80320-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="80320-150">可选。</span><span class="sxs-lookup"><span data-stu-id="80320-150">Optional.</span></span>|  
|[<span data-ttu-id="80320-151">\<令牌回放检测></span><span class="sxs-lookup"><span data-stu-id="80320-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="80320-152">启用令牌重播检测并指定令牌的过期时间。</span><span class="sxs-lookup"><span data-stu-id="80320-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="80320-153">可以在服务级别或安全令牌处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="80320-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="80320-154">可选。</span><span class="sxs-lookup"><span data-stu-id="80320-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80320-155">父元素</span><span class="sxs-lookup"><span data-stu-id="80320-155">Parent Elements</span></span>  
  
|<span data-ttu-id="80320-156">元素</span><span class="sxs-lookup"><span data-stu-id="80320-156">Element</span></span>|<span data-ttu-id="80320-157">说明</span><span class="sxs-lookup"><span data-stu-id="80320-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80320-158">\<安全令牌处理程序></span><span class="sxs-lookup"><span data-stu-id="80320-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="80320-159">指定向终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="80320-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80320-160">备注</span><span class="sxs-lookup"><span data-stu-id="80320-160">Remarks</span></span>  
 <span data-ttu-id="80320-161">本节提供<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="80320-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="80320-162">本节中配置的设置将覆盖服务上配置的设置。</span><span class="sxs-lookup"><span data-stu-id="80320-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="80320-163">反过来，其中一些设置可以被在将处理程序添加到安全令牌处理程序集合时指定的设置覆盖。</span><span class="sxs-lookup"><span data-stu-id="80320-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80320-164">示例</span><span class="sxs-lookup"><span data-stu-id="80320-164">Example</span></span>  
  
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
