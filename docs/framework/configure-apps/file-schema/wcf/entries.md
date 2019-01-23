---
title: '&lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 33f98cb4b138307622a14463ce5a3008058b6e31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587055"
---
# <a name="ltentriesgt"></a><span data-ttu-id="9febe-102">&lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="9febe-102">&lt;entries&gt;</span></span>
<span data-ttu-id="9febe-103">一个路由项，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="9febe-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="9febe-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9febe-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9febe-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="9febe-105">\<routing></span></span>  
<span data-ttu-id="9febe-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="9febe-106">\<routingTables></span></span>  
<span data-ttu-id="9febe-107">\<table></span><span class="sxs-lookup"><span data-stu-id="9febe-107">\<table></span></span>  
<span data-ttu-id="9febe-108">\<entries></span><span class="sxs-lookup"><span data-stu-id="9febe-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9febe-109">语法</span><span class="sxs-lookup"><span data-stu-id="9febe-109">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9febe-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9febe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9febe-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9febe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9febe-112">特性</span><span class="sxs-lookup"><span data-stu-id="9febe-112">Attributes</span></span>  
 <span data-ttu-id="9febe-113">无。</span><span class="sxs-lookup"><span data-stu-id="9febe-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9febe-114">子元素</span><span class="sxs-lookup"><span data-stu-id="9febe-114">Child Elements</span></span>  
  
|<span data-ttu-id="9febe-115">元素</span><span class="sxs-lookup"><span data-stu-id="9febe-115">Element</span></span>|<span data-ttu-id="9febe-116">描述</span><span class="sxs-lookup"><span data-stu-id="9febe-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9febe-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="9febe-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="9febe-118">将筛选器映射到以前定义的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="9febe-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="9febe-119">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="9febe-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9febe-120">父元素</span><span class="sxs-lookup"><span data-stu-id="9febe-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9febe-121">元素</span><span class="sxs-lookup"><span data-stu-id="9febe-121">Element</span></span>|<span data-ttu-id="9febe-122">描述</span><span class="sxs-lookup"><span data-stu-id="9febe-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9febe-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="9febe-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="9febe-124">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="9febe-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9febe-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="9febe-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
