---
title: '&lt;缓存&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2a9766b826eb7a708b4b4e99b6bd984f9fc76812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755209"
---
# <a name="ltcachesgt"></a><span data-ttu-id="6eb75-102">&lt;缓存&gt;</span><span class="sxs-lookup"><span data-stu-id="6eb75-102">&lt;caches&gt;</span></span>
<span data-ttu-id="6eb75-103">注册用于会话令牌和令牌重放检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="6eb75-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="6eb75-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6eb75-104">\<system.identityModel></span></span>  
<span data-ttu-id="6eb75-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6eb75-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6eb75-106">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="6eb75-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eb75-107">语法</span><span class="sxs-lookup"><span data-stu-id="6eb75-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6eb75-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6eb75-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6eb75-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6eb75-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6eb75-110">特性</span><span class="sxs-lookup"><span data-stu-id="6eb75-110">Attributes</span></span>  
 <span data-ttu-id="6eb75-111">无</span><span class="sxs-lookup"><span data-stu-id="6eb75-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6eb75-112">子元素</span><span class="sxs-lookup"><span data-stu-id="6eb75-112">Child Elements</span></span>  
  
|<span data-ttu-id="6eb75-113">元素</span><span class="sxs-lookup"><span data-stu-id="6eb75-113">Element</span></span>|<span data-ttu-id="6eb75-114">描述</span><span class="sxs-lookup"><span data-stu-id="6eb75-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6eb75-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="6eb75-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="6eb75-116">使用的服务或安全令牌处理程序集合中注册会话令牌的缓存。</span><span class="sxs-lookup"><span data-stu-id="6eb75-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="6eb75-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="6eb75-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="6eb75-118">使用的服务或安全令牌处理程序集合中注册的令牌重放缓存。</span><span class="sxs-lookup"><span data-stu-id="6eb75-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6eb75-119">父元素</span><span class="sxs-lookup"><span data-stu-id="6eb75-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6eb75-120">元素</span><span class="sxs-lookup"><span data-stu-id="6eb75-120">Element</span></span>|<span data-ttu-id="6eb75-121">描述</span><span class="sxs-lookup"><span data-stu-id="6eb75-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6eb75-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6eb75-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="6eb75-123">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="6eb75-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="6eb75-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6eb75-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="6eb75-125">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="6eb75-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eb75-126">备注</span><span class="sxs-lookup"><span data-stu-id="6eb75-126">Remarks</span></span>  
 <span data-ttu-id="6eb75-127">A`<caches>`可以在服务级别下指定元素`<identityConfiguration>`元素或下位于安全令牌处理程序集合级别`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="6eb75-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="6eb75-128">令牌处理程序集合上的设置会覆盖在服务上指定。</span><span class="sxs-lookup"><span data-stu-id="6eb75-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="6eb75-129">`<caches>`元素表示由<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>类。</span><span class="sxs-lookup"><span data-stu-id="6eb75-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="6eb75-130">配置的缓存由<xref:System.IdentityModel.Configuration.IdentityModelCaches>类。</span><span class="sxs-lookup"><span data-stu-id="6eb75-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eb75-131">示例</span><span class="sxs-lookup"><span data-stu-id="6eb75-131">Example</span></span>  
 <span data-ttu-id="6eb75-132">下面的 XML 演示自定义缓存用于保存会话安全令牌的配置 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。</span><span class="sxs-lookup"><span data-stu-id="6eb75-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="6eb75-133">配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="6eb75-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
