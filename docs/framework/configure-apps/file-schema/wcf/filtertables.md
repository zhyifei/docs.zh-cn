---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c49c7cf3a196595556c2bf1b4ed4365bfe1e4cbf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075725"
---
# <a name="filtertables"></a><span data-ttu-id="28897-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="28897-101">\<filterTables></span></span>
<span data-ttu-id="28897-102">表示一个用于定义路由表的配置节，这些路由表包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="28897-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="28897-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="28897-103">\<system.serviceModel></span></span>  
<span data-ttu-id="28897-104">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="28897-104">\<routing></span></span>  
<span data-ttu-id="28897-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="28897-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28897-106">语法</span><span class="sxs-lookup"><span data-stu-id="28897-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28897-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28897-107">Attributes and Elements</span></span>  
 <span data-ttu-id="28897-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28897-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28897-109">特性</span><span class="sxs-lookup"><span data-stu-id="28897-109">Attributes</span></span>  
 <span data-ttu-id="28897-110">无。</span><span class="sxs-lookup"><span data-stu-id="28897-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28897-111">子元素</span><span class="sxs-lookup"><span data-stu-id="28897-111">Child Elements</span></span>  
  
|<span data-ttu-id="28897-112">元素</span><span class="sxs-lookup"><span data-stu-id="28897-112">Element</span></span>|<span data-ttu-id="28897-113">描述</span><span class="sxs-lookup"><span data-stu-id="28897-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28897-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="28897-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="28897-115">一个路由表，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="28897-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28897-116">父元素</span><span class="sxs-lookup"><span data-stu-id="28897-116">Parent Elements</span></span>  
  
|<span data-ttu-id="28897-117">元素</span><span class="sxs-lookup"><span data-stu-id="28897-117">Element</span></span>|<span data-ttu-id="28897-118">描述</span><span class="sxs-lookup"><span data-stu-id="28897-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28897-119">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="28897-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="28897-120">一个包含路由筛选器和路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="28897-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28897-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="28897-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
