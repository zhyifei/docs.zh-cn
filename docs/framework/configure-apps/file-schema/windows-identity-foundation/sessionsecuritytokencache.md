---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646064"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="da9fd-101">\<会话安全令牌缓存></span><span class="sxs-lookup"><span data-stu-id="da9fd-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="da9fd-102">使用服务或安全令牌处理程序集合注册会话令牌的缓存。</span><span class="sxs-lookup"><span data-stu-id="da9fd-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="da9fd-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da9fd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da9fd-104">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="da9fd-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="da9fd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="da9fd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="da9fd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<缓存>**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="da9fd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="da9fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<会话安全令牌缓存>**</span><span class="sxs-lookup"><span data-stu-id="da9fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da9fd-108">语法</span><span class="sxs-lookup"><span data-stu-id="da9fd-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da9fd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da9fd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="da9fd-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da9fd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da9fd-111">特性</span><span class="sxs-lookup"><span data-stu-id="da9fd-111">Attributes</span></span>  
  
|<span data-ttu-id="da9fd-112">特性</span><span class="sxs-lookup"><span data-stu-id="da9fd-112">Attribute</span></span>|<span data-ttu-id="da9fd-113">说明</span><span class="sxs-lookup"><span data-stu-id="da9fd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da9fd-114">type</span><span class="sxs-lookup"><span data-stu-id="da9fd-114">type</span></span>|<span data-ttu-id="da9fd-115">派生自<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类的类型。</span><span class="sxs-lookup"><span data-stu-id="da9fd-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da9fd-116">子元素</span><span class="sxs-lookup"><span data-stu-id="da9fd-116">Child Elements</span></span>  
 <span data-ttu-id="da9fd-117">无</span><span class="sxs-lookup"><span data-stu-id="da9fd-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da9fd-118">父元素</span><span class="sxs-lookup"><span data-stu-id="da9fd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="da9fd-119">元素</span><span class="sxs-lookup"><span data-stu-id="da9fd-119">Element</span></span>|<span data-ttu-id="da9fd-120">说明</span><span class="sxs-lookup"><span data-stu-id="da9fd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da9fd-121">\<缓存></span><span class="sxs-lookup"><span data-stu-id="da9fd-121">\<caches></span></span>](caches.md)|<span data-ttu-id="da9fd-122">注册服务或安全令牌处理程序集合使用的缓存。</span><span class="sxs-lookup"><span data-stu-id="da9fd-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="da9fd-123">示例</span><span class="sxs-lookup"><span data-stu-id="da9fd-123">Example</span></span>  
 <span data-ttu-id="da9fd-124">以下 XML 显示了用于保存会话安全令牌的自定义缓存的配置 。<xref:System.IdentityModel.Tokens.SessionSecurityToken></span><span class="sxs-lookup"><span data-stu-id="da9fd-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="da9fd-125">配置取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="da9fd-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="da9fd-126">有关此示例的详细信息，请参阅[WIF 代码示例索引](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)。</span><span class="sxs-lookup"><span data-stu-id="da9fd-126">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="da9fd-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da9fd-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
