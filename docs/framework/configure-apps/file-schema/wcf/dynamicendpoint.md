---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: e1a53869faa1997d2e79c3d2869a15001ee29626
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187741"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="6ee2e-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="6ee2e-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="6ee2e-102">此配置元素定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="6ee2e-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="6ee2e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6ee2e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6ee2e-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="6ee2e-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ee2e-105">语法</span><span class="sxs-lookup"><span data-stu-id="6ee2e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ee2e-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6ee2e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6ee2e-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6ee2e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ee2e-108">特性</span><span class="sxs-lookup"><span data-stu-id="6ee2e-108">Attributes</span></span>  
 <span data-ttu-id="6ee2e-109">无。</span><span class="sxs-lookup"><span data-stu-id="6ee2e-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6ee2e-110">子元素</span><span class="sxs-lookup"><span data-stu-id="6ee2e-110">Child Elements</span></span>  
  
|<span data-ttu-id="6ee2e-111">元素</span><span class="sxs-lookup"><span data-stu-id="6ee2e-111">Element</span></span>|<span data-ttu-id="6ee2e-112">描述</span><span class="sxs-lookup"><span data-stu-id="6ee2e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ee2e-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="6ee2e-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="6ee2e-114">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="6ee2e-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ee2e-115">父元素</span><span class="sxs-lookup"><span data-stu-id="6ee2e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6ee2e-116">元素</span><span class="sxs-lookup"><span data-stu-id="6ee2e-116">Element</span></span>|<span data-ttu-id="6ee2e-117">描述</span><span class="sxs-lookup"><span data-stu-id="6ee2e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ee2e-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="6ee2e-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="6ee2e-119">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="6ee2e-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ee2e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ee2e-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
