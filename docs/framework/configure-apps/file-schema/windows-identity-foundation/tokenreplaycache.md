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
ms.workload: dotnet
ms.openlocfilehash: f388369d4dc2e590473ad98189ade70b77551b10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="829b6-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="829b6-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="829b6-103">使用的服务或安全令牌处理程序集合中注册的令牌重放缓存。</span><span class="sxs-lookup"><span data-stu-id="829b6-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="829b6-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="829b6-104">\<system.identityModel></span></span>  
<span data-ttu-id="829b6-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="829b6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="829b6-106">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="829b6-106">\<caches></span></span>  
<span data-ttu-id="829b6-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="829b6-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="829b6-108">语法</span><span class="sxs-lookup"><span data-stu-id="829b6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="829b6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="829b6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="829b6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="829b6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="829b6-111">特性</span><span class="sxs-lookup"><span data-stu-id="829b6-111">Attributes</span></span>  
  
|<span data-ttu-id="829b6-112">特性</span><span class="sxs-lookup"><span data-stu-id="829b6-112">Attribute</span></span>|<span data-ttu-id="829b6-113">描述</span><span class="sxs-lookup"><span data-stu-id="829b6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="829b6-114">类型</span><span class="sxs-lookup"><span data-stu-id="829b6-114">type</span></span>|<span data-ttu-id="829b6-115">派生自类型<xref:System.IdentityModel.Tokens.TokenReplayCache>类。</span><span class="sxs-lookup"><span data-stu-id="829b6-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="829b6-116">有关如何指定自定义的详细信息`type`，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="829b6-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="829b6-117">子元素</span><span class="sxs-lookup"><span data-stu-id="829b6-117">Child Elements</span></span>  
 <span data-ttu-id="829b6-118">无</span><span class="sxs-lookup"><span data-stu-id="829b6-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="829b6-119">父元素</span><span class="sxs-lookup"><span data-stu-id="829b6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="829b6-120">元素</span><span class="sxs-lookup"><span data-stu-id="829b6-120">Element</span></span>|<span data-ttu-id="829b6-121">描述</span><span class="sxs-lookup"><span data-stu-id="829b6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="829b6-122">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="829b6-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="829b6-123">注册的服务或安全令牌处理程序集合使用的缓存。</span><span class="sxs-lookup"><span data-stu-id="829b6-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="829b6-124">备注</span><span class="sxs-lookup"><span data-stu-id="829b6-124">Remarks</span></span>  
 <span data-ttu-id="829b6-125">令牌重放缓存用于检测重播的令牌。</span><span class="sxs-lookup"><span data-stu-id="829b6-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="829b6-126">令牌重放检测通过[ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)元素，它还指定令牌的最大到期时间。</span><span class="sxs-lookup"><span data-stu-id="829b6-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="829b6-127">示例</span><span class="sxs-lookup"><span data-stu-id="829b6-127">Example</span></span>  
 <span data-ttu-id="829b6-128">下面的 XML 演示自定义检测重播的令牌缓存的配置。</span><span class="sxs-lookup"><span data-stu-id="829b6-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="829b6-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="829b6-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="829b6-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="829b6-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
