---
title: "&lt;作用域&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0a2309bb19b30f6927d5e9cd3047950936dff08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="a8dc9-102">&lt;作用域&gt;</span><span class="sxs-lookup"><span data-stu-id="a8dc9-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="a8dc9-103">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="a8dc9-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="a8dc9-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a8dc9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a8dc9-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="a8dc9-105">\<behaviors></span></span>  
<span data-ttu-id="a8dc9-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a8dc9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a8dc9-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="a8dc9-107">\<behavior></span></span>  
<span data-ttu-id="a8dc9-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="a8dc9-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="a8dc9-109">\<作用域 ></span><span class="sxs-lookup"><span data-stu-id="a8dc9-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8dc9-110">语法</span><span class="sxs-lookup"><span data-stu-id="a8dc9-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8dc9-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a8dc9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a8dc9-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a8dc9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8dc9-113">特性</span><span class="sxs-lookup"><span data-stu-id="a8dc9-113">Attributes</span></span>  
 <span data-ttu-id="a8dc9-114">无。</span><span class="sxs-lookup"><span data-stu-id="a8dc9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8dc9-115">子元素</span><span class="sxs-lookup"><span data-stu-id="a8dc9-115">Child Elements</span></span>  
  
|<span data-ttu-id="a8dc9-116">特性</span><span class="sxs-lookup"><span data-stu-id="a8dc9-116">Attribute</span></span>|<span data-ttu-id="a8dc9-117">描述</span><span class="sxs-lookup"><span data-stu-id="a8dc9-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a8dc9-118">\<add></span><span class="sxs-lookup"><span data-stu-id="a8dc9-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="a8dc9-119">添加可在匹配条件以查找服务时使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="a8dc9-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8dc9-120">父元素</span><span class="sxs-lookup"><span data-stu-id="a8dc9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a8dc9-121">元素</span><span class="sxs-lookup"><span data-stu-id="a8dc9-121">Element</span></span>|<span data-ttu-id="a8dc9-122">描述</span><span class="sxs-lookup"><span data-stu-id="a8dc9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8dc9-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="a8dc9-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="a8dc9-124">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="a8dc9-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8dc9-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8dc9-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
