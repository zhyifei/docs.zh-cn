---
title: '&lt;discoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 5046d3342372960211942128372e9f62d98a2952
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573080"
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="aaf7a-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="aaf7a-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="aaf7a-103">一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="aaf7a-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="aaf7a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aaf7a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="aaf7a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="aaf7a-105">\<bindings></span></span>  
<span data-ttu-id="aaf7a-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="aaf7a-106">\<customBinding></span></span>  
<span data-ttu-id="aaf7a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="aaf7a-107">\<binding></span></span>  
<span data-ttu-id="aaf7a-108">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="aaf7a-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaf7a-109">语法</span><span class="sxs-lookup"><span data-stu-id="aaf7a-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaf7a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aaf7a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aaf7a-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="aaf7a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaf7a-112">特性</span><span class="sxs-lookup"><span data-stu-id="aaf7a-112">Attributes</span></span>  
  
|<span data-ttu-id="aaf7a-113">特性</span><span class="sxs-lookup"><span data-stu-id="aaf7a-113">Attribute</span></span>|<span data-ttu-id="aaf7a-114">描述</span><span class="sxs-lookup"><span data-stu-id="aaf7a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aaf7a-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="aaf7a-115">discoveryEndpoint</span></span>|<span data-ttu-id="aaf7a-116">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="aaf7a-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aaf7a-117">子元素</span><span class="sxs-lookup"><span data-stu-id="aaf7a-117">Child Elements</span></span>  
  
|<span data-ttu-id="aaf7a-118">元素</span><span class="sxs-lookup"><span data-stu-id="aaf7a-118">Element</span></span>|<span data-ttu-id="aaf7a-119">描述</span><span class="sxs-lookup"><span data-stu-id="aaf7a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaf7a-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="aaf7a-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="aaf7a-121">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="aaf7a-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="aaf7a-122">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续多久）。</span><span class="sxs-lookup"><span data-stu-id="aaf7a-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aaf7a-123">父元素</span><span class="sxs-lookup"><span data-stu-id="aaf7a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="aaf7a-124">元素</span><span class="sxs-lookup"><span data-stu-id="aaf7a-124">Element</span></span>|<span data-ttu-id="aaf7a-125">描述</span><span class="sxs-lookup"><span data-stu-id="aaf7a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaf7a-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="aaf7a-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="aaf7a-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="aaf7a-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aaf7a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="aaf7a-128">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
