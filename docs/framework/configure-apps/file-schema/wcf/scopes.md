---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213072"
---
# <a name="scopes"></a><span data-ttu-id="ab5b3-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="ab5b3-101">\<scopes></span></span>
<span data-ttu-id="ab5b3-102">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="ab5b3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ab5b3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ab5b3-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ab5b3-104">\<behaviors></span></span>  
<span data-ttu-id="ab5b3-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ab5b3-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="ab5b3-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ab5b3-106">\<behavior></span></span>  
<span data-ttu-id="ab5b3-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="ab5b3-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="ab5b3-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="ab5b3-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab5b3-109">语法</span><span class="sxs-lookup"><span data-stu-id="ab5b3-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab5b3-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ab5b3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ab5b3-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab5b3-112">特性</span><span class="sxs-lookup"><span data-stu-id="ab5b3-112">Attributes</span></span>  
 <span data-ttu-id="ab5b3-113">无。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ab5b3-114">子元素</span><span class="sxs-lookup"><span data-stu-id="ab5b3-114">Child Elements</span></span>  
  
|<span data-ttu-id="ab5b3-115">特性</span><span class="sxs-lookup"><span data-stu-id="ab5b3-115">Attribute</span></span>|<span data-ttu-id="ab5b3-116">描述</span><span class="sxs-lookup"><span data-stu-id="ab5b3-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ab5b3-117">\<add></span><span class="sxs-lookup"><span data-stu-id="ab5b3-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="ab5b3-118">添加可在匹配条件以查找服务时使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ab5b3-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ab5b3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ab5b3-120">元素</span><span class="sxs-lookup"><span data-stu-id="ab5b3-120">Element</span></span>|<span data-ttu-id="ab5b3-121">描述</span><span class="sxs-lookup"><span data-stu-id="ab5b3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab5b3-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="ab5b3-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="ab5b3-123">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab5b3-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab5b3-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
