---
title: <remove> 的 <namedCaches> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 22d06ab1df0d5ed74073772302421a680f1665ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257014"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="1c423-102">\<删除 > 元素\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="1c423-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="1c423-103">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="1c423-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="1c423-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="1c423-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="1c423-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="1c423-105">\<memoryCache></span></span>  
<span data-ttu-id="1c423-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="1c423-106">\<namedCaches></span></span>  
<span data-ttu-id="1c423-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="1c423-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c423-108">语法</span><span class="sxs-lookup"><span data-stu-id="1c423-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="1c423-109">类型</span><span class="sxs-lookup"><span data-stu-id="1c423-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c423-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c423-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1c423-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c423-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c423-112">特性</span><span class="sxs-lookup"><span data-stu-id="1c423-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="1c423-113">子元素</span><span class="sxs-lookup"><span data-stu-id="1c423-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="1c423-114">父元素</span><span class="sxs-lookup"><span data-stu-id="1c423-114">Parent Elements</span></span>  
  
|<span data-ttu-id="1c423-115">元素</span><span class="sxs-lookup"><span data-stu-id="1c423-115">Element</span></span>|<span data-ttu-id="1c423-116">描述</span><span class="sxs-lookup"><span data-stu-id="1c423-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c423-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="1c423-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="1c423-118">包含的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。</span><span class="sxs-lookup"><span data-stu-id="1c423-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c423-119">备注</span><span class="sxs-lookup"><span data-stu-id="1c423-119">Remarks</span></span>  
 <span data-ttu-id="1c423-120">`remove`元素中移除`namedCache`内存缓存的命名的缓存集合中的条目。</span><span class="sxs-lookup"><span data-stu-id="1c423-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c423-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c423-121">See also</span></span>
- [<span data-ttu-id="1c423-122">\<namedCaches > 元素 （缓存设置）</span><span class="sxs-lookup"><span data-stu-id="1c423-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
