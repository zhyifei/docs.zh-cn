---
title: '&lt;基址&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 8de962cc70e1399dd1e9459473055651f9aca5fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747481"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="3333e-102">&lt;基址&gt;</span><span class="sxs-lookup"><span data-stu-id="3333e-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="3333e-103">表示一个 `baseAddress` 元素集合，这些元素是自承载环境中服务主机的基址。</span><span class="sxs-lookup"><span data-stu-id="3333e-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="3333e-104">如果存在基址，则可以使用相对于基址的地址配置终结点。</span><span class="sxs-lookup"><span data-stu-id="3333e-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="3333e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3333e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3333e-106">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="3333e-106">\<client></span></span>  
<span data-ttu-id="3333e-107">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="3333e-107">\<endpoint></span></span>  
<span data-ttu-id="3333e-108">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="3333e-108">\<host></span></span>  
<span data-ttu-id="3333e-109">\<基址 ></span><span class="sxs-lookup"><span data-stu-id="3333e-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3333e-110">语法</span><span class="sxs-lookup"><span data-stu-id="3333e-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="3333e-111">类型</span><span class="sxs-lookup"><span data-stu-id="3333e-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3333e-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3333e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3333e-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3333e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3333e-114">特性</span><span class="sxs-lookup"><span data-stu-id="3333e-114">Attributes</span></span>  
 <span data-ttu-id="3333e-115">无。</span><span class="sxs-lookup"><span data-stu-id="3333e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3333e-116">子元素</span><span class="sxs-lookup"><span data-stu-id="3333e-116">Child Elements</span></span>  
  
|<span data-ttu-id="3333e-117">元素</span><span class="sxs-lookup"><span data-stu-id="3333e-117">Element</span></span>|<span data-ttu-id="3333e-118">描述</span><span class="sxs-lookup"><span data-stu-id="3333e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3333e-119">\<add></span><span class="sxs-lookup"><span data-stu-id="3333e-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="3333e-120">一个配置元素，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="3333e-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3333e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="3333e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3333e-122">元素</span><span class="sxs-lookup"><span data-stu-id="3333e-122">Element</span></span>|<span data-ttu-id="3333e-123">描述</span><span class="sxs-lookup"><span data-stu-id="3333e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3333e-124">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="3333e-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="3333e-125">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="3333e-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3333e-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3333e-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="3333e-127">承载</span><span class="sxs-lookup"><span data-stu-id="3333e-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
