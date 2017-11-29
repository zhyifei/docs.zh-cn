---
title: "&lt;scopes&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c720d99a5abee00eeb52f91586503e0a8a89027b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="e875f-102">&lt;scopes&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="e875f-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="e875f-103">添加可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="e875f-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="e875f-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e875f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e875f-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e875f-105">\<behaviors></span></span>  
<span data-ttu-id="e875f-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e875f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e875f-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e875f-107">\<behavior></span></span>  
<span data-ttu-id="e875f-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="e875f-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="e875f-109">\<作用域 ></span><span class="sxs-lookup"><span data-stu-id="e875f-109">\<scopes></span></span>  
<span data-ttu-id="e875f-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e875f-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e875f-111">语法</span><span class="sxs-lookup"><span data-stu-id="e875f-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e875f-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e875f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e875f-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e875f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e875f-114">特性</span><span class="sxs-lookup"><span data-stu-id="e875f-114">Attributes</span></span>  
  
|<span data-ttu-id="e875f-115">特性</span><span class="sxs-lookup"><span data-stu-id="e875f-115">Attribute</span></span>|<span data-ttu-id="e875f-116">描述</span><span class="sxs-lookup"><span data-stu-id="e875f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e875f-117">范围</span><span class="sxs-lookup"><span data-stu-id="e875f-117">scope</span></span>|<span data-ttu-id="e875f-118">一个 URI，包含在匹配条件以查找服务时可使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="e875f-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e875f-119">子元素</span><span class="sxs-lookup"><span data-stu-id="e875f-119">Child Elements</span></span>  
 <span data-ttu-id="e875f-120">无。</span><span class="sxs-lookup"><span data-stu-id="e875f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e875f-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e875f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e875f-122">元素</span><span class="sxs-lookup"><span data-stu-id="e875f-122">Element</span></span>|<span data-ttu-id="e875f-123">描述</span><span class="sxs-lookup"><span data-stu-id="e875f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e875f-124">\<作用域 ></span><span class="sxs-lookup"><span data-stu-id="e875f-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="e875f-125">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="e875f-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e875f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e875f-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
