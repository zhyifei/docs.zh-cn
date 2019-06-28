---
title: <namedCaches> 的 <clear> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: e563f8f27538e70ba90465fc28d300754509f7a4
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423310"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="69354-102">\<清除 > 元素\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="69354-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="69354-103">清除所有`namedCache`中的条目`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="69354-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="69354-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="69354-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="69354-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="69354-105">\<memoryCache></span></span>  
<span data-ttu-id="69354-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="69354-106">\<namedCaches></span></span>  
<span data-ttu-id="69354-107">\<add></span><span class="sxs-lookup"><span data-stu-id="69354-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69354-108">语法</span><span class="sxs-lookup"><span data-stu-id="69354-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="69354-109">类型</span><span class="sxs-lookup"><span data-stu-id="69354-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69354-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="69354-110">Attributes and Elements</span></span>  
 <span data-ttu-id="69354-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="69354-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69354-112">特性</span><span class="sxs-lookup"><span data-stu-id="69354-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="69354-113">子元素</span><span class="sxs-lookup"><span data-stu-id="69354-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="69354-114">父元素</span><span class="sxs-lookup"><span data-stu-id="69354-114">Parent Elements</span></span>  
  
|<span data-ttu-id="69354-115">元素</span><span class="sxs-lookup"><span data-stu-id="69354-115">Element</span></span>|<span data-ttu-id="69354-116">描述</span><span class="sxs-lookup"><span data-stu-id="69354-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69354-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="69354-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="69354-118">包含的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="69354-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69354-119">备注</span><span class="sxs-lookup"><span data-stu-id="69354-119">Remarks</span></span>  
 <span data-ttu-id="69354-120">`clear`元素中清除所有`namedCache`内存缓存的命名的缓存集合中的条目。</span><span class="sxs-lookup"><span data-stu-id="69354-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="69354-121">可以使用`clear`元素在使用之前`add`要添加新命名的缓存条目，以确保没有其他元素名为集合中的缓存。</span><span class="sxs-lookup"><span data-stu-id="69354-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69354-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="69354-122">See also</span></span>

- [<span data-ttu-id="69354-123">\<namedCaches > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="69354-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
