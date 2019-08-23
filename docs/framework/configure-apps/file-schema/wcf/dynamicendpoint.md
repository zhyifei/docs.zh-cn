---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 3dc7fb19c5c7729620a5d9f3df1111b2dbdacf78
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925838"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="d39c6-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="d39c6-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="d39c6-102">此配置元素定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="d39c6-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="d39c6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d39c6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d39c6-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d39c6-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d39c6-105">语法</span><span class="sxs-lookup"><span data-stu-id="d39c6-105">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d39c6-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d39c6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d39c6-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d39c6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d39c6-108">特性</span><span class="sxs-lookup"><span data-stu-id="d39c6-108">Attributes</span></span>  
 <span data-ttu-id="d39c6-109">无。</span><span class="sxs-lookup"><span data-stu-id="d39c6-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d39c6-110">子元素</span><span class="sxs-lookup"><span data-stu-id="d39c6-110">Child Elements</span></span>  
  
|<span data-ttu-id="d39c6-111">元素</span><span class="sxs-lookup"><span data-stu-id="d39c6-111">Element</span></span>|<span data-ttu-id="d39c6-112">描述</span><span class="sxs-lookup"><span data-stu-id="d39c6-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d39c6-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="d39c6-113">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="d39c6-114">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="d39c6-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d39c6-115">父元素</span><span class="sxs-lookup"><span data-stu-id="d39c6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d39c6-116">元素</span><span class="sxs-lookup"><span data-stu-id="d39c6-116">Element</span></span>|<span data-ttu-id="d39c6-117">描述</span><span class="sxs-lookup"><span data-stu-id="d39c6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d39c6-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d39c6-118">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d39c6-119">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="d39c6-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d39c6-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d39c6-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
