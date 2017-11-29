---
title: '&lt;filterTables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75e06b0258f2e4f65d441c25b5081cf7a6627518
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="5413e-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="5413e-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="5413e-103">表示一个用于定义路由表的配置节，这些路由表包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="5413e-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="5413e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="5413e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5413e-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="5413e-105">\<routing></span></span>  
<span data-ttu-id="5413e-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="5413e-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5413e-107">语法</span><span class="sxs-lookup"><span data-stu-id="5413e-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5413e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5413e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5413e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5413e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5413e-110">特性</span><span class="sxs-lookup"><span data-stu-id="5413e-110">Attributes</span></span>  
 <span data-ttu-id="5413e-111">无。</span><span class="sxs-lookup"><span data-stu-id="5413e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5413e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5413e-112">Child Elements</span></span>  
  
|<span data-ttu-id="5413e-113">元素</span><span class="sxs-lookup"><span data-stu-id="5413e-113">Element</span></span>|<span data-ttu-id="5413e-114">描述</span><span class="sxs-lookup"><span data-stu-id="5413e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5413e-115">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="5413e-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="5413e-116">一个路由表，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="5413e-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5413e-117">父元素</span><span class="sxs-lookup"><span data-stu-id="5413e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5413e-118">元素</span><span class="sxs-lookup"><span data-stu-id="5413e-118">Element</span></span>|<span data-ttu-id="5413e-119">描述</span><span class="sxs-lookup"><span data-stu-id="5413e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5413e-120">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="5413e-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="5413e-121">一个包含路由筛选器和路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="5413e-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5413e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5413e-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
