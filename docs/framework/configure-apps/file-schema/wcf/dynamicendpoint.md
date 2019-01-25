---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: dcb52143c874b14c9241940f9b326a07b3fa6a82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540243"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="c39dd-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="c39dd-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="c39dd-103">此配置元素定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="c39dd-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="c39dd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c39dd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c39dd-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c39dd-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c39dd-106">语法</span><span class="sxs-lookup"><span data-stu-id="c39dd-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c39dd-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c39dd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c39dd-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c39dd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c39dd-109">特性</span><span class="sxs-lookup"><span data-stu-id="c39dd-109">Attributes</span></span>  
 <span data-ttu-id="c39dd-110">无。</span><span class="sxs-lookup"><span data-stu-id="c39dd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c39dd-111">子元素</span><span class="sxs-lookup"><span data-stu-id="c39dd-111">Child Elements</span></span>  
  
|<span data-ttu-id="c39dd-112">元素</span><span class="sxs-lookup"><span data-stu-id="c39dd-112">Element</span></span>|<span data-ttu-id="c39dd-113">描述</span><span class="sxs-lookup"><span data-stu-id="c39dd-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c39dd-114">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="c39dd-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="c39dd-115">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="c39dd-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c39dd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c39dd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c39dd-117">元素</span><span class="sxs-lookup"><span data-stu-id="c39dd-117">Element</span></span>|<span data-ttu-id="c39dd-118">描述</span><span class="sxs-lookup"><span data-stu-id="c39dd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c39dd-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c39dd-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="c39dd-120">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="c39dd-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c39dd-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c39dd-121">See also</span></span>
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
