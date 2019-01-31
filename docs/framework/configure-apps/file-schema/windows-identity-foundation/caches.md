---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285657"
---
# <a name="caches"></a><span data-ttu-id="3cc40-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="3cc40-101">\<caches></span></span>
<span data-ttu-id="3cc40-102">注册用于会话令牌和令牌重放检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="3cc40-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="3cc40-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3cc40-103">\<system.identityModel></span></span>  
<span data-ttu-id="3cc40-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3cc40-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3cc40-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="3cc40-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc40-106">语法</span><span class="sxs-lookup"><span data-stu-id="3cc40-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cc40-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3cc40-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3cc40-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3cc40-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cc40-109">特性</span><span class="sxs-lookup"><span data-stu-id="3cc40-109">Attributes</span></span>  
 <span data-ttu-id="3cc40-110">无</span><span class="sxs-lookup"><span data-stu-id="3cc40-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3cc40-111">子元素</span><span class="sxs-lookup"><span data-stu-id="3cc40-111">Child Elements</span></span>  
  
|<span data-ttu-id="3cc40-112">元素</span><span class="sxs-lookup"><span data-stu-id="3cc40-112">Element</span></span>|<span data-ttu-id="3cc40-113">描述</span><span class="sxs-lookup"><span data-stu-id="3cc40-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cc40-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="3cc40-114">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="3cc40-115">使用的服务或安全令牌处理程序集合注册会话令牌的缓存。</span><span class="sxs-lookup"><span data-stu-id="3cc40-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="3cc40-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="3cc40-116">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="3cc40-117">使用的服务或安全令牌处理程序集合注册的标记重播缓存。</span><span class="sxs-lookup"><span data-stu-id="3cc40-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cc40-118">父元素</span><span class="sxs-lookup"><span data-stu-id="3cc40-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3cc40-119">元素</span><span class="sxs-lookup"><span data-stu-id="3cc40-119">Element</span></span>|<span data-ttu-id="3cc40-120">描述</span><span class="sxs-lookup"><span data-stu-id="3cc40-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cc40-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3cc40-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="3cc40-122">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="3cc40-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="3cc40-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3cc40-123">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="3cc40-124">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="3cc40-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cc40-125">备注</span><span class="sxs-lookup"><span data-stu-id="3cc40-125">Remarks</span></span>  
 <span data-ttu-id="3cc40-126">一个`<caches>`可以在服务级别下指定元素`<identityConfiguration>`元素下的安全令牌处理程序集合级别上或`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="3cc40-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="3cc40-127">标记处理程序集合上的设置将覆盖在服务上指定的。</span><span class="sxs-lookup"><span data-stu-id="3cc40-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="3cc40-128">`<caches>`元素表示由<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>类。</span><span class="sxs-lookup"><span data-stu-id="3cc40-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="3cc40-129">表示配置的缓存<xref:System.IdentityModel.Configuration.IdentityModelCaches>类。</span><span class="sxs-lookup"><span data-stu-id="3cc40-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cc40-130">示例</span><span class="sxs-lookup"><span data-stu-id="3cc40-130">Example</span></span>  
 <span data-ttu-id="3cc40-131">下面的 XML 演示的用于保存会话安全令牌的自定义缓存配置 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。</span><span class="sxs-lookup"><span data-stu-id="3cc40-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="3cc40-132">配置来自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="3cc40-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
