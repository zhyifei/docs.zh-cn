---
title: <add> 的 <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187079"
---
# <a name="add-of-scopes"></a><span data-ttu-id="8bc51-102">\<add> of \<scopes></span><span class="sxs-lookup"><span data-stu-id="8bc51-102">\<add> of \<scopes></span></span>
<span data-ttu-id="8bc51-103">添加可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="8bc51-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="8bc51-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8bc51-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8bc51-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8bc51-105">\<behaviors></span></span>  
<span data-ttu-id="8bc51-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8bc51-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8bc51-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8bc51-107">\<behavior></span></span>  
<span data-ttu-id="8bc51-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="8bc51-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="8bc51-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="8bc51-109">\<scopes></span></span>  
<span data-ttu-id="8bc51-110">\<add></span><span class="sxs-lookup"><span data-stu-id="8bc51-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc51-111">语法</span><span class="sxs-lookup"><span data-stu-id="8bc51-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bc51-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8bc51-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8bc51-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8bc51-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bc51-114">特性</span><span class="sxs-lookup"><span data-stu-id="8bc51-114">Attributes</span></span>  
  
|<span data-ttu-id="8bc51-115">特性</span><span class="sxs-lookup"><span data-stu-id="8bc51-115">Attribute</span></span>|<span data-ttu-id="8bc51-116">描述</span><span class="sxs-lookup"><span data-stu-id="8bc51-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bc51-117">范围</span><span class="sxs-lookup"><span data-stu-id="8bc51-117">scope</span></span>|<span data-ttu-id="8bc51-118">一个 URI，包含在匹配条件以查找服务时可使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="8bc51-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bc51-119">子元素</span><span class="sxs-lookup"><span data-stu-id="8bc51-119">Child Elements</span></span>  
 <span data-ttu-id="8bc51-120">无。</span><span class="sxs-lookup"><span data-stu-id="8bc51-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8bc51-121">父元素</span><span class="sxs-lookup"><span data-stu-id="8bc51-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8bc51-122">元素</span><span class="sxs-lookup"><span data-stu-id="8bc51-122">Element</span></span>|<span data-ttu-id="8bc51-123">描述</span><span class="sxs-lookup"><span data-stu-id="8bc51-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bc51-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="8bc51-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="8bc51-125">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="8bc51-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bc51-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bc51-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
