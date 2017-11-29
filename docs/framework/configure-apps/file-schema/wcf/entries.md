---
title: "&lt;条目&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b6d8d1c3797d60b26443e07cc527ea8b86f526e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="22848-102">&lt;条目&gt;</span><span class="sxs-lookup"><span data-stu-id="22848-102">&lt;entries&gt;</span></span>
<span data-ttu-id="22848-103">一个路由项，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="22848-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="22848-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="22848-104">\<system.serviceModel></span></span>  
<span data-ttu-id="22848-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="22848-105">\<routing></span></span>  
<span data-ttu-id="22848-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="22848-106">\<routingTables></span></span>  
<span data-ttu-id="22848-107">\<表 ></span><span class="sxs-lookup"><span data-stu-id="22848-107">\<table></span></span>  
<span data-ttu-id="22848-108">\<条目 ></span><span class="sxs-lookup"><span data-stu-id="22848-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22848-109">语法</span><span class="sxs-lookup"><span data-stu-id="22848-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="22848-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="22848-110">Attributes and Elements</span></span>  
 <span data-ttu-id="22848-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="22848-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22848-112">特性</span><span class="sxs-lookup"><span data-stu-id="22848-112">Attributes</span></span>  
 <span data-ttu-id="22848-113">无。</span><span class="sxs-lookup"><span data-stu-id="22848-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22848-114">子元素</span><span class="sxs-lookup"><span data-stu-id="22848-114">Child Elements</span></span>  
  
|<span data-ttu-id="22848-115">元素</span><span class="sxs-lookup"><span data-stu-id="22848-115">Element</span></span>|<span data-ttu-id="22848-116">描述</span><span class="sxs-lookup"><span data-stu-id="22848-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22848-117">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="22848-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="22848-118">将筛选器映射到以前定义的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="22848-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="22848-119">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="22848-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22848-120">父元素</span><span class="sxs-lookup"><span data-stu-id="22848-120">Parent Elements</span></span>  
  
|<span data-ttu-id="22848-121">元素</span><span class="sxs-lookup"><span data-stu-id="22848-121">Element</span></span>|<span data-ttu-id="22848-122">描述</span><span class="sxs-lookup"><span data-stu-id="22848-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22848-123">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="22848-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="22848-124">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="22848-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22848-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22848-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
