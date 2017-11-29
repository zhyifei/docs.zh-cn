---
title: "&lt;删除&gt;元素&lt;namedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6170b59e87948225708c9e697cba1542d756d2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="7fb8b-102">&lt;删除&gt;元素&lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="7fb8b-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="7fb8b-103">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="7fb8b-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="7fb8b-104">\<system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="7fb8b-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="7fb8b-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="7fb8b-105">\<memoryCache></span></span>  
<span data-ttu-id="7fb8b-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="7fb8b-106">\<namedCaches></span></span>  
<span data-ttu-id="7fb8b-107">\<删除 ></span><span class="sxs-lookup"><span data-stu-id="7fb8b-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb8b-108">语法</span><span class="sxs-lookup"><span data-stu-id="7fb8b-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="7fb8b-109">类型</span><span class="sxs-lookup"><span data-stu-id="7fb8b-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fb8b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7fb8b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7fb8b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7fb8b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fb8b-112">特性</span><span class="sxs-lookup"><span data-stu-id="7fb8b-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="7fb8b-113">子元素</span><span class="sxs-lookup"><span data-stu-id="7fb8b-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="7fb8b-114">父元素</span><span class="sxs-lookup"><span data-stu-id="7fb8b-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7fb8b-115">元素</span><span class="sxs-lookup"><span data-stu-id="7fb8b-115">Element</span></span>|<span data-ttu-id="7fb8b-116">描述</span><span class="sxs-lookup"><span data-stu-id="7fb8b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fb8b-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="7fb8b-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="7fb8b-118">包含的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="7fb8b-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fb8b-119">备注</span><span class="sxs-lookup"><span data-stu-id="7fb8b-119">Remarks</span></span>  
 <span data-ttu-id="7fb8b-120">`remove`元素中删除`namedCache`内存缓存的命名的缓存集合中的条目。</span><span class="sxs-lookup"><span data-stu-id="7fb8b-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb8b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fb8b-121">See Also</span></span>  
 [<span data-ttu-id="7fb8b-122">\<namedCaches > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="7fb8b-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
