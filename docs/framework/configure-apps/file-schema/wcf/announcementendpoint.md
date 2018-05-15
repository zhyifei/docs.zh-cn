---
title: '&lt;announcementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 3ce141d70e17c14facd6aa8560c7b3424a8d9ae8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="6fc22-102">&lt;announcementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="6fc22-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="6fc22-103">此配置元素定义具有固定公告协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="6fc22-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="6fc22-104">当分别打开或关闭服务时，服务可以选择通过发送一条联机和脱机公告消息来公告其可用性。</span><span class="sxs-lookup"><span data-stu-id="6fc22-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="6fc22-105">Windows Communication Foundation (WCF) 服务指定公告终结点中的[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)元素，并使用 AnnouncementClient 执行公告。</span><span class="sxs-lookup"><span data-stu-id="6fc22-105">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="6fc22-106">客户端希望侦听从其他服务公告实际充当[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务; 因此，你需要将公告终结点配置为在该客户端[\<服务 >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)部分。</span><span class="sxs-lookup"><span data-stu-id="6fc22-106">A client wishing to listen for the announcement from other service is actually acting as a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="6fc22-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6fc22-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="6fc22-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6fc22-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fc22-109">语法</span><span class="sxs-lookup"><span data-stu-id="6fc22-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxAnnouncementDelay="Timespan" 
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fc22-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6fc22-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6fc22-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6fc22-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fc22-112">特性</span><span class="sxs-lookup"><span data-stu-id="6fc22-112">Attributes</span></span>  
  
|<span data-ttu-id="6fc22-113">特性</span><span class="sxs-lookup"><span data-stu-id="6fc22-113">Attribute</span></span>|<span data-ttu-id="6fc22-114">描述</span><span class="sxs-lookup"><span data-stu-id="6fc22-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6fc22-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="6fc22-115">discoveryVersion</span></span>|<span data-ttu-id="6fc22-116">一个字符串，指定两个 WS-Discovery 协议版本中的其中一个版本。</span><span class="sxs-lookup"><span data-stu-id="6fc22-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="6fc22-117">有效值为 WSDiscovery11 和 WSDiscoveryApril2005。</span><span class="sxs-lookup"><span data-stu-id="6fc22-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="6fc22-118">此值的类型为 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>。</span><span class="sxs-lookup"><span data-stu-id="6fc22-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="6fc22-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="6fc22-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="6fc22-120">一个 Timespan 值，指定 Discovery 协议在发送 Hello 消息之前等待的最大延迟值。</span><span class="sxs-lookup"><span data-stu-id="6fc22-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="6fc22-121">消息在发送之前将等待一个随机时间值（介于 0 到此特性值之间）。</span><span class="sxs-lookup"><span data-stu-id="6fc22-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="6fc22-122">此特性用于设置随机的短时间延迟，以防止在网络出现故障后所有服务同时重新联机所造成的网络风暴。</span><span class="sxs-lookup"><span data-stu-id="6fc22-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="6fc22-123">name</span><span class="sxs-lookup"><span data-stu-id="6fc22-123">name</span></span>|<span data-ttu-id="6fc22-124">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="6fc22-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="6fc22-125">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="6fc22-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fc22-126">子元素</span><span class="sxs-lookup"><span data-stu-id="6fc22-126">Child Elements</span></span>  
 <span data-ttu-id="6fc22-127">无。</span><span class="sxs-lookup"><span data-stu-id="6fc22-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fc22-128">父元素</span><span class="sxs-lookup"><span data-stu-id="6fc22-128">Parent Elements</span></span>  
  
|<span data-ttu-id="6fc22-129">元素</span><span class="sxs-lookup"><span data-stu-id="6fc22-129">Element</span></span>|<span data-ttu-id="6fc22-130">描述</span><span class="sxs-lookup"><span data-stu-id="6fc22-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6fc22-131">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6fc22-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="6fc22-132">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="6fc22-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6fc22-133">示例</span><span class="sxs-lookup"><span data-stu-id="6fc22-133">Example</span></span>  
 <span data-ttu-id="6fc22-134">下面的示例演示通过 http 和对等网络侦听公告消息的客户端。</span><span class="sxs-lookup"><span data-stu-id="6fc22-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>  
  <service name="ServiceAnnouncementListener">  
    <endpoint name="httpAnnouncementEndpoint"  
              kind="announcementEndpoint"  
              binding="basicHttpBinding"  
              address="announcements" />  
    <endpoint name="peerNetAnnouncementEndpoint"  
              kind="announcementEndpoint"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />  
  ...  
  </service>  
</services>  
  
<standardEndpoints>  
  <announcementEndpoint>  
    <standardEndpoint name="httpAnnouncementEndpoint"                         
                      version="WSDiscoveryApril2005" />  
    <standardEndpoint name="peerNetAnnouncementEndpoint"                         
                      version="WSDiscoveryApril2005" />  
   </announcementEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6fc22-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fc22-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
