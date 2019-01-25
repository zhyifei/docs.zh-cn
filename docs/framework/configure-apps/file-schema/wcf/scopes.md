---
title: '&lt;scopes&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 1235b483f63ab71405803c16f2d3c9926b15cfad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642982"
---
# <a name="ltscopesgt"></a><span data-ttu-id="5dd0a-102">&lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="5dd0a-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="5dd0a-103">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="5dd0a-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="5dd0a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5dd0a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5dd0a-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5dd0a-105">\<behaviors></span></span>  
<span data-ttu-id="5dd0a-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5dd0a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5dd0a-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5dd0a-107">\<behavior></span></span>  
<span data-ttu-id="5dd0a-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5dd0a-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="5dd0a-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="5dd0a-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd0a-110">语法</span><span class="sxs-lookup"><span data-stu-id="5dd0a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dd0a-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5dd0a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5dd0a-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5dd0a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dd0a-113">特性</span><span class="sxs-lookup"><span data-stu-id="5dd0a-113">Attributes</span></span>  
 <span data-ttu-id="5dd0a-114">无。</span><span class="sxs-lookup"><span data-stu-id="5dd0a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5dd0a-115">子元素</span><span class="sxs-lookup"><span data-stu-id="5dd0a-115">Child Elements</span></span>  
  
|<span data-ttu-id="5dd0a-116">特性</span><span class="sxs-lookup"><span data-stu-id="5dd0a-116">Attribute</span></span>|<span data-ttu-id="5dd0a-117">描述</span><span class="sxs-lookup"><span data-stu-id="5dd0a-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="5dd0a-118">\<add></span><span class="sxs-lookup"><span data-stu-id="5dd0a-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="5dd0a-119">添加可在匹配条件以查找服务时使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="5dd0a-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5dd0a-120">父元素</span><span class="sxs-lookup"><span data-stu-id="5dd0a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5dd0a-121">元素</span><span class="sxs-lookup"><span data-stu-id="5dd0a-121">Element</span></span>|<span data-ttu-id="5dd0a-122">描述</span><span class="sxs-lookup"><span data-stu-id="5dd0a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dd0a-123">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5dd0a-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="5dd0a-124">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="5dd0a-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5dd0a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5dd0a-125">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
