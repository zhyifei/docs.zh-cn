---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855411"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="df3fa-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="df3fa-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="df3fa-102">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="df3fa-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="df3fa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="df3fa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="df3fa-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="df3fa-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="df3fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="df3fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="df3fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="df3fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="df3fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="df3fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="df3fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryClientSettings >**</span><span class="sxs-lookup"><span data-stu-id="df3fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df3fa-109">语法</span><span class="sxs-lookup"><span data-stu-id="df3fa-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df3fa-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="df3fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="df3fa-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="df3fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df3fa-112">特性</span><span class="sxs-lookup"><span data-stu-id="df3fa-112">Attributes</span></span>  
  
|<span data-ttu-id="df3fa-113">特性</span><span class="sxs-lookup"><span data-stu-id="df3fa-113">Attribute</span></span>|<span data-ttu-id="df3fa-114">描述</span><span class="sxs-lookup"><span data-stu-id="df3fa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df3fa-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="df3fa-115">discoveryEndpoint</span></span>|<span data-ttu-id="df3fa-116">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="df3fa-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df3fa-117">子元素</span><span class="sxs-lookup"><span data-stu-id="df3fa-117">Child Elements</span></span>  
  
|<span data-ttu-id="df3fa-118">元素</span><span class="sxs-lookup"><span data-stu-id="df3fa-118">Element</span></span>|<span data-ttu-id="df3fa-119">描述</span><span class="sxs-lookup"><span data-stu-id="df3fa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df3fa-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="df3fa-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="df3fa-121">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="df3fa-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="df3fa-122">可以将条件分组为搜索条件（指定要查找的服务）和查找终止条件（搜索应持续的时间长度）。</span><span class="sxs-lookup"><span data-stu-id="df3fa-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df3fa-123">父元素</span><span class="sxs-lookup"><span data-stu-id="df3fa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="df3fa-124">元素</span><span class="sxs-lookup"><span data-stu-id="df3fa-124">Element</span></span>|<span data-ttu-id="df3fa-125">描述</span><span class="sxs-lookup"><span data-stu-id="df3fa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df3fa-126">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="df3fa-126">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="df3fa-127">定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="df3fa-127">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df3fa-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="df3fa-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
