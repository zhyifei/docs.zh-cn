---
title: '&lt;serviceDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 73943f5f962a6963809e2c65ce8593f6181559f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587328"
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="6559d-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="6559d-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="6559d-103">指定服务终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="6559d-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="6559d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6559d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6559d-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6559d-105">\<behaviors></span></span>  
<span data-ttu-id="6559d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6559d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6559d-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6559d-107">\<behavior></span></span>  
<span data-ttu-id="6559d-108">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="6559d-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6559d-109">语法</span><span class="sxs-lookup"><span data-stu-id="6559d-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6559d-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6559d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6559d-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6559d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6559d-112">特性</span><span class="sxs-lookup"><span data-stu-id="6559d-112">Attributes</span></span>  
 <span data-ttu-id="6559d-113">无。</span><span class="sxs-lookup"><span data-stu-id="6559d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6559d-114">子元素</span><span class="sxs-lookup"><span data-stu-id="6559d-114">Child Elements</span></span>  
  
|<span data-ttu-id="6559d-115">元素</span><span class="sxs-lookup"><span data-stu-id="6559d-115">Element</span></span>|<span data-ttu-id="6559d-116">描述</span><span class="sxs-lookup"><span data-stu-id="6559d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6559d-117">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="6559d-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="6559d-118">一个公告终结点集合。</span><span class="sxs-lookup"><span data-stu-id="6559d-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="6559d-119">使用此节可指定用于发送公告消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="6559d-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="6559d-120">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="6559d-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="6559d-121">一个发现终结点集合。</span><span class="sxs-lookup"><span data-stu-id="6559d-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="6559d-122">使用此节可指定要在其上侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="6559d-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6559d-123">父元素</span><span class="sxs-lookup"><span data-stu-id="6559d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6559d-124">元素</span><span class="sxs-lookup"><span data-stu-id="6559d-124">Element</span></span>|<span data-ttu-id="6559d-125">描述</span><span class="sxs-lookup"><span data-stu-id="6559d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6559d-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6559d-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6559d-127">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="6559d-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6559d-128">备注</span><span class="sxs-lookup"><span data-stu-id="6559d-128">Remarks</span></span>  
 <span data-ttu-id="6559d-129">将此配置元素添加到服务的行为配置后，此元素可使系统检测到此服务的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="6559d-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="6559d-130">您可以进一步配置此类终结点的发现功能，通过使用[ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)或[ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)子元素。</span><span class="sxs-lookup"><span data-stu-id="6559d-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="6559d-131">使用[ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)部分，以通过指定要用于发送服务公告 （联机 /hello 和脱机 /bye） 的终结点配置来配置公告。</span><span class="sxs-lookup"><span data-stu-id="6559d-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="6559d-132">使用[ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)节可以手动指定上用来侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="6559d-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6559d-133">示例</span><span class="sxs-lookup"><span data-stu-id="6559d-133">Example</span></span>  
 <span data-ttu-id="6559d-134">下面的配置示例指定 CalculatorService 可供检测，并选择指定要使用的公告终结点。</span><span class="sxs-lookup"><span data-stu-id="6559d-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="6559d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="6559d-135">See also</span></span>
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
