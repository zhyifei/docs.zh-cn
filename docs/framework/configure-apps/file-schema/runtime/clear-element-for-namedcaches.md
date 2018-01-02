---
title: "&lt;清除&gt;元素&lt;namedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 501371346b3c1496122d93a98eb89dd4afc6bcd1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="a92da-102">&lt;清除&gt;元素&lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="a92da-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="a92da-103">清除所有`namedCache`中的条目`namedCaches`内存缓存的集合。</span><span class="sxs-lookup"><span data-stu-id="a92da-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="a92da-104">\<system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="a92da-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="a92da-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="a92da-105">\<memoryCache></span></span>  
<span data-ttu-id="a92da-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="a92da-106">\<namedCaches></span></span>  
<span data-ttu-id="a92da-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a92da-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a92da-108">语法</span><span class="sxs-lookup"><span data-stu-id="a92da-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="a92da-109">类型</span><span class="sxs-lookup"><span data-stu-id="a92da-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a92da-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a92da-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a92da-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a92da-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a92da-112">特性</span><span class="sxs-lookup"><span data-stu-id="a92da-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="a92da-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a92da-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="a92da-114">父元素</span><span class="sxs-lookup"><span data-stu-id="a92da-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a92da-115">元素</span><span class="sxs-lookup"><span data-stu-id="a92da-115">Element</span></span>|<span data-ttu-id="a92da-116">描述</span><span class="sxs-lookup"><span data-stu-id="a92da-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a92da-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="a92da-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="a92da-118">包含的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="a92da-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a92da-119">备注</span><span class="sxs-lookup"><span data-stu-id="a92da-119">Remarks</span></span>  
 <span data-ttu-id="a92da-120">`clear`元素清除所有`namedCache`内存缓存命名的缓存集合中的项。</span><span class="sxs-lookup"><span data-stu-id="a92da-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="a92da-121">你可以使用`clear`元素在使用之前`add`要添加新的命名的缓存条目，以确保没有其他元素名为集合中的缓存。</span><span class="sxs-lookup"><span data-stu-id="a92da-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a92da-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a92da-122">See Also</span></span>  
 [<span data-ttu-id="a92da-123">\<namedCaches > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="a92da-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
