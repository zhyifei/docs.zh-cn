---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: d1a3371872f5587a682b8242c29b71808508ca3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704046"
---
# <a name="discoveryendpoint"></a><span data-ttu-id="363eb-101">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="363eb-101">\<discoveryEndpoint></span></span>

<span data-ttu-id="363eb-102">此配置元素定义具有固定发现协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="363eb-102">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="363eb-103">将此元素添加到服务配置后，该元素将指定侦听发现消息的位置。</span><span class="sxs-lookup"><span data-stu-id="363eb-103">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="363eb-104">将此元素添加到客户端配置后，该元素将指定发送发现查询的位置。</span><span class="sxs-lookup"><span data-stu-id="363eb-104">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="363eb-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="363eb-105">\<system.serviceModel></span></span>  
<span data-ttu-id="363eb-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="363eb-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="363eb-107">语法</span><span class="sxs-lookup"><span data-stu-id="363eb-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="363eb-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="363eb-108">Attributes and elements</span></span>

<span data-ttu-id="363eb-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="363eb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="363eb-110">特性</span><span class="sxs-lookup"><span data-stu-id="363eb-110">Attributes</span></span>

| <span data-ttu-id="363eb-111">特性</span><span class="sxs-lookup"><span data-stu-id="363eb-111">Attribute</span></span>        | <span data-ttu-id="363eb-112">描述</span><span class="sxs-lookup"><span data-stu-id="363eb-112">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="363eb-113">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="363eb-113">discoveryMode</span></span>    | <span data-ttu-id="363eb-114">一个字符串，指定发现协议的模式。</span><span class="sxs-lookup"><span data-stu-id="363eb-114">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="363eb-115">有效值为"Adhoc"和"已托管"。</span><span class="sxs-lookup"><span data-stu-id="363eb-115">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="363eb-116">在托管模式下，协议依靠发现代理，此代理用作可检测服务的存储库。</span><span class="sxs-lookup"><span data-stu-id="363eb-116">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="363eb-117">即席模式要求协议使用 UDP 多播机制查找可用的服务。</span><span class="sxs-lookup"><span data-stu-id="363eb-117">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="363eb-118">该属性的详细信息，请参阅<xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="363eb-118">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="363eb-119">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="363eb-119">discoveryVersion</span></span> | <span data-ttu-id="363eb-120">一个字符串，指定两个 WS-Discovery 协议版本中的其中一个版本。</span><span class="sxs-lookup"><span data-stu-id="363eb-120">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="363eb-121">有效值为 WSDiscovery11 和 WSDiscoveryApril2005。</span><span class="sxs-lookup"><span data-stu-id="363eb-121">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="363eb-122">此值的类型为 <xref:System.ServiceModel.Discovery.DiscoveryVersion>。</span><span class="sxs-lookup"><span data-stu-id="363eb-122">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="363eb-123">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="363eb-123">maxResponseDelay</span></span> | <span data-ttu-id="363eb-124">一个 Timespan 值，指定 Discovery 协议在发送 Probe Match、Resolve Match 这类消息之前等待的最大延迟值。</span><span class="sxs-lookup"><span data-stu-id="363eb-124">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="363eb-125">如果同时发送所有 ProbeMatch，则可能发生网络风暴。</span><span class="sxs-lookup"><span data-stu-id="363eb-125">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="363eb-126">若要防止发生这种情况，可在发送 ProbeMatch 时在各 ProbeMatch 之间应用随机延迟。</span><span class="sxs-lookup"><span data-stu-id="363eb-126">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="363eb-127">随机延迟的范围是从 0 到此特性所设置的值之间。</span><span class="sxs-lookup"><span data-stu-id="363eb-127">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="363eb-128">如果将此特性设置为 0，则在不使用任何延迟的紧凑循环中发送 ProbeMatch 消息。</span><span class="sxs-lookup"><span data-stu-id="363eb-128">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="363eb-129">否则，在发送 ProbeMatch 消息时将应用一定的随机延迟，以使发送所有 ProbeMatch 消息所用的总时间不会超过 maxResponseDelay。</span><span class="sxs-lookup"><span data-stu-id="363eb-129">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="363eb-130">此值只与服务相关，不可用于客户端。</span><span class="sxs-lookup"><span data-stu-id="363eb-130">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="363eb-131">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="363eb-131">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="363eb-132">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="363eb-132">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="363eb-133">子元素</span><span class="sxs-lookup"><span data-stu-id="363eb-133">Child elements</span></span>

<span data-ttu-id="363eb-134">无。</span><span class="sxs-lookup"><span data-stu-id="363eb-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="363eb-135">父元素</span><span class="sxs-lookup"><span data-stu-id="363eb-135">Parent elements</span></span>

| <span data-ttu-id="363eb-136">元素</span><span class="sxs-lookup"><span data-stu-id="363eb-136">Element</span></span> | <span data-ttu-id="363eb-137">描述</span><span class="sxs-lookup"><span data-stu-id="363eb-137">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="363eb-138">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="363eb-138">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | <span data-ttu-id="363eb-139">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="363eb-139">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="363eb-140">示例</span><span class="sxs-lookup"><span data-stu-id="363eb-140">Example</span></span>

<span data-ttu-id="363eb-141">下面的示例演示通过对等网多播传输侦听发现消息的服务。</span><span class="sxs-lookup"><span data-stu-id="363eb-141">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="363eb-142">此示例明确指定 WS-Discovery 2005 年 4 月版。</span><span class="sxs-lookup"><span data-stu-id="363eb-142">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="363eb-143">标准终结点配置基于服务定义，无法在服务之间共享。</span><span class="sxs-lookup"><span data-stu-id="363eb-143">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="363eb-144">如果其他服务希望采用相同的发现终结点，则需要将相同配置添加到该服务的节中。</span><span class="sxs-lookup"><span data-stu-id="363eb-144">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="peerNetDiscovery"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              kind="discoveryEndpoint"
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  </service>
</services>
<standardEndpoints>
  <discoveryEndpoint>
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"
                      version="WSDiscoveryApril2005" />
  </discoveryEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="363eb-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="363eb-145">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
