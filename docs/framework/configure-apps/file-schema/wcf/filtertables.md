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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 028681acffcd93633807bdb1c6fa78aab98011c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="bc853-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="bc853-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="bc853-103">表示一个用于定义路由表的配置节，这些路由表包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="bc853-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="bc853-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bc853-104">\<system.serviceModel></span></span>  
<span data-ttu-id="bc853-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="bc853-105">\<routing></span></span>  
<span data-ttu-id="bc853-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="bc853-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc853-107">语法</span><span class="sxs-lookup"><span data-stu-id="bc853-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc853-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bc853-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bc853-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bc853-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc853-110">特性</span><span class="sxs-lookup"><span data-stu-id="bc853-110">Attributes</span></span>  
 <span data-ttu-id="bc853-111">无。</span><span class="sxs-lookup"><span data-stu-id="bc853-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bc853-112">子元素</span><span class="sxs-lookup"><span data-stu-id="bc853-112">Child Elements</span></span>  
  
|<span data-ttu-id="bc853-113">元素</span><span class="sxs-lookup"><span data-stu-id="bc853-113">Element</span></span>|<span data-ttu-id="bc853-114">描述</span><span class="sxs-lookup"><span data-stu-id="bc853-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc853-115">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="bc853-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="bc853-116">一个路由表，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="bc853-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc853-117">父元素</span><span class="sxs-lookup"><span data-stu-id="bc853-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bc853-118">元素</span><span class="sxs-lookup"><span data-stu-id="bc853-118">Element</span></span>|<span data-ttu-id="bc853-119">描述</span><span class="sxs-lookup"><span data-stu-id="bc853-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc853-120">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="bc853-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="bc853-121">一个包含路由筛选器和路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="bc853-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc853-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc853-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
