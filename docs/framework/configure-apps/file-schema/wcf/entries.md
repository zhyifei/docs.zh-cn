---
title: '&lt;条目&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: b9cc7f7736ffefaca68a0f197bd064a99c4dca9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746704"
---
# <a name="ltentriesgt"></a><span data-ttu-id="f3779-102">&lt;条目&gt;</span><span class="sxs-lookup"><span data-stu-id="f3779-102">&lt;entries&gt;</span></span>
<span data-ttu-id="f3779-103">一个路由项，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="f3779-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="f3779-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f3779-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f3779-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="f3779-105">\<routing></span></span>  
<span data-ttu-id="f3779-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="f3779-106">\<routingTables></span></span>  
<span data-ttu-id="f3779-107">\<表 ></span><span class="sxs-lookup"><span data-stu-id="f3779-107">\<table></span></span>  
<span data-ttu-id="f3779-108">\<条目 ></span><span class="sxs-lookup"><span data-stu-id="f3779-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3779-109">语法</span><span class="sxs-lookup"><span data-stu-id="f3779-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f3779-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f3779-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f3779-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f3779-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3779-112">特性</span><span class="sxs-lookup"><span data-stu-id="f3779-112">Attributes</span></span>  
 <span data-ttu-id="f3779-113">无。</span><span class="sxs-lookup"><span data-stu-id="f3779-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f3779-114">子元素</span><span class="sxs-lookup"><span data-stu-id="f3779-114">Child Elements</span></span>  
  
|<span data-ttu-id="f3779-115">元素</span><span class="sxs-lookup"><span data-stu-id="f3779-115">Element</span></span>|<span data-ttu-id="f3779-116">描述</span><span class="sxs-lookup"><span data-stu-id="f3779-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3779-117">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="f3779-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="f3779-118">将筛选器映射到以前定义的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="f3779-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="f3779-119">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="f3779-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3779-120">父元素</span><span class="sxs-lookup"><span data-stu-id="f3779-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f3779-121">元素</span><span class="sxs-lookup"><span data-stu-id="f3779-121">Element</span></span>|<span data-ttu-id="f3779-122">描述</span><span class="sxs-lookup"><span data-stu-id="f3779-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3779-123">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="f3779-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="f3779-124">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="f3779-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3779-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3779-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
