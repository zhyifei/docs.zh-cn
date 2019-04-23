---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 54a9833f56927568af711a103bd3831b767711e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209991"
---
# <a name="servicediscovery"></a><span data-ttu-id="499fc-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="499fc-101">\<serviceDiscovery></span></span>
<span data-ttu-id="499fc-102">指定服务终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="499fc-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="499fc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="499fc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="499fc-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="499fc-104">\<behaviors></span></span>  
<span data-ttu-id="499fc-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="499fc-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="499fc-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="499fc-106">\<behavior></span></span>  
<span data-ttu-id="499fc-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="499fc-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499fc-108">语法</span><span class="sxs-lookup"><span data-stu-id="499fc-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="499fc-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="499fc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="499fc-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="499fc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="499fc-111">特性</span><span class="sxs-lookup"><span data-stu-id="499fc-111">Attributes</span></span>  
 <span data-ttu-id="499fc-112">无。</span><span class="sxs-lookup"><span data-stu-id="499fc-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="499fc-113">子元素</span><span class="sxs-lookup"><span data-stu-id="499fc-113">Child Elements</span></span>  
  
|<span data-ttu-id="499fc-114">元素</span><span class="sxs-lookup"><span data-stu-id="499fc-114">Element</span></span>|<span data-ttu-id="499fc-115">描述</span><span class="sxs-lookup"><span data-stu-id="499fc-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="499fc-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="499fc-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="499fc-117">一个公告终结点集合。</span><span class="sxs-lookup"><span data-stu-id="499fc-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="499fc-118">使用此节可指定用于发送公告消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="499fc-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="499fc-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="499fc-119">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="499fc-120">一个发现终结点集合。</span><span class="sxs-lookup"><span data-stu-id="499fc-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="499fc-121">使用此节可指定要在其上侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="499fc-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="499fc-122">父元素</span><span class="sxs-lookup"><span data-stu-id="499fc-122">Parent Elements</span></span>  
  
|<span data-ttu-id="499fc-123">元素</span><span class="sxs-lookup"><span data-stu-id="499fc-123">Element</span></span>|<span data-ttu-id="499fc-124">描述</span><span class="sxs-lookup"><span data-stu-id="499fc-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="499fc-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="499fc-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="499fc-126">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="499fc-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="499fc-127">备注</span><span class="sxs-lookup"><span data-stu-id="499fc-127">Remarks</span></span>  
 <span data-ttu-id="499fc-128">将此配置元素添加到服务的行为配置后，此元素可使系统检测到此服务的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="499fc-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="499fc-129">您可以进一步配置此类终结点的发现功能，通过使用[ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)或[ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)子元素。</span><span class="sxs-lookup"><span data-stu-id="499fc-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="499fc-130">使用[ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)部分，以通过指定要用于发送服务公告 （联机 /hello 和脱机 /bye） 的终结点配置来配置公告。</span><span class="sxs-lookup"><span data-stu-id="499fc-130">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="499fc-131">使用[ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)节可以手动指定上用来侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="499fc-131">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="499fc-132">示例</span><span class="sxs-lookup"><span data-stu-id="499fc-132">Example</span></span>  
 <span data-ttu-id="499fc-133">下面的配置示例指定 CalculatorService 可供检测，并选择指定要使用的公告终结点。</span><span class="sxs-lookup"><span data-stu-id="499fc-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="499fc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="499fc-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
