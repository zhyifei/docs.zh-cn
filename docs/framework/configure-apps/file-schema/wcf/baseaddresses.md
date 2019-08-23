---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 059ea4e637ab906d1fde9807a73ac8341f81c574
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926422"
---
# <a name="baseaddresses"></a><span data-ttu-id="39bfb-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="39bfb-101">\<baseAddresses></span></span>
<span data-ttu-id="39bfb-102">表示一个 `baseAddress` 元素集合，这些元素是自承载环境中服务主机的基址。</span><span class="sxs-lookup"><span data-stu-id="39bfb-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="39bfb-103">如果存在基址，则可以使用相对于基址的地址配置终结点。</span><span class="sxs-lookup"><span data-stu-id="39bfb-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="39bfb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="39bfb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="39bfb-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="39bfb-105">\<client></span></span>  
<span data-ttu-id="39bfb-106">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="39bfb-106">\<endpoint></span></span>  
<span data-ttu-id="39bfb-107">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="39bfb-107">\<host></span></span>  
<span data-ttu-id="39bfb-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="39bfb-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bfb-109">语法</span><span class="sxs-lookup"><span data-stu-id="39bfb-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="39bfb-110">类型</span><span class="sxs-lookup"><span data-stu-id="39bfb-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39bfb-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="39bfb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="39bfb-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="39bfb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39bfb-113">特性</span><span class="sxs-lookup"><span data-stu-id="39bfb-113">Attributes</span></span>  
 <span data-ttu-id="39bfb-114">无。</span><span class="sxs-lookup"><span data-stu-id="39bfb-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39bfb-115">子元素</span><span class="sxs-lookup"><span data-stu-id="39bfb-115">Child Elements</span></span>  
  
|<span data-ttu-id="39bfb-116">元素</span><span class="sxs-lookup"><span data-stu-id="39bfb-116">Element</span></span>|<span data-ttu-id="39bfb-117">描述</span><span class="sxs-lookup"><span data-stu-id="39bfb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39bfb-118">\<add></span><span class="sxs-lookup"><span data-stu-id="39bfb-118">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="39bfb-119">一个配置元素，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="39bfb-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39bfb-120">父元素</span><span class="sxs-lookup"><span data-stu-id="39bfb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="39bfb-121">元素</span><span class="sxs-lookup"><span data-stu-id="39bfb-121">Element</span></span>|<span data-ttu-id="39bfb-122">描述</span><span class="sxs-lookup"><span data-stu-id="39bfb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39bfb-123">\<host></span><span class="sxs-lookup"><span data-stu-id="39bfb-123">\<host></span></span>](host.md)|<span data-ttu-id="39bfb-124">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="39bfb-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39bfb-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="39bfb-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="39bfb-126">承载</span><span class="sxs-lookup"><span data-stu-id="39bfb-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
