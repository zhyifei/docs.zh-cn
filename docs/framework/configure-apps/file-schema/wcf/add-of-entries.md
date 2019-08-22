---
title: <add> 的 <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 3052a7570d1d93836603454817be921b37d26060
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658829"
---
# <a name="add-of-entries"></a><span data-ttu-id="290e5-102">\<添加\<条目 > ></span><span class="sxs-lookup"><span data-stu-id="290e5-102">\<add> of \<entries></span></span>
<span data-ttu-id="290e5-103">表示将筛选器映射到以前定义的客户端终结点的路由项。</span><span class="sxs-lookup"><span data-stu-id="290e5-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="290e5-104">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="290e5-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="290e5-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="290e5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="290e5-106">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="290e5-106">\<routing></span></span>  
<span data-ttu-id="290e5-107">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="290e5-107">\<filterTables></span></span>  
<span data-ttu-id="290e5-108">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="290e5-108">\<filterTable></span></span>  
<span data-ttu-id="290e5-109">\<条目 ></span><span class="sxs-lookup"><span data-stu-id="290e5-109">\<entries></span></span>  
<span data-ttu-id="290e5-110">\<add></span><span class="sxs-lookup"><span data-stu-id="290e5-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290e5-111">语法</span><span class="sxs-lookup"><span data-stu-id="290e5-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="290e5-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="290e5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="290e5-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="290e5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="290e5-114">特性</span><span class="sxs-lookup"><span data-stu-id="290e5-114">Attributes</span></span>  
  
|<span data-ttu-id="290e5-115">特性</span><span class="sxs-lookup"><span data-stu-id="290e5-115">Attribute</span></span>|<span data-ttu-id="290e5-116">描述</span><span class="sxs-lookup"><span data-stu-id="290e5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="290e5-117">backupList</span><span class="sxs-lookup"><span data-stu-id="290e5-117">backupList</span></span>|<span data-ttu-id="290e5-118">一个字符串，指定对终结点备份列表的引用。</span><span class="sxs-lookup"><span data-stu-id="290e5-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="290e5-119">端点</span><span class="sxs-lookup"><span data-stu-id="290e5-119">endpoint</span></span>|<span data-ttu-id="290e5-120">一个字符串，指定对客户端终结点的引用，该终结点将接收与 `filterName` 特性所指定的筛选器匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="290e5-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="290e5-121">filterName</span><span class="sxs-lookup"><span data-stu-id="290e5-121">filterName</span></span>|<span data-ttu-id="290e5-122">一个字符串，指定对筛选器元素的引用。</span><span class="sxs-lookup"><span data-stu-id="290e5-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="290e5-123">priority</span><span class="sxs-lookup"><span data-stu-id="290e5-123">priority</span></span>|<span data-ttu-id="290e5-124">一个整数，指定此项的优先级。</span><span class="sxs-lookup"><span data-stu-id="290e5-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="290e5-125">将根据优先级计算路由表中的项，0 表示优先级最低。</span><span class="sxs-lookup"><span data-stu-id="290e5-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="290e5-126">将同时计算某个特定优先级的所有项，如果未找到当前优先级的匹配项，将计算下一个优先级。</span><span class="sxs-lookup"><span data-stu-id="290e5-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="290e5-127">此值为可选值。</span><span class="sxs-lookup"><span data-stu-id="290e5-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="290e5-128">子元素</span><span class="sxs-lookup"><span data-stu-id="290e5-128">Child Elements</span></span>  
 <span data-ttu-id="290e5-129">无。</span><span class="sxs-lookup"><span data-stu-id="290e5-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="290e5-130">父元素</span><span class="sxs-lookup"><span data-stu-id="290e5-130">Parent Elements</span></span>  
  
|<span data-ttu-id="290e5-131">元素</span><span class="sxs-lookup"><span data-stu-id="290e5-131">Element</span></span>|<span data-ttu-id="290e5-132">描述</span><span class="sxs-lookup"><span data-stu-id="290e5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="290e5-133">\<routing></span><span class="sxs-lookup"><span data-stu-id="290e5-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="290e5-134">一个包含路由映射项的配置节。</span><span class="sxs-lookup"><span data-stu-id="290e5-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="290e5-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="290e5-135">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
