---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739036"
---
# <a name="discoveryclient"></a><span data-ttu-id="78798-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="78798-101">\<discoveryClient></span></span>
<span data-ttu-id="78798-102">一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="78798-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="78798-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78798-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="78798-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="78798-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="78798-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="78798-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="78798-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="78798-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="78798-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="78798-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="78798-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryClient >**</span><span class="sxs-lookup"><span data-stu-id="78798-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78798-109">语法</span><span class="sxs-lookup"><span data-stu-id="78798-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78798-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="78798-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78798-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="78798-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78798-112">特性</span><span class="sxs-lookup"><span data-stu-id="78798-112">Attributes</span></span>  
  
|<span data-ttu-id="78798-113">特性</span><span class="sxs-lookup"><span data-stu-id="78798-113">Attribute</span></span>|<span data-ttu-id="78798-114">描述</span><span class="sxs-lookup"><span data-stu-id="78798-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78798-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="78798-115">discoveryEndpoint</span></span>|<span data-ttu-id="78798-116">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="78798-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78798-117">子元素</span><span class="sxs-lookup"><span data-stu-id="78798-117">Child Elements</span></span>  
  
|<span data-ttu-id="78798-118">元素</span><span class="sxs-lookup"><span data-stu-id="78798-118">Element</span></span>|<span data-ttu-id="78798-119">描述</span><span class="sxs-lookup"><span data-stu-id="78798-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78798-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="78798-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="78798-121">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="78798-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="78798-122">可以将条件分组为搜索条件（指定要查找的服务）和查找终止条件（搜索应持续的时间长度）。</span><span class="sxs-lookup"><span data-stu-id="78798-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78798-123">父元素</span><span class="sxs-lookup"><span data-stu-id="78798-123">Parent Elements</span></span>  
  
|<span data-ttu-id="78798-124">元素</span><span class="sxs-lookup"><span data-stu-id="78798-124">Element</span></span>|<span data-ttu-id="78798-125">描述</span><span class="sxs-lookup"><span data-stu-id="78798-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78798-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="78798-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="78798-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="78798-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78798-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="78798-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
