---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: e949b16f76f20191b84bbbbb6e8b019d913316f0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251835"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="4db94-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="4db94-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="4db94-102">使用服务或安全标记处理程序集合为会话令牌注册缓存。</span><span class="sxs-lookup"><span data-stu-id="4db94-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="4db94-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4db94-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4db94-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4db94-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4db94-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4db94-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4db94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<缓存 >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="4db94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="4db94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sessionsecuritytokencache> >**</span><span class="sxs-lookup"><span data-stu-id="4db94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db94-108">语法</span><span class="sxs-lookup"><span data-stu-id="4db94-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4db94-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4db94-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4db94-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4db94-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4db94-111">特性</span><span class="sxs-lookup"><span data-stu-id="4db94-111">Attributes</span></span>  
  
|<span data-ttu-id="4db94-112">特性</span><span class="sxs-lookup"><span data-stu-id="4db94-112">Attribute</span></span>|<span data-ttu-id="4db94-113">描述</span><span class="sxs-lookup"><span data-stu-id="4db94-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4db94-114">type</span><span class="sxs-lookup"><span data-stu-id="4db94-114">type</span></span>|<span data-ttu-id="4db94-115">派生自<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类的类型。</span><span class="sxs-lookup"><span data-stu-id="4db94-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4db94-116">子元素</span><span class="sxs-lookup"><span data-stu-id="4db94-116">Child Elements</span></span>  
 <span data-ttu-id="4db94-117">无</span><span class="sxs-lookup"><span data-stu-id="4db94-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4db94-118">父元素</span><span class="sxs-lookup"><span data-stu-id="4db94-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4db94-119">元素</span><span class="sxs-lookup"><span data-stu-id="4db94-119">Element</span></span>|<span data-ttu-id="4db94-120">描述</span><span class="sxs-lookup"><span data-stu-id="4db94-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4db94-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="4db94-121">\<caches></span></span>](caches.md)|<span data-ttu-id="4db94-122">注册服务使用的缓存或安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="4db94-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4db94-123">示例</span><span class="sxs-lookup"><span data-stu-id="4db94-123">Example</span></span>  
 <span data-ttu-id="4db94-124">下面的 XML 演示了用于保存会话安全令牌（<xref:System.IdentityModel.Tokens.SessionSecurityToken>）的自定义缓存配置。</span><span class="sxs-lookup"><span data-stu-id="4db94-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="4db94-125">此配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="4db94-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="4db94-126">有关此示例的详细信息，请参阅[WIF 代码示例索引](../../../security/wif-code-sample-index.md)。</span><span class="sxs-lookup"><span data-stu-id="4db94-126">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4db94-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="4db94-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
