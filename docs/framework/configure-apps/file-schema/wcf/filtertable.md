---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 83339eebef9a4f1b7f69e0bd1dd16b8278a68258
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534600"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="d1d3e-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="d1d3e-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="d1d3e-103">表示包含要评估针对消息和将消息路由到客户端终结点，如果筛选器的计算结果为 true 的筛选器列表的路由表。</span><span class="sxs-lookup"><span data-stu-id="d1d3e-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="d1d3e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d1d3e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d1d3e-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="d1d3e-105">\<routing></span></span>  
<span data-ttu-id="d1d3e-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="d1d3e-106">\<routingTables></span></span>  
<span data-ttu-id="d1d3e-107">\<table></span><span class="sxs-lookup"><span data-stu-id="d1d3e-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1d3e-108">语法</span><span class="sxs-lookup"><span data-stu-id="d1d3e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1d3e-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d1d3e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d1d3e-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d1d3e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1d3e-111">特性</span><span class="sxs-lookup"><span data-stu-id="d1d3e-111">Attributes</span></span>  
  
|<span data-ttu-id="d1d3e-112">元素</span><span class="sxs-lookup"><span data-stu-id="d1d3e-112">Element</span></span>|<span data-ttu-id="d1d3e-113">描述</span><span class="sxs-lookup"><span data-stu-id="d1d3e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1d3e-114">name</span><span class="sxs-lookup"><span data-stu-id="d1d3e-114">name</span></span>|<span data-ttu-id="d1d3e-115">一个字符串，包含此配置元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d1d3e-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1d3e-116">子元素</span><span class="sxs-lookup"><span data-stu-id="d1d3e-116">Child Elements</span></span>  
  
|<span data-ttu-id="d1d3e-117">元素</span><span class="sxs-lookup"><span data-stu-id="d1d3e-117">Element</span></span>|<span data-ttu-id="d1d3e-118">描述</span><span class="sxs-lookup"><span data-stu-id="d1d3e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1d3e-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="d1d3e-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="d1d3e-120">路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="d1d3e-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1d3e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="d1d3e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d1d3e-122">元素</span><span class="sxs-lookup"><span data-stu-id="d1d3e-122">Element</span></span>|<span data-ttu-id="d1d3e-123">描述</span><span class="sxs-lookup"><span data-stu-id="d1d3e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1d3e-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="d1d3e-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="d1d3e-125">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="d1d3e-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1d3e-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d3e-126">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
