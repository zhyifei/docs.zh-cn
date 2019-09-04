---
title: <namedCaches> 的 <clear> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252759"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="942c6-102">\<清除 namedCaches 的\<> 元素 ></span><span class="sxs-lookup"><span data-stu-id="942c6-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="942c6-103">清除内存`namedCache`缓存的`namedCaches`集合中的所有项。</span><span class="sxs-lookup"><span data-stu-id="942c6-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="942c6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="942c6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="942c6-105">&nbsp;&nbsp;[ **\<> 缓存**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="942c6-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="942c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="942c6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="942c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="942c6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="942c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<清除 >**</span><span class="sxs-lookup"><span data-stu-id="942c6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="942c6-109">语法</span><span class="sxs-lookup"><span data-stu-id="942c6-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="942c6-110">类型</span><span class="sxs-lookup"><span data-stu-id="942c6-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="942c6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="942c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="942c6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="942c6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="942c6-113">特性</span><span class="sxs-lookup"><span data-stu-id="942c6-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="942c6-114">子元素</span><span class="sxs-lookup"><span data-stu-id="942c6-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="942c6-115">父元素</span><span class="sxs-lookup"><span data-stu-id="942c6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="942c6-116">元素</span><span class="sxs-lookup"><span data-stu-id="942c6-116">Element</span></span>|<span data-ttu-id="942c6-117">描述</span><span class="sxs-lookup"><span data-stu-id="942c6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="942c6-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="942c6-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="942c6-119">包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="942c6-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="942c6-120">备注</span><span class="sxs-lookup"><span data-stu-id="942c6-120">Remarks</span></span>  
 <span data-ttu-id="942c6-121">元素清除内存缓存`namedCache`的命名缓存集合中的所有项。 `clear`</span><span class="sxs-lookup"><span data-stu-id="942c6-121">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="942c6-122">`clear` 在`add`使用元素添加新的命名缓存条目之前，可以使用元素，以便确定集合中没有其他命名缓存。</span><span class="sxs-lookup"><span data-stu-id="942c6-122">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942c6-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="942c6-123">See also</span></span>

- [<span data-ttu-id="942c6-124">\<namedCaches > 元素（缓存设置）</span><span class="sxs-lookup"><span data-stu-id="942c6-124">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
