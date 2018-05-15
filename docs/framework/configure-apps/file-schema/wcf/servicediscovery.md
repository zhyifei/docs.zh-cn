---
title: '&lt;serviceDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 78f1c7be1d8285cd2fdf79af1e1220a7e48b2893
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicediscoverygt"></a><span data-ttu-id="20add-102">&lt;serviceDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="20add-102">&lt;serviceDiscovery&gt;</span></span>
<span data-ttu-id="20add-103">指定服务终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="20add-103">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="20add-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="20add-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="20add-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="20add-105">\<behaviors></span></span>  
<span data-ttu-id="20add-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="20add-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="20add-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="20add-107">\<behavior></span></span>  
<span data-ttu-id="20add-108">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="20add-108">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20add-109">语法</span><span class="sxs-lookup"><span data-stu-id="20add-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20add-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20add-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20add-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20add-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20add-112">特性</span><span class="sxs-lookup"><span data-stu-id="20add-112">Attributes</span></span>  
 <span data-ttu-id="20add-113">无。</span><span class="sxs-lookup"><span data-stu-id="20add-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20add-114">子元素</span><span class="sxs-lookup"><span data-stu-id="20add-114">Child Elements</span></span>  
  
|<span data-ttu-id="20add-115">元素</span><span class="sxs-lookup"><span data-stu-id="20add-115">Element</span></span>|<span data-ttu-id="20add-116">描述</span><span class="sxs-lookup"><span data-stu-id="20add-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20add-117">\<announcementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="20add-117">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="20add-118">一个公告终结点集合。</span><span class="sxs-lookup"><span data-stu-id="20add-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="20add-119">使用此节可指定用于发送公告消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="20add-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="20add-120">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="20add-120">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="20add-121">一个发现终结点集合。</span><span class="sxs-lookup"><span data-stu-id="20add-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="20add-122">使用此节可指定要在其上侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="20add-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20add-123">父元素</span><span class="sxs-lookup"><span data-stu-id="20add-123">Parent Elements</span></span>  
  
|<span data-ttu-id="20add-124">元素</span><span class="sxs-lookup"><span data-stu-id="20add-124">Element</span></span>|<span data-ttu-id="20add-125">描述</span><span class="sxs-lookup"><span data-stu-id="20add-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20add-126">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="20add-126">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="20add-127">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="20add-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20add-128">备注</span><span class="sxs-lookup"><span data-stu-id="20add-128">Remarks</span></span>  
 <span data-ttu-id="20add-129">将此配置元素添加到服务的行为配置后，此元素可使系统检测到此服务的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="20add-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="20add-130">你可以进一步配置此类终结点的发现功能，通过使用[ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)或[ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)子元素。</span><span class="sxs-lookup"><span data-stu-id="20add-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="20add-131">使用[ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)部分以通过指定要用来发送服务公告 （联机/Hello 和 Bye 脱机/） 的终结点配置来配置公告。</span><span class="sxs-lookup"><span data-stu-id="20add-131">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="20add-132">使用[ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)部分手动指定上用于侦听发现消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="20add-132">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20add-133">示例</span><span class="sxs-lookup"><span data-stu-id="20add-133">Example</span></span>  
 <span data-ttu-id="20add-134">下面的配置示例指定 CalculatorService 可供检测，并选择指定要使用的公告终结点。</span><span class="sxs-lookup"><span data-stu-id="20add-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20add-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="20add-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
