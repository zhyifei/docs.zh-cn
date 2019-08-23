---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936276"
---
# <a name="servicediscovery"></a><span data-ttu-id="1d559-101">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="1d559-101">\<serviceDiscovery></span></span>
<span data-ttu-id="1d559-102">指定服务终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="1d559-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="1d559-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1d559-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d559-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1d559-104">\<behaviors></span></span>  
<span data-ttu-id="1d559-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1d559-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1d559-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1d559-106">\<behavior></span></span>  
<span data-ttu-id="1d559-107">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="1d559-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d559-108">语法</span><span class="sxs-lookup"><span data-stu-id="1d559-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d559-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1d559-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1d559-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1d559-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d559-111">特性</span><span class="sxs-lookup"><span data-stu-id="1d559-111">Attributes</span></span>  
 <span data-ttu-id="1d559-112">无。</span><span class="sxs-lookup"><span data-stu-id="1d559-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d559-113">子元素</span><span class="sxs-lookup"><span data-stu-id="1d559-113">Child Elements</span></span>  
  
|<span data-ttu-id="1d559-114">元素</span><span class="sxs-lookup"><span data-stu-id="1d559-114">Element</span></span>|<span data-ttu-id="1d559-115">描述</span><span class="sxs-lookup"><span data-stu-id="1d559-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d559-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="1d559-116">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="1d559-117">一个公告终结点集合。</span><span class="sxs-lookup"><span data-stu-id="1d559-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="1d559-118">使用此节可指定用于发送公告消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="1d559-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="1d559-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="1d559-119">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="1d559-120">一个发现终结点集合。</span><span class="sxs-lookup"><span data-stu-id="1d559-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="1d559-121">使用此节可指定要在其上侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="1d559-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d559-122">父元素</span><span class="sxs-lookup"><span data-stu-id="1d559-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1d559-123">元素</span><span class="sxs-lookup"><span data-stu-id="1d559-123">Element</span></span>|<span data-ttu-id="1d559-124">描述</span><span class="sxs-lookup"><span data-stu-id="1d559-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d559-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1d559-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1d559-126">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="1d559-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d559-127">备注</span><span class="sxs-lookup"><span data-stu-id="1d559-127">Remarks</span></span>  
 <span data-ttu-id="1d559-128">将此配置元素添加到服务的行为配置后，此元素可使系统检测到此服务的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="1d559-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="1d559-129">可以通过使用[ \<discoveryEndpoint >](discoveryendpoint.md)或[ \<announcementEndpoint >](announcementendpoint.md)子元素, 进一步配置此类终结点的发现功能。</span><span class="sxs-lookup"><span data-stu-id="1d559-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="1d559-130">使用 " [ \<announcementEndpoint >](announcementendpoint.md) " 部分, 通过指定要用于发送服务公告的终结点配置 (online/Hello 和 offline/再见) 来配置公告。</span><span class="sxs-lookup"><span data-stu-id="1d559-130">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="1d559-131">使用 " [ \<discoveryEndpoint >](discoveryendpoint.md) " 部分, 手动指定要在其上侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="1d559-131">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d559-132">示例</span><span class="sxs-lookup"><span data-stu-id="1d559-132">Example</span></span>  
 <span data-ttu-id="1d559-133">下面的配置示例指定 CalculatorService 可供检测，并选择指定要使用的公告终结点。</span><span class="sxs-lookup"><span data-stu-id="1d559-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d559-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d559-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
