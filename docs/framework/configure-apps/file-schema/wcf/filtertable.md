---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 4e5c7d56e35afe3001f4c70064adbfef7702c720
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673207"
---
# <a name="filtertable"></a><span data-ttu-id="284a5-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="284a5-101">\<filterTable></span></span>
<span data-ttu-id="284a5-102">表示包含要评估针对消息和将消息路由到客户端终结点，如果筛选器的计算结果为 true 的筛选器列表的路由表。</span><span class="sxs-lookup"><span data-stu-id="284a5-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="284a5-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="284a5-103">\<system.serviceModel></span></span>  
<span data-ttu-id="284a5-104">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="284a5-104">\<routing></span></span>  
<span data-ttu-id="284a5-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="284a5-105">\<routingTables></span></span>  
<span data-ttu-id="284a5-106">\<table></span><span class="sxs-lookup"><span data-stu-id="284a5-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="284a5-107">语法</span><span class="sxs-lookup"><span data-stu-id="284a5-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="284a5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="284a5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="284a5-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="284a5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="284a5-110">特性</span><span class="sxs-lookup"><span data-stu-id="284a5-110">Attributes</span></span>  
  
|<span data-ttu-id="284a5-111">元素</span><span class="sxs-lookup"><span data-stu-id="284a5-111">Element</span></span>|<span data-ttu-id="284a5-112">描述</span><span class="sxs-lookup"><span data-stu-id="284a5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="284a5-113">name</span><span class="sxs-lookup"><span data-stu-id="284a5-113">name</span></span>|<span data-ttu-id="284a5-114">一个字符串，包含此配置元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="284a5-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="284a5-115">子元素</span><span class="sxs-lookup"><span data-stu-id="284a5-115">Child Elements</span></span>  
  
|<span data-ttu-id="284a5-116">元素</span><span class="sxs-lookup"><span data-stu-id="284a5-116">Element</span></span>|<span data-ttu-id="284a5-117">描述</span><span class="sxs-lookup"><span data-stu-id="284a5-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="284a5-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="284a5-118">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="284a5-119">路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="284a5-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="284a5-120">父元素</span><span class="sxs-lookup"><span data-stu-id="284a5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="284a5-121">元素</span><span class="sxs-lookup"><span data-stu-id="284a5-121">Element</span></span>|<span data-ttu-id="284a5-122">描述</span><span class="sxs-lookup"><span data-stu-id="284a5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="284a5-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="284a5-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="284a5-124">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="284a5-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="284a5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="284a5-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
