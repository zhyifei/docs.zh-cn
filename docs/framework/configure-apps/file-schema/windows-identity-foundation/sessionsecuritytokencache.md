---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943714"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="d7d85-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d7d85-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="d7d85-102">使用服务或安全标记处理程序集合为会话令牌注册缓存。</span><span class="sxs-lookup"><span data-stu-id="d7d85-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="d7d85-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d7d85-103">\<system.identityModel></span></span>  
<span data-ttu-id="d7d85-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d7d85-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d7d85-105">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="d7d85-105">\<caches></span></span>  
<span data-ttu-id="d7d85-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="d7d85-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d85-107">语法</span><span class="sxs-lookup"><span data-stu-id="d7d85-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7d85-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d7d85-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d7d85-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d7d85-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7d85-110">特性</span><span class="sxs-lookup"><span data-stu-id="d7d85-110">Attributes</span></span>  
  
|<span data-ttu-id="d7d85-111">特性</span><span class="sxs-lookup"><span data-stu-id="d7d85-111">Attribute</span></span>|<span data-ttu-id="d7d85-112">描述</span><span class="sxs-lookup"><span data-stu-id="d7d85-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7d85-113">type</span><span class="sxs-lookup"><span data-stu-id="d7d85-113">type</span></span>|<span data-ttu-id="d7d85-114">派生自<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类的类型。</span><span class="sxs-lookup"><span data-stu-id="d7d85-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7d85-115">子元素</span><span class="sxs-lookup"><span data-stu-id="d7d85-115">Child Elements</span></span>  
 <span data-ttu-id="d7d85-116">无</span><span class="sxs-lookup"><span data-stu-id="d7d85-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7d85-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d7d85-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d7d85-118">元素</span><span class="sxs-lookup"><span data-stu-id="d7d85-118">Element</span></span>|<span data-ttu-id="d7d85-119">描述</span><span class="sxs-lookup"><span data-stu-id="d7d85-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7d85-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="d7d85-120">\<caches></span></span>](caches.md)|<span data-ttu-id="d7d85-121">注册服务使用的缓存或安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="d7d85-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d7d85-122">示例</span><span class="sxs-lookup"><span data-stu-id="d7d85-122">Example</span></span>  
 <span data-ttu-id="d7d85-123">下面的 XML 演示了用于保存会话安全令牌 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>) 的自定义缓存配置。</span><span class="sxs-lookup"><span data-stu-id="d7d85-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="d7d85-124">此配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="d7d85-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="d7d85-125">有关此示例的详细信息, 请参阅[WIF 代码示例索引](../../../security/wif-code-sample-index.md)。</span><span class="sxs-lookup"><span data-stu-id="d7d85-125">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7d85-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7d85-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
