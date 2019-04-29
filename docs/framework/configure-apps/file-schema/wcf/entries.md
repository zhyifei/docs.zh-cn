---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 5561cf61cef2258ec61bd32770538add1c69f5c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704201"
---
# <a name="entries"></a><span data-ttu-id="7b8b2-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="7b8b2-101">\<entries></span></span>
<span data-ttu-id="7b8b2-102">一个路由项，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="7b8b2-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="7b8b2-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7b8b2-103">\<system.serviceModel></span></span>  
<span data-ttu-id="7b8b2-104">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="7b8b2-104">\<routing></span></span>  
<span data-ttu-id="7b8b2-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="7b8b2-105">\<routingTables></span></span>  
<span data-ttu-id="7b8b2-106">\<table></span><span class="sxs-lookup"><span data-stu-id="7b8b2-106">\<table></span></span>  
<span data-ttu-id="7b8b2-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="7b8b2-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8b2-108">语法</span><span class="sxs-lookup"><span data-stu-id="7b8b2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b8b2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7b8b2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7b8b2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7b8b2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b8b2-111">特性</span><span class="sxs-lookup"><span data-stu-id="7b8b2-111">Attributes</span></span>  
 <span data-ttu-id="7b8b2-112">无。</span><span class="sxs-lookup"><span data-stu-id="7b8b2-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7b8b2-113">子元素</span><span class="sxs-lookup"><span data-stu-id="7b8b2-113">Child Elements</span></span>  
  
|<span data-ttu-id="7b8b2-114">元素</span><span class="sxs-lookup"><span data-stu-id="7b8b2-114">Element</span></span>|<span data-ttu-id="7b8b2-115">描述</span><span class="sxs-lookup"><span data-stu-id="7b8b2-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b8b2-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="7b8b2-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="7b8b2-117">将筛选器映射到以前定义的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="7b8b2-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="7b8b2-118">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="7b8b2-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b8b2-119">父元素</span><span class="sxs-lookup"><span data-stu-id="7b8b2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7b8b2-120">元素</span><span class="sxs-lookup"><span data-stu-id="7b8b2-120">Element</span></span>|<span data-ttu-id="7b8b2-121">描述</span><span class="sxs-lookup"><span data-stu-id="7b8b2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b8b2-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="7b8b2-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="7b8b2-123">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="7b8b2-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b8b2-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b8b2-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
