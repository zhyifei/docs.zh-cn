---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251892"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="d9cd2-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d9cd2-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="d9cd2-102">为标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="d9cd2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d9cd2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d9cd2-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d9cd2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d9cd2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d9cd2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d9cd2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d9cd2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d9cd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securityTokenHandlerConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="d9cd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9cd2-108">语法</span><span class="sxs-lookup"><span data-stu-id="d9cd2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9cd2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d9cd2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d9cd2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9cd2-111">特性</span><span class="sxs-lookup"><span data-stu-id="d9cd2-111">Attributes</span></span>  
  
|<span data-ttu-id="d9cd2-112">特性</span><span class="sxs-lookup"><span data-stu-id="d9cd2-112">Attribute</span></span>|<span data-ttu-id="d9cd2-113">描述</span><span class="sxs-lookup"><span data-stu-id="d9cd2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9cd2-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="d9cd2-114">saveBootstrapContext</span></span>|<span data-ttu-id="d9cd2-115">指定是否应在会话令牌中包含启动令牌。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="d9cd2-116">还可以通过在`saveBootstrapContext` [ \<identityConfiguration >](identityconfiguration.md)元素上设置属性，在令牌处理程序集合上设置该值。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="d9cd2-117">标记处理程序集合上设置的值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="d9cd2-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="d9cd2-118">maximumClockSkew</span></span>|<span data-ttu-id="d9cd2-119">一个<xref:System.TimeSpan> ，它指定允许的最大时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="d9cd2-120">控制执行区分时间的操作时允许的最大时钟偏差，如验证登录会话的过期时间。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="d9cd2-121">默认值为5分钟 "00:05:00"。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="d9cd2-122">有关如何指定<xref:System.TimeSpan>值的详细信息，请参阅[Timespan 值](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="d9cd2-123">通过在`maximumClockSkew` [ \<identityConfiguration >](identityconfiguration.md)元素上设置属性，还可以在服务级别设置最大时钟偏差。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="d9cd2-124">标记处理程序集合上设置的值将覆盖在服务上设置的值。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9cd2-125">子元素</span><span class="sxs-lookup"><span data-stu-id="d9cd2-125">Child Elements</span></span>  
  
|<span data-ttu-id="d9cd2-126">元素</span><span class="sxs-lookup"><span data-stu-id="d9cd2-126">Element</span></span>|<span data-ttu-id="d9cd2-127">描述</span><span class="sxs-lookup"><span data-stu-id="d9cd2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9cd2-128">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="d9cd2-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="d9cd2-129">指定作为此信赖方的可接受标识符的 Uri 集。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="d9cd2-130">可选。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-130">Optional.</span></span>|  
|[<span data-ttu-id="d9cd2-131">\<caches></span><span class="sxs-lookup"><span data-stu-id="d9cd2-131">\<caches></span></span>](caches.md)|<span data-ttu-id="d9cd2-132">注册用于会话令牌和令牌重播检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="d9cd2-133">可在服务级别或安全标记处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="d9cd2-134">可选。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-134">Optional.</span></span>|  
|[<span data-ttu-id="d9cd2-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="d9cd2-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="d9cd2-136">控制标记处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="d9cd2-137">可在服务级别或安全标记处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="d9cd2-138">如果为特定处理程序配置了其自己的验证程序，则会重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="d9cd2-139">可选。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-139">Optional.</span></span>|  
|[<span data-ttu-id="d9cd2-140">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d9cd2-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="d9cd2-141">配置标记处理程序集合中的处理程序使用的颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d9cd2-142">可选。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-142">Optional.</span></span>|  
|[<span data-ttu-id="d9cd2-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d9cd2-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="d9cd2-144">注册由标记处理程序集合中的处理程序使用的颁发者令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d9cd2-145">颁发者令牌解析器用于解析传入令牌和消息的签名令牌。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="d9cd2-146">可选。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-146">Optional.</span></span>|  
|[<span data-ttu-id="d9cd2-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d9cd2-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="d9cd2-148">注册令牌处理程序集合中的处理程序使用的服务令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d9cd2-149">服务令牌解析器用于解析传入令牌和消息的加密令牌。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="d9cd2-150">可选。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-150">Optional.</span></span>|  
|[<span data-ttu-id="d9cd2-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="d9cd2-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="d9cd2-152">启用令牌重播检测并指定令牌的过期时间。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="d9cd2-153">可在服务级别或安全标记处理程序集合上指定。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="d9cd2-154">可选。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9cd2-155">父元素</span><span class="sxs-lookup"><span data-stu-id="d9cd2-155">Parent Elements</span></span>  
  
|<span data-ttu-id="d9cd2-156">元素</span><span class="sxs-lookup"><span data-stu-id="d9cd2-156">Element</span></span>|<span data-ttu-id="d9cd2-157">描述</span><span class="sxs-lookup"><span data-stu-id="d9cd2-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9cd2-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d9cd2-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="d9cd2-159">指定注册到终结点的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9cd2-160">备注</span><span class="sxs-lookup"><span data-stu-id="d9cd2-160">Remarks</span></span>  
 <span data-ttu-id="d9cd2-161">本部分提供<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="d9cd2-162">此部分中配置的设置将覆盖在服务上配置的设置。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="d9cd2-163">其中的某些设置可以通过在将处理程序添加到安全标记处理程序集合时指定的设置重写。</span><span class="sxs-lookup"><span data-stu-id="d9cd2-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9cd2-164">示例</span><span class="sxs-lookup"><span data-stu-id="d9cd2-164">Example</span></span>  
  
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
