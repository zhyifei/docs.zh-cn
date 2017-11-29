---
title: '&lt;discoveryClientSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd2e9f3fd6d2cd0b99c6b63bc8ad0eefc9ff3e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="33862-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="33862-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="33862-103">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="33862-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="33862-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="33862-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="33862-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="33862-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33862-106">语法</span><span class="sxs-lookup"><span data-stu-id="33862-106">Syntax</span></span>  
  
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
              <add name="String" namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33862-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="33862-107">Attributes and Elements</span></span>  
 <span data-ttu-id="33862-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="33862-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33862-109">特性</span><span class="sxs-lookup"><span data-stu-id="33862-109">Attributes</span></span>  
  
|<span data-ttu-id="33862-110">特性</span><span class="sxs-lookup"><span data-stu-id="33862-110">Attribute</span></span>|<span data-ttu-id="33862-111">描述</span><span class="sxs-lookup"><span data-stu-id="33862-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33862-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="33862-112">discoveryEndpoint</span></span>|<span data-ttu-id="33862-113">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="33862-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33862-114">子元素</span><span class="sxs-lookup"><span data-stu-id="33862-114">Child Elements</span></span>  
  
|<span data-ttu-id="33862-115">元素</span><span class="sxs-lookup"><span data-stu-id="33862-115">Element</span></span>|<span data-ttu-id="33862-116">描述</span><span class="sxs-lookup"><span data-stu-id="33862-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33862-117">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="33862-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="33862-118">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="33862-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="33862-119">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续的时长）。</span><span class="sxs-lookup"><span data-stu-id="33862-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33862-120">父元素</span><span class="sxs-lookup"><span data-stu-id="33862-120">Parent Elements</span></span>  
  
|<span data-ttu-id="33862-121">元素</span><span class="sxs-lookup"><span data-stu-id="33862-121">Element</span></span>|<span data-ttu-id="33862-122">描述</span><span class="sxs-lookup"><span data-stu-id="33862-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33862-123">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="33862-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="33862-124">定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="33862-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33862-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33862-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
