---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399931"
---
# <a name="scopes"></a><span data-ttu-id="7d5bd-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="7d5bd-101">\<scopes></span></span>
<span data-ttu-id="7d5bd-102">包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。</span><span class="sxs-lookup"><span data-stu-id="7d5bd-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="7d5bd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d5bd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d5bd-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7d5bd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d5bd-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d5bd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7d5bd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d5bd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="7d5bd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d5bd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="7d5bd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointDiscovery >** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="7d5bd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="7d5bd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<范围 >**</span><span class="sxs-lookup"><span data-stu-id="7d5bd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5bd-110">语法</span><span class="sxs-lookup"><span data-stu-id="7d5bd-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d5bd-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7d5bd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7d5bd-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7d5bd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d5bd-113">特性</span><span class="sxs-lookup"><span data-stu-id="7d5bd-113">Attributes</span></span>  
 <span data-ttu-id="7d5bd-114">无。</span><span class="sxs-lookup"><span data-stu-id="7d5bd-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d5bd-115">子元素</span><span class="sxs-lookup"><span data-stu-id="7d5bd-115">Child Elements</span></span>  
  
|<span data-ttu-id="7d5bd-116">特性</span><span class="sxs-lookup"><span data-stu-id="7d5bd-116">Attribute</span></span>|<span data-ttu-id="7d5bd-117">描述</span><span class="sxs-lookup"><span data-stu-id="7d5bd-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7d5bd-118">\<add></span><span class="sxs-lookup"><span data-stu-id="7d5bd-118">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="7d5bd-119">添加可在匹配条件以查找服务时使用的终结点的范围信息。</span><span class="sxs-lookup"><span data-stu-id="7d5bd-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d5bd-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7d5bd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7d5bd-121">元素</span><span class="sxs-lookup"><span data-stu-id="7d5bd-121">Element</span></span>|<span data-ttu-id="7d5bd-122">描述</span><span class="sxs-lookup"><span data-stu-id="7d5bd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d5bd-123">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="7d5bd-123">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="7d5bd-124">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="7d5bd-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d5bd-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d5bd-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
