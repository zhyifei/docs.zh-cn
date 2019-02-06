---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: cf6b09d48c276b7465fc87e0cbfcddbc492ef800
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759725"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="8d563-101">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="8d563-101">\<netNamedPipeBinding></span></span>
<span data-ttu-id="8d563-102">定义一个既安全又可靠且针对计算机上跨进程通信进行了优化的绑定。</span><span class="sxs-lookup"><span data-stu-id="8d563-102">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="8d563-103">默认情况下，此绑定生成一个运行时通信堆栈，该堆栈包含 WS-ReliableMessaging 以保证可靠性，包含传输安全机制以保证传递的安全性，包含命名管道以便进行消息传递，并且包含二进制消息编码机制。</span><span class="sxs-lookup"><span data-stu-id="8d563-103">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
 <span data-ttu-id="8d563-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8d563-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d563-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8d563-105">\<bindings></span></span>  
<span data-ttu-id="8d563-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="8d563-106">\<netNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d563-107">语法</span><span class="sxs-lookup"><span data-stu-id="8d563-107">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WS-AtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d563-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8d563-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8d563-109">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8d563-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d563-110">特性</span><span class="sxs-lookup"><span data-stu-id="8d563-110">Attributes</span></span>  
  
|<span data-ttu-id="8d563-111">特性</span><span class="sxs-lookup"><span data-stu-id="8d563-111">Attribute</span></span>|<span data-ttu-id="8d563-112">描述</span><span class="sxs-lookup"><span data-stu-id="8d563-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d563-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="8d563-113">closeTimeout</span></span>|<span data-ttu-id="8d563-114">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8d563-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8d563-115">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8d563-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d563-116">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="8d563-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="8d563-117">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="8d563-117">hostnameComparisonMode</span></span>|<span data-ttu-id="8d563-118">指定用于分析 URI 的 HTTP 主机名比较模式。</span><span class="sxs-lookup"><span data-stu-id="8d563-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="8d563-119">此属性的类型为 `System.ServiceModel.HostnameComparisonMode`，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="8d563-119">This attribute is of type `System.ServiceModel.HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="8d563-120">默认值为 `StrongWildcard`，表示忽略匹配项中的主机名。</span><span class="sxs-lookup"><span data-stu-id="8d563-120">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="8d563-121">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="8d563-121">maxBufferPoolSize</span></span>|<span data-ttu-id="8d563-122">一个整数，指定此绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="8d563-122">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="8d563-123">默认值为 524,288 字节 (512 \* 1024)。</span><span class="sxs-lookup"><span data-stu-id="8d563-123">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="8d563-124">Windows Communication Foundation (WCF) 的许多部件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8d563-124">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="8d563-125">每次使用缓冲区时，创建和销毁它们都将占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="8d563-125">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="8d563-126">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回给缓冲池。</span><span class="sxs-lookup"><span data-stu-id="8d563-126">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="8d563-127">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="8d563-127">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="8d563-128">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="8d563-128">maxBufferSize</span></span>|<span data-ttu-id="8d563-129">一个正整数，指定内存中用于存储消息的缓冲区的最大大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="8d563-129">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="8d563-130">如果缓冲区已满，则多余的数据会保留在基础套接字中，直到缓冲区重新具有可用空间。</span><span class="sxs-lookup"><span data-stu-id="8d563-130">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="8d563-131">该值不能小于 `maxReceivedMessageSize` 属性。</span><span class="sxs-lookup"><span data-stu-id="8d563-131">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="8d563-132">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="8d563-132">The default is 65536.</span></span> <span data-ttu-id="8d563-133">有关详细信息，请参阅<xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>。</span><span class="sxs-lookup"><span data-stu-id="8d563-133">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="8d563-134">maxConnections</span><span class="sxs-lookup"><span data-stu-id="8d563-134">maxConnections</span></span>|<span data-ttu-id="8d563-135">一个整数，指定服务将创建/接受的最大出站和入站连接数。</span><span class="sxs-lookup"><span data-stu-id="8d563-135">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="8d563-136">传入和传出连接分别根据此属性指定的限制进行计数。</span><span class="sxs-lookup"><span data-stu-id="8d563-136">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="8d563-137">超出此限制的入站连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="8d563-137">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="8d563-138">超出此限制的出站连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="8d563-138">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="8d563-139">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="8d563-139">The default is 10.</span></span>|  
|<span data-ttu-id="8d563-140">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="8d563-140">maxReceivedMessageSize</span></span>|<span data-ttu-id="8d563-141">一个正整数，指定采用此绑定配置的通道上可以接收的最大消息大小（字节），包括消息头。</span><span class="sxs-lookup"><span data-stu-id="8d563-141">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="8d563-142">如果消息超出此限制，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="8d563-142">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="8d563-143">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="8d563-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="8d563-144">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="8d563-144">The default is 65536.</span></span>|  
|<span data-ttu-id="8d563-145">name</span><span class="sxs-lookup"><span data-stu-id="8d563-145">name</span></span>|<span data-ttu-id="8d563-146">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="8d563-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8d563-147">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8d563-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8d563-148">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="8d563-148">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8d563-149">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8d563-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="8d563-150">openTimeout</span><span class="sxs-lookup"><span data-stu-id="8d563-150">openTimeout</span></span>|<span data-ttu-id="8d563-151">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8d563-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8d563-152">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8d563-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d563-153">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="8d563-153">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="8d563-154">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="8d563-154">receiveTimeout</span></span>|<span data-ttu-id="8d563-155">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8d563-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8d563-156">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8d563-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d563-157">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="8d563-157">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="8d563-158">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="8d563-158">sendTimeout</span></span>|<span data-ttu-id="8d563-159">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8d563-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8d563-160">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8d563-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8d563-161">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="8d563-161">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="8d563-162">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="8d563-162">transactionFlow</span></span>|<span data-ttu-id="8d563-163">一个布尔值，指定绑定是否支持流动 WS-Transactions。</span><span class="sxs-lookup"><span data-stu-id="8d563-163">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="8d563-164">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="8d563-164">The default is `false`.</span></span>|  
|<span data-ttu-id="8d563-165">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="8d563-165">transactionProtocol</span></span>|<span data-ttu-id="8d563-166">指定与此绑定一起使用的事务处理协议。</span><span class="sxs-lookup"><span data-stu-id="8d563-166">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="8d563-167">有效值为</span><span class="sxs-lookup"><span data-stu-id="8d563-167">Valid values are</span></span><br /><br /> <span data-ttu-id="8d563-168">-   OleTransactions</span><span class="sxs-lookup"><span data-stu-id="8d563-168">-   OleTransactions</span></span><br /><span data-ttu-id="8d563-169">-   WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="8d563-169">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="8d563-170">默认值为 OleTransactions。</span><span class="sxs-lookup"><span data-stu-id="8d563-170">The default is OleTransactions.</span></span> <span data-ttu-id="8d563-171">此属性的类型为 <xref:System.ServiceModel.TransactionProtocol>。</span><span class="sxs-lookup"><span data-stu-id="8d563-171">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="8d563-172">transferMode</span><span class="sxs-lookup"><span data-stu-id="8d563-172">transferMode</span></span>|<span data-ttu-id="8d563-173">一个 <xref:System.ServiceModel.TransferMode> 值，指定为请求或响应对消息进行缓冲处理还是流式处理。</span><span class="sxs-lookup"><span data-stu-id="8d563-173">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d563-174">子元素</span><span class="sxs-lookup"><span data-stu-id="8d563-174">Child Elements</span></span>  
  
|<span data-ttu-id="8d563-175">元素</span><span class="sxs-lookup"><span data-stu-id="8d563-175">Element</span></span>|<span data-ttu-id="8d563-176">描述</span><span class="sxs-lookup"><span data-stu-id="8d563-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d563-177">\<security></span><span class="sxs-lookup"><span data-stu-id="8d563-177">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="8d563-178">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="8d563-178">Defines the security settings for the binding.</span></span> <span data-ttu-id="8d563-179">此元素的类型为 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="8d563-179">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|<span data-ttu-id="8d563-180">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8d563-180">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="8d563-181">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="8d563-181">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8d563-182">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="8d563-182">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d563-183">父元素</span><span class="sxs-lookup"><span data-stu-id="8d563-183">Parent Elements</span></span>  
  
|<span data-ttu-id="8d563-184">元素</span><span class="sxs-lookup"><span data-stu-id="8d563-184">Element</span></span>|<span data-ttu-id="8d563-185">描述</span><span class="sxs-lookup"><span data-stu-id="8d563-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d563-186">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8d563-186">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="8d563-187">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="8d563-187">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d563-188">备注</span><span class="sxs-lookup"><span data-stu-id="8d563-188">Remarks</span></span>  
 <span data-ttu-id="8d563-189">默认情况下，`NetNamedPipeBinding` 会生成一个运行时通信堆栈，该堆栈可使用传输安全、用于消息传递的命名管道和二进制消息编码。</span><span class="sxs-lookup"><span data-stu-id="8d563-189">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="8d563-190">此绑定是 Windows Communication Foundation (WCF) 系统提供的一个相应选项，可用于计算机上的通信。</span><span class="sxs-lookup"><span data-stu-id="8d563-190">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="8d563-191">它还支持事务。</span><span class="sxs-lookup"><span data-stu-id="8d563-191">It also supports transactions.</span></span>  
  
 <span data-ttu-id="8d563-192">`NetNamedPipeBinding` 的默认配置与 `NetTcpBinding` 所提供的配置类似，但要简单一些，因为 WCF 实现仅计划在计算机上使用，因此公开的功能就更少。</span><span class="sxs-lookup"><span data-stu-id="8d563-192">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="8d563-193">其中最显著的差异在于 `securityMode` 设置只提供 `None` 和 `Transport` 选项。</span><span class="sxs-lookup"><span data-stu-id="8d563-193">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="8d563-194">不包括 SOAP 安全支持选项。</span><span class="sxs-lookup"><span data-stu-id="8d563-194">SOAP security support is not an included option.</span></span> <span data-ttu-id="8d563-195">可以使用可选的 `securityMode` 属性配置安全行为。</span><span class="sxs-lookup"><span data-stu-id="8d563-195">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d563-196">示例</span><span class="sxs-lookup"><span data-stu-id="8d563-196">Example</span></span>  
 <span data-ttu-id="8d563-197">下面的示例演示在同一台计算机上提供跨进程通信的 netNamedPipeBinding 绑定。</span><span class="sxs-lookup"><span data-stu-id="8d563-197">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="8d563-198">命名管道不能跨计算机工作。</span><span class="sxs-lookup"><span data-stu-id="8d563-198">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="8d563-199">绑定是在客户端和服务的配置文件中指定的。</span><span class="sxs-lookup"><span data-stu-id="8d563-199">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="8d563-200">绑定类型是在 `binding` 元素的 `<endpoint>` 属性中指定的。</span><span class="sxs-lookup"><span data-stu-id="8d563-200">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="8d563-201">如果要配置 netNamedPipeBinding 绑定并更改它的一些设置，则必须定义绑定配置。</span><span class="sxs-lookup"><span data-stu-id="8d563-201">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="8d563-202">终结点必须使用 `bindingConfiguration` 属性按名称来引用绑定配置。</span><span class="sxs-lookup"><span data-stu-id="8d563-202">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="8d563-203">在此示例中，此绑定配置被命名为 Binding1。</span><span class="sxs-lookup"><span data-stu-id="8d563-203">In this example, the binding configuration is named Binding1.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
          </baseAddresses>
        </host>
        <!-- this endpoint is exposed at the base address provided by host: net.pipe://localhost/ServiceModelSamples/service  -->
        <endpoint address="net.pipe://localhost/ServiceModelSamples/service"
                  binding="netNamedPipeBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netNamedPipeBinding>
        <binding closeTimeout="00:01:00"
                 openTimeout="00:01:00"
                 receiveTimeout="00:10:00"
                 sendTimeout="00:01:00"
                 transactionFlow="false"
                 transferMode="Buffered"
                 transactionProtocol="OleTransactions"
                 hostNameComparisonMode="StrongWildcard"
                 maxBufferPoolSize="524288"
                 maxBufferSize="65536"
                 maxConnections="10"
                 maxReceivedMessageSize="65536">
          <security mode="Transport">
            <transport protectionLevel="EncryptAndSign" />
          </security>
        </binding>
      </netNamedPipeBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="8d563-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d563-204">See also</span></span>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [<span data-ttu-id="8d563-205">\<binding></span><span class="sxs-lookup"><span data-stu-id="8d563-205">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="8d563-206">绑定</span><span class="sxs-lookup"><span data-stu-id="8d563-206">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8d563-207">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="8d563-207">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8d563-208">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="8d563-208">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
