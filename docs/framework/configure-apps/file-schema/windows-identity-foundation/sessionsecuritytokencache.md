---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0b0d3c01a81f110f79f64d75aa2ab2ff2873fedd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755040"
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="9b27d-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="9b27d-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="9b27d-103">使用的服务或安全令牌处理程序集合中注册会话令牌的缓存。</span><span class="sxs-lookup"><span data-stu-id="9b27d-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="9b27d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="9b27d-104">\<system.identityModel></span></span>  
<span data-ttu-id="9b27d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9b27d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9b27d-106">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="9b27d-106">\<caches></span></span>  
<span data-ttu-id="9b27d-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="9b27d-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b27d-108">语法</span><span class="sxs-lookup"><span data-stu-id="9b27d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b27d-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b27d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b27d-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b27d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b27d-111">特性</span><span class="sxs-lookup"><span data-stu-id="9b27d-111">Attributes</span></span>  
  
|<span data-ttu-id="9b27d-112">特性</span><span class="sxs-lookup"><span data-stu-id="9b27d-112">Attribute</span></span>|<span data-ttu-id="9b27d-113">描述</span><span class="sxs-lookup"><span data-stu-id="9b27d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b27d-114">类型</span><span class="sxs-lookup"><span data-stu-id="9b27d-114">type</span></span>|<span data-ttu-id="9b27d-115">派生自类型<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类。</span><span class="sxs-lookup"><span data-stu-id="9b27d-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b27d-116">子元素</span><span class="sxs-lookup"><span data-stu-id="9b27d-116">Child Elements</span></span>  
 <span data-ttu-id="9b27d-117">无</span><span class="sxs-lookup"><span data-stu-id="9b27d-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b27d-118">父元素</span><span class="sxs-lookup"><span data-stu-id="9b27d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9b27d-119">元素</span><span class="sxs-lookup"><span data-stu-id="9b27d-119">Element</span></span>|<span data-ttu-id="9b27d-120">描述</span><span class="sxs-lookup"><span data-stu-id="9b27d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b27d-121">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="9b27d-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="9b27d-122">注册的服务或安全令牌处理程序集合使用的缓存。</span><span class="sxs-lookup"><span data-stu-id="9b27d-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b27d-123">示例</span><span class="sxs-lookup"><span data-stu-id="9b27d-123">Example</span></span>  
 <span data-ttu-id="9b27d-124">下面的 XML 演示自定义缓存用于保存会话安全令牌的配置 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。</span><span class="sxs-lookup"><span data-stu-id="9b27d-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="9b27d-125">配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="9b27d-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="9b27d-126">有关此示例的详细信息，请参阅[WIF 代码示例索引](../../../../../docs/framework/security/wif-code-sample-index.md)。</span><span class="sxs-lookup"><span data-stu-id="9b27d-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b27d-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b27d-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
