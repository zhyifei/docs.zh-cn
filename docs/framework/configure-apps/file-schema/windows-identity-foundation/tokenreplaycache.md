---
title: '&lt;tokenReplayCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e43e79416ddb8862cbc6e52d9d449a02b123af83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="99bb2-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="99bb2-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="99bb2-103">使用的服务或安全令牌处理程序集合中注册的令牌重放缓存。</span><span class="sxs-lookup"><span data-stu-id="99bb2-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="99bb2-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="99bb2-104">\<system.identityModel></span></span>  
<span data-ttu-id="99bb2-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="99bb2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="99bb2-106">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="99bb2-106">\<caches></span></span>  
<span data-ttu-id="99bb2-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="99bb2-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99bb2-108">语法</span><span class="sxs-lookup"><span data-stu-id="99bb2-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99bb2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="99bb2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="99bb2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="99bb2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99bb2-111">特性</span><span class="sxs-lookup"><span data-stu-id="99bb2-111">Attributes</span></span>  
  
|<span data-ttu-id="99bb2-112">特性</span><span class="sxs-lookup"><span data-stu-id="99bb2-112">Attribute</span></span>|<span data-ttu-id="99bb2-113">描述</span><span class="sxs-lookup"><span data-stu-id="99bb2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99bb2-114">类型</span><span class="sxs-lookup"><span data-stu-id="99bb2-114">type</span></span>|<span data-ttu-id="99bb2-115">派生自类型<xref:System.IdentityModel.Tokens.TokenReplayCache>类。</span><span class="sxs-lookup"><span data-stu-id="99bb2-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="99bb2-116">有关如何指定自定义的详细信息`type`，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="99bb2-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="99bb2-117">子元素</span><span class="sxs-lookup"><span data-stu-id="99bb2-117">Child Elements</span></span>  
 <span data-ttu-id="99bb2-118">无</span><span class="sxs-lookup"><span data-stu-id="99bb2-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99bb2-119">父元素</span><span class="sxs-lookup"><span data-stu-id="99bb2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="99bb2-120">元素</span><span class="sxs-lookup"><span data-stu-id="99bb2-120">Element</span></span>|<span data-ttu-id="99bb2-121">描述</span><span class="sxs-lookup"><span data-stu-id="99bb2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99bb2-122">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="99bb2-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="99bb2-123">注册的服务或安全令牌处理程序集合使用的缓存。</span><span class="sxs-lookup"><span data-stu-id="99bb2-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99bb2-124">备注</span><span class="sxs-lookup"><span data-stu-id="99bb2-124">Remarks</span></span>  
 <span data-ttu-id="99bb2-125">令牌重放缓存用于检测重播的令牌。</span><span class="sxs-lookup"><span data-stu-id="99bb2-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="99bb2-126">令牌重放检测通过[ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)元素，它还指定令牌的最大到期时间。</span><span class="sxs-lookup"><span data-stu-id="99bb2-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99bb2-127">示例</span><span class="sxs-lookup"><span data-stu-id="99bb2-127">Example</span></span>  
 <span data-ttu-id="99bb2-128">下面的 XML 演示自定义检测重播的令牌缓存的配置。</span><span class="sxs-lookup"><span data-stu-id="99bb2-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99bb2-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99bb2-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="99bb2-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="99bb2-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
