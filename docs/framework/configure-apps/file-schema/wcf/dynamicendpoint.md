---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855341"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="25555-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="25555-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="25555-102">此配置元素定义一个标准终结点，应用程序通过利用该终结点包含的信息，能够充当可在运行时动态查找终结点地址的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="25555-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="25555-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25555-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25555-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="25555-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="25555-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="25555-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="25555-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dynamicEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="25555-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25555-107">语法</span><span class="sxs-lookup"><span data-stu-id="25555-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25555-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="25555-108">Attributes and Elements</span></span>  
 <span data-ttu-id="25555-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="25555-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25555-110">特性</span><span class="sxs-lookup"><span data-stu-id="25555-110">Attributes</span></span>  
 <span data-ttu-id="25555-111">无。</span><span class="sxs-lookup"><span data-stu-id="25555-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="25555-112">子元素</span><span class="sxs-lookup"><span data-stu-id="25555-112">Child Elements</span></span>  
  
|<span data-ttu-id="25555-113">元素</span><span class="sxs-lookup"><span data-stu-id="25555-113">Element</span></span>|<span data-ttu-id="25555-114">描述</span><span class="sxs-lookup"><span data-stu-id="25555-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25555-115">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="25555-115">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="25555-116">包含应用程序以客户端形式参与服务发现过程所需的设置。</span><span class="sxs-lookup"><span data-stu-id="25555-116">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25555-117">父元素</span><span class="sxs-lookup"><span data-stu-id="25555-117">Parent Elements</span></span>  
  
|<span data-ttu-id="25555-118">元素</span><span class="sxs-lookup"><span data-stu-id="25555-118">Element</span></span>|<span data-ttu-id="25555-119">描述</span><span class="sxs-lookup"><span data-stu-id="25555-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25555-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="25555-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="25555-121">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="25555-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25555-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="25555-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
