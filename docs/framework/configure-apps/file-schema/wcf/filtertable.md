---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f9e64e667befb70d617574b2a03c3e6bebb2a143
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925606"
---
# <a name="filtertable"></a><span data-ttu-id="cf893-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="cf893-101">\<filterTable></span></span>
<span data-ttu-id="cf893-102">表示一个路由表, 该表包含用于评估消息的筛选器的列表, 以及在筛选器计算结果为 true 时要将消息路由到的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="cf893-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="cf893-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cf893-103">\<system.serviceModel></span></span>  
<span data-ttu-id="cf893-104">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="cf893-104">\<routing></span></span>  
<span data-ttu-id="cf893-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="cf893-105">\<routingTables></span></span>  
<span data-ttu-id="cf893-106">\<表 ></span><span class="sxs-lookup"><span data-stu-id="cf893-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf893-107">语法</span><span class="sxs-lookup"><span data-stu-id="cf893-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf893-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cf893-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cf893-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cf893-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf893-110">特性</span><span class="sxs-lookup"><span data-stu-id="cf893-110">Attributes</span></span>  
  
|<span data-ttu-id="cf893-111">元素</span><span class="sxs-lookup"><span data-stu-id="cf893-111">Element</span></span>|<span data-ttu-id="cf893-112">描述</span><span class="sxs-lookup"><span data-stu-id="cf893-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cf893-113">NAME</span><span class="sxs-lookup"><span data-stu-id="cf893-113">name</span></span>|<span data-ttu-id="cf893-114">一个字符串，包含此配置元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="cf893-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf893-115">子元素</span><span class="sxs-lookup"><span data-stu-id="cf893-115">Child Elements</span></span>  
  
|<span data-ttu-id="cf893-116">元素</span><span class="sxs-lookup"><span data-stu-id="cf893-116">Element</span></span>|<span data-ttu-id="cf893-117">描述</span><span class="sxs-lookup"><span data-stu-id="cf893-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf893-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="cf893-118">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="cf893-119">路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="cf893-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf893-120">父元素</span><span class="sxs-lookup"><span data-stu-id="cf893-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cf893-121">元素</span><span class="sxs-lookup"><span data-stu-id="cf893-121">Element</span></span>|<span data-ttu-id="cf893-122">描述</span><span class="sxs-lookup"><span data-stu-id="cf893-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf893-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="cf893-123">\<routing></span></span>](routing.md)|<span data-ttu-id="cf893-124">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="cf893-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf893-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf893-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
