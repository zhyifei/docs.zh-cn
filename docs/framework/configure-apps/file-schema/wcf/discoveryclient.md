---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 512a91bf25180606213eb9eb3b4f7c6a0cb4cbbf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366226"
---
# <a name="discoveryclient"></a><span data-ttu-id="f85cf-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="f85cf-101">\<discoveryClient></span></span>
<span data-ttu-id="f85cf-102">一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="f85cf-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="f85cf-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f85cf-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f85cf-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f85cf-104">\<bindings></span></span>  
<span data-ttu-id="f85cf-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f85cf-105">\<customBinding></span></span>  
<span data-ttu-id="f85cf-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f85cf-106">\<binding></span></span>  
<span data-ttu-id="f85cf-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="f85cf-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85cf-108">语法</span><span class="sxs-lookup"><span data-stu-id="f85cf-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f85cf-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f85cf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f85cf-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f85cf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f85cf-111">特性</span><span class="sxs-lookup"><span data-stu-id="f85cf-111">Attributes</span></span>  
  
|<span data-ttu-id="f85cf-112">特性</span><span class="sxs-lookup"><span data-stu-id="f85cf-112">Attribute</span></span>|<span data-ttu-id="f85cf-113">描述</span><span class="sxs-lookup"><span data-stu-id="f85cf-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f85cf-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="f85cf-114">discoveryEndpoint</span></span>|<span data-ttu-id="f85cf-115">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="f85cf-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f85cf-116">子元素</span><span class="sxs-lookup"><span data-stu-id="f85cf-116">Child Elements</span></span>  
  
|<span data-ttu-id="f85cf-117">元素</span><span class="sxs-lookup"><span data-stu-id="f85cf-117">Element</span></span>|<span data-ttu-id="f85cf-118">描述</span><span class="sxs-lookup"><span data-stu-id="f85cf-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f85cf-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="f85cf-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="f85cf-120">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="f85cf-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="f85cf-121">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续多久）。</span><span class="sxs-lookup"><span data-stu-id="f85cf-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f85cf-122">父元素</span><span class="sxs-lookup"><span data-stu-id="f85cf-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f85cf-123">元素</span><span class="sxs-lookup"><span data-stu-id="f85cf-123">Element</span></span>|<span data-ttu-id="f85cf-124">描述</span><span class="sxs-lookup"><span data-stu-id="f85cf-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f85cf-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="f85cf-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f85cf-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="f85cf-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f85cf-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="f85cf-127">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
