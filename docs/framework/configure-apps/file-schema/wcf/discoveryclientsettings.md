---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 5b60c7281b92a487ba3ee275f7405cb82bd6cd87
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282238"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="945eb-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="945eb-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="945eb-102">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="945eb-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="945eb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="945eb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="945eb-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="945eb-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="945eb-105">语法</span><span class="sxs-lookup"><span data-stu-id="945eb-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="945eb-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="945eb-106">Attributes and Elements</span></span>  
 <span data-ttu-id="945eb-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="945eb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="945eb-108">特性</span><span class="sxs-lookup"><span data-stu-id="945eb-108">Attributes</span></span>  
  
|<span data-ttu-id="945eb-109">特性</span><span class="sxs-lookup"><span data-stu-id="945eb-109">Attribute</span></span>|<span data-ttu-id="945eb-110">描述</span><span class="sxs-lookup"><span data-stu-id="945eb-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="945eb-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="945eb-111">discoveryEndpoint</span></span>|<span data-ttu-id="945eb-112">一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。</span><span class="sxs-lookup"><span data-stu-id="945eb-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="945eb-113">子元素</span><span class="sxs-lookup"><span data-stu-id="945eb-113">Child Elements</span></span>  
  
|<span data-ttu-id="945eb-114">元素</span><span class="sxs-lookup"><span data-stu-id="945eb-114">Element</span></span>|<span data-ttu-id="945eb-115">描述</span><span class="sxs-lookup"><span data-stu-id="945eb-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="945eb-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="945eb-116">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="945eb-117">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="945eb-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="945eb-118">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续多久）。</span><span class="sxs-lookup"><span data-stu-id="945eb-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="945eb-119">父元素</span><span class="sxs-lookup"><span data-stu-id="945eb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="945eb-120">元素</span><span class="sxs-lookup"><span data-stu-id="945eb-120">Element</span></span>|<span data-ttu-id="945eb-121">描述</span><span class="sxs-lookup"><span data-stu-id="945eb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="945eb-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="945eb-122">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="945eb-123">定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="945eb-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="945eb-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="945eb-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
