---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: aa4cd8f4d7dcfa438ede71c394f1d0b0ac6faa50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926553"
---
# <a name="announcementendpoint"></a><span data-ttu-id="76620-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="76620-101">\<announcementEndpoint></span></span>
<span data-ttu-id="76620-102">此配置元素定义具有固定公告协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="76620-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="76620-103">当分别打开或关闭服务时，服务可以选择通过发送一条联机和脱机公告消息来公告其可用性。</span><span class="sxs-lookup"><span data-stu-id="76620-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="76620-104">Windows Communication Foundation (WCF) 服务指定[ \<serviceDiscovery >](servicediscovery.md)元素中的公告终结点, 并使用 AnnouncementClient 来执行公告。</span><span class="sxs-lookup"><span data-stu-id="76620-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="76620-105">希望侦听来自其他服务的公告的客户端实际充当 WCF 服务;因此, 您必须在 " [ \<服务 >](services.md) " 部分中配置该客户端的公告终结点。</span><span class="sxs-lookup"><span data-stu-id="76620-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="76620-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="76620-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="76620-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="76620-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76620-108">语法</span><span class="sxs-lookup"><span data-stu-id="76620-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76620-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="76620-109">Attributes and Elements</span></span>  
 <span data-ttu-id="76620-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="76620-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76620-111">特性</span><span class="sxs-lookup"><span data-stu-id="76620-111">Attributes</span></span>  
  
|<span data-ttu-id="76620-112">特性</span><span class="sxs-lookup"><span data-stu-id="76620-112">Attribute</span></span>|<span data-ttu-id="76620-113">描述</span><span class="sxs-lookup"><span data-stu-id="76620-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76620-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="76620-114">discoveryVersion</span></span>|<span data-ttu-id="76620-115">一个字符串，指定两个 WS-Discovery 协议版本中的其中一个版本。</span><span class="sxs-lookup"><span data-stu-id="76620-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="76620-116">有效值为 WSDiscovery11 和 WSDiscoveryApril2005。</span><span class="sxs-lookup"><span data-stu-id="76620-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="76620-117">此值的类型为 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>。</span><span class="sxs-lookup"><span data-stu-id="76620-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="76620-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="76620-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="76620-119">一个 Timespan 值，指定 Discovery 协议在发送 Hello 消息之前等待的最大延迟值。</span><span class="sxs-lookup"><span data-stu-id="76620-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="76620-120">消息在发送之前将等待一个随机时间值（介于 0 到此特性值之间）。</span><span class="sxs-lookup"><span data-stu-id="76620-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="76620-121">此特性用于设置随机的短时间延迟，以防止在网络出现故障后所有服务同时重新联机所造成的网络风暴。</span><span class="sxs-lookup"><span data-stu-id="76620-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="76620-122">NAME</span><span class="sxs-lookup"><span data-stu-id="76620-122">name</span></span>|<span data-ttu-id="76620-123">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="76620-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="76620-124">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="76620-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76620-125">子元素</span><span class="sxs-lookup"><span data-stu-id="76620-125">Child Elements</span></span>  
 <span data-ttu-id="76620-126">无。</span><span class="sxs-lookup"><span data-stu-id="76620-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76620-127">父元素</span><span class="sxs-lookup"><span data-stu-id="76620-127">Parent Elements</span></span>  
  
|<span data-ttu-id="76620-128">元素</span><span class="sxs-lookup"><span data-stu-id="76620-128">Element</span></span>|<span data-ttu-id="76620-129">描述</span><span class="sxs-lookup"><span data-stu-id="76620-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76620-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="76620-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="76620-131">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="76620-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="76620-132">示例</span><span class="sxs-lookup"><span data-stu-id="76620-132">Example</span></span>  
 <span data-ttu-id="76620-133">下面的示例演示通过 http 和对等网络侦听公告消息的客户端。</span><span class="sxs-lookup"><span data-stu-id="76620-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76620-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="76620-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
