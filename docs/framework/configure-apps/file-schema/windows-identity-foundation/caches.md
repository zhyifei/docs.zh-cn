---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252159"
---
# <a name="caches"></a><span data-ttu-id="a55ab-101">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="a55ab-101">\<caches></span></span>
<span data-ttu-id="a55ab-102">注册用于会话令牌和令牌重播检测的缓存。</span><span class="sxs-lookup"><span data-stu-id="a55ab-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
<span data-ttu-id="a55ab-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a55ab-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a55ab-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a55ab-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a55ab-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a55ab-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a55ab-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<缓存 >**</span><span class="sxs-lookup"><span data-stu-id="a55ab-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a55ab-107">语法</span><span class="sxs-lookup"><span data-stu-id="a55ab-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a55ab-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a55ab-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a55ab-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a55ab-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a55ab-110">特性</span><span class="sxs-lookup"><span data-stu-id="a55ab-110">Attributes</span></span>  
 <span data-ttu-id="a55ab-111">无</span><span class="sxs-lookup"><span data-stu-id="a55ab-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a55ab-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a55ab-112">Child Elements</span></span>  
  
|<span data-ttu-id="a55ab-113">元素</span><span class="sxs-lookup"><span data-stu-id="a55ab-113">Element</span></span>|<span data-ttu-id="a55ab-114">描述</span><span class="sxs-lookup"><span data-stu-id="a55ab-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a55ab-115">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="a55ab-115">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="a55ab-116">使用服务或安全标记处理程序集合为会话令牌注册缓存。</span><span class="sxs-lookup"><span data-stu-id="a55ab-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="a55ab-117">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="a55ab-117">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="a55ab-118">向服务或安全标记处理程序集合注册令牌重播缓存。</span><span class="sxs-lookup"><span data-stu-id="a55ab-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a55ab-119">父元素</span><span class="sxs-lookup"><span data-stu-id="a55ab-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a55ab-120">元素</span><span class="sxs-lookup"><span data-stu-id="a55ab-120">Element</span></span>|<span data-ttu-id="a55ab-121">描述</span><span class="sxs-lookup"><span data-stu-id="a55ab-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a55ab-122">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a55ab-122">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="a55ab-123">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="a55ab-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="a55ab-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="a55ab-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="a55ab-125">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="a55ab-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a55ab-126">备注</span><span class="sxs-lookup"><span data-stu-id="a55ab-126">Remarks</span></span>  
 <span data-ttu-id="a55ab-127">可以在元素`<identityConfiguration>`下的服务级别指定元素，或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<caches>`</span><span class="sxs-lookup"><span data-stu-id="a55ab-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="a55ab-128">标记处理程序集合上的设置将重写服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="a55ab-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="a55ab-129">元素由<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>类表示。 `<caches>`</span><span class="sxs-lookup"><span data-stu-id="a55ab-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="a55ab-130">配置的缓存由<xref:System.IdentityModel.Configuration.IdentityModelCaches>类表示。</span><span class="sxs-lookup"><span data-stu-id="a55ab-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a55ab-131">示例</span><span class="sxs-lookup"><span data-stu-id="a55ab-131">Example</span></span>  
 <span data-ttu-id="a55ab-132">下面的 XML 演示了用于保存会话安全令牌（<xref:System.IdentityModel.Tokens.SessionSecurityToken>）的自定义缓存配置。</span><span class="sxs-lookup"><span data-stu-id="a55ab-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="a55ab-133">此配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="a55ab-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
