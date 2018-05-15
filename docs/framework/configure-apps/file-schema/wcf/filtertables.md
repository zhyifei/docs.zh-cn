---
title: '&lt;filterTables&gt;'
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: 966556a1a8bde72e33640dcc6fd37ae7a044ceef
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="d7c81-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="d7c81-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="d7c81-103">表示一个用于定义路由表的配置节，这些路由表包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="d7c81-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="d7c81-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d7c81-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d7c81-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="d7c81-105">\<routing></span></span>  
<span data-ttu-id="d7c81-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="d7c81-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7c81-107">语法</span><span class="sxs-lookup"><span data-stu-id="d7c81-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d7c81-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d7c81-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d7c81-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d7c81-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7c81-110">特性</span><span class="sxs-lookup"><span data-stu-id="d7c81-110">Attributes</span></span>  
 <span data-ttu-id="d7c81-111">无。</span><span class="sxs-lookup"><span data-stu-id="d7c81-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d7c81-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d7c81-112">Child Elements</span></span>  
  
|<span data-ttu-id="d7c81-113">元素</span><span class="sxs-lookup"><span data-stu-id="d7c81-113">Element</span></span>|<span data-ttu-id="d7c81-114">描述</span><span class="sxs-lookup"><span data-stu-id="d7c81-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7c81-115">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="d7c81-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="d7c81-116">一个路由表，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="d7c81-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7c81-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d7c81-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d7c81-118">元素</span><span class="sxs-lookup"><span data-stu-id="d7c81-118">Element</span></span>|<span data-ttu-id="d7c81-119">描述</span><span class="sxs-lookup"><span data-stu-id="d7c81-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7c81-120">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="d7c81-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="d7c81-121">一个包含路由筛选器和路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="d7c81-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7c81-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7c81-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
