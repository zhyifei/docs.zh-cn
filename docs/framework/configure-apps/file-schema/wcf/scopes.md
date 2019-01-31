---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: eee6382c578648866045fd9b283454d9e0e76fcb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275018"
---
# <a name="scopes"></a><span data-ttu-id="5b89f-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="5b89f-101">\<scopes></span></span>
<span data-ttu-id="5b89f-102">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="5b89f-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="5b89f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5b89f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b89f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5b89f-104">\<behaviors></span></span>  
<span data-ttu-id="5b89f-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5b89f-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="5b89f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5b89f-106">\<behavior></span></span>  
<span data-ttu-id="5b89f-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5b89f-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="5b89f-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="5b89f-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b89f-109">语法</span><span class="sxs-lookup"><span data-stu-id="5b89f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b89f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5b89f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5b89f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5b89f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b89f-112">特性</span><span class="sxs-lookup"><span data-stu-id="5b89f-112">Attributes</span></span>  
 <span data-ttu-id="5b89f-113">无。</span><span class="sxs-lookup"><span data-stu-id="5b89f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b89f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="5b89f-114">Child Elements</span></span>  
  
|<span data-ttu-id="5b89f-115">特性</span><span class="sxs-lookup"><span data-stu-id="5b89f-115">Attribute</span></span>|<span data-ttu-id="5b89f-116">描述</span><span class="sxs-lookup"><span data-stu-id="5b89f-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="5b89f-117">\<add></span><span class="sxs-lookup"><span data-stu-id="5b89f-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="5b89f-118">添加可在匹配条件以查找服务时使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="5b89f-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b89f-119">父元素</span><span class="sxs-lookup"><span data-stu-id="5b89f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5b89f-120">元素</span><span class="sxs-lookup"><span data-stu-id="5b89f-120">Element</span></span>|<span data-ttu-id="5b89f-121">描述</span><span class="sxs-lookup"><span data-stu-id="5b89f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b89f-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5b89f-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="5b89f-123">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="5b89f-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b89f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b89f-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
