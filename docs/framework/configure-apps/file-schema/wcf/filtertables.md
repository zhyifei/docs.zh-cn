---
title: '&lt;filterTables&gt;'
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: 2b537619a276f32c50576561aea03b5fbbb58e7d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147780"
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="df5f0-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="df5f0-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="df5f0-103">表示一个用于定义路由表的配置节，这些路由表包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="df5f0-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="df5f0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="df5f0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="df5f0-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="df5f0-105">\<routing></span></span>  
<span data-ttu-id="df5f0-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="df5f0-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df5f0-107">语法</span><span class="sxs-lookup"><span data-stu-id="df5f0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df5f0-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="df5f0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="df5f0-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="df5f0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df5f0-110">特性</span><span class="sxs-lookup"><span data-stu-id="df5f0-110">Attributes</span></span>  
 <span data-ttu-id="df5f0-111">无。</span><span class="sxs-lookup"><span data-stu-id="df5f0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="df5f0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="df5f0-112">Child Elements</span></span>  
  
|<span data-ttu-id="df5f0-113">元素</span><span class="sxs-lookup"><span data-stu-id="df5f0-113">Element</span></span>|<span data-ttu-id="df5f0-114">描述</span><span class="sxs-lookup"><span data-stu-id="df5f0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df5f0-115">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="df5f0-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="df5f0-116">一个路由表，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="df5f0-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df5f0-117">父元素</span><span class="sxs-lookup"><span data-stu-id="df5f0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="df5f0-118">元素</span><span class="sxs-lookup"><span data-stu-id="df5f0-118">Element</span></span>|<span data-ttu-id="df5f0-119">描述</span><span class="sxs-lookup"><span data-stu-id="df5f0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df5f0-120">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="df5f0-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="df5f0-121">一个包含路由筛选器和路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="df5f0-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df5f0-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="df5f0-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
