---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: a039e805bc4378582d7a7bcf6ef84591ec3d2b6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261433"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="cddc6-101">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="cddc6-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="cddc6-102">为特定于对等通道的 TCP 消息定义绑定。</span><span class="sxs-lookup"><span data-stu-id="cddc6-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="cddc6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cddc6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cddc6-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cddc6-104">\<bindings></span></span>  
<span data-ttu-id="cddc6-105">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="cddc6-105">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cddc6-106">语法</span><span class="sxs-lookup"><span data-stu-id="cddc6-106">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding name="string"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           listenIPAddress="String"
           maxBufferPoolSize="integer"
           maxReceiveMessageSize="Integer"
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cddc6-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cddc6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cddc6-108">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cddc6-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cddc6-109">特性</span><span class="sxs-lookup"><span data-stu-id="cddc6-109">Attributes</span></span>  
  
|<span data-ttu-id="cddc6-110">特性</span><span class="sxs-lookup"><span data-stu-id="cddc6-110">Attribute</span></span>|<span data-ttu-id="cddc6-111">描述</span><span class="sxs-lookup"><span data-stu-id="cddc6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cddc6-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="cddc6-112">closeTimeout</span></span>|<span data-ttu-id="cddc6-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="cddc6-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="cddc6-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="cddc6-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cddc6-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="cddc6-115">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="cddc6-116">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="cddc6-116">listenIPAddress</span></span>|<span data-ttu-id="cddc6-117">一个字符串，指定对等节点将在其上侦听 TCP 消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="cddc6-117">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="cddc6-118">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="cddc6-118">The default is `null`.</span></span>|  
|<span data-ttu-id="cddc6-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="cddc6-119">maxBufferPoolSize</span></span>|<span data-ttu-id="cddc6-120">一个整数，指定此绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="cddc6-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="cddc6-121">默认值为 524,288 字节 (512 \* 1024)。</span><span class="sxs-lookup"><span data-stu-id="cddc6-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="cddc6-122">Windows Communication Foundation (WCF) 的许多部件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="cddc6-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="cddc6-123">每次使用缓冲区时，创建和销毁它们都将占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="cddc6-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="cddc6-124">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回给缓冲池。</span><span class="sxs-lookup"><span data-stu-id="cddc6-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="cddc6-125">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="cddc6-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="cddc6-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="cddc6-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="cddc6-127">一个正整数，指定采用此绑定配置的通道上可以接收的最大消息大小（字节），包括消息头。</span><span class="sxs-lookup"><span data-stu-id="cddc6-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="cddc6-128">如果消息超出此限制，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="cddc6-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="cddc6-129">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="cddc6-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="cddc6-130">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="cddc6-130">The default is 65536.</span></span>|  
|<span data-ttu-id="cddc6-131">name</span><span class="sxs-lookup"><span data-stu-id="cddc6-131">name</span></span>|<span data-ttu-id="cddc6-132">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="cddc6-132">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="cddc6-133">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="cddc6-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="cddc6-134">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="cddc6-134">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="cddc6-135">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="cddc6-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="cddc6-136">openTimeout</span><span class="sxs-lookup"><span data-stu-id="cddc6-136">openTimeout</span></span>|<span data-ttu-id="cddc6-137">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="cddc6-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="cddc6-138">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="cddc6-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cddc6-139">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="cddc6-139">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="cddc6-140">端口</span><span class="sxs-lookup"><span data-stu-id="cddc6-140">port</span></span>|<span data-ttu-id="cddc6-141">一个整数，指定此绑定将用于处理对等通道 TCP 消息的网络接口端口。</span><span class="sxs-lookup"><span data-stu-id="cddc6-141">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="cddc6-142">该值必须介于 <xref:System.Net.IPEndPoint.MinPort> 和 <xref:System.Net.IPEndPoint.MaxPort> 之间。</span><span class="sxs-lookup"><span data-stu-id="cddc6-142">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="cddc6-143">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="cddc6-143">The default is 0.</span></span>|  
|<span data-ttu-id="cddc6-144">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="cddc6-144">receiveTimeout</span></span>|<span data-ttu-id="cddc6-145">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="cddc6-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="cddc6-146">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="cddc6-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cddc6-147">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="cddc6-147">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="cddc6-148">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="cddc6-148">sendTimeout</span></span>|<span data-ttu-id="cddc6-149">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="cddc6-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="cddc6-150">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="cddc6-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cddc6-151">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="cddc6-151">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cddc6-152">子元素</span><span class="sxs-lookup"><span data-stu-id="cddc6-152">Child Elements</span></span>  
  
|<span data-ttu-id="cddc6-153">元素</span><span class="sxs-lookup"><span data-stu-id="cddc6-153">Element</span></span>|<span data-ttu-id="cddc6-154">描述</span><span class="sxs-lookup"><span data-stu-id="cddc6-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cddc6-155">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="cddc6-155">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="cddc6-156">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="cddc6-156">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="cddc6-157">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="cddc6-157">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="cddc6-158">\<resolver></span><span class="sxs-lookup"><span data-stu-id="cddc6-158">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="cddc6-159">指定一个对等解析程序，此绑定将使用该解析程序将对等网格 ID 解析为对等网格中节点的终结点 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="cddc6-159">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="cddc6-160">\<security></span><span class="sxs-lookup"><span data-stu-id="cddc6-160">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="cddc6-161">定义消息的安全设置。</span><span class="sxs-lookup"><span data-stu-id="cddc6-161">Defines the security settings for the message.</span></span> <span data-ttu-id="cddc6-162">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="cddc6-162">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cddc6-163">父元素</span><span class="sxs-lookup"><span data-stu-id="cddc6-163">Parent Elements</span></span>  
  
|<span data-ttu-id="cddc6-164">元素</span><span class="sxs-lookup"><span data-stu-id="cddc6-164">Element</span></span>|<span data-ttu-id="cddc6-165">描述</span><span class="sxs-lookup"><span data-stu-id="cddc6-165">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cddc6-166">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cddc6-166">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="cddc6-167">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="cddc6-167">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cddc6-168">备注</span><span class="sxs-lookup"><span data-stu-id="cddc6-168">Remarks</span></span>  
 <span data-ttu-id="cddc6-169">此绑定为使用 TCP 上的对等传输创建对等应用程序或多方应用程序提供支持。</span><span class="sxs-lookup"><span data-stu-id="cddc6-169">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="cddc6-170">每个对等节点均可承载使用此绑定类型定义的多个对等通道。</span><span class="sxs-lookup"><span data-stu-id="cddc6-170">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cddc6-171">示例</span><span class="sxs-lookup"><span data-stu-id="cddc6-171">Example</span></span>  
 <span data-ttu-id="cddc6-172">下面的示例演示如何使用 NetPeerTcpBinding 绑定，该绑定使用对等通道提供多方通信。</span><span class="sxs-lookup"><span data-stu-id="cddc6-172">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="cddc6-173">使用此绑定的详细方案，请参阅[Net 的对等 TCP](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae)。</span><span class="sxs-lookup"><span data-stu-id="cddc6-173">For a detailed scenario of using this binding, see [Net Peer TCP](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 maxBufferSize="1001"
                 maxConnections="123"
                 maxReceiveMessageSize="1000">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="TransportWithMessageCredential">
            <message clientCredentialType="CardSpace" />
          </security>
        </binding>
      </netPeerBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="cddc6-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="cddc6-174">See also</span></span>
- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="cddc6-175">绑定</span><span class="sxs-lookup"><span data-stu-id="cddc6-175">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cddc6-176">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="cddc6-176">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cddc6-177">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="cddc6-177">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cddc6-178">\<binding></span><span class="sxs-lookup"><span data-stu-id="cddc6-178">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="cddc6-179">网络对等 TCP</span><span class="sxs-lookup"><span data-stu-id="cddc6-179">Net Peer TCP</span></span>](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae)
- [<span data-ttu-id="cddc6-180">对等网络</span><span class="sxs-lookup"><span data-stu-id="cddc6-180">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
