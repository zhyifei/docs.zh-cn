---
title: '&lt;discoveryClient&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c9cbdb61152a5315aaf919e3a3c58d9329449e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="59ad3-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="59ad3-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="59ad3-103">一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="59ad3-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="59ad3-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="59ad3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="59ad3-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="59ad3-105">\<bindings></span></span>  
<span data-ttu-id="59ad3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="59ad3-106">\<customBinding></span></span>  
<span data-ttu-id="59ad3-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="59ad3-107">\<binding></span></span>  
<span data-ttu-id="59ad3-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="59ad3-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ad3-109">语法</span><span class="sxs-lookup"><span data-stu-id="59ad3-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String" >
  <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String" namespace="String" />
    <contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59ad3-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59ad3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59ad3-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59ad3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59ad3-112">特性</span><span class="sxs-lookup"><span data-stu-id="59ad3-112">Attributes</span></span>  
  
|<span data-ttu-id="59ad3-113">特性</span><span class="sxs-lookup"><span data-stu-id="59ad3-113">Attribute</span></span>|<span data-ttu-id="59ad3-114">描述</span><span class="sxs-lookup"><span data-stu-id="59ad3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59ad3-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="59ad3-115">discoveryEndpoint</span></span>|<span data-ttu-id="59ad3-116">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="59ad3-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59ad3-117">子元素</span><span class="sxs-lookup"><span data-stu-id="59ad3-117">Child Elements</span></span>  
  
|<span data-ttu-id="59ad3-118">元素</span><span class="sxs-lookup"><span data-stu-id="59ad3-118">Element</span></span>|<span data-ttu-id="59ad3-119">描述</span><span class="sxs-lookup"><span data-stu-id="59ad3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59ad3-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="59ad3-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="59ad3-121">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="59ad3-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="59ad3-122">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续的时长）。</span><span class="sxs-lookup"><span data-stu-id="59ad3-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59ad3-123">父元素</span><span class="sxs-lookup"><span data-stu-id="59ad3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="59ad3-124">元素</span><span class="sxs-lookup"><span data-stu-id="59ad3-124">Element</span></span>|<span data-ttu-id="59ad3-125">描述</span><span class="sxs-lookup"><span data-stu-id="59ad3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59ad3-126">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="59ad3-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="59ad3-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="59ad3-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59ad3-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="59ad3-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
