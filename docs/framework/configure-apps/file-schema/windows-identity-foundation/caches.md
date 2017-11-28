---
title: "&lt;缓存&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f0c46532cb7716f4dc066f0e96c14534d7fa0b42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltcachesgt"></a><span data-ttu-id="feb18-102">&lt;缓存&gt;</span><span class="sxs-lookup"><span data-stu-id="feb18-102">&lt;caches&gt;</span></span>
<span data-ttu-id="feb18-103">注册用于会话令牌和令牌重放检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="feb18-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="feb18-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="feb18-104">\<system.identityModel></span></span>  
<span data-ttu-id="feb18-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="feb18-105">\<identityConfiguration></span></span>  
<span data-ttu-id="feb18-106">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="feb18-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb18-107">语法</span><span class="sxs-lookup"><span data-stu-id="feb18-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="feb18-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="feb18-108">Attributes and Elements</span></span>  
 <span data-ttu-id="feb18-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="feb18-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="feb18-110">特性</span><span class="sxs-lookup"><span data-stu-id="feb18-110">Attributes</span></span>  
 <span data-ttu-id="feb18-111">无</span><span class="sxs-lookup"><span data-stu-id="feb18-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="feb18-112">子元素</span><span class="sxs-lookup"><span data-stu-id="feb18-112">Child Elements</span></span>  
  
|<span data-ttu-id="feb18-113">元素</span><span class="sxs-lookup"><span data-stu-id="feb18-113">Element</span></span>|<span data-ttu-id="feb18-114">描述</span><span class="sxs-lookup"><span data-stu-id="feb18-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="feb18-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="feb18-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="feb18-116">使用的服务或安全令牌处理程序集合中注册会话令牌的缓存。</span><span class="sxs-lookup"><span data-stu-id="feb18-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="feb18-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="feb18-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="feb18-118">使用的服务或安全令牌处理程序集合中注册的令牌重放缓存。</span><span class="sxs-lookup"><span data-stu-id="feb18-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="feb18-119">父元素</span><span class="sxs-lookup"><span data-stu-id="feb18-119">Parent Elements</span></span>  
  
|<span data-ttu-id="feb18-120">元素</span><span class="sxs-lookup"><span data-stu-id="feb18-120">Element</span></span>|<span data-ttu-id="feb18-121">描述</span><span class="sxs-lookup"><span data-stu-id="feb18-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="feb18-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="feb18-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="feb18-123">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="feb18-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="feb18-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="feb18-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="feb18-125">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="feb18-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feb18-126">备注</span><span class="sxs-lookup"><span data-stu-id="feb18-126">Remarks</span></span>  
 <span data-ttu-id="feb18-127">A`<caches>`可以在服务级别下指定元素`<identityConfiguration>`元素或下位于安全令牌处理程序集合级别`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="feb18-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="feb18-128">令牌处理程序集合上的设置会覆盖在服务上指定。</span><span class="sxs-lookup"><span data-stu-id="feb18-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="feb18-129">`<caches>`元素表示由<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>类。</span><span class="sxs-lookup"><span data-stu-id="feb18-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="feb18-130">配置的缓存由<xref:System.IdentityModel.Configuration.IdentityModelCaches>类。</span><span class="sxs-lookup"><span data-stu-id="feb18-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="feb18-131">示例</span><span class="sxs-lookup"><span data-stu-id="feb18-131">Example</span></span>  
 <span data-ttu-id="feb18-132">下面的 XML 演示自定义缓存用于保存会话安全令牌的配置 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。</span><span class="sxs-lookup"><span data-stu-id="feb18-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="feb18-133">配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="feb18-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
