---
title: "&lt;entries&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d62236c604cd91c2dfe4b92cfaac4004fc18d439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="011bc-102">&lt;entries&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="011bc-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="011bc-103">表示将筛选器映射到以前定义的客户端终结点的路由项。</span><span class="sxs-lookup"><span data-stu-id="011bc-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="011bc-104">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="011bc-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="011bc-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="011bc-105">\<system.serviceModel></span></span>  
<span data-ttu-id="011bc-106">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="011bc-106">\<routing></span></span>  
<span data-ttu-id="011bc-107">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="011bc-107">\<routingTables></span></span>  
<span data-ttu-id="011bc-108">\<表 ></span><span class="sxs-lookup"><span data-stu-id="011bc-108">\<table></span></span>  
<span data-ttu-id="011bc-109">\<条目 ></span><span class="sxs-lookup"><span data-stu-id="011bc-109">\<entries></span></span>  
<span data-ttu-id="011bc-110">\<add></span><span class="sxs-lookup"><span data-stu-id="011bc-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="011bc-111">语法</span><span class="sxs-lookup"><span data-stu-id="011bc-111">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="011bc-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="011bc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="011bc-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="011bc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="011bc-114">特性</span><span class="sxs-lookup"><span data-stu-id="011bc-114">Attributes</span></span>  
  
|<span data-ttu-id="011bc-115">特性</span><span class="sxs-lookup"><span data-stu-id="011bc-115">Attribute</span></span>|<span data-ttu-id="011bc-116">描述</span><span class="sxs-lookup"><span data-stu-id="011bc-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="011bc-117">backupList</span><span class="sxs-lookup"><span data-stu-id="011bc-117">backupList</span></span>|<span data-ttu-id="011bc-118">一个字符串，指定对终结点备份列表的引用。</span><span class="sxs-lookup"><span data-stu-id="011bc-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="011bc-119">endpoint（终结点）</span><span class="sxs-lookup"><span data-stu-id="011bc-119">endpoint</span></span>|<span data-ttu-id="011bc-120">一个字符串，指定对客户端终结点的引用，该终结点将接收与 `filterName` 特性所指定的筛选器匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="011bc-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="011bc-121">filterName</span><span class="sxs-lookup"><span data-stu-id="011bc-121">filterName</span></span>|<span data-ttu-id="011bc-122">一个字符串，指定对筛选器元素的引用。</span><span class="sxs-lookup"><span data-stu-id="011bc-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="011bc-123">priority</span><span class="sxs-lookup"><span data-stu-id="011bc-123">priority</span></span>|<span data-ttu-id="011bc-124">一个整数，指定此项的优先级。</span><span class="sxs-lookup"><span data-stu-id="011bc-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="011bc-125">将根据优先级计算路由表中的项，0 表示优先级最低。</span><span class="sxs-lookup"><span data-stu-id="011bc-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="011bc-126">将同时计算某个特定优先级的所有项，如果未找到当前优先级的匹配项，将计算下一个优先级。</span><span class="sxs-lookup"><span data-stu-id="011bc-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="011bc-127">此值为可选值。</span><span class="sxs-lookup"><span data-stu-id="011bc-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="011bc-128">子元素</span><span class="sxs-lookup"><span data-stu-id="011bc-128">Child Elements</span></span>  
 <span data-ttu-id="011bc-129">无。</span><span class="sxs-lookup"><span data-stu-id="011bc-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="011bc-130">父元素</span><span class="sxs-lookup"><span data-stu-id="011bc-130">Parent Elements</span></span>  
  
|<span data-ttu-id="011bc-131">元素</span><span class="sxs-lookup"><span data-stu-id="011bc-131">Element</span></span>|<span data-ttu-id="011bc-132">描述</span><span class="sxs-lookup"><span data-stu-id="011bc-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="011bc-133">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="011bc-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="011bc-134">一个包含路由映射项的配置节。</span><span class="sxs-lookup"><span data-stu-id="011bc-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="011bc-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="011bc-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
