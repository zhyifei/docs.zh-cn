---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251782"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="f69f6-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f69f6-101">\<tokenReplayCache></span></span>
<span data-ttu-id="f69f6-102">向服务或安全标记处理程序集合注册令牌重播缓存。</span><span class="sxs-lookup"><span data-stu-id="f69f6-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="f69f6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f69f6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f69f6-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f69f6-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f69f6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f69f6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f69f6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<缓存 >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="f69f6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="f69f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenReplayCache >**</span><span class="sxs-lookup"><span data-stu-id="f69f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f69f6-108">语法</span><span class="sxs-lookup"><span data-stu-id="f69f6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f69f6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f69f6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f69f6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f69f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f69f6-111">特性</span><span class="sxs-lookup"><span data-stu-id="f69f6-111">Attributes</span></span>  
  
|<span data-ttu-id="f69f6-112">特性</span><span class="sxs-lookup"><span data-stu-id="f69f6-112">Attribute</span></span>|<span data-ttu-id="f69f6-113">描述</span><span class="sxs-lookup"><span data-stu-id="f69f6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f69f6-114">type</span><span class="sxs-lookup"><span data-stu-id="f69f6-114">type</span></span>|<span data-ttu-id="f69f6-115">派生自<xref:System.IdentityModel.Tokens.TokenReplayCache>类的类型。</span><span class="sxs-lookup"><span data-stu-id="f69f6-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f69f6-116">有关如何指定自定义`type`的详细信息，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="f69f6-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f69f6-117">子元素</span><span class="sxs-lookup"><span data-stu-id="f69f6-117">Child Elements</span></span>  
 <span data-ttu-id="f69f6-118">无</span><span class="sxs-lookup"><span data-stu-id="f69f6-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f69f6-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f69f6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f69f6-120">元素</span><span class="sxs-lookup"><span data-stu-id="f69f6-120">Element</span></span>|<span data-ttu-id="f69f6-121">描述</span><span class="sxs-lookup"><span data-stu-id="f69f6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f69f6-122">\<caches></span><span class="sxs-lookup"><span data-stu-id="f69f6-122">\<caches></span></span>](caches.md)|<span data-ttu-id="f69f6-123">注册服务使用的缓存或安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="f69f6-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f69f6-124">备注</span><span class="sxs-lookup"><span data-stu-id="f69f6-124">Remarks</span></span>  
 <span data-ttu-id="f69f6-125">令牌重播缓存用于检测重播的标记。</span><span class="sxs-lookup"><span data-stu-id="f69f6-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f69f6-126">令牌重播检测由[ \<tokenReplayDetection >](tokenreplaydetection.md)元素启用，该元素还指定了令牌的最长到期时间。</span><span class="sxs-lookup"><span data-stu-id="f69f6-126">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f69f6-127">示例</span><span class="sxs-lookup"><span data-stu-id="f69f6-127">Example</span></span>  
 <span data-ttu-id="f69f6-128">下面的 XML 演示了用于检测重播令牌的自定义缓存配置。</span><span class="sxs-lookup"><span data-stu-id="f69f6-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f69f6-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f69f6-129">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="f69f6-130">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="f69f6-130">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
