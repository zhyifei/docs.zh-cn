---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128422"
---
# <a name="discoveryclient"></a><span data-ttu-id="45a62-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="45a62-101">\<discoveryClient></span></span>
<span data-ttu-id="45a62-102">一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="45a62-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="45a62-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="45a62-103">\<system.serviceModel></span></span>  
<span data-ttu-id="45a62-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="45a62-104">\<bindings></span></span>  
<span data-ttu-id="45a62-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="45a62-105">\<customBinding></span></span>  
<span data-ttu-id="45a62-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="45a62-106">\<binding></span></span>  
<span data-ttu-id="45a62-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="45a62-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a62-108">语法</span><span class="sxs-lookup"><span data-stu-id="45a62-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45a62-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="45a62-109">Attributes and Elements</span></span>  
 <span data-ttu-id="45a62-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="45a62-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45a62-111">特性</span><span class="sxs-lookup"><span data-stu-id="45a62-111">Attributes</span></span>  
  
|<span data-ttu-id="45a62-112">特性</span><span class="sxs-lookup"><span data-stu-id="45a62-112">Attribute</span></span>|<span data-ttu-id="45a62-113">描述</span><span class="sxs-lookup"><span data-stu-id="45a62-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45a62-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="45a62-114">discoveryEndpoint</span></span>|<span data-ttu-id="45a62-115">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="45a62-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45a62-116">子元素</span><span class="sxs-lookup"><span data-stu-id="45a62-116">Child Elements</span></span>  
  
|<span data-ttu-id="45a62-117">元素</span><span class="sxs-lookup"><span data-stu-id="45a62-117">Element</span></span>|<span data-ttu-id="45a62-118">描述</span><span class="sxs-lookup"><span data-stu-id="45a62-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45a62-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="45a62-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="45a62-120">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="45a62-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="45a62-121">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续多久）。</span><span class="sxs-lookup"><span data-stu-id="45a62-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45a62-122">父元素</span><span class="sxs-lookup"><span data-stu-id="45a62-122">Parent Elements</span></span>  
  
|<span data-ttu-id="45a62-123">元素</span><span class="sxs-lookup"><span data-stu-id="45a62-123">Element</span></span>|<span data-ttu-id="45a62-124">描述</span><span class="sxs-lookup"><span data-stu-id="45a62-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45a62-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="45a62-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="45a62-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="45a62-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45a62-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="45a62-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
