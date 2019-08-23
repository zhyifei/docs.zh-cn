---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944077"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="f17d5-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f17d5-101">\<tokenReplayCache></span></span>
<span data-ttu-id="f17d5-102">向服务或安全标记处理程序集合注册令牌重播缓存。</span><span class="sxs-lookup"><span data-stu-id="f17d5-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="f17d5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f17d5-103">\<system.identityModel></span></span>  
<span data-ttu-id="f17d5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f17d5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f17d5-105">\<缓存 ></span><span class="sxs-lookup"><span data-stu-id="f17d5-105">\<caches></span></span>  
<span data-ttu-id="f17d5-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f17d5-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17d5-107">语法</span><span class="sxs-lookup"><span data-stu-id="f17d5-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f17d5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f17d5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f17d5-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f17d5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f17d5-110">特性</span><span class="sxs-lookup"><span data-stu-id="f17d5-110">Attributes</span></span>  
  
|<span data-ttu-id="f17d5-111">特性</span><span class="sxs-lookup"><span data-stu-id="f17d5-111">Attribute</span></span>|<span data-ttu-id="f17d5-112">描述</span><span class="sxs-lookup"><span data-stu-id="f17d5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f17d5-113">type</span><span class="sxs-lookup"><span data-stu-id="f17d5-113">type</span></span>|<span data-ttu-id="f17d5-114">派生自<xref:System.IdentityModel.Tokens.TokenReplayCache>类的类型。</span><span class="sxs-lookup"><span data-stu-id="f17d5-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f17d5-115">有关如何指定自定义`type`的详细信息, 请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="f17d5-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f17d5-116">子元素</span><span class="sxs-lookup"><span data-stu-id="f17d5-116">Child Elements</span></span>  
 <span data-ttu-id="f17d5-117">无</span><span class="sxs-lookup"><span data-stu-id="f17d5-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f17d5-118">父元素</span><span class="sxs-lookup"><span data-stu-id="f17d5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f17d5-119">元素</span><span class="sxs-lookup"><span data-stu-id="f17d5-119">Element</span></span>|<span data-ttu-id="f17d5-120">描述</span><span class="sxs-lookup"><span data-stu-id="f17d5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f17d5-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="f17d5-121">\<caches></span></span>](caches.md)|<span data-ttu-id="f17d5-122">注册服务使用的缓存或安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="f17d5-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f17d5-123">备注</span><span class="sxs-lookup"><span data-stu-id="f17d5-123">Remarks</span></span>  
 <span data-ttu-id="f17d5-124">令牌重播缓存用于检测重播的标记。</span><span class="sxs-lookup"><span data-stu-id="f17d5-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f17d5-125">令牌重播检测由[ \<tokenReplayDetection >](tokenreplaydetection.md)元素启用, 该元素还指定了令牌的最长到期时间。</span><span class="sxs-lookup"><span data-stu-id="f17d5-125">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f17d5-126">示例</span><span class="sxs-lookup"><span data-stu-id="f17d5-126">Example</span></span>  
 <span data-ttu-id="f17d5-127">下面的 XML 演示了用于检测重播令牌的自定义缓存配置。</span><span class="sxs-lookup"><span data-stu-id="f17d5-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f17d5-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f17d5-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="f17d5-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="f17d5-129">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
