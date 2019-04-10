---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 4e5c7d56e35afe3001f4c70064adbfef7702c720
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229272"
---
# <a name="filtertable"></a><span data-ttu-id="0c67b-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="0c67b-101">\<filterTable></span></span>
<span data-ttu-id="0c67b-102">表示包含要评估针对消息和将消息路由到客户端终结点，如果筛选器的计算结果为 true 的筛选器列表的路由表。</span><span class="sxs-lookup"><span data-stu-id="0c67b-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="0c67b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0c67b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0c67b-104">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="0c67b-104">\<routing></span></span>  
<span data-ttu-id="0c67b-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="0c67b-105">\<routingTables></span></span>  
<span data-ttu-id="0c67b-106">\<table></span><span class="sxs-lookup"><span data-stu-id="0c67b-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c67b-107">语法</span><span class="sxs-lookup"><span data-stu-id="0c67b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c67b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0c67b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0c67b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0c67b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c67b-110">特性</span><span class="sxs-lookup"><span data-stu-id="0c67b-110">Attributes</span></span>  
  
|<span data-ttu-id="0c67b-111">元素</span><span class="sxs-lookup"><span data-stu-id="0c67b-111">Element</span></span>|<span data-ttu-id="0c67b-112">描述</span><span class="sxs-lookup"><span data-stu-id="0c67b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c67b-113">name</span><span class="sxs-lookup"><span data-stu-id="0c67b-113">name</span></span>|<span data-ttu-id="0c67b-114">一个字符串，包含此配置元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="0c67b-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c67b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="0c67b-115">Child Elements</span></span>  
  
|<span data-ttu-id="0c67b-116">元素</span><span class="sxs-lookup"><span data-stu-id="0c67b-116">Element</span></span>|<span data-ttu-id="0c67b-117">描述</span><span class="sxs-lookup"><span data-stu-id="0c67b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c67b-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="0c67b-118">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="0c67b-119">路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="0c67b-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c67b-120">父元素</span><span class="sxs-lookup"><span data-stu-id="0c67b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0c67b-121">元素</span><span class="sxs-lookup"><span data-stu-id="0c67b-121">Element</span></span>|<span data-ttu-id="0c67b-122">描述</span><span class="sxs-lookup"><span data-stu-id="0c67b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c67b-123">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="0c67b-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="0c67b-124">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="0c67b-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c67b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c67b-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
