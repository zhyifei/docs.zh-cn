---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941967"
---
# <a name="caches"></a><span data-ttu-id="5ab91-101">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="5ab91-101">\<caches></span></span>
<span data-ttu-id="5ab91-102">注册用于会话令牌和令牌重播检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="5ab91-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="5ab91-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5ab91-103">\<system.identityModel></span></span>  
<span data-ttu-id="5ab91-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5ab91-104">\<identityConfiguration></span></span>  
<span data-ttu-id="5ab91-105">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="5ab91-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab91-106">语法</span><span class="sxs-lookup"><span data-stu-id="5ab91-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ab91-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5ab91-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5ab91-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5ab91-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ab91-109">特性</span><span class="sxs-lookup"><span data-stu-id="5ab91-109">Attributes</span></span>  
 <span data-ttu-id="5ab91-110">无</span><span class="sxs-lookup"><span data-stu-id="5ab91-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ab91-111">子元素</span><span class="sxs-lookup"><span data-stu-id="5ab91-111">Child Elements</span></span>  
  
|<span data-ttu-id="5ab91-112">元素</span><span class="sxs-lookup"><span data-stu-id="5ab91-112">Element</span></span>|<span data-ttu-id="5ab91-113">描述</span><span class="sxs-lookup"><span data-stu-id="5ab91-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ab91-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="5ab91-114">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="5ab91-115">使用服务或安全标记处理程序集合为会话令牌注册缓存。</span><span class="sxs-lookup"><span data-stu-id="5ab91-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="5ab91-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="5ab91-116">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="5ab91-117">向服务或安全标记处理程序集合注册令牌重播缓存。</span><span class="sxs-lookup"><span data-stu-id="5ab91-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ab91-118">父元素</span><span class="sxs-lookup"><span data-stu-id="5ab91-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5ab91-119">元素</span><span class="sxs-lookup"><span data-stu-id="5ab91-119">Element</span></span>|<span data-ttu-id="5ab91-120">描述</span><span class="sxs-lookup"><span data-stu-id="5ab91-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ab91-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5ab91-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="5ab91-122">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="5ab91-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="5ab91-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="5ab91-123">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="5ab91-124">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="5ab91-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ab91-125">备注</span><span class="sxs-lookup"><span data-stu-id="5ab91-125">Remarks</span></span>  
 <span data-ttu-id="5ab91-126">可以在元素`<identityConfiguration>`下的服务级别指定元素, 或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<caches>`</span><span class="sxs-lookup"><span data-stu-id="5ab91-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="5ab91-127">标记处理程序集合上的设置将重写服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="5ab91-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="5ab91-128">元素由<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>类表示。 `<caches>`</span><span class="sxs-lookup"><span data-stu-id="5ab91-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="5ab91-129">配置的缓存由<xref:System.IdentityModel.Configuration.IdentityModelCaches>类表示。</span><span class="sxs-lookup"><span data-stu-id="5ab91-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ab91-130">示例</span><span class="sxs-lookup"><span data-stu-id="5ab91-130">Example</span></span>  
 <span data-ttu-id="5ab91-131">下面的 XML 演示了用于保存会话安全令牌 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>) 的自定义缓存配置。</span><span class="sxs-lookup"><span data-stu-id="5ab91-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="5ab91-132">此配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="5ab91-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
