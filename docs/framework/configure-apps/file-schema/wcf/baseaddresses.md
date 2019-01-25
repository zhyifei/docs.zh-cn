---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 34d400e74b24e9eb4140d1b43597b0217b23d80c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730121"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="6e749-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="6e749-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="6e749-103">表示一个 `baseAddress` 元素集合，这些元素是自承载环境中服务主机的基址。</span><span class="sxs-lookup"><span data-stu-id="6e749-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="6e749-104">如果存在基址，则可以使用相对于基址的地址配置终结点。</span><span class="sxs-lookup"><span data-stu-id="6e749-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="6e749-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6e749-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6e749-106">\<client></span><span class="sxs-lookup"><span data-stu-id="6e749-106">\<client></span></span>  
<span data-ttu-id="6e749-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="6e749-107">\<endpoint></span></span>  
<span data-ttu-id="6e749-108">\<host></span><span class="sxs-lookup"><span data-stu-id="6e749-108">\<host></span></span>  
<span data-ttu-id="6e749-109">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6e749-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e749-110">语法</span><span class="sxs-lookup"><span data-stu-id="6e749-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="6e749-111">类型</span><span class="sxs-lookup"><span data-stu-id="6e749-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e749-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6e749-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6e749-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6e749-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e749-114">特性</span><span class="sxs-lookup"><span data-stu-id="6e749-114">Attributes</span></span>  
 <span data-ttu-id="6e749-115">无。</span><span class="sxs-lookup"><span data-stu-id="6e749-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e749-116">子元素</span><span class="sxs-lookup"><span data-stu-id="6e749-116">Child Elements</span></span>  
  
|<span data-ttu-id="6e749-117">元素</span><span class="sxs-lookup"><span data-stu-id="6e749-117">Element</span></span>|<span data-ttu-id="6e749-118">描述</span><span class="sxs-lookup"><span data-stu-id="6e749-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e749-119">\<add></span><span class="sxs-lookup"><span data-stu-id="6e749-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="6e749-120">一个配置元素，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="6e749-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e749-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6e749-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6e749-122">元素</span><span class="sxs-lookup"><span data-stu-id="6e749-122">Element</span></span>|<span data-ttu-id="6e749-123">描述</span><span class="sxs-lookup"><span data-stu-id="6e749-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e749-124">\<host></span><span class="sxs-lookup"><span data-stu-id="6e749-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="6e749-125">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="6e749-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e749-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e749-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="6e749-127">承载</span><span class="sxs-lookup"><span data-stu-id="6e749-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
