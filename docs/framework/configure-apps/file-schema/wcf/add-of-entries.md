---
title: <add> 的 <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850506"
---
# <a name="add-of-entries"></a><span data-ttu-id="429d1-102">\<添加\<条目 > ></span><span class="sxs-lookup"><span data-stu-id="429d1-102">\<add> of \<entries></span></span>
<span data-ttu-id="429d1-103">表示将筛选器映射到以前定义的客户端终结点的路由项。</span><span class="sxs-lookup"><span data-stu-id="429d1-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="429d1-104">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="429d1-104">Messages matching this filter will be sent to this destination.</span></span>  
  
<span data-ttu-id="429d1-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="429d1-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="429d1-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="429d1-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="429d1-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="429d1-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="429d1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="429d1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="429d1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTable >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="429d1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="429d1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<条目 >** ](entries.md)</span><span class="sxs-lookup"><span data-stu-id="429d1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)</span></span>\
<span data-ttu-id="429d1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="429d1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="429d1-112">语法</span><span class="sxs-lookup"><span data-stu-id="429d1-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="429d1-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="429d1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="429d1-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="429d1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="429d1-115">特性</span><span class="sxs-lookup"><span data-stu-id="429d1-115">Attributes</span></span>  
  
|<span data-ttu-id="429d1-116">特性</span><span class="sxs-lookup"><span data-stu-id="429d1-116">Attribute</span></span>|<span data-ttu-id="429d1-117">描述</span><span class="sxs-lookup"><span data-stu-id="429d1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="429d1-118">backupList</span><span class="sxs-lookup"><span data-stu-id="429d1-118">backupList</span></span>|<span data-ttu-id="429d1-119">一个字符串，指定对终结点备份列表的引用。</span><span class="sxs-lookup"><span data-stu-id="429d1-119">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="429d1-120">端点</span><span class="sxs-lookup"><span data-stu-id="429d1-120">endpoint</span></span>|<span data-ttu-id="429d1-121">一个字符串，指定对客户端终结点的引用，该终结点将接收与 `filterName` 特性所指定的筛选器匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="429d1-121">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="429d1-122">filterName</span><span class="sxs-lookup"><span data-stu-id="429d1-122">filterName</span></span>|<span data-ttu-id="429d1-123">一个字符串，指定对筛选器元素的引用。</span><span class="sxs-lookup"><span data-stu-id="429d1-123">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="429d1-124">priority</span><span class="sxs-lookup"><span data-stu-id="429d1-124">priority</span></span>|<span data-ttu-id="429d1-125">一个整数，指定此项的优先级。</span><span class="sxs-lookup"><span data-stu-id="429d1-125">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="429d1-126">将根据优先级计算路由表中的项，0 表示优先级最低。</span><span class="sxs-lookup"><span data-stu-id="429d1-126">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="429d1-127">将同时计算某个特定优先级的所有项，如果未找到当前优先级的匹配项，将计算下一个优先级。</span><span class="sxs-lookup"><span data-stu-id="429d1-127">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="429d1-128">此值为可选值。</span><span class="sxs-lookup"><span data-stu-id="429d1-128">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="429d1-129">子元素</span><span class="sxs-lookup"><span data-stu-id="429d1-129">Child Elements</span></span>  
 <span data-ttu-id="429d1-130">无。</span><span class="sxs-lookup"><span data-stu-id="429d1-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="429d1-131">父元素</span><span class="sxs-lookup"><span data-stu-id="429d1-131">Parent Elements</span></span>  
  
|<span data-ttu-id="429d1-132">元素</span><span class="sxs-lookup"><span data-stu-id="429d1-132">Element</span></span>|<span data-ttu-id="429d1-133">描述</span><span class="sxs-lookup"><span data-stu-id="429d1-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="429d1-134">\<routing></span><span class="sxs-lookup"><span data-stu-id="429d1-134">\<routing></span></span>](routing.md)|<span data-ttu-id="429d1-135">一个包含路由映射项的配置节。</span><span class="sxs-lookup"><span data-stu-id="429d1-135">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="429d1-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="429d1-136">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
