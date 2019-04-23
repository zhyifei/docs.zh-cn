---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212097"
---
# <a name="baseaddresses"></a><span data-ttu-id="4c0be-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="4c0be-101">\<baseAddresses></span></span>
<span data-ttu-id="4c0be-102">表示一个 `baseAddress` 元素集合，这些元素是自承载环境中服务主机的基址。</span><span class="sxs-lookup"><span data-stu-id="4c0be-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="4c0be-103">如果存在基址，则可以使用相对于基址的地址配置终结点。</span><span class="sxs-lookup"><span data-stu-id="4c0be-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="4c0be-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4c0be-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4c0be-105">\<client></span><span class="sxs-lookup"><span data-stu-id="4c0be-105">\<client></span></span>  
<span data-ttu-id="4c0be-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="4c0be-106">\<endpoint></span></span>  
<span data-ttu-id="4c0be-107">\<host></span><span class="sxs-lookup"><span data-stu-id="4c0be-107">\<host></span></span>  
<span data-ttu-id="4c0be-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="4c0be-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c0be-109">语法</span><span class="sxs-lookup"><span data-stu-id="4c0be-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="4c0be-110">类型</span><span class="sxs-lookup"><span data-stu-id="4c0be-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c0be-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4c0be-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4c0be-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4c0be-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c0be-113">特性</span><span class="sxs-lookup"><span data-stu-id="4c0be-113">Attributes</span></span>  
 <span data-ttu-id="4c0be-114">无。</span><span class="sxs-lookup"><span data-stu-id="4c0be-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4c0be-115">子元素</span><span class="sxs-lookup"><span data-stu-id="4c0be-115">Child Elements</span></span>  
  
|<span data-ttu-id="4c0be-116">元素</span><span class="sxs-lookup"><span data-stu-id="4c0be-116">Element</span></span>|<span data-ttu-id="4c0be-117">描述</span><span class="sxs-lookup"><span data-stu-id="4c0be-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c0be-118">\<add></span><span class="sxs-lookup"><span data-stu-id="4c0be-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="4c0be-119">一个配置元素，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="4c0be-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c0be-120">父元素</span><span class="sxs-lookup"><span data-stu-id="4c0be-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4c0be-121">元素</span><span class="sxs-lookup"><span data-stu-id="4c0be-121">Element</span></span>|<span data-ttu-id="4c0be-122">描述</span><span class="sxs-lookup"><span data-stu-id="4c0be-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c0be-123">\<host></span><span class="sxs-lookup"><span data-stu-id="4c0be-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="4c0be-124">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="4c0be-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c0be-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c0be-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="4c0be-126">承载</span><span class="sxs-lookup"><span data-stu-id="4c0be-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
