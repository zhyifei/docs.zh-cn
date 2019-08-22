---
title: <namedCaches> 的 <remove> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663477"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="10560-102">\<删除 namedCaches > 的\<> 元素</span><span class="sxs-lookup"><span data-stu-id="10560-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="10560-103">从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="10560-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="10560-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="10560-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="10560-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="10560-105">\<memoryCache></span></span>  
<span data-ttu-id="10560-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="10560-106">\<namedCaches></span></span>  
<span data-ttu-id="10560-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="10560-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10560-108">语法</span><span class="sxs-lookup"><span data-stu-id="10560-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="10560-109">类型</span><span class="sxs-lookup"><span data-stu-id="10560-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10560-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="10560-110">Attributes and Elements</span></span>  
 <span data-ttu-id="10560-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10560-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10560-112">特性</span><span class="sxs-lookup"><span data-stu-id="10560-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="10560-113">子元素</span><span class="sxs-lookup"><span data-stu-id="10560-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="10560-114">父元素</span><span class="sxs-lookup"><span data-stu-id="10560-114">Parent Elements</span></span>  
  
|<span data-ttu-id="10560-115">元素</span><span class="sxs-lookup"><span data-stu-id="10560-115">Element</span></span>|<span data-ttu-id="10560-116">描述</span><span class="sxs-lookup"><span data-stu-id="10560-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10560-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="10560-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="10560-118">包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="10560-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10560-119">备注</span><span class="sxs-lookup"><span data-stu-id="10560-119">Remarks</span></span>  
 <span data-ttu-id="10560-120">元素从内存缓存`namedCache`的命名缓存集合中删除一个条目。 `remove`</span><span class="sxs-lookup"><span data-stu-id="10560-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10560-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="10560-121">See also</span></span>

- [<span data-ttu-id="10560-122">\<namedCaches > 元素 (缓存设置)</span><span class="sxs-lookup"><span data-stu-id="10560-122">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
