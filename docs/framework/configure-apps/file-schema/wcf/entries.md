---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 5561cf61cef2258ec61bd32770538add1c69f5c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201788"
---
# <a name="entries"></a><span data-ttu-id="12b94-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="12b94-101">\<entries></span></span>
<span data-ttu-id="12b94-102">一个路由项，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="12b94-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="12b94-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="12b94-103">\<system.serviceModel></span></span>  
<span data-ttu-id="12b94-104">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="12b94-104">\<routing></span></span>  
<span data-ttu-id="12b94-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="12b94-105">\<routingTables></span></span>  
<span data-ttu-id="12b94-106">\<table></span><span class="sxs-lookup"><span data-stu-id="12b94-106">\<table></span></span>  
<span data-ttu-id="12b94-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="12b94-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b94-108">语法</span><span class="sxs-lookup"><span data-stu-id="12b94-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12b94-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="12b94-109">Attributes and Elements</span></span>  
 <span data-ttu-id="12b94-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="12b94-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12b94-111">特性</span><span class="sxs-lookup"><span data-stu-id="12b94-111">Attributes</span></span>  
 <span data-ttu-id="12b94-112">无。</span><span class="sxs-lookup"><span data-stu-id="12b94-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12b94-113">子元素</span><span class="sxs-lookup"><span data-stu-id="12b94-113">Child Elements</span></span>  
  
|<span data-ttu-id="12b94-114">元素</span><span class="sxs-lookup"><span data-stu-id="12b94-114">Element</span></span>|<span data-ttu-id="12b94-115">描述</span><span class="sxs-lookup"><span data-stu-id="12b94-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12b94-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="12b94-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="12b94-117">将筛选器映射到以前定义的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="12b94-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="12b94-118">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="12b94-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12b94-119">父元素</span><span class="sxs-lookup"><span data-stu-id="12b94-119">Parent Elements</span></span>  
  
|<span data-ttu-id="12b94-120">元素</span><span class="sxs-lookup"><span data-stu-id="12b94-120">Element</span></span>|<span data-ttu-id="12b94-121">描述</span><span class="sxs-lookup"><span data-stu-id="12b94-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12b94-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="12b94-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="12b94-123">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="12b94-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12b94-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="12b94-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
