---
title: '&lt;filterTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96425604fab8f70456ea1e0d97efb2c3bf843224
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="1c42e-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="1c42e-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="1c42e-103">表示包含要评估针对消息和消息路由到的客户端终结点，如果筛选器的计算结果为 true 的筛选器列表的路由表。</span><span class="sxs-lookup"><span data-stu-id="1c42e-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="1c42e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1c42e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1c42e-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="1c42e-105">\<routing></span></span>  
<span data-ttu-id="1c42e-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="1c42e-106">\<routingTables></span></span>  
<span data-ttu-id="1c42e-107">\<表 ></span><span class="sxs-lookup"><span data-stu-id="1c42e-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c42e-108">语法</span><span class="sxs-lookup"><span data-stu-id="1c42e-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1c42e-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c42e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c42e-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c42e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c42e-111">特性</span><span class="sxs-lookup"><span data-stu-id="1c42e-111">Attributes</span></span>  
  
|<span data-ttu-id="1c42e-112">元素</span><span class="sxs-lookup"><span data-stu-id="1c42e-112">Element</span></span>|<span data-ttu-id="1c42e-113">描述</span><span class="sxs-lookup"><span data-stu-id="1c42e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c42e-114">name</span><span class="sxs-lookup"><span data-stu-id="1c42e-114">name</span></span>|<span data-ttu-id="1c42e-115">一个字符串，包含此配置元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="1c42e-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c42e-116">子元素</span><span class="sxs-lookup"><span data-stu-id="1c42e-116">Child Elements</span></span>  
  
|<span data-ttu-id="1c42e-117">元素</span><span class="sxs-lookup"><span data-stu-id="1c42e-117">Element</span></span>|<span data-ttu-id="1c42e-118">描述</span><span class="sxs-lookup"><span data-stu-id="1c42e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c42e-119">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="1c42e-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="1c42e-120">路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="1c42e-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c42e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="1c42e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1c42e-122">元素</span><span class="sxs-lookup"><span data-stu-id="1c42e-122">Element</span></span>|<span data-ttu-id="1c42e-123">描述</span><span class="sxs-lookup"><span data-stu-id="1c42e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c42e-124">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="1c42e-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="1c42e-125">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="1c42e-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c42e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c42e-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
