---
title: '&lt;DiscoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 9aef599ebf8068a383fd093b126a6bde1670b291
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151392"
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="24f4f-102">&lt;DiscoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="24f4f-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="24f4f-103">一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="24f4f-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="24f4f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="24f4f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="24f4f-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="24f4f-105">\<bindings></span></span>  
<span data-ttu-id="24f4f-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="24f4f-106">\<customBinding></span></span>  
<span data-ttu-id="24f4f-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="24f4f-107">\<binding></span></span>  
<span data-ttu-id="24f4f-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="24f4f-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f4f-109">语法</span><span class="sxs-lookup"><span data-stu-id="24f4f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24f4f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="24f4f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="24f4f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="24f4f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24f4f-112">特性</span><span class="sxs-lookup"><span data-stu-id="24f4f-112">Attributes</span></span>  
  
|<span data-ttu-id="24f4f-113">特性</span><span class="sxs-lookup"><span data-stu-id="24f4f-113">Attribute</span></span>|<span data-ttu-id="24f4f-114">描述</span><span class="sxs-lookup"><span data-stu-id="24f4f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24f4f-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="24f4f-115">discoveryEndpoint</span></span>|<span data-ttu-id="24f4f-116">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="24f4f-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24f4f-117">子元素</span><span class="sxs-lookup"><span data-stu-id="24f4f-117">Child Elements</span></span>  
  
|<span data-ttu-id="24f4f-118">元素</span><span class="sxs-lookup"><span data-stu-id="24f4f-118">Element</span></span>|<span data-ttu-id="24f4f-119">描述</span><span class="sxs-lookup"><span data-stu-id="24f4f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24f4f-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="24f4f-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="24f4f-121">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="24f4f-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="24f4f-122">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续多久）。</span><span class="sxs-lookup"><span data-stu-id="24f4f-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24f4f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="24f4f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="24f4f-124">元素</span><span class="sxs-lookup"><span data-stu-id="24f4f-124">Element</span></span>|<span data-ttu-id="24f4f-125">描述</span><span class="sxs-lookup"><span data-stu-id="24f4f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24f4f-126">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="24f4f-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="24f4f-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="24f4f-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24f4f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="24f4f-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
