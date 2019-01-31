---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 697c20d1f526cb376c2430f0006349f7d8f9b2f1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257935"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="edfad-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="edfad-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="edfad-102">使用的服务或安全令牌处理程序集合注册会话令牌的缓存。</span><span class="sxs-lookup"><span data-stu-id="edfad-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="edfad-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="edfad-103">\<system.identityModel></span></span>  
<span data-ttu-id="edfad-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="edfad-104">\<identityConfiguration></span></span>  
<span data-ttu-id="edfad-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="edfad-105">\<caches></span></span>  
<span data-ttu-id="edfad-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="edfad-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edfad-107">语法</span><span class="sxs-lookup"><span data-stu-id="edfad-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edfad-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="edfad-108">Attributes and Elements</span></span>  
 <span data-ttu-id="edfad-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="edfad-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edfad-110">特性</span><span class="sxs-lookup"><span data-stu-id="edfad-110">Attributes</span></span>  
  
|<span data-ttu-id="edfad-111">特性</span><span class="sxs-lookup"><span data-stu-id="edfad-111">Attribute</span></span>|<span data-ttu-id="edfad-112">描述</span><span class="sxs-lookup"><span data-stu-id="edfad-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="edfad-113">类型</span><span class="sxs-lookup"><span data-stu-id="edfad-113">type</span></span>|<span data-ttu-id="edfad-114">从派生的类型的<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类。</span><span class="sxs-lookup"><span data-stu-id="edfad-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edfad-115">子元素</span><span class="sxs-lookup"><span data-stu-id="edfad-115">Child Elements</span></span>  
 <span data-ttu-id="edfad-116">无</span><span class="sxs-lookup"><span data-stu-id="edfad-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="edfad-117">父元素</span><span class="sxs-lookup"><span data-stu-id="edfad-117">Parent Elements</span></span>  
  
|<span data-ttu-id="edfad-118">元素</span><span class="sxs-lookup"><span data-stu-id="edfad-118">Element</span></span>|<span data-ttu-id="edfad-119">描述</span><span class="sxs-lookup"><span data-stu-id="edfad-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edfad-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="edfad-120">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="edfad-121">注册服务或安全令牌处理程序集合使用的缓存。</span><span class="sxs-lookup"><span data-stu-id="edfad-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="edfad-122">示例</span><span class="sxs-lookup"><span data-stu-id="edfad-122">Example</span></span>  
 <span data-ttu-id="edfad-123">下面的 XML 演示的用于保存会话安全令牌的自定义缓存配置 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。</span><span class="sxs-lookup"><span data-stu-id="edfad-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="edfad-124">配置来自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="edfad-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="edfad-125">有关此示例的详细信息，请参阅[WIF 代码示例索引](../../../../../docs/framework/security/wif-code-sample-index.md)。</span><span class="sxs-lookup"><span data-stu-id="edfad-125">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edfad-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="edfad-126">See also</span></span>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
