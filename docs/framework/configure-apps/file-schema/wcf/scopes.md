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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b35696cbecb0badf397d6d48e7c97aae3d0232e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="7792e-102">&lt;作用域&gt;</span><span class="sxs-lookup"><span data-stu-id="7792e-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="7792e-103">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="7792e-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="7792e-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7792e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7792e-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="7792e-105">\<behaviors></span></span>  
<span data-ttu-id="7792e-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7792e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7792e-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="7792e-107">\<behavior></span></span>  
<span data-ttu-id="7792e-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="7792e-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="7792e-109">\<作用域 ></span><span class="sxs-lookup"><span data-stu-id="7792e-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7792e-110">语法</span><span class="sxs-lookup"><span data-stu-id="7792e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7792e-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7792e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7792e-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7792e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7792e-113">特性</span><span class="sxs-lookup"><span data-stu-id="7792e-113">Attributes</span></span>  
 <span data-ttu-id="7792e-114">无。</span><span class="sxs-lookup"><span data-stu-id="7792e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7792e-115">子元素</span><span class="sxs-lookup"><span data-stu-id="7792e-115">Child Elements</span></span>  
  
|<span data-ttu-id="7792e-116">特性</span><span class="sxs-lookup"><span data-stu-id="7792e-116">Attribute</span></span>|<span data-ttu-id="7792e-117">描述</span><span class="sxs-lookup"><span data-stu-id="7792e-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7792e-118">\<add></span><span class="sxs-lookup"><span data-stu-id="7792e-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="7792e-119">添加可在匹配条件以查找服务时使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="7792e-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7792e-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7792e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7792e-121">元素</span><span class="sxs-lookup"><span data-stu-id="7792e-121">Element</span></span>|<span data-ttu-id="7792e-122">描述</span><span class="sxs-lookup"><span data-stu-id="7792e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7792e-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="7792e-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="7792e-124">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="7792e-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7792e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7792e-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
