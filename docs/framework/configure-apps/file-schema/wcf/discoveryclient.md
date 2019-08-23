---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: f9d7e3a4957d2a8f30724f0bfc04e58a57fc5f7d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919272"
---
# <a name="discoveryclient"></a><span data-ttu-id="82faa-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="82faa-101">\<discoveryClient></span></span>
<span data-ttu-id="82faa-102">一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="82faa-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="82faa-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="82faa-103">\<system.serviceModel></span></span>  
<span data-ttu-id="82faa-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="82faa-104">\<bindings></span></span>  
<span data-ttu-id="82faa-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="82faa-105">\<customBinding></span></span>  
<span data-ttu-id="82faa-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="82faa-106">\<binding></span></span>  
<span data-ttu-id="82faa-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="82faa-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82faa-108">语法</span><span class="sxs-lookup"><span data-stu-id="82faa-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82faa-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="82faa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="82faa-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="82faa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82faa-111">特性</span><span class="sxs-lookup"><span data-stu-id="82faa-111">Attributes</span></span>  
  
|<span data-ttu-id="82faa-112">特性</span><span class="sxs-lookup"><span data-stu-id="82faa-112">Attribute</span></span>|<span data-ttu-id="82faa-113">描述</span><span class="sxs-lookup"><span data-stu-id="82faa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82faa-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="82faa-114">discoveryEndpoint</span></span>|<span data-ttu-id="82faa-115">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="82faa-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82faa-116">子元素</span><span class="sxs-lookup"><span data-stu-id="82faa-116">Child Elements</span></span>  
  
|<span data-ttu-id="82faa-117">元素</span><span class="sxs-lookup"><span data-stu-id="82faa-117">Element</span></span>|<span data-ttu-id="82faa-118">描述</span><span class="sxs-lookup"><span data-stu-id="82faa-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82faa-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="82faa-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="82faa-120">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="82faa-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="82faa-121">可以将条件分组为搜索条件 (指定要查找的服务) 和查找终止条件 (搜索应持续的时间长度)。</span><span class="sxs-lookup"><span data-stu-id="82faa-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82faa-122">父元素</span><span class="sxs-lookup"><span data-stu-id="82faa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="82faa-123">元素</span><span class="sxs-lookup"><span data-stu-id="82faa-123">Element</span></span>|<span data-ttu-id="82faa-124">描述</span><span class="sxs-lookup"><span data-stu-id="82faa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82faa-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="82faa-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="82faa-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="82faa-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82faa-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="82faa-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
