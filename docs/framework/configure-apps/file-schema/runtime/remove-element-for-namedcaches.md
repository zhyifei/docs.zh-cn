---
title: '&lt;删除&gt;元素&lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7e183a624b95e207d34697c906cc3f278c967ae9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499758"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="a6f72-102">&lt;删除&gt;元素&lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="a6f72-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="a6f72-103">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="a6f72-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="a6f72-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="a6f72-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="a6f72-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="a6f72-105">\<memoryCache></span></span>  
<span data-ttu-id="a6f72-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="a6f72-106">\<namedCaches></span></span>  
<span data-ttu-id="a6f72-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="a6f72-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f72-108">语法</span><span class="sxs-lookup"><span data-stu-id="a6f72-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="a6f72-109">类型</span><span class="sxs-lookup"><span data-stu-id="a6f72-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6f72-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a6f72-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a6f72-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a6f72-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6f72-112">特性</span><span class="sxs-lookup"><span data-stu-id="a6f72-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="a6f72-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a6f72-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="a6f72-114">父元素</span><span class="sxs-lookup"><span data-stu-id="a6f72-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a6f72-115">元素</span><span class="sxs-lookup"><span data-stu-id="a6f72-115">Element</span></span>|<span data-ttu-id="a6f72-116">描述</span><span class="sxs-lookup"><span data-stu-id="a6f72-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6f72-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="a6f72-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="a6f72-118">包含的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="a6f72-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6f72-119">备注</span><span class="sxs-lookup"><span data-stu-id="a6f72-119">Remarks</span></span>  
 <span data-ttu-id="a6f72-120">`remove`元素中移除`namedCache`内存缓存的命名的缓存集合中的条目。</span><span class="sxs-lookup"><span data-stu-id="a6f72-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f72-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f72-121">See also</span></span>
- [<span data-ttu-id="a6f72-122">\<namedCaches > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="a6f72-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
