---
title: <namedCaches> 的 <clear> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658861"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="fdc3a-102">\<清除 namedCaches 的\<> 元素 ></span><span class="sxs-lookup"><span data-stu-id="fdc3a-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="fdc3a-103">清除内存`namedCache`缓存的`namedCaches`集合中的所有项。</span><span class="sxs-lookup"><span data-stu-id="fdc3a-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="fdc3a-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="fdc3a-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="fdc3a-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="fdc3a-105">\<memoryCache></span></span>  
<span data-ttu-id="fdc3a-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="fdc3a-106">\<namedCaches></span></span>  
<span data-ttu-id="fdc3a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="fdc3a-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc3a-108">语法</span><span class="sxs-lookup"><span data-stu-id="fdc3a-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="fdc3a-109">类型</span><span class="sxs-lookup"><span data-stu-id="fdc3a-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdc3a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fdc3a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fdc3a-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fdc3a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdc3a-112">特性</span><span class="sxs-lookup"><span data-stu-id="fdc3a-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="fdc3a-113">子元素</span><span class="sxs-lookup"><span data-stu-id="fdc3a-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="fdc3a-114">父元素</span><span class="sxs-lookup"><span data-stu-id="fdc3a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="fdc3a-115">元素</span><span class="sxs-lookup"><span data-stu-id="fdc3a-115">Element</span></span>|<span data-ttu-id="fdc3a-116">描述</span><span class="sxs-lookup"><span data-stu-id="fdc3a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdc3a-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="fdc3a-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="fdc3a-118">包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="fdc3a-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdc3a-119">备注</span><span class="sxs-lookup"><span data-stu-id="fdc3a-119">Remarks</span></span>  
 <span data-ttu-id="fdc3a-120">元素清除内存缓存`namedCache`的命名缓存集合中的所有项。 `clear`</span><span class="sxs-lookup"><span data-stu-id="fdc3a-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="fdc3a-121">`clear` 在`add`使用元素添加新的命名缓存条目之前, 可以使用元素, 以便确定集合中没有其他命名缓存。</span><span class="sxs-lookup"><span data-stu-id="fdc3a-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc3a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdc3a-122">See also</span></span>

- [<span data-ttu-id="fdc3a-123">\<namedCaches > 元素 (缓存设置)</span><span class="sxs-lookup"><span data-stu-id="fdc3a-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
