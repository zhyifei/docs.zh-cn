---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 32b14f8fb3235040a51455f2099a403c8312c699
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855396"
---
# <a name="discoveryendpoint"></a><span data-ttu-id="3fe2c-101">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="3fe2c-101">\<discoveryEndpoint></span></span>

<span data-ttu-id="3fe2c-102">此配置元素定义具有固定发现协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-102">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="3fe2c-103">将此元素添加到服务配置后，该元素将指定侦听发现消息的位置。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-103">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="3fe2c-104">将此元素添加到客户端配置后，该元素将指定发送发现查询的位置。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-104">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="3fe2c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3fe2c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3fe2c-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3fe2c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3fe2c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3fe2c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="3fe2c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="3fe2c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe2c-109">语法</span><span class="sxs-lookup"><span data-stu-id="3fe2c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fe2c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3fe2c-110">Attributes and elements</span></span>

<span data-ttu-id="3fe2c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fe2c-112">特性</span><span class="sxs-lookup"><span data-stu-id="3fe2c-112">Attributes</span></span>

| <span data-ttu-id="3fe2c-113">特性</span><span class="sxs-lookup"><span data-stu-id="3fe2c-113">Attribute</span></span>        | <span data-ttu-id="3fe2c-114">描述</span><span class="sxs-lookup"><span data-stu-id="3fe2c-114">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="3fe2c-115">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="3fe2c-115">discoveryMode</span></span>    | <span data-ttu-id="3fe2c-116">一个字符串，指定发现协议的模式。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-116">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="3fe2c-117">有效值为 "即席" 和 "Managed"。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-117">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="3fe2c-118">在托管模式下，协议依靠发现代理，此代理用作可检测服务的存储库。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-118">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="3fe2c-119">即席模式要求协议使用 UDP 多播机制查找可用的服务。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-119">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="3fe2c-120">有关属性的详细信息，请参阅<xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-120">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="3fe2c-121">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="3fe2c-121">discoveryVersion</span></span> | <span data-ttu-id="3fe2c-122">一个字符串，指定两个 WS-Discovery 协议版本中的其中一个版本。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-122">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="3fe2c-123">有效值为 WSDiscovery11 和 WSDiscoveryApril2005。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-123">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="3fe2c-124">此值的类型为 <xref:System.ServiceModel.Discovery.DiscoveryVersion>。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-124">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="3fe2c-125">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="3fe2c-125">maxResponseDelay</span></span> | <span data-ttu-id="3fe2c-126">一个 Timespan 值，指定 Discovery 协议在发送 Probe Match、Resolve Match 这类消息之前等待的最大延迟值。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-126">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="3fe2c-127">如果同时发送所有 ProbeMatch，则可能发生网络风暴。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-127">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="3fe2c-128">若要防止发生这种情况，可在发送 ProbeMatch 时在各 ProbeMatch 之间应用随机延迟。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-128">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="3fe2c-129">随机延迟的范围是从 0 到此特性所设置的值之间。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-129">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="3fe2c-130">如果将此特性设置为 0，则在不使用任何延迟的紧凑循环中发送 ProbeMatch 消息。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-130">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="3fe2c-131">否则，在发送 ProbeMatch 消息时将应用一定的随机延迟，以使发送所有 ProbeMatch 消息所用的总时间不会超过 maxResponseDelay。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-131">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="3fe2c-132">此值只与服务相关，不可用于客户端。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-132">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="3fe2c-133">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-133">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3fe2c-134">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-134">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="3fe2c-135">子元素</span><span class="sxs-lookup"><span data-stu-id="3fe2c-135">Child elements</span></span>

<span data-ttu-id="3fe2c-136">无。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-136">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fe2c-137">父元素</span><span class="sxs-lookup"><span data-stu-id="3fe2c-137">Parent elements</span></span>

| <span data-ttu-id="3fe2c-138">元素</span><span class="sxs-lookup"><span data-stu-id="3fe2c-138">Element</span></span> | <span data-ttu-id="3fe2c-139">描述</span><span class="sxs-lookup"><span data-stu-id="3fe2c-139">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="3fe2c-140">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3fe2c-140">\<standardEndpoints></span></span>](standardendpoints.md) | <span data-ttu-id="3fe2c-141">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-141">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="3fe2c-142">示例</span><span class="sxs-lookup"><span data-stu-id="3fe2c-142">Example</span></span>

<span data-ttu-id="3fe2c-143">下面的示例演示通过对等网多播传输侦听发现消息的服务。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-143">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="3fe2c-144">此示例明确指定 WS-Discovery 2005 年 4 月版。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-144">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="3fe2c-145">标准终结点配置基于服务定义，无法在服务之间共享。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-145">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="3fe2c-146">如果其他服务希望采用相同的发现终结点，则需要将相同配置添加到该服务的节中。</span><span class="sxs-lookup"><span data-stu-id="3fe2c-146">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3fe2c-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fe2c-147">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
