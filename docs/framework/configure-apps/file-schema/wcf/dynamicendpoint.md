---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 215bc9d8540b2d782a0c63f2f5be96f6fcde6812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="101a1-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="101a1-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="101a1-103">此配置元素定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="101a1-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="101a1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="101a1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="101a1-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="101a1-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="101a1-106">语法</span><span class="sxs-lookup"><span data-stu-id="101a1-106">Syntax</span></span>  
  
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
            <add scope="URI" />
          </scopes>
        </findCriteria>
      </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="101a1-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="101a1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="101a1-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="101a1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="101a1-109">特性</span><span class="sxs-lookup"><span data-stu-id="101a1-109">Attributes</span></span>  
 <span data-ttu-id="101a1-110">无。</span><span class="sxs-lookup"><span data-stu-id="101a1-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="101a1-111">子元素</span><span class="sxs-lookup"><span data-stu-id="101a1-111">Child Elements</span></span>  
  
|<span data-ttu-id="101a1-112">元素</span><span class="sxs-lookup"><span data-stu-id="101a1-112">Element</span></span>|<span data-ttu-id="101a1-113">描述</span><span class="sxs-lookup"><span data-stu-id="101a1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="101a1-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="101a1-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="101a1-115">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="101a1-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="101a1-116">父元素</span><span class="sxs-lookup"><span data-stu-id="101a1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="101a1-117">元素</span><span class="sxs-lookup"><span data-stu-id="101a1-117">Element</span></span>|<span data-ttu-id="101a1-118">描述</span><span class="sxs-lookup"><span data-stu-id="101a1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="101a1-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="101a1-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="101a1-120">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="101a1-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="101a1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="101a1-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
